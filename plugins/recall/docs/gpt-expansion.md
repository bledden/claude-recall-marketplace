# Cross-agent Recall

Cross-agent recovery is now part of the active update window. Claude and Codex can contribute evidence to the same durable SQLite store, and coding clients can read it through an optional local MCP server. The existing Claude plugin and Codex skill continue to work. Capture, tool connectivity and verified model use are separate capabilities.

## Connect a coding client

First, explicitly import the histories you want to retain. Use absolute paths and a store you have backed up if it already contains data:

```sh
python3 /path/to/recall/scripts/recall_capture.py --db /path/to/recall.db --agent codex --path /path/to/codex/sessions
python3 /path/to/recall/scripts/recall_capture.py --db /path/to/recall.db --agent claude --path /path/to/claude/project-transcripts
```

Each command reports progress. Repeat while `pending_files` is nonzero. Imports populate the durable evidence store; they do not synthesize legacy exchanges, highlights or session links. For continuous refresh, add `--watch`; the process runs in the foreground and stops with Ctrl-C. It checks every 10 seconds by default (`--interval` changes that), gives sources fair turns within a soft four-second cycle budget (`--seconds`), and detects new files and appended records. Discovery and a single large record can exceed that budget. Source edits that require `index --rebuild` are reported and never rebuilt automatically. Stop a watcher before pruning if you want to prevent later source updates from being reimported.

Launch the MCP server with one explicit repository scope:

```sh
python3 /path/to/recall/scripts/recall_mcp.py --db /path/to/recall.db --cwd /path/to/project
```

`--cwd` resolves the same repository identity used by Recall's existing commands. Alternatively supply `--repo-id` with the exact ID shown by `recall_memory.py sources`. Work done in a non-repository directory has that directory's identity; moving into a nested Git repository does not automatically move its history. Use the existing explicit `rescope` command to correct an imported source when needed.

A generic stdio MCP configuration is:

```json
{
  "mcpServers": {
    "recall": {
      "command": "/absolute/path/to/python3",
      "args": ["/path/to/recall/scripts/recall_mcp.py", "--db", "/path/to/recall.db", "--cwd", "/path/to/project"]
    }
  }
}
```

For Codex, the corresponding configuration is:

```toml
[mcp_servers.recall]
command = "/absolute/path/to/python3"
args = ["/path/to/recall/scripts/recall_mcp.py", "--db", "/path/to/recall.db", "--cwd", "/path/to/project"]
startup_timeout_sec = 10
tool_timeout_sec = 10
```

Codex supports local STDIO servers and project-scoped `.codex/config.toml` in trusted projects. A client starts the server; it does not automatically start the separate capture process. [Official MCP configuration documentation](https://learn.chatgpt.com/docs/extend/mcp).

The four tools are `recall_search`, `recall_get`, `recall_brief` and `recall_status`. Search includes both source agents in the configured repository. Use `kind: "tool_use"` for exact commands, and follow `next_start` from get for long evidence. Briefs contain sampled historical excerpts, not a complete or live account. Status reports only that repository's known sources and derived counts. An empty search is not proof that an event never occurred.

## What is verified

| Client or source | Retrieval | Capture | Evidence still needed |
|---|---|---|---|
| Claude Code | Existing skill; real CLI MCP health check reports Connected | Existing hooks; optional explicit refresh/watch | Authenticated natural MCP/skill use and actual compact receipt in the working terminal |
| Codex | Installed skill discovered and exercised in a live desktop task; MCP configuration supported by its host | Existing Codex adapter; independent foreground refresh/watch | Fresh desktop-task MCP discovery and natural model use |
| Official Python MCP SDK 2.1.1 | Independent client negotiated 2025-11-25; search/get/brief/status and scope checks passed | Observed an appended Codex record from the independent watcher through the same reader | This is protocol verification, not a model-quality score |
| Other coding clients with compatible stdio MCP support | Same endpoint/configuration contract; individual hosts not yet tested | Only Claude and Codex source formats are currently ingested | Host-specific discovery/behavior; any new transcript adapter needs format evidence and tests |

The SDK probe also verifies exact Unicode pagination, rejection of another repository's block ID, empty results for an absent marker, unchanged store bytes after read calls, and clean watcher shutdown. Server and capture run with Python site packages disabled in that probe; the SDK is a developer test dependency, not a Recall runtime dependency.

## Boundaries

The server uses a read-only SQLite connection and a consistent read transaction per tool call. It neither initializes/migrates/repairs the store nor imports histories, executes recalled commands, or offers write tools. A missing, incompatible or broken store returns an actionable tool error. Repository scope is set outside model arguments and checked on source filters and get-by-ID as well as searches. Each call sees a fresh database connection so separately committed capture becomes visible. SQLite may use WAL coordination sidecars; read-only serving means it does not modify retained data or schema.

The stdio implementation supports the 2024-11-05 through 2025-11-25 revisions listed in its code. The current SDK's fallback to 2025-11-25 was verified; the server does not claim native 2026-protocol semantics. Messages are newline-delimited JSON-RPC. Input is capped at 256 KiB; each tool's JSON payload at 65,536 characters, with smaller search/page limits. SQL has a two-second progress timeout and a 500 ms lock wait; these are not hard limits on Python work over unusually large retained blocks. [MCP transport](https://modelcontextprotocol.io/specification/2025-11-25/basic/transports), [lifecycle](https://modelcontextprotocol.io/specification/2025-11-25/basic/lifecycle) and [tools specification](https://modelcontextprotocol.io/specification/2025-11-25/server/tools).

Recall itself makes no network requests. Retrieved evidence goes to the calling host and may be sent to its configured model provider. A read-only tool annotation does not make recalled text trustworthy instructions or make cloud inference local.

ChatGPT web access and ChatGPT export ingestion remain separate decisions (P59). The present implementation opens no HTTP port and does not imply access to account chat history. Additional transcript formats are also separate from allowing another client to read existing Claude/Codex evidence. P58/P60–P62 track the active implementation, host checks and cross-agent handoffs; the original activation, human-evaluation and publication gates remain.
