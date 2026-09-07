# Durable memory: implementation and rollout

The [total update-window plan](update-window-plan.md) tracks remaining work, historical deferrals, integration, installation and publication. This document describes the implementation already on the development branch; it is not a declaration that the rollout is complete.

Version 2.5.0 is an unreleased development change. It adds a source/block/passage store alongside the v2.4 exchange store. The new search interface retrieves historical evidence with exact references; the host agent writes the explanation and checks current facts separately.

## What changed

- Claude hooks retain complete redacted user/assistant text blocks and tool-call inputs. Passage size and display limits no longer determine how much text survives.
- `find` retrieves passages with agent, session, timestamp, block ID and character offsets. `get` supports exact pagination and neighboring messages.
- Prose is searched by default. `--kind tool_use` searches commands/inputs; `--kind all` includes both. Terms are quoted for FTS, common English question words are omitted, and `--require-all` selects conjunction instead of the default disjunction.
- `brief` selects the opening ask, recent evidence and passages containing decision/failure/open-work language. It is a bounded heuristic sample, not a comprehensive summary or a classifier of verified decisions. Head and tail excerpts carry offsets. `--live-git` puts an independently observed branch/commit/worktree state in a separate field.
- Explicit Claude and Codex JSONL adapters share agent-qualified source IDs. Normalized Git remotes group equivalent SSH/HTTPS clones; common Git directories group local worktrees. `--cwd` can correct absent or unsuitable source metadata.
- `status`, `sources` and `doctor` expose source coverage, cursors, backlog, last capture time, omitted/malformed counts and integrity checks. Empty search results do not prove absence from unimported histories.
- One optional local sentence-transformers backend can build vectors and fuse rankings with lexical search. Hooks never load a model. It remains opt-in after mixed results in the [retrieval probe](../benchmarks/README.md).

## Try it without changing the live database

Run from this repository; Python 3.9+ with SQLite FTS5 is required. Default paths need no third-party Python packages.

```bash
python3 scripts/recall_memory.py --db /tmp/recall-trial.db index /explicit/trace.jsonl --agent claude --cwd /path/to/project
python3 scripts/recall_memory.py --db /tmp/recall-trial.db index /explicit/codex-history --agent codex --cwd /path/to/project
python3 scripts/recall_memory.py --db /tmp/recall-trial.db search "why rejected batching" --cwd /path/to/project
python3 scripts/recall_memory.py --db /tmp/recall-trial.db get BLOCK_ID --start 0 --max-chars 8000 --neighbors 2
python3 scripts/recall_memory.py --db /tmp/recall-trial.db brief --cwd /path/to/project --live-git
python3 scripts/recall_memory.py --db /tmp/recall-trial.db doctor
```

`--db` precedes the operation. A timed import reports committed progress; repeat it without `--rebuild` to resume. Directory discovery and any single oversized JSONL record can exceed the soft time budget. Unterminated final records wait for their newline.

Current source adapters exclude reasoning, system/developer messages, tool results, image blocks and inline base64 data URIs. Other structured or unsupported records count as omitted. They do not install continuous Codex capture. Tool inputs and ordinary prose can still contain unrecognized sensitive material: [redaction is pattern based](../PRIVACY.md).

## Storage and recovery

Schema 6 preserves legacy rows and FTS while adding durable tables. Existing sessions get an independent backfill cursor when their hooks next run; bulk backfill is explicit. The old capped text cannot recover a discarded tail unless its original transcript is still available.

Source IDs combine agent and session. Message IDs come from the trace where available, otherwise its byte position. Block IDs derive from source/message identity, content ordinal and kind; repeating an import or rebuilding the same source does not duplicate blocks. Passage offsets refer to the retained redacted text, not original unredacted characters. Byte ranges identify source JSONL records.

Missing originals leave retained evidence readable. Shrinkage and changes to the 256 bytes preceding a saved cursor stop incremental capture and request `--rebuild`; this is an append-continuity check, not a full-file tamper detector. Earlier edits that leave that window unchanged require explicit rebuild. Rebuild atomically replaces content in each indexing pass, then resumes the rest; it is not an all-or-nothing replacement of a multi-pass source.

`prune AGENT:SESSION` removes a durable source, chunks, FTS entries and vectors in the same transaction. It leaves original transcripts and legacy exchange rows. Legacy session pruning also removes matching durable sources. `export AGENT:SESSION` emits complete redacted blocks and provenance as `recall-blocks-v1` JSON; this is an archival format, not another JSONL importer input.

Make a SQLite backup before installing against an important live database. The schema upgrade is additive, but reverting the plugin does not remove new retained data or undo the migration. This development work leaves the installed plugin at Fable's v2.4.0; reload Claude's plugins or restart its session to activate that already completed update.

## Optional semantic experiment

Install sentence-transformers separately if desired, and supply a trusted model directory that already exists locally:

```bash
python3 scripts/recall_memory.py --db /tmp/recall-trial.db semantic-build --model-path /existing/local/model
python3 scripts/recall_memory.py --db /tmp/recall-trial.db search "reason for the earlier choice" --all --semantic
```

Model files are fingerprinted; a changed model refuses retrieval until rebuilt. Source changes invalidate their vectors, and a build only attaches vectors to the exact text encoded. New passages need another explicit build. Semantic search scans the scoped vector corpus in memory; this is a small-corpus experiment, not a scalable approximate-nearest-neighbor service. No confidence threshold turns retrieved similarity into a factual answer.

## Update-window changes after the first revision (2026-09-05, Fable)

- Schema 7: `memory_sources` gains `excluded`, `metadata_records`, `unsupported_types`, `generation`, `head_hash`; `memory_blocks` gains `ordinal` and `generation`. Migration is idempotent and tested from schema 6 and from a schema-5 backup.
- Rebuilds are generation-based and safe when interrupted; edit detection covers the file header and the cursor tail and names the changed window.
- `doctor` emits one next action per source state; `status` explains each skipped-record counter.
- `backup`/`restore`/`import-export`/`rescope`/`config`/`install-codex-skill` commands; opt-in Codex import at Claude session start; verbatim compaction recovery on `SessionStart(compact)`.
- Durable search defaults to a 30-day recency half-life (P12). Redaction regex made linear (P27). Directory imports newest-first.
- Evidence for every change is in [the plan's evidence log](update-window-plan.md#evidence-log).

## Accepted work and release status

| Work | Status |
|---|---|
| Full retained source text; head/tail concern | Implemented; exact retrieval and bounded head/tail brief excerpts; compaction recovery quotes tails |
| Claude/Codex import, repository identity, provenance | Implemented; explicit Codex import |
| Briefing and capture diagnostics | Implemented; historical evidence separated from live Git |
| Retrieval evaluation | 60-question real-history anchor probe; human answer-quality labels remain with the maintainer; fresh synthetic Claude/Codex behavioral checks are recorded separately |
| Embeddings | One offline backend implemented and tested; kept opt-in |
| Installed local plugin update | v2.4.0 installed (cache 2.4.0); active session reload pending the user's window (P22); 2.5.0 install pending P20/P23 |
| Blog npm vulnerabilities | Separate dependency branch updates Astro/MDX/sharp/integrations and CI Node; clean install/build and zero-vulnerability audit |
| Git push / publication | Excluded by user instruction; no push or publication performed |

Validation covers migration with existing v5 rows, complete long-answer pagination, partial UTF-8/JSONL recovery, bounded progress, changed/missing sources, agent isolation, redaction before FTS, cascade deletion, durable SessionEnd backfill, explicit prose/command selection, model changes and capture during embedding. Real Claude/Codex traces are exercised only in isolated temporary stores; raw histories are not committed.

Final local validation of the first revision: 481 tests passed (`python3 -m pytest -q`), and `claude plugin validate` passed. After the update-window changes: 521 tests; see the plan for per-item evidence. The blog branch passed `npm ci`, `npm run build` (13 pages), and a live `npm audit` with zero reported vulnerabilities.

The real-trace smoke run retained 1,540 Claude blocks and 79 Codex blocks, verified exact paginated retrieval, selected eight briefing references, matched the main checkout's repository identity to its worktree, and passed both SQLite and external-content FTS integrity checks. These counts describe that snapshot, not all available histories.

Schema 10 adds [retained revisions and atomic rebuilds](revision-evidence-design.md).
[Explicit conversation imports](history-import.md) supplement local transcript capture.
