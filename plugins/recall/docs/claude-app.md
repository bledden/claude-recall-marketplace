# Recall in Claude for Mac: chat and Cowork

Claude Code, Desktop chat and Cowork have different execution and connection
mechanisms. Installing the Code plugin does not configure all three. The 2.5
candidate includes a scoped app reader preparation command. Generated launch
configurations pass subprocess tests; actual Mac app discovery and model use
remain an explicit validation gate.

| Surface | Retrieval route | Capture of new conversations |
|---|---|---|
| Claude Code, including Code sessions launched by the app | Existing Recall plugin hooks/skill or scoped MCP | Hooks verified in Code; a particular app-launched session must actually load the plugin |
| Desktop **Chat** | Local stdio MCP entry in Desktop configuration | Not implemented; reading indexed Code/Codex/Cowork history does not capture the current chat |
| **Local Cowork** | Plugin-bundled local MCP server, subject to app policy | Two local Cowork transcript prefixes imported successfully through the Claude adapter into a scratch store; no automatic watcher or Cowork hook delivery verified |
| **Cloud Cowork** | This host-local stdio reader cannot run there | Not implemented; no implicit account-history access or host-store upload |

Anthropic documents that plugins carry skills across chat and Cowork, while hooks
are unavailable in chat. [Plugin support](https://support.claude.com/en/articles/13837440-use-plugins-in-claude).
Desktop chat's local MCP configuration is separate and is not available in Cowork.
[Connector routing](https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp).
Local Cowork's agent loop can run plugin MCP servers on the device; shell execution
runs inside a Linux VM. Cloud Cowork runs in a separate sandbox and cannot run
these local servers. [Cowork architecture](https://support.claude.com/en/articles/14479288-claude-cowork-architecture-overview).
Sources checked September 6, 2026; verify the session's execution mode rather than
inferring it from use of the Mac app.

## Prepare a reader for one indexed repository

Run on the Mac, using an existing schema-compatible store and the actual project
directory, or an exact `--repo-id` from `recall_memory.py sources`:

```sh
python3 /path/to/recall/scripts/prepare_claude_app.py \
  --db /path/to/recall.db \
  --cwd /path/to/project \
  --output /path/to/new-recall-app-reader
```

Python 3.9+ with SQLite FTS5 is required. The preparer records the absolute Python
executable; `--python /absolute/path/to/python3` selects another installed runtime.
It checks that the store has sources in the selected scope, freezes that scope
into the launch arguments, copies the four stdlib reader modules, and emits:

- `desktop-config-snippet.json`, for Desktop chat;
- `recall-reader.zip`, with `.mcp.json`, a retrieval-only skill and the manifest
  at its root, for local Cowork;
- an unpacked `recall-reader/` used by the Desktop configuration;
- a `BUILD.json` with file hashes, selected repository and configuration details.

The output directory must be new. No history, credentials, hook scripts or capture
commands are bundled. This is a **machine-specific private configuration**, not
the public release ZIP: it contains local database/interpreter paths. Preparing it
does not install anything, migrate the store, start a watcher or restart an app.
The reader sees future commits from separately configured capture processes.

## Desktop chat setup

In Claude Desktop Settings > Developer > Edit Config, merge the generated entry
into `mcpServers` in `~/Library/Application Support/Claude/claude_desktop_config.json`.
Preserve existing servers and other settings; keep a backup before editing. Do not
overwrite an existing entry of the same name without reviewing it. Use `--name`
when preparing separate readers for separate repositories. Keep the unpacked
reader directory in its final location. Quit/restart only after running sessions
finish, then enable the reader for the chat and inspect its four tools.
[Official Desktop configuration guide](https://modelcontextprotocol.io/docs/develop/connect-local-servers).

The MCP tool descriptions support natural discovery without requiring a skill
installation. If a Recall skill is present, it chooses the MCP interface first.
Do not execute host paths in chat's code sandbox.

## Local Cowork setup

Open Customize > Plugins and upload the generated `recall-reader.zip`. Enable its
MCP component and skill. This local plugin route is separate from the chat
configuration. If local MCP is disabled by policy or the task is cloud-based, this
package cannot provide a connection; report that explicitly. Do not substitute
`localhost` as a remote connector URL or expose the database via a public tunnel.

Cowork also accepts marketplace repositories; the old README's “ZIP only” claim
was incorrect. A generic Code-plugin install still does not supply the explicit
scope/database connection configured by this preparer.
[Cowork installation](https://claude.com/docs/cowork/guide/plugins),
[plugin MCP format](https://code.claude.com/docs/en/plugins-reference#mcp-servers).

## Import selected local Cowork history

The observed local app version stores Claude-shaped transcripts under
`~/Library/Application Support/Claude/local-agent-mode-sessions/.../.claude/projects/.../*.jsonl`.
This path is an observed implementation detail, not a stable public app API.
`audit.jsonl` is not a conversation transcript. Select specific main-session
files; do not scan the entire app support directory or include subagents blindly.

The existing explicit `recall_memory.py index FILE --agent claude --cwd PROJECT`
can import an identified transcript. Verify `sources` afterwards: VM working
directories do not necessarily identify the corresponding Mac repository. Use
the explicit `rescope` command when the retained source needs a different scope.
The foreground capture command can watch a selected file, but automatic discovery,
new-session mapping and Cowork compaction hooks have not been validated. The app
reader deliberately bundles no Code capture hooks that could write an unrelated
VM store and falsely appear to share host memory.

## Acceptance checks, independently in chat and Cowork

1. Confirm the execution surface/mode and that all four Recall tools appear.
2. Ask naturally about a known indexed decision without naming Recall. Record
   whether the model searches, retrieves the original block and cites its offset.
3. Verify the returned source agent and repository. Test another repository's
   known block ID: get must reject it. Check a false premise stays unconfirmed.
4. Append a synthetic decision through the separate capture command; ask again in
   the same reader session and confirm it sees the new evidence.
5. Keep capture separate: a new app message is not considered retained until an
   actual source import and later retrieval prove it. A plugin checkmark alone
   does not prove either capture or retrieval.

P67–P70 in the update-window plan track the prepared integration, live app gates,
capture boundaries and cloud-mode follow-through. None of these checks authorizes
publication or counts as P10's human retrieval evaluation.
