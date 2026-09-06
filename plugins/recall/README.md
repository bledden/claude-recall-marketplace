<!-- Durable-memory work on feat/durable-memory; not yet published. -->

# Claude Recall Plugin v2.5.0 (unreleased)

[Current update-window plan](docs/update-window-plan.md): remaining product work, historical deferrals, integration and release status.

A [Claude Code](https://docs.anthropic.com/en/docs/claude-code) plugin that persists conversation context across sessions, `/clear` commands, and compaction events. It adds cross-session search, tagging, highlight sharing between sessions, and observability.

> **Marketplace Status:** Published in Anthropic's community marketplace as `recall@claude-community` (`/plugin marketplace add anthropics/claude-plugins-community`, then install `recall`). The catalog entry is pinned to one commit of this repo and is moved by pull request, so it can lag the releases here.
>
> **Pre-built Marketplace:** [claude-recall-marketplace](https://github.com/bledden/claude-recall-marketplace) (the same release, and the only reliable path for the VSCode extension)

---

## Why Recall (vs. native Claude Code)

Claude Code ships with `/recap`, `/resume`, and a `memory/` directory. Recall is positioned around what those do **not** cover:

- **Cross-project full-text search (FTS5).** Native `/recap` and `/resume` operate within the current session/project. Recall indexes every exchange into SQLite FTS5 and searches this session (`search`), every session of this repository (`--all`) or every repository (`--global`) — including past, closed sessions. Since 2.5 the default search reads the durable store of complete text; `--legacy` reads the capped exchange rows.
- **Tagging.** Apply manual tags to sessions or individual exchanges, plus automatic keyword extraction, then query them across projects (`/recall tag`, `/recall tags`, `/recall search --tag`). The native `memory/` directory is freeform notes, not a queryable tag index.
- **Highlight & connection sharing between parallel sessions.** Link two live sessions and share findings as lightweight highlights delivered to a connected session's inbox (`/recall connect`, `/recall highlight`, `/recall inbox`). Native Claude Code has no mechanism to push a finding from one session to another.
- **The exact commands Claude ran.** Tool calls (shell commands, files edited, URLs fetched) are indexed alongside the prose, so "how did we spin up that pod" returns the real command line from the real session, not a reconstruction.

If you only need to re-anchor within the current session, native `/recap` / `/resume` may be enough. Recall is for cross-session, cross-project retrieval, tagging, and sharing.

---

## Requirements

- **Claude Code** 2.1.x or later (uses the `Stop` hook and the `SessionStart` `compact` matcher; see the 2.1.x note below), or **Claude Cowork** (macOS desktop app)
- **Python 3.9+** (for hook and script execution; the durable store uses `str.removesuffix`, so 3.6–3.8 fail)

---

## UPDATE: Claude Code 2.1.x Breaking Change

**As of Claude Code 2.1.x, local plugins no longer persist across sessions.** This is an undocumented breaking change from 2.0.x behavior. See [issue #17089](https://github.com/anthropics/claude-code/issues/17089).

Custom plugins now **require a marketplace structure** to work reliably with the VSCode extension. The `--plugin-dir` flag only works with the CLI, not VSCode.

---

## Installation

### Claude Cowork (macOS Desktop App)

**From GitHub:**
1. Open the Claude Desktop app
2. Navigate to the **Cowork** tab
3. Click **"Plugins"** in the left sidebar
4. Click **"Add from GitHub"**
5. Enter: `https://github.com/bledden/claude-recall-plugin`

**From zip file:**
1. **[Download claude-recall-plugin.zip](https://github.com/bledden/claude-recall-plugin/releases/latest/download/claude-recall-plugin.zip)**
2. In the Cowork **Plugins** sidebar, click **"Upload plugin"**
3. Select the downloaded `claude-recall-plugin.zip` file

The plugin will appear in your Cowork plugins list. Invoke with `/recall` during a Cowork session.

### Claude Code: Option 1 - Pre-Built Marketplace (Recommended for VSCode)

This is the recommended method: it serves the latest published release, and it is the only reliable method for the VSCode extension. (The community-marketplace listing `recall@claude-community` is pinned to a commit and may lag this marketplace.)

```bash
claude plugin marketplace add https://github.com/bledden/claude-recall-marketplace
claude plugin install recall@recall-local
```

The plugin will now persist across sessions in both CLI and VSCode.

<details>
<summary><strong>Alternative: Build Your Own Marketplace</strong></summary>

If you prefer to create your own local marketplace:

**Step 1: Clone and set up marketplace structure**

```bash
# Clone this repo
git clone https://github.com/bledden/claude-recall-plugin.git

# Create a marketplace wrapper
mkdir -p claude-recall-marketplace/.claude-plugin
mkdir -p claude-recall-marketplace/plugins
cp -R claude-recall-plugin claude-recall-marketplace/plugins/recall
```

**Step 2: Create the marketplace manifest**

Create `claude-recall-marketplace/.claude-plugin/marketplace.json`:

```json
{
  "$schema": "https://anthropic.com/claude-code/marketplace.schema.json",
  "name": "recall-local",
  "version": "2.2.2",
  "description": "Local marketplace for the recall plugin",
  "owner": {
    "name": "your-name",
    "email": "your-email@example.com"
  },
  "plugins": [
    {
      "name": "recall",
      "description": "Recover conversation context when Claude loses track",
      "source": "./plugins/recall",
      "category": "productivity"
    }
  ]
}
```

**Step 3: Register and install**

```bash
claude plugin marketplace add /path/to/claude-recall-marketplace
claude plugin install recall@recall-local
```

</details>

### Claude Code: Option 2 - Shell Alias (CLI Only)

This method works for the terminal but **does not work with the VSCode extension**.

```bash
git clone https://github.com/bledden/claude-recall-plugin.git
```

**For Zsh (default on macOS):**
```bash
echo "alias claude='claude --plugin-dir /path/to/claude-recall-plugin'" >> ~/.zshrc
source ~/.zshrc
```

**For Bash:**
```bash
echo "alias claude='claude --plugin-dir /path/to/claude-recall-plugin'" >> ~/.bashrc
source ~/.bashrc
```

### Claude Code: Option 3 - Plugin Install Command (Not Recommended)

```bash
claude plugins install https://github.com/bledden/claude-recall-plugin
```

> **Warning:** This method does not reliably persist in Claude Code 2.1.x. The plugin may disappear after restarting. Use Option 1 instead.

---

## Migration from v1.0.1

Migration is automatic. On the first prompt after upgrading to v2.0.0, the hook migrates your existing `index.json` into SQLite and renames the file to `index.json.migrated`. No manual steps required.

**Rollback:** If you need to go back to v1.0.1, rename `index.json.migrated` to `index.json`. v1.0.1 ignores `recall.db`.

---

## Quick Start

When Claude seems to have lost context, run:

```
/recall:recall
```

This will:
1. Show you a timestamped index of all exchanges in your session
2. Present a menu asking what you'd like to recall
3. Fetch and display the exchanges you select
4. Summarize where you left off

---

## Full Command Reference

### Core Commands

```
/recall                             Interactive menu (index + options)
/recall last5                       Last 5 exchanges, current session
/recall last10                      Last N exchanges (lastN — any positive N)
/recall around 2pm                  Exchanges around a time
/recall search <keyword>            Search current session
```

### Cross-Session and Cross-Project Search

```
/recall search <keyword> --all              Search all sessions, current project
/recall search <keyword> --global           Search across ALL projects
/recall search <keyword> --project <name>   Search a specific project by name
/recall search <keyword> --half-life 0      Rank by relevance only (default: 30-day recency half-life)
```

### Session Management

```
/recall sessions                    List all sessions (current project)
/recall sessions --all              List sessions across all projects
/recall sessions --project <name>   List sessions in a specific project by name
/recall session <id> last10         Browse a specific past session
```

> **`--project` matching:** For `search --project <name>` and `sessions --project <name>`, `<name>` is matched as an **unanchored substring** of the stored project path (`LIKE '%name%'`, case-insensitive for ASCII letters (SQLite default)) — any session whose project path contains the substring matches.
>
> **`tags --project` is different:** `/recall tags --project <hash>` expects a project **HASH** (exact match), *not* a name/path. This is distinct from `sessions --project <name>`, which takes a name/path.

### Tagging

```
/recall tag <name>                  Tag the current session
/recall tag <name> #<exchange>      Tag a specific exchange by number
/recall tags                        Show all tags
/recall tags --project <hash>       Show tags for a specific project HASH (exact match)
/recall search --tag <name>         Find sessions and exchanges by tag
```

### Cross-Session Sharing

```
/recall highlight "summary"              Flag a finding for connected sessions
/recall connect <session-id> "topic"     Watch another session for highlights
/recall connect --latest "topic"         Watch most recent active session (same project)
/recall disconnect <session-id>          Stop watching a session
/recall inbox                            View new highlights from connected sessions
```

### Configuration

```
/recall config check_mode decay          Enable decay-based polling (default: explicit)
/recall config delivery_mode inject      Auto-inject highlights as system messages (default: silent)
/recall config auto_highlight true       Enable heuristic highlight detection (default: false)
/recall config skill_enabled true        Enable the recall-assistant skill (default: false)
/recall config detection_signals explicit,behavioral,temporal   Configure context-loss detection signals
/recall config auto_run_highlight true   Auto-flag findings without asking (default: false)
```

### Maintenance

```
/recall stats                               Storage statistics
/recall usage                               How often /recall has been invoked (by command, month, project)
/recall prune --session <id>                Delete a specific session
/recall prune --before 2026-01-01           Delete all sessions before a date
/recall export --session <id>               Export a session to JSON (always JSON)
```

### Time Format Support

The plugin understands various time formats:

| Format | Example |
|--------|---------|
| 12-hour | `2pm`, `2:30pm`, `2:30 pm` |
| 24-hour | `14:30`, `14:00` |
| With date (month day) | `jan 5 2pm`, `dec 25 10am` |
| With date (numeric) | `1/5 2pm`, `12/25 10:30am` |
| Relative | `yesterday 2pm`, `today 10am` |

---

## Features

### 1. Per-Turn Capture and /clear Survival

Every completed turn is indexed by a `Stop` hook the moment Claude finishes responding (with a `UserPromptSubmit` pass as belt-and-braces and a final catch-up on `SessionEnd`), so the last thing said in a session is normally captured without waiting for another prompt. Capture reads the transcript file, so a record that has not been flushed to disk yet is picked up by a later pass (the next prompt, or the bounded `SessionEnd` drain), and `/recall status` shows any backlog that remains. Legacy exchange rows still truncate at 4,000 characters per reply; since 2.5.0 the durable store keeps the complete redacted text and `get <block_id>` pages through it. The whole reply is kept: all of Claude's text blocks between two prompts are merged into one exchange, not just the first "let me look" block. Context is persisted to SQLite before `/clear` executes, so clearing the window no longer means losing the record of what happened.

### 2. Cross-Session Search

Search this session by default, every session of this repository with `--all`, or every repository you've worked in with `--global`. Durable results carry a block id, character range and `get` reference; legacy results (`--legacy`) include session ID, project, timestamp and a content preview.

```
/recall search "auth flow" --all
/recall search "triton kernel" --global
```

### 3. Post-Compaction Recovery

When a session resumes after compaction (`SessionStart` with `matcher: "compact"`), the plugin injects a brief context-recovery note into Claude's context (`additionalContext`): how much of this session and project is indexed, recent topics, the last few exchange previews, and a reminder that `/recall` recovers the detail the summary dropped.

### 4. Auto-Tagging

Technical terms are extracted automatically from each exchange — function names, file paths, identifiers, command names. These feed into FTS5 search so you can find exchanges without remembering the exact wording.

### 5. Manual Tagging

Apply your own tags to sessions or individual exchanges for cross-project discovery:

```
/recall tag auth-refactor
/recall tag metal-backend #42
```

Tags are queryable across all sessions and projects.

### 6. Cross-Session Context Sharing

Share findings between parallel sessions working on related problems. Highlights are lightweight tag-pointers, not full context — checks are token-efficient. Full context is pulled on demand via `/recall search`.

**Two highlight creation paths:**

- **Explicit** (default): Claude proactively runs `/recall highlight "summary"` when it produces a finding worth sharing — a bug fix, performance technique, architectural insight, or config that solved a problem.
- **Auto-detect** (opt-in): Enable with `/recall config auto_highlight true`. The hook scans assistant responses for solution signals (e.g., "the fix is", "the solution", "resolved by"). If 2+ signals appear in one exchange and the response is 25+ words, a highlight is created automatically with `source='auto'`.

**Check frequency:**

By default, connections are `check_mode=explicit` — highlights only appear when you run `/recall inbox`. Enable decay polling with `/recall config check_mode decay`: starts checking every 7th prompt, grows by 3 each time, caps at every 30th prompt.

**Delivery modes:**

- `silent` (default): highlights queue silently, view with `/recall inbox`
- `inject`: highlights are injected as system messages automatically

**Natural language support:** Claude translates "watch session abc123 for kernel work" into `/recall connect abc123 "kernel work"` automatically.

```
/recall connect abc123 "CUDA reduction kernels"
/recall connect --latest "Blackwell dispatch work"
/recall inbox
```

### 7. Recall Assistant Skill (Opt-In)

An optional skill that teaches Claude to proactively use the recall plugin. Enable with `/recall config skill_enabled true`.

When enabled, Claude will:
- **Detect context loss** — explicit phrases ("didn't we already...", "remind me what...") are caught *deterministically by the `UserPromptSubmit` hook*, which injects a `[Recall]` suggestion (so it no longer depends on the model noticing); behavioral signals (contradicting itself) and temporal signals (post-compaction) stay model-driven
- **Suggest highlighting** — when Claude produces a transferable finding, it suggests `/recall highlight` (or auto-runs it if `auto_run_highlight` is enabled)
- **Translate natural language** — "keep an eye on session abc123" becomes `/recall connect abc123 "..."`
- **Suggest inbox checks** — when working on topics that overlap with connected sessions

The skill is fully opt-in and respects all existing opt-in gates. It never auto-runs connect, disconnect, or inbox commands.

### 8. Concurrent Session Safety

Multiple Claude sessions in the same project write to the same database without conflicts (SQLite WAL mode allows concurrent reads and serializes writes). Each session also resolves *its own* identity from the native, per-session `CLAUDE_CODE_SESSION_ID` that Claude Code injects into every command — so `/recall` always returns the current session's history, never a concurrent session's, even with several sessions open at once.

### 9. SQLite Storage

All context is stored in a single SQLite database (`recall.db`) with FTS5 for full-text search, plus one small `settings.json` for global opt-ins. No external dependencies beyond Python's built-in `sqlite3` module.

### 10. Timestamped Conversation Index

Every exchange is indexed with its timestamp:

```
Session started: Jan 5, 2026 at 9:00 AM (Jan 5 - Jan 7)
Total exchanges: 117

Showing page 1 of 6 (most recent first):

Jan 7:
#117 [5:13 pm] "root@dendritic-distillation:~/dendritic# ls..."
#116 [2:49 pm] "Yes, give me the command to kick that off"

Jan 6:
#115 [1:33 pm] "It looks like the experiment is complete..."
```

### 11. Full-Content Search

Search looks in user prompts, assistant responses and the tool calls of each exchange. **Durable search (default since 2.5):** terms are combined with OR after common question words are dropped, `--require-all` demands every term, quoting does not make a multi-word phrase exact, and `--kind tool_use` searches commands instead of prose. **Legacy search (`--legacy`):** multi-word queries use AND logic and a quoted string is matched as an exact phrase. Both stem terms (`kernel` matches `kernels`). Results are **ranked**: BM25 relevance blended with recency (the recency component halves every 30 days, and a hit's total weight never drops below half its relevance score; `--half-life 0` for pure relevance), best match first, and every hit shows the passage that matched:

```
### Exchange #162 [Sep 5 6:41 pm]

> Match: $ cd ~/Documents/claude-recall-plugin «gh» «pr» ready 2 …
```

```
/recall search dimension
/recall search "auth flow"
```

Durable search returns the top 5 ranked passages (`--limit` up to 50); legacy search shows up to 10 most recent matches, grouped by date.

### 12. Observability Logging

Every `/recall` invocation is logged:

```
~/.claude/recall-events.log
```

Log format:
```
2026-01-05T16:45:00+00:00 | session=abc123 | exchanges=72 | CONTEXT_RECALL_TRIGGERED
```

### 13. Tool-Call Capture

Every tool call Claude makes in a turn is stored as one compact line — `$ ssh root@ssh.runpod.io -p 22222`, `Edit /p/kernel.py`, `Grep BLOCK_S in /p`, `WebFetch https://…` — under the exchange's **Tools run**, and it is searchable. Tool *output* is never stored, so the store stays small (a 20 MB transcript indexes to well under 1 MB of tool lines).

### 14. Secrets Redaction

Credential-looking strings are replaced with `[REDACTED:<kind>]` before storage: well-known token formats, `KEY=value` assignments with secret-like names, and phrasings like "my password is …". Pattern-based, not a guarantee — see [PRIVACY.md](PRIVACY.md).

### 15. Claude Invokes Recall on Its Own

`/recall:recall` is a skill whose description carries trigger phrases ("didn't we already", "what was that command", "earlier you said", "last time", …). When the user refers to earlier work, Claude invokes it without being asked, runs the most specific search directly (no menu), and quotes what it recovered. The separate, opt-in `recall-assistant` skill adds behavioural/temporal detection and cross-session suggestions.

### 16. Pagination

Long sessions are paginated (20 exchanges per page):

```
Showing page 1 of 6 (most recent first)

Navigation:
- Show newer: page 1
- Show older: page 2
```

---

## Usage Examples

### Claude lost context mid-task

```
/recall last5
```

### Find a specific discussion from earlier

```
/recall search "API endpoint"
```

### Find something across all sessions in this project

```
/recall search "gradient checkpointing" --all
```

### Find a concept you worked on in a different project

```
/recall search "WAL mode" --global
```

### Return to work from yesterday afternoon

```
/recall around "yesterday 3pm"
```

### Tag a session for later reference

```
/recall tag metal-backend
```

### Browse a past session

```
/recall sessions
/recall session abc123 last10
```

### Clean up old sessions

```
/recall prune --before 2026-01-01
```

### Share a finding with a parallel session

```
/recall highlight "threadgroup size 512 optimal for Blackwell dispatch"
```

### Watch another session for highlights

```
/recall connect abc123 "CUDA reduction kernel work"
# or connect to the most recent active session in this project:
/recall connect --latest "Metal backend optimizations"
```

### Check for new highlights from connected sessions

```
/recall inbox
```

---

## How It Works

### Hooks

Five hook registrations:

- **SessionStart** — Exports the session's env vars (a legacy fallback for resolving the current session/project; the native `CLAUDE_CODE_SESSION_ID` is preferred).
- **SessionStart (`matcher: "compact"`)** — After a compaction, injects a context-recovery note into Claude's context (`additionalContext`) so it re-anchors on the session state.
- **UserPromptSubmit** — Indexes any completed turns not yet captured, runs connection checks (decay mode), auto-highlight detection, and the deterministic proactive-recall suggestion (all if enabled). Anything Claude must act on is returned as `additionalContext`; `systemMessage` is reserved for user-facing notices.
- **Stop** — Indexes the turn that just completed. The transcript can lag the in-memory turn; whatever is on disk is stored now and assistant blocks that land later are appended to the same exchange (FTS kept in sync) by the next pass.
- **SessionEnd** — Drains the remaining backlog in committed passes within a 7 s budget, then finalizes the session record; anything beyond the budget stays as backlog for the next session's hooks.

### Storage

SQLite with FTS5 for full-text search and WAL mode for concurrent session safety. Default capture and lexical search need no external services or dependencies beyond Python's standard library. Optional semantic commands use separately installed sentence-transformers dependencies and an existing local model.

### Tagging

A hybrid approach: auto-tags are extracted from exchange content at index time; manual tags are applied via `/recall tag`. Both are searchable via FTS5.

### Cross-Session Sharing

Highlights are created via two paths: explicit (Claude runs `/recall highlight`) or auto-detection (heuristic scan of assistant responses, opt-in). Connections are opt-in links between sessions stored in the `connections` table. The `UserPromptSubmit` hook checks connections on each prompt when `check_mode=decay` is set. Delivery is either silent (queue for `/recall inbox`) or injected as a system message.

---

## Data Storage

```
~/.claude/context-recall/recall.db     Single SQLite database (WAL mode, FTS5)
~/.claude/recall-events.log            Recall event log (unchanged from v1)
```

The database contains these legacy tables, plus the 2.5 durable-store tables `memory_sources`, `memory_blocks`, `memory_chunks`, `memory_fts`, `memory_vectors` and `memory_semantic_config`:
- `sessions` — one row per session, with project, timestamps, and metadata (including per-session config like `auto_highlight`)
- `exchanges` — one row per exchange: user text, merged assistant text, and `tool_text` (one line per tool call)
- `tags` — session and exchange-level tags
- `highlights` — findings flagged for sharing, linked to a session and exchange; `source` field distinguishes explicit vs auto-detected
- `connections` — opt-in links between sessions; stores `check_mode`, `check_interval`, `delivery_mode`, and `last_checked_at`
- `invocations` (v2.2.3+) — one row per recall command invocation (timestamp, session, project hash, command, args); powers `/recall usage`

The legacy FTS5 virtual table (porter stemming, introduced in schema v5) indexes capped prompts, replies, previews and tool calls; legacy searches rank by BM25 × recency and return match snippets. Schema v6 adds the separate durable source/block/passage tables described below.

---

## Analyzing Recall Patterns

```bash
# View recent recall events
tail -20 ~/.claude/recall-events.log

# Count recalls per day
cut -dT -f1 ~/.claude/recall-events.log | uniq -c

# Find sessions with frequent recalls (portable: BSD/macOS sed too)
sed -n 's/.*session=\([^ ]*\).*/\1/p' ~/.claude/recall-events.log | sort | uniq -c | sort -rn

# Count total recalls
wc -l ~/.claude/recall-events.log
```

---

## Plugin Structure

```
claude-recall-plugin/
├── .claude-plugin/
│   └── plugin.json                  # Plugin metadata (v2.5.0 development)
├── skills/
│   ├── recall/
│   │   └── SKILL.md                 # The /recall:recall skill (Claude can invoke it on its own)
│   └── recall-assistant/
│       └── SKILL.md                 # Opt-in proactive assistant skill
├── hooks/
│   ├── hooks.json                   # Hook config (SessionStart, SessionStart:compact, UserPromptSubmit, Stop, SessionEnd)
│   ├── session_start.py             # Exports session env vars (legacy fallback)
│   ├── prompt_submit.py             # Incremental indexer (shared; continuation-append) + auto-tagging + proactive recall
│   ├── stop.py                      # Per-turn capture (Stop)
│   ├── post_compact.py              # Post-compaction recovery note (SessionStart: compact)
│   └── session_end.py               # Final catch-up index + session finalization
├── scripts/
│   ├── db.py                        # SQLite layer (FTS5, WAL, all CRUD)
│   ├── utils.py                     # Shared utilities: session/project resolution, redaction, tool-call extraction, time parsing
│   ├── auto_tagger.py               # TF-based keyword extraction
│   ├── highlight.py                 # Highlight creation (explicit + auto-detect)
│   ├── manage_connections.py        # Connect, disconnect, inbox, config
│   ├── manage_tags.py               # Tag CRUD, search by tag
│   ├── manage_sessions.py           # Session list, prune, export, stats
│   ├── fetch_exchanges.py           # Fetch exchanges by query
│   └── show_index.py                # Paginated index display
├── tests/                          # 671 tests: unit + integration + skill evals + external-review regressions
│                                    #   + stress (scale/concurrent/clear/sharing)
│                                    #   run with `python3 -m pytest -q` (see pytest.ini)
├── pytest.ini                      # Collects test_*.py AND stress_test_*.py
├── docs/
│   └── superpowers/
│       ├── specs/                   # Design specifications
│       └── plans/                   # Implementation plans
├── README.md
├── CHANGELOG.md
├── PRIVACY.md
├── LICENSE
└── .gitignore
```

---

## Running Tests

```bash
cd claude-recall-plugin

# Full suite — unit, integration, and stress (671 tests)
# pytest.ini collects both test_*.py and stress_test_*.py
python3 -m pytest -q
```

---

## Use Recall across coding agents

Claude and Codex histories can share the durable store. The installed Codex skill provides command-line retrieval; `scripts/recall_mcp.py` also exposes scoped `recall_search`, `recall_get`, `recall_brief` and `recall_status` tools to compatible local MCP clients. The server reads one configured repository and never captures or migrates data.

`scripts/recall_capture.py` refreshes explicitly selected Claude/Codex files without a Claude process. Add `--watch` to keep that capture process running in the foreground. This is separate from starting the MCP reader.

See [cross-agent setup and verified-client matrix](docs/gpt-expansion.md) for import commands, client configuration, scope rules, and the distinction between a connected tool and a verified model workflow. Other clients can read the supported source formats; their own transcripts require an additional adapter.

## Contributing

1. Fork the repository
2. Make your changes
3. Run tests: `python3 -m pytest tests/ -v`
4. Submit a pull request

---

## Privacy and Data Handling

Recall stores data **locally on your machine**, by default in `~/.claude/context-recall/` or at the explicitly configured store/export/backup path. It makes no network requests and includes no telemetry. Recalled passages are returned to the calling agent and may reach that agent’s configured model provider.

For full details on what data is stored, how to delete it, and your control options, see [PRIVACY.md](PRIVACY.md).

---

## Security

### Reporting Vulnerabilities

To report a security vulnerability, please open an issue at [github.com/bledden/claude-recall-plugin/issues](https://github.com/bledden/claude-recall-plugin/issues) or contact the author directly via GitHub.

### Security Practices

- All SQL queries use parameterized statements
- No dynamic code execution of any kind
- No external network requests or downloads
- Diagnostic output includes local source paths and capture state for troubleshooting
- Legacy and durable capture each process up to 2 MB / 1,000 records per pass, allowing one oversized record to ensure progress. These are soft budgets, not hard memory or time limits; SessionEnd drains within a soft time budget
- Legacy exchanges retain capped text (1,000 chars per prompt, 4,000 per reply, 2,000 of compact tool calls). Version 2.5 also retains complete redacted source blocks and tool-call inputs; tool output and thinking remain excluded
- Credential-looking strings are redacted before storage (see PRIVACY.md)
- Hook commands quote the interpreter and script path (plugin roots with spaces work)
- Default database directory created with owner-only permissions (0o700) when first created
- Hook stdin reads bounded to 1MB

---

## Known Limitations

- **Claude Cowork requires zip upload** — Cowork does not yet support marketplace installation; upload the plugin zip file manually via the Plugins sidebar
- **VSCode extension requires marketplace** — Due to a [breaking change in 2.1.x](https://github.com/anthropics/claude-code/issues/17089), the VSCode extension requires the marketplace installation method
- **Experimental semantic search** — Default retrieval uses SQLite FTS5 (BM25 × 30-day recency). Optional local embeddings require a separate dependency and explicit build; the current small evaluation does not justify enabling them by default
- **Attachment references are not attachment bodies** — a Codex rollout that only names an attachment path cannot supply its contents to Recall. Pasted reports keep the role recorded in the transcript.
- **Source edit detection is windowed** — only the first 256 bytes and the 256 bytes before the saved cursor are hashed; an edit between them is not detected until an explicit rebuild
- **Codex capture is polling** — the opt-in `codex_import` setting refreshes at Claude session start; the independent foreground watcher can refresh without Claude. Starting the MCP server alone does not capture new work
- **Cross-session sharing is polling-based** — No real-time push; highlights appear on the next check interval or via `/recall inbox`

---

## Troubleshooting

**`Unknown skill: recall:recall` (often on Linux)** — this means the plugin's command didn't load, not that anything in the plugin is broken. It's the [2.1.x local-plugin breaking change](https://github.com/anthropics/claude-code/issues/17089): non-marketplace installs (a `--plugin-dir` flag or shell alias) no longer persist. Fix: install from a **marketplace** (see [Installation](#installation)), then `/reload-plugins` (or restart). The recall *scripts* still work regardless of the wrapper, which is why the plugin can also be driven conversationally ("use `/recall` to catch up") even when the `/recall:recall` command is missing.

**Hooks don't seem to fire on Linux** — if your environment ships `python` but not `python3` on `PATH`, upgrade to **v2.2.2+** (hooks now probe for `python3` and fall back to `python`).

**`/recall` shows an old or partial session** — on very large, actively-growing transcripts the indexer catches up incrementally over several turns (2 MB per hook run) and makes progress on every pass, even on a single multi-MB record; `SessionEnd` drains within its budget and `/recall status` shows what remains. **v2.3+** captures each turn as it completes via the `Stop` hook, so the most recent exchange is normally already there. `/recall usage` reports your invocation history.

---

## Uninstalling

If you configured the optional MCP server, remove its `recall` entry from that client’s configuration and stop any foreground `recall_capture.py --watch` process. Removing the Claude plugin alone does not remove these separately configured integrations.

**If installed via marketplace:**
```bash
claude plugin uninstall recall@recall-local
claude plugin marketplace remove recall-local
```

**If using shell alias:**
Remove the alias line from your `~/.zshrc` or `~/.bashrc`, then run `source ~/.zshrc` or `source ~/.bashrc`.

**Removing stored data:**
```bash
rm -rf ~/.claude/context-recall/
```

---

## Changelog

See [CHANGELOG.md](CHANGELOG.md) for the full version history.

---

## License

MIT License - see LICENSE file for details.

## Durable evidence and cross-agent recovery (2.5.0, unreleased)

`/recall find "why did we reject batching"` searches complete redacted text in indexed Claude and Codex sessions. Each result includes a stable block reference and a precise character range. `/recall get <block_id>` reads it, optionally with `--start N` and `--neighbors N`. Pagination limits output, not retained text. Legacy `/recall search`, `lastN`, and `around` continue to read capped exchange rows; `find`/`get` use the durable block store.

`/recall brief` returns selected historical passages for the host agent to synthesize into a cited project briefing. Current Git state is observed separately. The briefing is a sample, not evidence that an unselected decision never occurred. No generative model runs during capture or briefing selection.

`/recall index /explicit/path --agent claude` (or `codex`) imports a file or JSONL directory. Imports are resumable and idempotent, and never sweep personal history directories implicitly. Normal Claude hooks capture durable blocks too. Existing indexed sessions backfill as their hooks run, or through an explicit import. Missing original files leave retained text readable; old truncated rows cannot restore text that is no longer available in a transcript.

Repository identity uses a normalized Git remote when available, then the common Git directory, then the directory path. This groups worktrees and SSH/HTTPS checkouts of the same remote. Agent/session identities stay separate. Codex support currently imports `response_item` messages/tool calls and the older top-level `message` format; mirrored events, internal instructions and reasoning are excluded. Continuous Codex capture is not installed automatically.

`/recall status` and `/recall doctor` show capture time, backlog, why records were skipped (`excluded_by_policy`, `metadata_records`, `unsupported` with the record types, `malformed`), missing/changed sources, database checks, and one concrete next action per source. `sources --offset N` continues a source listing. A changed source is never overwritten silently: `index PATH --agent AGENT --rebuild` starts a new generation and rescans from byte 0. Messages the rescan has not reached keep their old text until the rescan reaches end of file, when anything the file no longer contains is deleted; a message whose id is unchanged but whose text changed is replaced at the moment the rescan reaches it. An interrupted rebuild resumes on the next index pass, also after a transient source-changed state, and `rescope AGENT:SESSION --cwd DIR` pins a corrected repository scope against later passes (`--auto` unpins). During a rebuild, results can mix old and new content; a block id resolves to its latest indexed text, not to an immutable snapshot.

After a compaction, the session-start hook re-anchors Claude with verbatim excerpts from the durable store (opening ask + tails of the last three text blocks, each cited with `get <block_id> --start N`, ≤ 3,500 chars, never repeated for an unchanged state).

Cross-agent: `config codex_import on` imports new Codex rollouts at each Claude session start (newest first, 4 s budget); `install-codex-skill` writes a Codex skill that points at this plugin's `recall_memory.py` into `~/.agents/skills` (the user-skills location in current Codex documentation; `--skills-dir ~/.codex/skills` for older hosts), so Codex sessions can query the same store; confirm in a fresh Codex task that `recall` appears in its skills. Both are explicit opt-ins.

Optional local semantic retrieval uses one sentence-transformers backend. Install that optional package yourself and supply an existing local model directory to `/recall semantic-build --model-path /path/to/model`. No model download occurs. Searches use it only with `--semantic`; otherwise the runtime remains Python stdlib only. Models are fingerprinted, vectors are invalidated when source blocks change, and new passages require another explicit build. This is experimental pending retrieval evaluation; see `benchmarks/README.md`.

All new operations are available directly through `python3 scripts/recall_memory.py --help`; `--db PATH` before the operation selects an isolated store. See `docs/durable-memory.md` for rollout and validation.
