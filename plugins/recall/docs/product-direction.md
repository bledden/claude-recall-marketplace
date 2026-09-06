# Recall's product direction

Recall makes earlier work easy to recover and check: the original words, exact commands, decisions and reasons, with enough surrounding evidence to continue confidently.

Its priorities are:

- **Lightweight operation, measured in use.** Keep setup effort, memory, latency, storage and model context proportional to the recovery benefit. Python standard library and SQLite provide the default capture and lexical path. A small local embedding model can also qualify as lightweight when measurements support it; dependency count alone does not decide.
- **Evidence people can inspect.** Readable citations and precise ranges, visible coverage gaps, and clear distinctions between proposals, accepted decisions and current state.
- **Continuity in the user's existing workflow.** Claude Code capture, Codex recovery, and scoped Claude Chat/Cowork readers where verified. Each interface should explain what it can read and what it captures.
- **Deliberate scope and ownership.** Local stores, explicitly selected repositories and capture sources, opt-in extra resources, and user-controlled retention and sharing.
- **Useful day-to-day organization.** Session/time navigation, tags, and small highlights between ongoing sessions when those help the user resume work.

New work should solve an observed failure or repeated user need, have a measurable resource cost, and preserve these properties. A competing project's feature list is not sufficient justification. Broader agent adapters, automatic synchronization, additional retrieval models and integrations wait for evidence that they improve this workflow enough to justify their maintenance and resource costs.

The current update window prioritizes safe everyday activation, the human evaluation, operational reliability and context efficiency. The Funes comparison is a factual landscape check, not a parity checklist or an accuracy claim.

Optional embeddings already exist: an explicit build with a supplied local model,
followed by CLI search with `--semantic`. They are not a retired or forbidden
direction. Current evaluation supports keeping lexical retrieval as the default;
it does not establish that every model or future corpus favors lexical retrieval.
Reassess the optional path using retrieval benefit and cold/warm latency, peak memory,
index size, refresh cost and context use. As of the September 6 live-store check,
the everyday store has no configured semantic model and zero vectors: earlier
builds were evaluation fixtures. Current MCP readers expose lexical retrieval.
