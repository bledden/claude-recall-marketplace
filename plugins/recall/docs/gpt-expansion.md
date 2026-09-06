# GPT expansion recommendation — September 6, 2026

Yes: make the retained evidence usable across agents. The immediate value is being able to continue a Claude task in Codex and retrieve the original decision, command and source passage. That workflow already works through Recall's Codex adapter and installed skill; Astra exercised discovery, search and get in a live desktop task. Automatic capture and fresh-task activation must be described separately from retrieval.

## Proposed next increment

Keep one SQLite store, one set of source identities, and one retrieval implementation. Add a small optional local MCP interface over `memory_store` only if testing shows the skill/CLI route is insufficient or another host needs tools. Its four operations should be `search`, `get`, `brief` and `status`. Preserve block IDs, character offsets, scope, source time and coverage notices in tool results. A model can then check evidence instead of asking another model to reconstruct a memory.

Current official documentation lists local STDIO and Streamable HTTP MCP servers for Codex hosts, shared configuration across the desktop app, CLI and IDE, and remote plugin-provided MCP tools for ChatGPT web. This establishes possible integration routes; it does not establish automatic access to ChatGPT conversation history. [Official MCP documentation](https://learn.chatgpt.com/docs/extend/mcp), read September 6, 2026.

Start with a local process. Configure allowed repositories/sources outside model-supplied arguments and enforce them on every operation, especially `get` by block ID. Do not expose arbitrary SQL, filesystem paths, indexing, restore or deletion as retrieval tools. Use a genuinely read-only connection for serving: the current `get_connection()` can migrate a store, so simply wrapping the CLI is not sufficient for a read-only server. Migration/import remains an explicit local operation. Retrieved text remains untrusted historical evidence.

For ChatGPT web, a remote endpoint introduces authentication, authorization, transport and data-handling work. Treat that as a separate opt-in product decision after the local workflow earns its place. An explicit user-supplied ChatGPT export adapter is another possible increment, contingent on inspecting an authorized export and handling branches, edited messages, roles and attachment references honestly. No account scraping or implied access to all past chats.

## Evidence needed before shipping an additional interface

- A fresh GPT-powered host discovers Recall and chooses search/get from a natural request, with a correct citation.
- A Claude-to-Codex and Codex-to-Claude handoff recovers the accepted decision and distinguishes rejected or superseded text.
- Allowed-source boundaries hold even when a caller supplies a valid block ID from another repository.
- Missing answers remain distinguishable from vaguely relevant hits; complete source evidence can be paginated.
- Capture freshness and attachment-body limits are visible. Tool availability is not proof of continuous capture.
- A matched evaluation shows the additional interface improves completion or removes a real integration obstacle without creating another ranking implementation.

This is a recommendation, not a new release promise. P58 records the local MCP decision; P59 records the separate ChatGPT web/export decision. Neither is part of the 2.5.0 release gates unless the maintainer explicitly changes scope. The current skill/CLI route remains the supported Codex path.
