# Recall: total update-window plan

## Current completion candidate — September 7, schema 10; session privacy added

The maintainer explicitly promoted the previous revision/history/quality boundaries
into work for this update. This section supersedes the older future dispositions
below. Fable independently reviewed the candidate with no blocker. The maintainer restarted
Codex and authorized proceeding with activation. Follow the latest activation
receipt in the local review folder for installed revision, schema and remaining
connection refreshes; do not interrupt resumed project tasks. Publication is held.

| Row | Current disposition | Evidence / remaining action |
|---|---|---|
| P38/P52/P83 | Implemented, tested and installed in the live schema-10 store | Atomic staged durable rebuilds; exact revision reads; bounded history/pins/GC; archive integrity; portable history; migration rehearsal. 333 MB staging max 83 ms, final publication 0.83 s, peak 39.4 MB. Legacy exchange commands retain their separate behavior. |
| P59/P69/P84 | Offline selected-history import implemented; real visible Chat path verified | Preview/select/scope workflow, Claude and ChatGPT export-shape fixtures, current-branch rules, explicit copied-chat snapshot. Real 690/1,095-character Chat messages round-trip exactly. No local account export found; certify a representative real export when supplied. No automatic account capture claim. |
| P70 | Concrete portable handoff available | Explicit per-source export for a user's chosen cloud attachment flow. Connected-Mac MCP remains supported. No remote service is needed for this manual route; always-on remote reading would require a separately provisioned authenticated endpoint, which does not exist here. |
| P71/P85 | Independent of P10: fresh synthetic model checks completed | Two fresh sessions each in Claude and Codex, eight questions each. Astra's rubric review matches all 16 substantive answers; 18/18 requested quotations verified. Four initial Codex searches exceeded the limit and were retried. Generic validation errors now state allowed bounds. This is not a human score or real-world generalization claim. |
| P07 | Capture, compaction and new rebuild measurements pass | 333 MB capture max 198 ms, steady 4.4 ms, 41.8 MB RSS. Compaction fixtures remain below their gates. Snapshot migration preserved existing blocks/chunks/vectors/exchanges/sessions. |
| P10 | PASS: maintainer accepts the completed review, including the two noted answers | September 7: maintainer explicitly allows candidate-codex-02 and -22 for this practical acceptance, noting the answering model was known to be brief. Human evaluation is no longer a release gate. Preserve Astra's source findings, six qualifications and corrected worksheet citation in p10-completed/REVIEW.md; acceptance does not erase them. Five frozen source hashes and 47 supplied reference blocks match. All 28 earlier-project answers reference the eval set, so this remains practical acceptance rather than a blind score. The receipt supersedes older pending-label dispositions; the frozen packet remains unchanged. |
| P22/P86 | Current Codex connection verified September 7; older terminal reloads remain per terminal | This task's live MCP status/search/revision-get succeeded with a valid exact quote. Receipt: schema10-activation/codex-reconnect-2026-09-07.json in the local review folder. No further Codex restart needed for the current runtime. Desktop Chat and Mac-connected Cowork were reloaded and verified through separate connectors. Source capture backlog is separate from connection health. |
| P87 | Packaged first-install and upgrade workflows verified; release instructions included | Isolated packaged CLI/MCP flows pass for an empty store, v2.4/schema-5 upgrade and schema-9 upgrade; local marketplace 2.4→2.5 install/update also passes with isolated client settings. Documented backup, migration, generated-reader replacement, reconnect, quote offsets and rollback limits. See [install/update checklist](install-and-update.md). |
| P88 | Session privacy scoped; host binding feasibility next | Maintainer requested shared/session-only/do-not-retain modes. [Design and retest matrix](session-privacy-design.md) distinguishes Recall access enforcement from host filesystem isolation. No broader system permission requirement; verify trusted caller binding per host before promising session-only support. |
| P89 | Active, not implemented | Versioned policy registry, separate private stores, suppression records and routing across all durable/legacy capture paths. No private-to-shared fallback. |
| P90 | Active, not implemented | Restricted CLI/MCP, current/revision/neighbor reads, semantic/legacy paths, counts, compaction, exports and supported per-session host attachment. No model-controlled identity grants. |
| P91 | Active, not implemented | Explicit privacy transitions and existing-content handling, crash-safe conversion, compatibility boundary, backups/restores and rollback preserving policy. No retroactive revocation claim for already disclosed text. |
| P92 | Active, depends on P89–P91 | Automated owner/foreign/no-identity access matrix, negative filesystem probes for any host-isolation claim, full regression suite, fresh/continued host checks and resource/token rerun. Refresh affected P10 cases without asking for blanket relabeling. |
| P93 | Active, depends on tested implementation | Exact user-facing guarantees and permissions, unsupported-host behavior, first-install/update instructions, rebuilt artifacts/readers/cache and repeated packaged installation/upgrade verification. Earlier runtime receipts do not certify privacy. |
| P94 | Observed coverage/mapping/reading issues fixed; live selected histories backfilled; ongoing capture integration remains active | September 7 usage-repairs receipts: 765 tests; full-scope source_agents counts, persistent explicit CLI mapping with foreign-scope refusal, matching-reader/approved-route reuse and bounded evidence guidance. Original arrwDB evidence now returns; triton scope includes its Codex task. Claude transcript audit found missing original history and hidden coverage during evaluation, with no model Recall calls in the two sampled ordinary work sessions. No ranking or automatic-selection suppression. Read-only access still depends on host permissions; use the approved route. These are observed-case checks, not fresh model-quality certification. |
| P95 | P10 submission reviewed and PDF delivered; findings feed P94's fresh checks | p10-completed/ contains all 50 original answers, per-case assessments, derived label corrections and a verified 39-page PDF. Add historical-date boundaries and agent-versus-human review attribution to the fresh behavior checks. No blanket 50-case human rerun; no model ranking or blind accuracy claim from this exposed worksheet. |
| Publication | Held, last, unchanged | Push dev/marketplace, tag/asset, blog deploy, catalog pin PR, stale PR closure, hotfix decision only on maintainer instruction. |

Receipts: `~/Documents/recall-review-2026-09-05/active-completion/`.
Detailed current contracts: [revisions](revision-evidence-design.md),
[history import](history-import.md), and the candidate completion report.

### Earlier status and chronology (superseded where stated above)


This is the single working plan for the current update window. It includes Fable's open items, the durable-memory work, gaps exposed by that implementation, distribution work, and outstanding ideas in the older plans. New findings must be added here rather than left in a chat or described only as future work.

**Outcome:** reliable recovery of prior work across coding agents, with complete retained evidence, useful retrieval, visible coverage, and an installation that has been exercised in a real session. Passing unit tests or committing a branch does not by itself complete this outcome.

**Current constraint:** no Git push or publication. Prepare and validate local changes and release artifacts; remote release/deployment remains a tracked step requiring that instruction to change. Do not interrupt a running Claude session to reload it.

## Active ownership (2026-09-06, Astra takeover)

The maintainer asked Astra to take over integration and the remaining local work from Fable. Astra now owns implementation, verification, local commits, installation and distribution preparation. Fable's final P13 review landed in `6ee3b4a` while this work was underway; its two formatting fixes and the accepted compaction patch are preserved. The historical ownership table below is superseded by this paragraph.

P13 is accepted. P17/P55/P61 have live installed-skill and restarted-desktop MCP evidence; P19 has Fable's fresh authenticated skill/compaction receipts. P62 now has fresh Claude and fresh ephemeral Codex MCP evidence recovering both source agents. P22 remains the maintainer's convenient refresh of stale skill text in the existing Claude session; its hooks/scripts are 2.5.0. P10 human labels/evaluation remain open. P52/P59 now have explicit dispositions in the current closure map. Publication remains held.

## Current closure map — September 6, caveat pass

This section supersedes stale status wording in the dated evidence log. Historical
receipts remain evidence for their measured revisions; they are not the current
open list. The agent-owned runtime fixes and measurements from this pass are
P79–P82 below. 733 tests pass on the completed candidate; manifest validation and the 333 MB
capture budget pass (14.8 s backfill, 194 ms worst pass, 42 MB peak RSS).
Final installation/test receipts are in the local
`recall-review-2026-09-05/caveat-closure/` packet.

| Owner / disposition | Rows | Current action or boundary |
|---|---|---|
| Maintainer | P10 | Human acceptance/corrections of the unchanged 50-case packet. Agent then runs the declared evaluation; no tuning on those labels first. General answer quality remains unproven. |
| Maintainer, at a convenient boundary | P22 | Refresh stale Claude Code skill text. Do not interrupt an active task; installed files and newly launched readers are separate from cached session instructions. |
| Held publication | P26/P27/P30/P32 | Push dev/marketplace, tag/release with validated asset, deploy blog, catalog pin PR, close stale PR #1, then decide 2.4.1 hotfix. Nothing is authorized remotely by this pass. |
| Runtime work addressed | P66/P71/P79/P80 | Exact quote/hash checking, evidence provenance, flagged legacy host filtering and explicit historical cleanup. A passing model trial proves use of the mechanism, not that every future answer will obey it. P71's remaining general quality judgment is P10. |
| Supported local capture, external source boundary | P69/P81 | Foreground capture accepts an explicit pinned host mapping for selected local Cowork JSONL. Current cloud-only Cowork and Chat have no verified transcript source/export adapter. Reading existing indexed history remains supported through the connected Mac. Do not invent an account-history capture path. |
| Resource decision complete, quality gated | P14/P82 | Existing offline embeddings remain opt-in; CPU build/cold/warm/no-op/incremental costs measured. No live model/config/vectors enabled. A default/backend change requires demonstrated benefit under P10, not feature parity. |
| Explicitly excluded from 2.5 | P52 | Concrete revision/generation design in [revision-evidence-design.md](revision-evidence-design.md). Current hashes detect edits; immutable revisions/atomic whole-source rebuilds are not promised. Reopen for a concrete saved-citation requirement. |
| External data contract / separate product scope | P59/P70 | User-supplied export adapters require an authorized representative format and branch/edit/attachment semantics. Standalone remote access requires an authenticated scoped deployment contract; this release supplies local readers plus portable export/import, without a listener or implicit upload. |
| Deliberately not added | P76 | Codex foreground refresh/watch is implemented and tested. The reported index-unavailable incident was read access/SQLite sidecars (P77), not evidence of a lifecycle-capture gap. No second hook system is added to solve that incident. Reopen only for a reproduced freshness failure that the selected watcher cannot address; never bypass host hook trust. |
| Implemented and locally checked | All other active P01–P78 rows | Prior integration, capture/compaction budgets, restore/schema, scope/read-only access, diagnostics, token measurements and distribution fixes stand. Blog dependency work is local and checked; origin alert closure is held publication verification. Earlier “pending docs/review” wording is historical, not a hidden agent task. |

### P79–P82: substantive caveat work

| ID | Status / evidence | Contract |
|---|---|---|
| P79 | Exact quote/hash checks and provenance implemented in CLI/MCP, search/get/brief and skills; reproduces the actual wrong-ID citation as invalid and correct range as valid; fresh Claude trial used checks | Unicode offsets in returned redacted text; a hash detects changed content, not immutable history. Tool inputs prove requested actions, not execution or resulting files. P10 remains independent. |
| P80 | Legacy parser skips isMeta/isCompactSummary without losing cursor or assistant continuation; explicit cleanup matched 207 host prompts in a backup rehearsal with IDs/replies/tools/annotations/durable data preserved | Match original timestamp plus exact redacted capped prompt; skip ambiguous real-user duplicates; transaction locks before selecting FTS delete payload. Live application and backup recorded in the closure receipt. Old transcripts/backups/tags are not purged. |
| P81 | Explicit --cwd mapping in independent capture, scope pinning and foreign-scope refusal; two real Cowork prefixes and appended records exercised in scratch stores; a foreground CLI watch also captured initial/appended/new-file records under one pinned host scope | Selected local sources only. This is not automatic capture of new cloud-only app tasks, nor a Cowork compaction hook claim. |
| P82 | Same-snapshot token rerun and cached-model CPU resource probe; full resource details in product-direction.md and local raw JSON | Five-hit search + 2,000-char get median: Recall 4,391.5 → 4,820.5 proxy tokens; triton 2,108.5 → 2,550. Extra hashes/provenance/check guidance have a cost. Exact check adds 65–67 output proxy tokens in two sampled gets. Static MCP schema 759 → 850, Code skill 3,603 → 3,725. No provider savings or human quality claim. |

## Starting state

| Area | Verified state at plan creation |
|---|---|
| Released Recall | Fable's v2.4.0, development main `b41994f`; release and marketplace sync reported by Fable |
| Installed Recall | Local plugin update to v2.4.0 succeeded; active-session reload remains unverified |
| New Recall implementation | `feat/durable-memory`, commit `87918cb`, in `claude-recall-memory-next`; not merged, installed or released |
| New implementation checks | 481 tests pass; plugin manifest validation passes; real Claude/Codex imports, exact retrieval and integrity checks pass in temporary stores |
| Retrieval evidence | One 60-question, single-session anchor probe; no untouched holdout or human answer-quality evaluation |
| Blog dependency fix | `fix/dependency-audit`, commit `410fde5`, in `recall-blog-dependency-fix`; clean install, 13-page build, zero reported npm audit vulnerabilities; not merged or deployed |
| Existing blog content | Fable's September update is already live; this work has not changed posts |
| Parked v3 | `feature/v3-tiered-architecture` at `47cdcba`; separate old implementation, not a release-ready addition to the current branch |

Implementation details and existing evidence: [durable memory](durable-memory.md), [retrieval probe](../benchmarks/README.md). Historical inputs: Fable's September update, the supplied briefing, [v3 design](superpowers/specs/2026-04-08-recall-v3-tiered-architecture-design.md), [v3 implementation plan](superpowers/plans/2026-04-08-recall-v3-implementation.md), and [sharing design](superpowers/specs/2026-04-01-cross-session-sharing-design.md).

## Execution order and completion criteria

Unless marked otherwise, implementation and verification are owned by the coding agent working this plan. Human review is identified where it is needed for credible evaluation or activation. Each row remains open until its completion criterion has evidence recorded here.

### 1. Reconcile scope and old branches

| ID | Status | Work and completion criterion |
|---|---|---|
| P01 | Complete | Consolidate all known open/deferred items into this file and link it from the current implementation notes. |
| P02 | Reviewed; disposition recorded (evidence log) | Review the diff of the parked v3 branch against current main. Map every distinct feature and follow-up to the disposition table below; identify useful code that can be reused without restoring obsolete hook assumptions. Record the result before closing that branch's roadmap. Branch deletion is not required. |
| P03 | Docs reconciled on branch (durable-memory.md, README 2.5.0 section, PRIVACY, CHANGELOG, SKILL); old plans left as history; briefing questions answered in the evidence log | Reconcile the old briefing's questions and claims with final behavior: full retention vs legacy caps, hook selection, verbatim compaction recovery, relevance/recency, optional dependencies, and positioning. Update stale active docs; retain old plans as explicitly historical records. |

### 2. Finish the durable-memory product

| ID | Status | Work and completion criterion |
|---|---|---|
| P04 | Implemented; independently reviewed on real Claude and Codex traces; two defects fixed (evidence log); remaining checks listed | Full redacted block retention, stable citations, pagination and neighbors. Independently review source adapters and exercise repeated/updated message IDs, multi-block messages, malformed shapes, unsupported layouts, and redaction boundaries. Fix any loss, duplication or misleading completeness claims found. |
| P05 | Implemented and exercised through the normal skill path by Fable under P19; complete get and cited answer observed | Resolve the split between durable `find/get` and capped legacy `search/lastN/around`. Choose and implement a consistent default recovery path, while preserving documented compatibility. Verify a long answer can be found and fully read through the normal skill flow without knowing which store to select. |
| P06 | Implemented with accepted P38 semantics: revisited same-id text changes immediately; unvisited old blocks remain until EOF; incomplete state is visible | Strengthen source lifecycle behavior. Decide and implement safe interrupted rebuild semantics, meaningful detection/reporting of source edits before the cursor, and truthful import progress. Verify that stopping mid-rebuild cannot silently present partial replacement as complete history. Current rebuild is per-pass; current continuity check covers only the preceding 256 bytes. |
| P07 | Fixture budget work complete: previous capture/concurrency evidence plus full manifest compaction sequences measured by benchmarks/compaction_budget.py (shell/Python startup, ordinary/10k-block history, 8 MiB selected blocks, writer lock, Codex refresh). All named gates below 2 s / 100 MB; prose-heavy storage ratios reported separately. Limits and raw receipt below | Establish hard resource behavior for large records/corpora, concurrent hooks and imports, and database growth. Measure capture latency, peak memory and size against v2.4 on identical snapshots; choose documented budgets before changing the implementation. Fix identified failures. Current byte/time limits are soft and embeddings scan vectors in memory. |
| P08 | Implemented: skipped-record classification + per-source next actions; verification on real traces recorded | Finish operational diagnostics: distinguish known-source coverage from all-history coverage, global vs scoped counts, unsupported records, changed/missing files, incomplete imports and stale semantic indexes. Doctor must give an actionable next step for each supported failure state. |
| P09 | Implemented: backup/restore (SQLite backup API, migrations re-run after restore) and export/import-export round trip; deletion matrix recorded; PRIVACY text update pending under P03 | Review retention and deletion across legacy rows, durable blocks, passages, vectors, exports and original transcripts. Add explicit export/restore support or a tested backup/restore path; verify privacy text, deletion commands and recovery instructions agree. Full retention increases storage and exposure beyond v2.4's caps. |

### 3. Establish retrieval and briefing quality

| ID | Status | Work and completion criterion |
|---|---|---|
| P10 | 50 proposed cases prepared for human review: 28 previously evaluated Claude cases plus 22 Codex candidates, five source sessions, hash-checked prefixes and exact source labels. No retrieval run on the expansion. Correlated cases and reused data mean this is not a new untouched holdout. Human validation and a subsequent declared evaluation remain open (takeover/human-evaluation-review.md) | Create an independently reviewed 50–100-question evaluation spanning multiple sessions and both agents. Include accepted vs rejected decisions, changes over time, exact commands, paths, code symbols, paraphrases, missing answers and cross-repository distractors. Label the actual answer-bearing blocks. Keep a fresh holdout untouched until choices are frozen; human label review is required to call it human-judged. |
| P11 | Three arms compared on one snapshot (legacy v2.4 / durable lexical / hybrid), evidence log; Funes comparison not run: no local funes binary/authorized corpus mapping, recorded as incompatibility, no parity claim | Compare v2.4 lexical retrieval, durable lexical retrieval and optional hybrid retrieval on the same snapshot and output budget. Add a pinned Funes comparison if it can run locally on the same authorized corpus; otherwise record the precise incompatibility and do not claim parity/superiority. Report retrieval success, evidence correctness, answer-absent behavior, latency, returned context size and index footprint. |
| P12 | Decided and frozen: 30-day recency half-life default; AND-first ladder rejected (no gain); reserved-split result recorded once | Tune retrieval only on development data. Test prose/command selection, question stopwords, exact identifiers, recency and neighbor selection. Freeze the chosen behavior before evaluating the holdout. Review misses rather than treating an anchor hit as proof of a useful answer. |
| P13 | Complete for this reviewed workflow: maintainer explicitly accepted integration-82988a6/real-brief.md as useful; Fable completed the requested second read (6ee3b4a), fixed two formatting issues and documented attachment/pasted-report limitations. No general briefing-quality score claimed | Validate briefings as a user-facing workflow: original objective, accepted decisions and reasons, rejected approaches, completed work, open work and contradictions, all with retrievable references. Keep historical evidence separate from current repository observations. The current bounded heuristic selector must not imply completeness or that a proposed decision was accepted. |
| P14 | Implemented (030cb21): vectors are packed little-endian float32 blobs (`f32le-v1`, 1,536 bytes per 384-dim vector versus ~5–8 KB JSON); pre-9 JSON rows are converted in place at migration, invalid or mismatched rows dropped; format and dimension recorded in `memory_semantic_config`; the query path builds one matrix from the bytes. Embeddings stay opt-in. Astra's synthetic probe: exact round-trip, 81.8% smaller payload, decode 62.7 → 0.6 ms per 1,000 vectors | Finish the embeddings decision using P10–P12. Keep the single local backend opt-in unless evidence supports a different default. Check missing dependencies/models, model changes, stale vectors, concurrent capture, resumable builds, large corpora and clear fallback behavior. The current experiment is implemented, but its product decision is not closed by one weak benchmark. |

### 4. Complete capture and agent integration

| ID | Status | Work and completion criterion |
|---|---|---|
| P15 | Measured; decision: keep Stop + UserPromptSubmit + SessionEnd (evidence log) | Resolve the earlier Stop/UserPromptSubmit question with measured hook overhead and recovery tests. Retain redundant capture until an alternative proves final-turn, blocked-Stop, delayed-flush, compaction and session-exit coverage. Record the choice; no hook removal merely to simplify the diagram. |
| P16 | Implemented: bounded verbatim recovery with block citations on SessionStart/compact, de-duplicated by fingerprint, legacy nudge as fallback; context cost measured; live verification under P19/P22 | Implement and validate bounded verbatim compaction recovery using retained blocks and citations on the supported compaction-start event. Compare selected evidence with the existing nudge, prevent repeated injection, and measure context cost. Do not load embeddings in a prompt hook. |
| P17 | Functional integration verified: installed skill use, unprompted use in triton-msl, restarted-desktop MCP calls, and fresh ephemeral Codex MCP recovery. Foreground capture is implemented; no daemon enabled. P63 addresses target-scope guidance | Make cross-agent use operational. Explicit Codex imports exist; design opt-in continuous capture or refresh using a verified supported integration. Provide discoverable retrieval to Codex as well as Claude, using a skill/CLI or a small MCP interface as justified by the host. Verify capture and recall in an actual session; adapter tests alone do not establish integration. |
| P18 | Implemented and tested: worktrees, subdirectories, SSH/HTTPS remotes, changed remote (stable until explicit `rescope`), missing/non-repo directories, `--cwd` correction, cross-repo isolation of search and brief | Exercise repository identity across worktrees, remote protocols, clones, changed remotes, unavailable source directories and deliberate project overrides. Provide a correction path for histories imported under the wrong scope; verify one repository cannot contaminate another's default briefing. |
| P19 | Verified by Fable: fresh authenticated skill selection, search/get/cited answer, real compact boundary with delivered additionalContext, and post-compact re-recovery. Host-record defect fixed under P65 | Smoke-test the model-initiated skill in a fresh Claude session: natural references to earlier work should cause search, exact retrieval and cited synthesis. Test Python fallback and installation paths with spaces. Inspect what the host actually receives, not just the returned hook JSON. |

### 5. Integrate and prepare the update

| ID | Status | Work and completion criterion |
|---|---|---|
| P20 | Local integration includes Fable’s final brief fixes and Astra’s compaction patch (6ee3b4a), followed by Astra’s budget/packaging work. Final checks and committed revision are recorded in the takeover receipts and release BUILD.json; no publication | Review the Recall branch, resolve current-main conflicts if any, and integrate locally after the required product checks. Preserve Fable/user working files. Final tests and plugin validation must run on the integrated revision, with docs/version/privacy/release notes matching it. |
| P21 | Two dated facts as before, plus 2026-09-06 activation: fresh backup `recall.db.bak-20260906-preactivation` (48.3 MB, integrity ok) taken before Fable rebuilt the three live Claude sources and imported both everyday scopes' histories (evidence log); legacy tables unchanged | Back up the live database with SQLite's backup mechanism; prove restoration using a copy. Install the chosen local update only after migration/recovery checks. Record the installed revision and store version; distinguish v2.4 installation from v2.5 development. |
| P22 | Maintainer-confirmed Recall plugin 2.5; Fable verified hooks/scripts at 2.5.0 and schema 9, with old 2.4.0 skill text cached in the working session. Refresh/new-session choice remains with the maintainer; no forced reload | Reload or restart the active Claude session when the user can do so without losing ongoing work; then verify actual plugin version, hooks and natural-language recall. If activation is postponed, keep this row open instead of calling the rollout complete. |
| P23 | Reproducible local preparation via scripts/prepare_release.py from clean committed tracked files. Archive/marketplace/cache revision and per-file hashes are recorded in ~/Documents/recall-release-2.5.0/BUILD.json and takeover receipts. Publish-time date/version check remains before P26 | Prepare the marketplace copy and applicable plugin archive locally from the same final revision. Validate manifests, file parity and fresh-install behavior. Check the community listing's actual pin as a distribution task; do not assume Fable's v2.4 sync distributes the new version. |
| P24 | Integrated into local blog main d4e5d1e (not pushed); clean install/build/audit repeated on the integrated revision: 0 findings; 30 Dependabot alerts remain open on origin/main until the held deploy | Review the blog's major Astro/MDX dependency upgrade and Node 22 requirement, inspect representative rendered pages/RSS/sitemap, integrate locally and repeat clean install/build/audit on the integrated revision. Compare GitHub Dependabot findings when access is available: zero local npm findings does not establish that every remote alert has closed. Posts remain unchanged unless a separate claim correction is justified. |
| P25 | README "never lost" replaced with measured behavior (01668dc); documented flags verified against the CLI; `/recall find` is the skill alias of `recall_memory.py search`; release notes are the CHANGELOG [2.5.0] section; blog v2.5 paragraph committed locally (bledden.github.io d598b29, unpushed) with overhead numbers only, no probe accuracy figures | Reconcile public claims with measured final behavior. Prepare release notes and any warranted blog update locally, including retention changes, actual test/evaluation evidence, optional ML footprint and remaining limits. Do not publish new quality claims based on the old 15%→95% measurement or this anchor probe. |
| P26 | Held by no-push instruction | Push integrated commits, create release tags/releases, publish marketplace artifacts and deploy the blog only after the user changes the current instruction. After publication, verify installed artifact versions, distribution pins, deployed pages and vulnerability status. |

## Disposition of every known deferred feature

These are tracked design decisions for this window, not implicit promises to add every historical feature. A retirement is complete only when the rationale and active documentation are reconciled in P02/P03. No item should remain merely “parked.”

| Deferred item | Planned disposition in this window | Closure route |
|---|---|---|
| Head- vs tail-preserving storage | Full redacted retained blocks, exact pagination; labeled bounded excerpts for display | P04/P05, already implemented in the new store |
| `commands/` to skill migration | Closed by Fable's v2.4; verify end-to-end operation after installation | P19/P22 |
| BM25 vs recency-first search | Measure on the new evaluation; preserve an explicit recency control and exact-query behavior | P10–P12 |
| Verbatim compaction recovery | Bring into the active update plan | P16 |
| Lite/Standard/Enhanced tier system | Retired after branch audit: one durable SQLite core and explicit optional semantic commands replace tiers | P02/P03 |
| Lite JSON storage and tier-transition follow-ups | Retired with tiers; backup/restore/upgrade and portable export/import fulfill the data-preservation objective | P02/P09/P21 |
| MLX/ONNX/TF-IDF fallback chain | Retired: retain the single tested offline backend rather than advertise several unvalidated fallbacks | P02/P14 |
| ONNX export, tokenizer, download and hash-verification follow-up | Retired with ONNX; no model download is implemented or required by the chosen local-model contract | P02/P14 |
| First-run backend detection, tier consent and global tier settings | Closed: explicit local-model build/configuration and diagnostics replace detection and tier consent | P08/P14/P23 |
| Checkpoint embedding in hooks | Closed: explicit resumable semantic-build; models remain outside hooks, no inference scheduler added | P07/P14/P17 |
| Semantic compaction selection | Not selected for 2.5: lexical compaction recovery works within budget; semantic selection needs a measured benefit under P10 before a new implementation | P12/P14/P16 |
| Semantic highlight matching | Keep keyword sharing; semantic highlight matching is not selected without human-reviewed evidence of a missed workflow | P02/P10/P14 |
| Silent proactive surfacing | Keep optional proactive features off by default: relevance/repetition benefit is unproven and unsolicited context costs tokens. Natural skill selection remains available | P02/P13/P16 |
| Per-connection check/delivery overrides | Closed: current manage_connections.py supports per-connection check_mode/delivery_mode. Additional semantic-specific overrides retire with the old tier architecture | P02/P03 |
| Reranking and approximate vector indexes | Not selected: no demonstrated scale/quality failure requiring ANN or a reranker; live vectors are zero and the optional backend remains an experiment | P07/P11/P14 |
| Additional agent adapters beyond Claude/Codex | Claude/Codex adapters are supported; observed local Cowork uses the Claude format. Other adapters require a concrete authorized source contract (P59/P69), not parity work | P02/P17 |
| Cross-machine sharing / remote dataset publishing | Portable backup/export/import/restore implemented; automatic synchronization and remote publishing excluded from 2.5 pending separate identity/authentication/publication contracts (P70) | P02/P09/P26 |
| MCP recall/get tools | Closed: four scoped read-only MCP tools share the durable core and have actual Claude/Codex/Chat/Cowork receipts | P17/P19 |
| Blog dependency alerts | Included as release work, including integration and remote verification | P24/P26 |

## How this plan stays current

- Record status and evidence against these IDs as work proceeds. Use “implemented,” “verified,” “integrated,” “installed,” and “published” distinctly.
- Every new bug, limitation, deferred enhancement or external dependency gets an ID or is mapped to an existing row, with a next action and completion criterion.
- An item can close through implementation, evidence-backed rejection, or explicit supersession. “Later” is not a closure state.
- External/human dependencies remain visible. Do not invent approval, host support, human evaluation, a successful reload or remote publication.
- Before ending the window, reconcile all rows, report any remaining held steps, and identify the exact tested and installed revisions. The no-push hold is expected until the user changes it.

## New rows added during execution

| ID | Status | Work and completion criterion |
|---|---|---|
| P27 | Hotfix branch `hotfix/2.4.1` prepared locally (worktree `~/Documents/claude-recall-hotfix-2.4.1`, da8b0c8: bounded redaction + RECALL_DB hook fix + isolation test; 469 tests, validate passes; version 2.4.1). Not tagged or pushed; released v2.4.0 still affected | The v2.4.0 generic credential redaction pattern (`[A-Za-z0-9_.-]*` before the keyword) backtracks quadratically on long no-space runs: 5k chars 450 ms, 20k chars 7.2 s, 80k chars hangs. Redaction runs on uncapped merged text before truncation, so one pasted minified blob times out every capture hook for that turn and the offset never advances. Bounded quantifiers on the branch (`{0,48}`/`{8,512}`, negative lookbehind); regression test requires 400k chars under 0.5 s. Completion: v2.4.1 hotfix published from the same fix once the push hold lifts, and the installed plugin verified past 2.4.0. |
| P28 | Verified | Mixed hook versions against a newer store: the live database is already at schema 5 (a v2.4.0 session migrated it) while this session's hooks may still be 2.3.1; 2.3.1 writes 3 of 4 FTS columns and SQLite accepts the omitted column. No corruption path found. Completion: none required; recorded so P21/P22 do not treat schema drift as an error. |
| P30 | Open (release step, held) | README's Cowork instructions link to `releases/latest/download/claude-recall-plugin.zip`, but no release since 2.3.0 carries a zip asset (checked v2.3.1 and v2.4.0 via the GitHub API); the only local zip is from January (v1 layout, 23 files). Completion: attach the validated 2.5.0 archive to the release when P26 lifts, and add the archive step to the release checklist. |
| P29 | Implemented (branch) | In-message block order was only implicit in the block id hash; `get --neighbors` and `export` returned a turn's text/tool/text blocks in hash order. `memory_blocks.ordinal` added (v7), written on upsert, used for neighbour and export ordering; regression test. |
| P31 | Fixed on main (7202f89) and hotfix (da8b0c8); live store already migrated | `hooks/session_end.py` and `hooks/post_compact.py` passed `DB_PATH` explicitly to `get_connection()`, bypassing the `RECALL_DB` override that every other entry point honors (present since those hooks existed; v2.4.0 affected). Found because the 19:21 release smoke test, run with `RECALL_DB` pointed at a scratch file, still opened the developer's real store through `session_end.py` and migrated it from schema 5 to 7 (durable tables created empty; exchanges, tags and invocations unchanged; `recall.db.bak-20260905-preupdate` is the schema-5 state). Regression test `tests/test_store_isolation.py` runs 5 hooks and 9 script commands under a throwaway HOME (14 cases). Completion: none beyond release; the store state is what a 2.5.0 install would have produced. |
| P32 | Open (distribution step, held) | The community catalog (`anthropics/claude-plugins-community`, 2,282 plugins) pins `recall` to commit 761a38d (the v2.2.3 README commit, `version: null`), so catalog installs receive 2.2.3, not 2.4.0 or 2.5.0; Fable's earlier marketplace sync did not change this. Completion: after P26, open a catalog pull request that bumps the sha to the released 2.5.0 commit, then verify a catalog install reports 2.5.0. Also at that window: dev-repo PR #1 (`blake-snc:fix-session-id-substitution`, May 28) edits `commands/recall.md`, which no longer exists (the skill uses `$CLAUDE_CODE_SESSION_ID` directly); close it with that explanation. |
| P33 | Fixed on main (schema 8) | Durable capture was quadratic in session length: `index_file` looked up each new message with `WHERE source_key=? AND message_key=?`, which could only use the `source_key` prefix of the `(source_key, seq, ordinal)` index and so scanned every block of the session per message. On the 328.8 MB transcript a 2 MB hook pass took 2.06 s median and 6.9 s worst (10 s hook timeout), full backfill 372 s, steady state 19 ms. Fix: `memory_blocks(source_key, message_key)` index; schema version 8 re-runs the idempotent `initialize()` so existing schema-7 stores gain it (verified on a copy of the live store). After: 87 ms median, 156 ms worst, 13.9 s backfill, 4.3 ms steady. Found by the P07 benchmark; the branch-era P07 numbers on the 21 MB transcript did not expose it. Completion: none beyond release. |
| P34 | Fixed on main (030cb21) and hotfix (2a08646) | R01 (Astra): the credential delimiter `\s*["']?\s*` was still quadratic over whitespace (1,000 spaces 4 ms, 16,000 1 s, 64,000 hang; the prepared hotfix had it too). Every whitespace run in every pattern is now bounded and followed by a required token; tests cover 7 adversarial families (spaces, tabs, quote runs, missing delimiter, bearer, 400k no-space) under 0.5 s and 7 shapes that must still redact. Completion: none beyond release. |
| P35 | Fixed on main (030cb21); hardened f9e70c5 (P47, P50); verifier completed 663a6fb (P53) | R02 (Astra): `restore` overwrote the target before proving the file was a Recall store. Now: read-only open, integrity check, required tables, schema not newer than the plugin, source≠target; migrations run on a staging copy and only the migrated, integrity-checked copy is written over the target. Tests: non-Recall, corrupt, newer-schema and same-file inputs leave the target intact; an older valid backup still restores. |
| P36 | Fixed on main (030cb21) and hotfix (2a08646) | R03 (Astra, P31 class): the v1 `index.json` migration read and renamed the default-home file even with `RECALL_DB` elsewhere. The legacy index is now looked for beside the store in use; the isolation test seeds a legacy file and a sentinel under a fake HOME and requires exit 0 and no change. |
| P37 | Fixed on main (030cb21) | R04 (Astra): `import-export` copied per-block generations from the file, so a rebuild could keep deleted blocks. Imported blocks now take the source's generation. |
| P38 | Accepted by both agents as a documented limitation (f9e70c5). Astra's P38-opinion.md: the weaker semantics are coherent for an append-oriented store; the stronger form (immutable revisions, atomic generation activation) is a future product decision, see P52. Discoverability sentence added to README and SKILL: during a rebuild results can mix old and new content; a block id resolves to its latest indexed text | R05 (Astra): during an interrupted rebuild a message whose id is unchanged but whose text changed loses its old text when rescanned. Keeping both versions would need a versioned block id plus an FTS swap at activation; instead the behaviour is defined: a rescanned same-id message shows the new text (the file is the truth), messages not yet reached keep their old text until end of file. README, CHANGELOG and the `index_file` docstring say so; Astra's reproducer is replaced by a test of the documented behaviour. Reopen if a user needs both versions of an edited message. |
| P39 | Fixed on main (030cb21) | R06 (Astra): a transient `source_changed` during a rebuild dropped the in-progress flag, so end of file skipped the stale-generation cleanup. "Rebuild in progress" is now derived from the data (blocks older than the source generation exist) via the new `(source_key, generation, seq)` index. |
| P40 | Fixed on main (030cb21) | R07 (Astra): the next ordinary index pass recomputed identity from the transcript cwd and undid `rescope`. `memory_sources.scope_pinned` (schema 9) makes the correction sticky; `rescope SOURCE --auto` unpins. Test: pin survives passes with new records; unpin restores the observed path. |
| P41 | Fixed on main (030cb21); P33 re-verified | R08 (Astra): a rebuild kept old sequence numbers, so an inserted earlier message sorted last. Sequence numbers now follow the current generation and are rewritten on rescans. The first version of this fix added a generation predicate to the per-message lookup and the planner switched to the generation index, re-creating the P33 scan (329 MB: 364 s backfill, 6.4 s worst pass); the lookup now names the message index (`INDEXED BY`) and the 329 MB run is 14.0 s / 173 ms worst again. Lesson recorded: run `capture_budget.py` on the 329 MB transcript after any change to `index_file`. |
| P42 | Fixed on main (030cb21) | R09 (Astra): a valid JSON record with an integer `message.content` raised inside the durable pass; the savepoint rolled the pass back and the cursor never advanced. Field types are validated, per-record failures are counted as malformed and skipped; 8 odd shapes (int/object content, non-dict blocks, null tool name, string input, null timestamp, string message) tested. |
| P43 | Fixed (030cb21, f9e70c5); the compaction fixture harness `benchmarks/compaction_budget.py` (P07, Astra) now measures the compaction sequence; host delivery observed under P19 | R10 (Astra): compaction recovery fetched every text block of the session to emit ≤ 3,500 chars. It now selects the opening user block and the last three blocks with SQL `substr`/`length`; a 61-block fixture returns < 10 KB from SQLite; the `--start` offsets are tested exact. Compaction still has no separate resource benchmark (open under P07). |
| P44 | Fixed on main (030cb21) | R11 (Astra): `--source` searches reported repository-wide coverage. `status()` takes the same source filter as retrieval, for search and brief. |
| P45 | Applied on main (030cb21) and, where relevant, the hotfix and blog | Claims audit C01–C18 (Astra): Python 3.9+ (the 3.10 candidate was a variable named `match`); the community catalog is commit-pinned, not tracking main; one search contract (`search` = this session, `--all` = this repository, `--global` = every repository, same words for durable and `--legacy`) in README and SKILL, with the durable OR/`--require-all`/no-exact-phrase behaviour stated; recency wording corrected (the recency component halves, total weight never below half); global `config codex_*` keys route to `recall_memory.py config`; every skill command quotes the plugin root; PRIVACY states what is on by default (capture, the recall skill, compaction recovery), where data can live besides `~/.claude`, when 0700 applies, and which routes bypass redaction; README table list, test count (584), result counts and capture wording updated; CHANGELOG rebuild and redaction wording corrected; blog names the v2.4.1 baseline, says "161 bounded passes", states Stop/SessionEnd capture, and opens with a note that the July body is historical. |
| P46 | Fixed on main (030cb21) | Env-audit gaps (Astra): the suite now isolates HOME, RECALL_SETTINGS and CLAUDE_ENV_FILE at conftest import and restores every inherited value; `test_codex_integration` restores RECALL_SETTINGS; the entry-point isolation test asserts exit 0 and seeds a sentinel plus a legacy index; Astra's four positive controls (settings, events, Codex import, skill install) are in the suite. Remaining known bypass: none found after R03. |
| P47 | Fixed on main (f9e70c5); verifier completed on 663a6fb after Astra's integration verification (P53) | R3-01 (Astra): a schema-9 file missing `memory_fts` passed page integrity, the table-name check, the version check and the staging count, replaced the target, and the next durable search raised. The migrated staging copy is now checked for every required table, column, index (including the forced `memory_blocks_message`) and a working FTS index (`MATCH` plus FTS `integrity-check`) and clean `foreign_key_check`; anything missing rejects the backup with the target untouched. Repair of derived objects is deliberately not part of restore (a file that lacks them was not produced by `backup`); it lives behind `doctor --repair`, and `doctor` reports `schema_check`. Tests: FTS-less and index-less backups rejected, base-table-less rejected, repair path verified. |
| P48 | Fixed on main (f9e70c5) | R3-02 (Astra): a pre-9 JSON vector holding `1e100` raised `OverflowError` inside the migration and wedged every store open; a JSON string or object was reinterpreted as a vector. `pack_vector` accepts only a non-empty array of real numbers that are finite and within float32 range (booleans, strings, nested arrays rejected); the migration catches every validation error and drops the row. |
| P49 | Fixed on main (f9e70c5) | R3-03 (Astra): the migration converted vectors but left `memory_semantic_config` without `format`/`dimension`, and a build with zero new vectors never set the dimension. The migration now adds the columns, sets `f32le-v1` and the configured model's dimension (NULL for an empty index); `build` records the dimension from existing rows when nothing new is embedded. Dimension policy stated: a model's first valid row fixes it; blob or JSON rows that disagree are dropped and counted. |
| P50 | Fixed on main (f9e70c5) | R3-04 (Astra): `restore` interpolated the backup path into a `file:` URI, so `backup?#copy.db` opened a different file and lost `mode=ro`. The URI is built with `Path.as_uri()` (percent-encodes `?`, `#`, `%`, spaces, quotes) plus the one controlled parameter; tests cover five literal names and assert no sibling file is created. |
| P51 | Fixed on main (f9e70c5) | R3-05 (Astra): SQLite `length`/`substr` stop at an embedded NUL, so the compaction excerpt of such a block lost its tail and mis-cited `--start`. Rows are fetched with an `instr(CAST(text AS BLOB), x'00')` flag; only a flagged block is re-read whole and sliced in Python, so the no-NUL path keeps its bounded query and character offsets match `get`. The function comment now says what is bounded (returned text and Python allocation per selected block; SQLite still counts the source's blocks). |
| P52 | Recorded, not scheduled | Future product decision (Astra, P38-opinion.md): immutable revision ids `(logical_id, content_hash)`, candidate generations promoted atomically at end of file, `get --revision`, retention policy. Trigger: a promise of immutable audit evidence, saved citations that must keep their contents, or an atomic brief while a large source rebuilds. None of those is promised by 2.5.0. |
| P53 | Fixed on main (663a6fb) | Integration verification (Astra): the P47 verifier enumerated only recently added columns, no triggers, and an FTS structural check that does not compare the index with its content table, so backups with `memory_blocks.timestamp` dropped, the `memory_chunks_insert` trigger dropped, or `memory_fts` emptied by `delete-all` were still accepted (all pass page integrity). The expected schema is now read from a throwaway pristine store created by the current code (every table with its columns, every index, every trigger); both FTS indexes must answer a query and pass the external-content integrity check (`rank=1`), which is what `doctor` already ran for the durable index; `doctor` and `restore` share the one verifier. `doctor --repair` also runs the legacy DDL and rebuilds FTS from content. Tests: Astra's four contract cases (adopted) plus five damage kinds and the repair/no-column-invention boundary. |
| P54 | Fixed, including the mixed/indented-wrapper follow-up (f0a75f2, Astra patch committed by Fable during P13 review). Filtered tails stay in the final prose segment; exact offsets and unchanged retention tested; short brief spans remain whole | Brief and compaction recovery treated host-injected user-role wrappers as the user's words: on a real Codex task the brief's first evidence was the `<recommended_plugins>` list (Astra, `integration-6264d27/real-brief.md`); Claude Code sessions have the same shape (`<system-reminder>`, `<command-name>`, `<local-command-stdout>`). Retention is unchanged; `prose_segments()` finds the spans outside known wrappers, metadata-only blocks are skipped as opening ask and evidence, and a mixed record is excerpted from the user's words with exact offsets (`host_metadata_stripped` flag). Compaction re-reads a selected block when its full retained text contains `<`, covering mixed and indented wrappers. Unknown wrappers are treated as prose (listed tags: recommended_plugins, system-reminder, command-name, command-message, command-args, local-command-stdout, local-command-caveat, ide_selection, ide_opened_file, task-notification, user-memory-input, available_plugins, environment_context). |
| P55 | Installed at ~/.agents/skills/recall/SKILL.md; discovery/use verified, including spontaneous selection in another task. Target-repository guidance updated under P63 | `install-codex-skill` wrote to `~/.codex/skills`; current Codex documentation lists `~/.agents/skills` for user skills and Recall was absent from a real task's catalog. Default changed to `~/.agents/skills`, `--skills-dir ~/.codex/skills` kept for older hosts; README and CHANGELOG say so. A successful installer exit is not model-initiated skill use. |


| P56 | Fixed by Astra; 10 synthetic runner checks pass; real 50-case preflight validates five source prefixes and 47 positive labels with zero retrieval runs | Frozen evaluation preparation exposed missing Codex message-key labels, continuing on source hash mismatch, unsupported legacy Codex inputs, and inapplicable legacy exact-ID zeros. Runner now fails on mismatched snapshots/unresolved labels, handles both key formats, marks unsupported arms, aligns legacy repository scope, and requires actual human-review provenance for the broader packet. Historical exact-ID zeros corrected to N/A; broad/right-session measurements unchanged. Human review remains P10. |
| P57 | Fixed by Astra; one regression covers original evidence, excluded summary and a genuinely unknown event | Live P17 source reported three normal Codex `compacted` records as unsupported. Their payload contains a generated summary and replacement/guardian histories. Classify these as excluded by policy, retaining original response items only. No summary is newly searchable. A rebuild now clears old type names as well as counts; the cached pre-reset row previously restored stale type names. Previously stored unsupported counters are historical until explicit rebuild; no live store rebuild is performed. |
| P58 | Implemented and reviewed; independent SDK, real Claude and fresh Codex model/tool checks pass. Explicit scope/read-only contract preserved | Cross-agent retrieval: implement a stdlib local MCP interface exposing scoped search/get/brief/status over the existing store, while retaining the installed skill/CLI. Verify wire compatibility with an independent MCP client and test cross-repository boundaries. Read-only serving must avoid automatic migration and enforce allowlists even for get-by-ID. See gpt-expansion.md for acceptance criteria. This is now part of the active update window; original activation/evaluation gates remain. |
| P59 | Separate product decision; implementation not scheduled | ChatGPT web/export expansion: verify the exact target host and authorized data source; remote tools need explicit authenticated data access, while a user-supplied export needs a separate adapter with branch/edit/attachment semantics. No blanket chat-history access or upload is implied. Recommendation in gpt-expansion.md. |


| P60 | Implemented and verified with an actual foreground watch/append/shutdown subprocess; no daemon installed | Capture independent of Claude: provide an explicit foreground refresh/watch command for authorized Claude/Codex source roots, with incremental imports, fair progress across sources, visible errors/backlog, bounded work per pass and clean shutdown. Do not require Claude SessionStart for a Codex-only workflow; do not silently install a background service. |
| P61 | Client/source matrix reconciled: Claude and Codex live model checks pass; other compatible MCP clients remain untested individually; only Claude/Codex transcript ingestion is supported | Publish a client capability matrix distinguishing retrieval transport, transcript ingestion, refresh and verified model use. Exercise the generic MCP protocol with an independent client; configure a real supported coding host where authorized. Additional client compatibility is not a claim that its transcripts are ingested. |
| P62 | Verified on the shared synthetic fixture: fresh Claude and fresh ephemeral Codex each searched and got both source agents with correct cited decisions and command. Not a human quality score | Demonstrate Claude-to-Codex and Codex-to-Claude evidence recovery through the same MCP endpoint, including accepted/rejected decisions, commands, exact citations, missing answers and scope isolation. Record deterministic transport checks separately from host/model smoke tests and P10 human evaluation. |
| P65 | Integrated from Fable 2772de0 plus Astra upgrade fix: new isMeta exclusion, host summary role, brief/recovery filtering, and role correction on unchanged or edited existing blocks during explicit rebuild; real fixture replay passes | Found on the real P19 compaction receipt: the `SessionStart:compact` context cited the rendered body of the recall skill (a 12,751-char user record flagged `isMeta`, `sourceToolUseID`) as "most recent" context, and the host's compaction summary (`isCompactSummary`) is retained as the user's words. The durable adapter now excludes `isMeta` records by policy (counted under `excluded`), retains compaction summaries under role `host` (searchable, never quoted by brief or compaction recovery), and brief/compaction select only user/assistant roles. Codex records unaffected. Legacy host prompts are tracked separately in P66. Existing durable sources require explicit rebuild to apply the new policy; previously retained metadata is removed when that rebuild reaches EOF. |
| P64 | Integrated from Fable 2772de0; specific query-budget/busy/maintenance messages and tests pass | MCP tool errors mapped every SQLite failure to "needs maintenance", including the 2-second query budget (`interrupted`) and a busy store; the three cases now carry distinct messages. Read of `recall_mcp.py`/`recall_capture.py` against the stated contract otherwise found no defect; probes: unknown-repository block and out-of-scope source rejected, boolean-for-integer rejected, unknown 2026 protocol request falls back to 2025-11-25, a held write lock does not block a WAL read, store bytes unchanged; capture discovery does not follow a symlinked directory out of an authorized root on Python 3.12 and 3.14. |

## Evidence log

Entries are dated and cite the revision they were measured on. "Verified" means exercised on real data or a reproducer, not inferred from reading.

### 2026-09-05, revision c7a17c9 plus uncommitted branch changes (Fable)

**P02 (parked v3 branch, `feature/v3-tiered-architecture` at 47cdcba, 27 files, +3,545 lines):** feature-by-feature disposition, checked against the diff rather than the old plans.
- `scripts/config.py` (tiers lite/standard/enhanced, backend auto-detect, first-run flag, global JSON config): retire. The durable core replaces the tier system; explicit `--db`/`--semantic`/`--model-path` replace config files and consent prompts.
- `scripts/embeddings.py` (MLX → sentence-transformers → ONNX → TF-IDF fallback chain, model download to `~/.claude/context-recall/models`): retire. The branch keeps one offline backend with a supplied local model and no download; the ONNX/TF-IDF paths were the untested capability claims WI-5 already had to walk back.
- `scripts/vector_search.py` (cosine + hybrid score merge) and `scripts/vectorize.py`: superseded by `semantic_memory.py` (fingerprinted model, reciprocal-rank fusion). Nothing to port.
- `db.py` vector CRUD: one reusable idea, `serialize_vector`/`deserialize_vector` (packed float32 blobs). The branch stores vectors as JSON text (~4–8 KB per 384-dim chunk versus 1.5 KB packed); adopt packed storage under P07/P14 if embeddings stay.
- Hook changes (first-run setup message via `systemMessage`, checkpoint embedding in PostCompact/SessionEnd, silent surfacing that embeds the prompt inside `UserPromptSubmit`): retire. They contradict "hooks never load a model" and use `systemMessage`, which does not reach Claude.
- Highlight embedding, semantic highlight matching, `connections` per-connection overrides on that branch: retire pending a measured need (disposition table rows unchanged).
- Tests on that branch (embeddings/config/vector_search/vectorize): not portable; their subjects are gone. Branch left in place as a historical record; no deletion.

**P04 (adapters, real data, isolated stores only):**
- Claude: this session's transcript (21.3 MB) imported in one 60 s budget, `state=complete`, 1,554 blocks (558 assistant text, 778 tool_use, 218 user text), 2,089 passages, longest block 28,619 chars paginated exactly (8,000 + `next_start`), re-import added 0 blocks, no duplicate (source, message, kind, ordinal) tuples. Search "why did the catalog pin stay stale" returned the July exchanges with snippets.
- Codex: newest real rollout (5.0 MB; 338 event_msg, 231 response_item = 66 custom_tool_call, 66 outputs, 63 reasoning, 36 messages) imported `complete`: 100 blocks (25 assistant text, 66 tool_use, 9 user); no block with a role outside user/assistant; hits for "developer"/"analysis"/"function_call_output" were prose mentions inside Codex's own patch commands, not leaks. Session cwd was `~/Documents` (not a repo), so `repo_id` is a directory hash: that is the P18 scoping case.
- Edge cases (new `tests/test_memory_adapters_edges.py`, 13 tests): multi-block messages, same message key updated across records (content replaced, FTS refreshed, seq stable), string/`input_text`/`output_text` content, missing message, null content, non-dict tool input, bare strings in content lists, unsupported record types, tool-result-only user records, corrupt complete lines (skipped and counted), a secret straddling the 1,600-char passage boundary (redacted in block, passages and FTS), a 3 MB single record (consumed, progress guaranteed), passage coverage with exact offsets and overlap, base64 data-URI elision.
- Defects found and fixed: P27 (quadratic redaction) and P29 (block ordinal). Open: interrupted-rebuild semantics (P06), and the `omitted` counter meaning (now P08, fixed).

**P07 (same 21.3 MB real transcript, temp stores, one process each; `measure_capture.py` in the session scratchpad):**

| Measure | v2.4.0 (main b41994f) | durable branch |
|---|---:|---:|
| Full backfill passes (2 MB / 1,000 records each) | 12 | 12 |
| Full backfill wall time | 0.31 s | 1.51 s |
| Slowest single pass | 53 ms | 293 ms |
| Median pass | 24 ms | 153 ms |
| Steady-state pass (one new turn) | 3.9 ms | 5.2 ms |
| Peak RSS | 33.0 MB | 34.8 MB |
| Database size | 1.29 MB | 6.2 MB |
| Rows | 165 exchanges | + 1,556 blocks, 2,091 passages |

Proposed budgets (to enforce/test under P07 next): steady-state hook pass ≤ 25 ms; any single pass ≤ 1 s on a 2 MB read; peak RSS ≤ 100 MB; database ≤ 0.5 × transcript bytes with vectors excluded. Vectors as JSON text would add roughly 8–17 MB for 2,091 passages; packed float32 (P02 note) would add ~3 MB. Not yet measured: concurrent hooks from parallel sessions writing durable tables, and a 100 MB+ corpus.

**P08:** `memory_sources.omitted` lumped every non-block record together (3,990 on the Claude transcript: 783 tool results, 613 attachments, 336 last-prompt, 329 each of mode/permission-mode/ai-title, 327 system; 554 on the Codex rollout). Now classified per record as `excluded_by_policy` (tool results, reasoning, developer/system, thinking/image-only turns, mirrored events), `metadata_records` (no conversation content), `unsupported` (unrecognised shapes, with up to 8 type names kept per source) and `malformed`; `status` documents each meaning and `doctor` emits one next action per source state (missing, changed, partial record, backlog, unsupported, malformed, current) plus a stale-vector action. Tests cover Claude and Codex classification and the doctor actions. Schema bumped 6 → 7 with an idempotent, tested migration.

**P28 / mixed versions:** live store observed at `user_version 5` with `tool_text` present while this session had not reloaded; confirmed by reading `installed_plugins.json` (2.4.0 cache present) and the live DB read-only.

### 2026-09-05, later the same day, revisions e1befaa → 9d7d497 plus uncommitted (Fable)

**P05 (one default recovery path):** decision: durable `search` is the default for both `/recall find` and `/recall search`, scoped to the repository (`--global`/`--all` widens). The skill reads `coverage.source_count` from the result and falls back to the legacy `fetch_exchanges.py` mapping when it is 0 for the scope or when the user asked for legacy-only scoping (`--tag`, `--project NAME`); `search --legacy` forces the old store. `lastN` and `around` stay session-navigation commands over legacy rows. Long answers are finished with `get --start next_start` until null. This keeps every documented legacy contract intact; the only change is which store answers first and that the skill must say which one did. Verified mechanically (`test_full_answer_and_precise_pagination`, skill-manifest test); the "through the normal skill flow" half of the criterion needs a live session (P19).

**P06 (source lifecycle):** rebuild is now generation-based: `--rebuild` bumps the source's generation and rescans from byte 0 *without deleting anything*; every block the rescan touches is stamped; only when the rescan reaches EOF are blocks of older generations deleted, in the same transaction that marks the source complete. An interrupted rebuild leaves state `rebuilding`, both generations searchable, a doctor action saying so, and plain `index` calls resume it (the CLI loop continues through `rebuilding`). Edit detection now checks the first 256 bytes (header) as well as the 256 bytes before the cursor and names which window changed; edits between the two windows are still undetected (documented). Tests: interrupted rebuild keeps old evidence then removes exactly the stale blocks; unchanged-file rebuild keeps ids and removes nothing; same-size header edit detected and named.

**P09 (retention and deletion matrix, verified by tests):**

| Action | Legacy rows | Durable blocks/passages | Vectors | Original transcript |
|---|---|---|---|---|
| `/recall prune --session` (legacy) | deleted | deleted (cascade) | deleted (cascade) | untouched |
| `recall_memory.py prune AGENT:SESSION` | untouched | deleted | deleted | untouched |
| `export AGENT:SESSION` | n/a | complete redacted blocks + provenance (`recall-blocks-v1`) | not exported | untouched |
| `import-export FILE` | n/a | blocks and passages rebuilt; source marked `source_missing` until re-indexed | none | n/a |
| `backup DEST` / `restore SRC --yes` | whole store | whole store | whole store | untouched |

`backup` refuses to overwrite; `restore` requires `--yes`, checks the backup's integrity first, and re-runs schema migrations afterwards (found by the P21 proof: restoring a schema-5 backup into a schema-7 store crashed before this).

**P15 (hook overhead, same 21 MB transcript, steady state, in-process):** Stop with one new turn median 6.1 ms (p95 6.6); the redundant UserPromptSubmit pass that follows, 0.9 ms; a no-op Stop, 0.8 ms; interpreter + imports start-up ≈ 36 ms per hook process. Decision: keep all three capture points. The redundancy costs ~1 ms plus one interpreter start per prompt and is what covers the transcript-lag, blocked-Stop and session-exit cases (tests `test_stop_hook.py`, `test_review_regressions.py`). No hook removed.

**P16 (verbatim compaction recovery):** `SessionStart` (`matcher: compact`) now injects, from the durable store, the head (600 chars) of the session's opening ask and the tails (700 chars each) of the last 3 text blocks, each with `get <block_id> --start N`, capped at 3,500 chars (~900 tokens), never a summary; when the session has no durable blocks it falls back to the legacy preview nudge. Repeated injection is prevented by a fingerprint of the selected content stored in session config; a new block changes the fingerprint. No embeddings are loaded in the hook. Measured context cost: ≤ 3,500 chars by construction (test), typically 1.5–2.5k on real turns.

**P18 (repository identity, tests on real temporary git repos):** worktrees and subdirectories resolve to the main checkout's identity; SSH and HTTPS clones of one remote match and differ from another repo; a changed remote leaves already-indexed sources in their old scope (stable) until an explicit `rescope AGENT:SESSION --cwd DIR`; missing and non-repo directories get stable directory hashes; `--cwd` corrects unsuitable trace metadata; search and brief scoped to one repo never return another repo's blocks.

**P21 (backup and restoration proof):** `~/.claude/context-recall/recall.db.bak-20260905-preupdate` (9.1 MB) taken with the SQLite backup API from the live store; restored into a temporary target: sessions 46, exchanges 4,076, tags 3,348, invocations 101 (identical to live), `integrity_check ok`, migrated 5 → 7 with durable tables present, legacy FTS answering. The live store remains at schema 5; installed plugin cache directories: 2.2.3, 2.3.1, 2.4.0. Installation of the new revision is deferred until P20 produces the integrated revision.

### 2026-09-05, evening (Fable), revisions 9d7d497 → ee64695 plus this commit

**P12 (development split only, temp store, same transcript):** current OR 48.7%; AND-first ladder 48.7% (rejected: no gain, more context); OR + 30-day recency 66.7%; ladder + recency 66.7%. Decision frozen: durable `search` defaults to `--half-life 30` (already the legacy default), `--half-life 0` available. Caveat recorded: this fixture asks about recent development history, which favours recency; P10's multi-session set must include old-answer questions before this is called general. Reserved split evaluated once after freezing (see below).

**P03 (old briefing questions, final answers):** head vs tail → durable blocks keep everything; excerpts (brief, compaction recovery) label offsets and quote tails. Hook selection → keep Stop + UserPromptSubmit + SessionEnd (P15). Verbatim compaction recovery → P16 implemented. Relevance/recency → BM25 × 30-day half-life, measured (P12). Optional dependencies → stdlib default; sentence-transformers strictly opt-in with a supplied local model (PRIVACY updated). Positioning → zero-dependency, Claude-native, now with explicit opt-in Codex import; README "Known limitations" states the windowed edit detection and polling-based Codex capture.

**P17:** `settings.json` (explicit opt-ins only), `config codex_import on|off`, bounded newest-first import at every Claude session start, `install-codex-skill` writing `~/.codex/skills/recall/SKILL.md` (Codex 0.7.0 has a `skills` root and a `notify` hook already occupied by another app, so polling at Claude start was chosen over rewriting the user's `notify`). Real rollout imported earlier (100 blocks). Not yet verified: that Codex actually lists and uses the installed skill (needs a Codex session; user).

**P19 checklist (to run in a fresh Claude session after P22):**
1. `claude` in the recall repo; `/recall doctor` → actions list, plugin version 2.5.0 in `/plugin`.
2. Say: "what did we decide about the catalog pin last time?" → expect the skill to run durable `search`, then `get`, and answer with dates and block ids; confirm in the transcript that `recall_memory.py search` ran (not the legacy script).
3. Ask for a command: "how did we back up the live DB?" → expect `--kind tool_use` or a tool_use hit quoting the backup command.
4. `/recall search rsync marketplace` → durable answers first; `/recall search --legacy rsync` → legacy path; both say which store answered.
5. Trigger `/compact`; after it, check that the next model request carried the `[Context Compacted] Verbatim excerpts…` reminder (visible via `/context` or by asking Claude what it received), and that a second compaction with no new turns injects nothing.
6. Python fallback: `PATH` without `python3` in a shell, run one hook command from `hooks.json` by hand; plugin root with a space (already smoke-tested in v2.4).
7. `/recall status` shows this session's source with `Complete and current` and the skipped-record breakdown.

**P24:** branch `fix/dependency-audit` (410fde5) merged into local blog `main` as d4e5d1e; `npm ci` (208 packages), build (15 HTML pages, RSS 13 items, sitemap 15 URLs), `npm audit` 0/0/0/0/0 on the integrated revision; recall post renders with its addendum, 8 diagrams and the OG card. Origin/main still shows 30 open Dependabot alerts; they can only close after the held push and deploy (P26).

### 2026-09-05, night (Fable): evaluation arms, brief fix, integration dry run

**P11/P14 (same 21 MB snapshot, temp store, top-5 budget, semantic build: 2537 vectors in 54 s):**
```
semantic build: 2537 vectors in 54 s
development  legacy: hit@5=7.7% ctx=569ch p50=0ms p95=1ms | lexical: hit@5=61.5% ctx=5795ch p50=8ms p95=20ms | hybrid: hit@5=59.0% ctx=5260ch p50=94ms p95=147ms
held_out     legacy: hit@5=5.3% ctx=380ch p50=0ms p95=1ms | lexical: hit@5=68.4% ctx=5196ch p50=8ms p95=15ms | hybrid: hit@5=63.2% ctx=4484ch p50=94ms p95=101ms
dev rescued by hybrid: ['What limits each incremental transcript read?', 'Where does the session start hook export fallback varia', 'How are project directories grouped for history search?', 'How should the installed plugin be refreshed?']
dev lost by hybrid: ['How is the last session backlog drained?', 'What change keeps replies across tool calls?', 'How are query matches shown inside search results?', 'How can singular searches find plural words?', 'How can old conversation history be removed?']
dev still missed by both: 11
```
Reading: the legacy v2.4 arm is not "6× worse" in general; it ANDs every query word including stopwords, so natural-language questions mostly return nothing, while it does fine on keyword queries (its documented use). Hybrid (RRF of BM25 and bge-small cosine) helps the development split and hurts the reserved split, at ~12× the per-query latency and a 54 s build; a genuine held-out set (P10) is required before either number is quoted as accuracy. Decision (P14): lexical stays the default, semantic stays opt-in with a supplied local model; if it is ever promoted, vectors should be packed float32 (1,536 bytes) rather than JSON text (~4.5 KB) — both measured above. Funes was not run: no binary is installed here and its indexer wants its own corpus layout; recorded as an incompatibility, no parity or superiority claim is made anywhere.

**P13:** on the real 1,554-block import the first `brief` was 7 of 8 shell commands (tool inputs matched the decision-language regex and dominated recency). Fixed: evidence is prose only (`kind='text'`), tool calls appear as `recent_actions` (5 most recent, one line each). The rerun's evidence is the June 24 opening ask plus recent prose; a human read of a brief against a session they remember is still the completion criterion.

**P20 dry run:** `feat/durable-memory` merge-base equals `main` HEAD (`b41994f`), so integration is a fast-forward with no conflicts; `main` working tree clean (only untracked `memory/`).

**P23:** see the archive build entry below; `gh release view` shows no assets on v2.3.1 or v2.4.0 (P30).

### 2026-09-05, late evening (Fable): integration, install, packaging, claims, hotfix

**P20:** `git merge --ff-only feat/durable-memory` on local `main` (b41994f → ea5c881; 28 files, +2,672/−33), then 01668dc (README claim) and 7202f89 (P31 fix). On 7202f89: 536 passed, `claude plugin validate .` passed, untracked `memory/` preserved. Branch kept equal to `main`.

**P23 marketplace copy:** rebuilt from the tracked files of `main` (all except `benchmarks/`, `.github/`, `.claude/`, `memory/`), in place without a delete-first window; 80 files byte-identical to 7202f89; stale files removed; `marketplace.json` version 2.5.0 and description extended (no em dashes); plugin and marketplace validation passed; 522/536 tests passed inside the copy. Local commit 09ad017; origin/main remains 3b5f295.

**P23 archive:** `git archive` of `main` minus tests/benchmarks/CI/pytest files, with `docs/` included because the README links it: `~/Documents/recall-release-2.5.0/claude-recall-plugin.zip` (200,998 bytes; sha256 `90f469aa…`, full value in `claude-recall-plugin.zip.sha256`; `BUILD.txt` names the commit). Extracted copy validates; with HOME, `RECALL_DB` and `RECALL_SETTINGS` isolated, the four hooks ran on a two-record transcript, the fresh store came up at schema 7 with the credential redacted in the legacy row, and zero files appeared under the isolated HOME. Retrieval from the archive store is checked in the entry below.

**P21 install:** `claude plugin update recall@recall-local` → "updated from 2.4.0 to 2.5.0 … Restart to apply changes"; `installed_plugins.json` installPath now the 2.5.0 cache dir. Because the update reported "already at the latest version" after the 7202f89 fix, the cache dir was refreshed by direct copy and diffed against the marketplace copy (identical). No running session was reloaded; the 2.4.0 cache dir (67 files) is intact for them.

**P31 diagnosis (why the live store is at schema 7 with no durable rows):** the live file's mtime (19:21:36) matched the scratch `t.db` of the first archive smoke test to the second; the test suite was cleared (whole suite and per file under a fake HOME: nothing created; `--help` opens nothing); per-entry-point runs under a fake HOME with `RECALL_DB` set elsewhere showed exactly `session_end.py` and `post_compact.py` creating `~/.claude/context-recall/recall.db`. A 2.5.0 capture pass on a copy of the live store with this session's transcript produced 1 source / 234 blocks with no error, so a capture hook was not the writer. Schema 7 with empty durable tables is the signature of a bare `get_connection()` migration. Live data unchanged (exchanges 4,077 = 4,076 at the 19:04 backup + one later turn from another session; invocations 101).

**Durable capture on real transcripts (P07/P19 evidence):** the 2.5.0 capture hook ran three bounded passes per session on a copy of the live store against the 13 transcripts modified in the last 3 hours (0.7 MB to 327.8 MB): no durable-capture error on any; 0.14–0.38 s per three passes; 7 sources complete, 6 in backlog after three passes (backfill continues on later hooks).

**P25:** README line about capture no longer says "never lost"; it states the Stop/prompt/SessionEnd coverage, the 4,000-char legacy cap and the durable store. Flags documented in README/SKILL/CHANGELOG (`--offset`, `--rebuild`, `--cwd`, `--yes`, `--start`, `--neighbors`, `--model-path`, `--half-life`, `--live-git`, `--since`) all exist on the CLI; `/recall find` is defined in SKILL.md as the alias of `recall_memory.py search` (`--global` → `--all`). Blog: heading "v2.3 to v2.5" and one v2.5 paragraph using the P07 overhead numbers (5.2 vs 3.9 ms, 1.5 vs 0.3 s, 6.2 vs 1.3 MB); no accuracy figure from the probe. Local commit d598b29 on the blog's `main` (three commits ahead of origin, unpushed).

**P27:** `hotfix/2.4.1` from tag v2.4.0: 0560410 (bounded redaction, 400k chars in 0.03 s) and da8b0c8 (RECALL_DB hook fix, isolation test); plugin.json 2.4.1, CHANGELOG [2.4.1], README title; 469 passed; validate passed. Held.

**Shipped-copy note:** the marketplace copy, cache copy and archive were built from 7202f89 and therefore carry the plan as of that commit; this evidence commit is docs-only and will be picked up by the release rebuild (P26).

**Archive retrieval (P23, closing the smoke test):** from the store the archive's hooks created, `recall_memory.py search "archive smoke" --cwd /tmp` returns both blocks (question and answer) with the credential shown as `[REDACTED:credential]`; without `--cwd` the search is scoped to the shell's own repository and finds nothing, which is the documented scoping, not a defect.

**P32:** community catalog pin read from `raw.githubusercontent.com` at 19:5x PDT: `source.sha` 761a38d, `version` null. No remote change made.

## Historical ownership (2026-09-05, superseded by Astra takeover)

Maintainer instruction: push and release is the very last step; the remaining rows are shared with Astra. The handoff text is section 13 of `~/Documents/recall-briefing-for-astra.md`; Astra's deliverables land in `~/Documents/recall-review-2026-09-05/round2/` or on `astra/<topic>` branches off 6c5ef78, and Fable integrates them here with attribution.

| Row | Owner | Completion criterion |
|---|---|---|
| P10 | 50 proposed cases prepared for human review: 28 previously evaluated Claude cases plus 22 Codex candidates, five source sessions, hash-checked prefixes and exact source labels. No retrieval run on the expansion. Correlated cases and reused data mean this is not a new untouched holdout. Human validation and a subsequent declared evaluation remain open (takeover/human-evaluation-review.md) | 28 questions delivered with message/ordinal labels; three-arm results recorded in the evidence log; broader P10 still open |
| Fresh review of `v2.4.0..2a4c21b` | Astra (delivered: R01–R11) | Ten fixed, one declined with documented semantics (P34–P44) |
| P31-class audit (home-directory writes outside the store) | Astra (delivered) | R03 fixed; four positive controls adopted; harness gaps closed (P36, P46) |
| P25 second reading | Astra (delivered: C01–C18) | All eighteen applied (P45) |
| P14 storage format | Astra recommended packed float32; Fable implemented | Done (schema 9) |
| P07 budgets | Fable | Thresholds enforced by a manual benchmark with recorded results |
| P13, P17, P19, P22 | Maintainer | Human read, live Codex check, fresh-session smoke test, reload |
| Round-3 read of `2a4c21b..main` (restore staging, `INDEXED BY` lookup and seq renumbering, vector migration, compaction query); view on P38 | Astra | Findings with reproducers, or an explicit "nothing found" |
| P26, P30, P32, stale PR #1 | Maintainer with Fable, last | Push, tags, release asset, marketplace, blog deploy, catalog PR, PR closed |

### 2026-09-05, night (Fable): P07 budgets, P33 quadratic capture

`benchmarks/capture_budget.py` (new; temp store, HOME and all `RECALL_*` overrides isolated), same code path as the hooks (`index_transcript`: legacy exchanges + durable blocks):

| Transcript | Revision | Passes | Backfill | Pass median / max | Steady pass | Peak RSS | DB (ratio) |
|---|---|---:|---:|---:|---:|---:|---:|
| this session, 23.0 MB | 7202f89 (before) | 13 | 1.44 s | 105 / 285 ms | 5.4 ms | 37.2 MB | 7.11 MB (0.31×) |
| this session, 23.0 MB | after P33 | 13 | 0.76 s | 73 / 110 ms | 4.4 ms | 38.3 MB | 7.26 MB (0.32×) |
| triton-metal, 328.8 MB | 7202f89 (before) | 161 | 372.3 s | 2,056 / 6,923 ms | 19.1 ms | 43.4 MB | 102.6 MB (0.31×) |
| triton-metal, 328.8 MB | after P33 | 161 | 13.9 s | 87 / 156 ms | 4.3 ms | 43.6 MB | 104.4 MB (0.32×) |

Rows on the 328.8 MB store: 1,458 exchanges, 30,879 blocks, 40,570 passages. Concurrency: 4 processes × 3 passes on copies of the 23 MB transcript into one store: 0 lock errors (busy_timeout 5 s, WAL), 248 exchanges / 2,876 blocks / 4 sources, `integrity_check` ok. Profile before the fix (cProfile over passes 3–5 of the first 12 MB): 83% of pass time inside `memory_store.index_file`, dominated by `sqlite3.Connection.execute`; `EXPLAIN QUERY PLAN` showed `SEARCH memory_blocks USING INDEX memory_blocks_source (source_key=?)` for the message lookup; after the fix it uses `memory_blocks_message (source_key=? AND message_key=?)`. Budgets from the P07 proposal stand unchanged; all met.

**Fair pair for the public cost numbers (P25):** same benchmark, same 23.1 MB transcript, run back to back. v2.4.1 code (hotfix worktree): backfill 0.22 s, pass median/max 17/31 ms, steady 3.8 ms, RSS 35.6 MB, DB 1.29 MB. v2.5.0 (2a4c21b): backfill 0.77 s, 80/110 ms, steady 4.8 ms (4.4 ms in the previous run; ±0.5 ms jitter), RSS 37.9 MB, DB 7.29 MB (5.7×). The blog paragraph now quotes these instead of the branch-era 21 MB figures. `capture_budget.py` tolerates stores without durable tables so it can be dropped into an older checkout for baselines. Commits after 2a4c21b touch only `benchmarks/`, `docs/` and the blog; the shipped copies (marketplace 48e2734, cache, archive `781f95f3…`) equal main's runtime files.

### 2026-09-05, night (Fable): integration of Astra's round 2

Inputs: `~/Documents/recall-review-2026-09-05/round2/` (review.md, claims-audit.md, env-audit.md, vectors.md, questions.json + sha256, two test files, receipts) and branch `astra/round2-review` (4344e3a, tests only, base 2a4c21b). Astra's unmodified-base receipt: 536 passed; new tests 11 expected failures / 4 passing controls.

After integration (030cb21): 584 tests pass under random order (536 previous + Astra's 15, adopted as `tests/test_astra_round2.py` and `tests/test_astra_env_audit.py` with attribution, + 33 of Fable's in `tests/test_round2_fixes.py`); Astra's runner (`run_review_tests.py --repo <dev repo>`, fully isolated environment) reports 15 passed for the delivered tests. `claude plugin validate` to be re-run on the shipped copies. Hotfix branch `hotfix/2.4.1` at 2a08646 carries R01 and R03 with their tests (484 passed) and the corrected CHANGELOG wording; it does not carry the durable-store fixes because 2.4.x has no durable store.

Schema is now 9 (indexes for the message lookup and the generation bookkeeping, `scope_pinned`, packed vectors). The live store (schema 7, durable tables empty) migrates on the first 2.5.0 hook run; `test_schema_9_migration_from_a_schema_7_copy_adds_indexes_and_column` covers that shape. Shipped copies must be rebuilt from 030cb21 or later; the pre-round-2 copies (2a4c21b content) are superseded, as Astra noted.

**P10 (frozen set, run once, no tuning; `benchmarks/evaluate_frozen.py`, results in `round2/frozen-results.json`):** fixture sha256 verified; all four frozen prefixes matched their hashes (arrw 0.7 MB, quantum 25.1 MB, optic 18.5 MB, roles 0.3 MB; 3,199 durable blocks, 266 legacy exchanges); semantic build 4835 vectors in 86.4 s. 25 positives, top-5 budget, exact = the labelled message/ordinal block is in the top 5, broad = the anchor text appears in a returned passage.

| Arm | exact hit@5 unscoped / scoped | broad unscoped / scoped | right session | median latency | mean context chars |
|---|---|---|---|---|---|
| legacy | N/A / N/A (corrected under P56) | 0% / 0% | 0% | 0.3 / 0.1 ms | 0 / 0 |
| lexical | 96% / 96% | 88% / 88% | 100% | 8.0 / 5.5 ms | 6,370 / 5,902 |
| hybrid | 76% / 88% | 76% / 88% | 100% | 39.9 / 20.1 ms | 6,312 / 5,911 |

Reading: durable lexical search (the default) returns the exact labelled block for 24 of 25 questions in both scopes; the miss (round2-11, "handoff failure") returns the right session but a different block in every durable arm. Hybrid (bge-small + BM25, reciprocal-rank fusion) is worse than lexical on this set too (19/25 unscoped, 22/25 scoped) at 4–5× the latency, so embeddings stay opt-in (P14 unchanged). Legacy broad/right-session scores are 0 because it ANDs every query word and these are question-shaped queries; a spot check with the anchor text (`500-vector index`) or keywords (`arrwDB extension index`) returns the right exchange, so the broad/right-session numbers describe its query contract. The historical exact-ID zeros were a harness defect: legacy exchanges have no durable block IDs, so that metric is inapplicable (corrected under P56 without rerunning the set). Broad < exact for lexical because three anchors are not literally contained in the labelled block's returned passage window. The three false-premise cases return plausible top-5 blocks from the right session in every durable arm; retrieval cannot reject a premise, that is the host's job with the evidence in hand. Caveats carried from Astra: not human-judged, not fully author-blind, several questions share long answers so scores are correlated, Claude sources only. Broader P10 (more questions, both agents, human review) stays open.

**Shipped copies after round 2:** marketplace copy 994b772 (83-file parity with main 54bea2e; validate and 584 tests pass inside the copy), installed cache 2.5.0 identical to it (2.4.0 dir untouched, no session reloaded), archive rebuilt from 54bea2e (214,331 bytes; sha256 in the .sha256 file; extracted copy validates). Astra's runner on the final revision: 15 passed (delivered tests), 569 passed (baseline). Handoff to Astra: section 14 of the briefing. This entry is docs-only; the copies carry the plan as of 54bea2e.

### 2026-09-06 (Fable): integration of Astra's round 3

Inputs: `~/Documents/recall-review-2026-09-05/round3/` (review.md with R3-01..R3-05, test_astra_round3.py, P38-opinion.md, compaction probe and results, receipts, exact snapshot of 54bea2e). Astra's receipts on the unmodified base: 584 passed; 7 expected failures / 4 passing controls.

After integration (f9e70c5): 623 tests pass under random order (584 + Astra's 11, adopted as `tests/test_astra_round3.py` with attribution, + 28 of Fable's in `tests/test_round3_fixes.py`); Astra's round-3 runner on the dev repo: 11 passed; round-2 runner: 15 passed; `claude plugin validate` passes. No hotfix change: none of R3-01..R3-05 exists in 2.4.x (no durable store, no restore, legacy compaction nudge only).

**P07/P43 compaction evidence (Astra's synthetic warm-query probe, revision 54bea2e; `round3/compaction-results.json`):** 4,096-char text blocks, one fresh process per size, Python allocation measured around the recovery call only.

| Blocks | Retained text | Median warm query | Max of 7 | Python query peak |
|---:|---:|---:|---:|---:|
| 1,000 | 4.1 MB | 0.095 ms | 0.323 ms | 19,050 B |
| 10,000 | 41.0 MB | 1.222 ms | 1.761 ms | 19,053 B |
| 50,000 | 204.8 MB | 7.28 ms | 7.939 ms | 19,053 B |

Reading (Astra's, adopted): the query removed the allocation proportional to the whole session, but SQLite work still scales linearly (`count(*)` visits the source's blocks) and a single huge selected block is a separate case; the "bounded" wording in the code is narrowed accordingly. This is not a SessionStart hook budget: it excludes interpreter start, catch-up indexing, lock waits and cold I/O. The full compaction-hook budget stays open under P07.

### 2026-09-06 (Fable): integration verification by Astra on 6264d27

Inputs: `~/Documents/recall-review-2026-09-05/integration-6264d27/` (HANDOFF.md, test_restore_contract.py + run_tests.py, restore-contract-results.txt: 4 failed / 1 passed on 6264d27; round3-tests.txt: 11 passed; suite.txt: 623 passed; codex-cli-receipt.json; prepare_live_check.py; real-brief.md/json). Astra changed nothing on main, in the live store, caches or publication state.

After integration (663a6fb): 640 tests pass under random order (623 + Astra's 5 contract tests adopted as `tests/test_astra_restore_contract.py` + 12 of Fable's in `tests/test_verification_fixes.py`); Astra's `run_tests.py` against the dev repo: 5 passed; `claude plugin validate` passes.

**P17 evidence (Astra, read-only, 6264d27):** a fixed 9,075,538-byte prefix (sha256 `8d4358cf…`) of a live Codex rollout was indexed into a temporary store in five capped passes to end of file (22 blocks); `search "P38 rebuild semantics"` returned five hits from that task; `get` on the leading hit and every brief excerpt matched its retained block and character offset. This establishes manual capture, search and get from a real Codex task; it does not establish model-initiated skill use or continuous refresh, and the task's skill catalog did not contain Recall (P55).

**P13 evidence (Astra):** the real brief's first evidence block was the host-injected plugin list; the remaining blocks were the task's recent review progress and Fable's report with truthful sampling caveats. Fixed in P54; a human read of a corrected brief is still required.

Shipped copies rebuilt from 663a6fb (below).

### 2026-09-06 (Fable): review of the corrected real brief (`integration-82988a6/real-brief.md`)

Astra regenerated the brief on 82988a6 from a 9,269,593-byte read-only snapshot of the same live Codex task; the suite (640), the restore-contract tests (5) and every excerpt offset were verified by Astra first. What the brief gets right: the first slot is the user's actual request, the plugin list is gone, every excerpt cites a block id and a character offset that `get` reproduces, and the notice states it is a sample.

What the read found, and what was done:
1. `host_metadata_stripped: true` on 6 of 8 blocks that contained no wrapper; the flag was set whenever leading or trailing whitespace was trimmed. Fixed (f0a75f2): set only when a wrapper matched.
2. Two replies of 783 and 717 characters were split into a 500-char head and a contiguous tail, cutting a markdown link path in the middle ("/Users/bledd" + "en/Documents"). Fixed (f0a75f2): a single prose span up to 1,000 chars is one excerpt; longer spans keep a 500-char head and 500-char tail, each inside one prose segment.
3. The opening ask reads "Get caught up on this:" followed by a reference to a pasted attachment; the objective's substance is in `~/.codex/attachments/…/pasted-text.txt`, which the rollout only names. Not fixed: attachment bodies are outside the transcript; recorded as a limitation of Codex capture (the brief cannot show what the user pasted, only that they pasted it).
4. Two of eight slots are user-role blocks that are Fable's reports pasted into the task; the brief labels them "user", which is what the transcript says. Not changed: the role is correct and the text is the user's chosen input; a reader must know that pasted agent output is not the user's own words. Noted for the human read rather than a product change.
5. Ordering is opening ask, then newest first, then signal-ranked; for an 8-slot sample of a 22-block task that surfaced the latest state (verification integrated, restore gap closed, open list) and the round-3 history (P38 accepted, five findings). Usable to reconstruct where the task stands; it does not convey reasons for decisions beyond what the pasted reports contain.

Suite after the follow-up: 645 under random order; Astra's wrapper runner: 3 passed. Shipped copies rebuilt from the plan commit below.


### 2026-09-06 (Astra): takeover, P13 acceptance and local verification

The maintainer transferred implementation/integration ownership to Astra and accepted the corrected real brief as useful, while explicitly requesting that Fable's second read finish first. Fable's review and fixes then landed as f0a75f2/6ee3b4a; both conditions for the reviewed P13 workflow are met. Attachment bodies absent from the rollout and transcript roles on pasted reports remain documented limitations, not claims of complete recovery.

**P54:** Astra's mixed-wrapper patch was applied locally and then committed by Fable during the P13 review. The adopted three tests cover leading whitespace, prose before a wrapper, and multiple wrappers between prose spans. Exact tail offsets and unchanged retained text are asserted. Fable's two brief-formatting regressions are preserved. The final combined suite is rerun by Astra before packaging.

**P07:** benchmarks/compaction_budget.py invokes the actual two SessionStart shell commands from hooks.json in fresh processes, with HOME and every Recall path isolated. Gates were fixed before measurement: total sequence <=2,000 ms, peak hook RSS <=100 MB. Three trials per case. Maximum sequence / peak RSS: ordinary 70.56 ms / 25.33 MB; 10,000 blocks 68.93 ms / 27.08 MB; 8 MiB angle-containing selected block 93.82 ms / 42.11 MB; 8 MiB NUL block 78.58 ms / 42.14 MB; 250 ms writer lock 281.97 ms / 25.41 MB; opt-in Codex import 94.59 ms / 25.30 MB. Every output stayed <=3,500 characters and an unchanged repeat injected nothing. New Codex content appended after the first import became searchable on the next SessionStart. Raw receipt: ~/Documents/recall-review-2026-09-05/takeover/compaction-budget.json.

Prose-heavy fixtures cost 2.59–2.83 database bytes per equivalent JSONL byte and 2.61–2.89 bytes per retained UTF-8 byte (durable blocks/chunks/FTS; no vectors). Thus the earlier tool-heavy transcript <=0.5 ratio cannot be universal. These are warm-OS-cache fixture gates including shell/interpreter startup and a named lock wait, not bounds for unlimited records, cold disks or an arbitrarily long lock. The opt-in fixture has one rollout and a 1-second importer budget. Actual model receipt stays under P19.

**P17:** installed and byte-verified the generated skill at ~/.agents/skills/recall/SKILL.md, pointing at the dev repo CLI. Both old/new locations were absent beforehand. No active Codex task was restarted; fresh desktop-task discovery is still open. The shell CLI reports codex-cli 0.7.0.

**P19:** a fresh isolated Claude CLI process loaded recall@inline, advertised recall:recall and recall:recall-assistant, and successfully ran SessionStart. The model step reported “Not logged in · Please run /login” in the isolated HOME. This does not mean the user's normal account is logged out and is not a passing natural-recall smoke. No credentials were copied or active Claude session reloaded. Receipt: takeover/claude-smoke.stdout.jsonl. An initial harness attempt pointed CLAUDE_CONFIG_DIR at the normal directory, which changed the expected config-file location; that override was removed, not repaired against the user's files.

**Distribution:** scripts/prepare_release.py builds from clean committed tracked files, hashes every marketplace file and archive entry, excludes untracked memory/ and private review material, and never publishes. BUILD.json is the external receipt for the final artifact revision. Cache refresh is a separate explicit operation; the 2.4.0 cache and live store remain untouched.

**P10 preparation:** takeover/human-evaluation-candidates.json and human-evaluation-review.md contain 50 proposed cases (28 existing Claude cases + 22 Codex cases; five sessions). Existing frozen source-prefix hashes verified; new Codex source prefix hashed. Full proposed answer-bearing blocks are supplied for the human reviewer, with historical-report-versus-current-fact cautions and pending review fields. No retrieval run or tuning on the expansion. The reused Claude cohort and correlated Codex reports mean this is not a new untouched holdout and cannot be presented as a human-judged score yet.

**P19 fallback/space-path check:** all six manifest command invocations (startup, prompt, Stop, compact twice, SessionEnd) passed with only `python` on PATH and a plugin directory containing spaces. Recovery included the expected conclusion and the second compact injected nothing. Receipt: takeover/path-fallback-smoke.json.

### 2026-09-06 (Astra): activation follow-through and evaluation preflight

**P17:** Recall appeared in this existing desktop task's model-visible skill catalog. Astra opened the installed SKILL.md and used its search/get commands on an explicitly frozen 11,647,151-byte prefix of this task (sha256 `649ee6c3a9cff7b80318c63da90b645d3a5a8810f34eef45214f31c98e8b2ca3`), indexed in six capped passes into a scratch store. Search `P38 accepted limitation revision` returned the pasted round-3 disposition; get on `2aa76eacc7adadcd2286eda58acc65f9` returned all 2,098 characters plus neighboring references, including Astra's own acceptance. This is actual installed-skill use in the current desktop task, not a separate fresh task or default live-store migration. Receipts: `recall-review-2026-09-05/activation/codex-{snapshot,search,get}.json`.

**P19/P22:** Fresh Claude diagnostic with normal HOME, temporary Recall DB/settings/log, local-only settings and disabled session persistence loaded both Recall skills and ran SessionStart/UserPromptSubmit. The model request retried a missing `/Users/bledden/.config/anthropic/credentials/default.json`; the bounded 35-second retry timed out. This does not contradict the maintainer's working interactive `claude` session in Documents. Maintainer requested a Markdown handoff for Fable to exercise that shell. No active session was interrupted or reloaded. Handoff: `/Users/bledden/Documents/recall-fable-activation-handoff-2026-09-06.md`.

**P10/P56:** The unchanged 50-case packet hash is `210569cca11d76dc5a5e03eadf531f1d21a3f74712c7499bc402092599de606c`. Validation imported hash-checked prefixes from five sources and resolved all 47 positive exact labels; three false-premise cases intentionally have no gold block. Ten synthetic runner tests cover Codex payload IDs and byte offsets, unsupported legacy input, null exact/anchor metrics, hash/label failures and the human-review gate. No retrieval run, model build or tuning was performed on the broader packet. All 50 human decisions remain pending unless a subsequent actual maintainer review receipt says otherwise.

**P57:** Normal Codex compaction summaries were the only unsupported record type in the real task prefix. They remain excluded from evidence; their classification now avoids an erroneous adapter-support warning on newly indexed/rebuilt sources. Existing counters require explicit rebuild rather than an unrequested live-store migration.

**P58/P59:** The maintainer invited a GPT expansion opinion. Recommendation: support cross-agent evidence recovery through the existing Codex skill first; consider a scoped local MCP interface only for a demonstrated host/workflow need. ChatGPT web access and export ingestion are separate opt-in decisions. These rows collect future scope without silently expanding 2.5.0.

**Final local validation for P57:** 646 runtime tests pass in 9.63 s; the existing 330.3 MB transcript budget passes (162 passes, 14.08 s backfill, worst 157.4 ms, steady 4.2 ms, RSS 44.4 MB, store/source ratio 0.32). A scratch rebuild of the real Codex prefix preserves all 244 block IDs/content hashes and clears both the unsupported count and stale type names. Receipts: activation/full-suite.txt, capture-budget.json and codex-compaction-classification.json. No live source/store was changed.

### 2026-09-06: maintainer expands the active cross-agent scope

The maintainer explicitly asked Recall to help across coding agents as Funes does, add this to the total plan, and continue implementation. P58 is promoted from an unscheduled recommendation to active work. P60–P62 cover independent capture, client evidence and bidirectional handoffs. The shared SQLite retention/retrieval core and stdlib runtime remain; ChatGPT web/export ingestion (P59) is separate from coding-agent integration. P10, P17, P19/P22 and the publication hold remain in force.

### 2026-09-06 (Astra): cross-agent implementation and backup proof

**P58/P60:** Added stdlib `recall_mcp.py` and `recall_capture.py`. The reader exposes search/get/brief/status, requires a launch-time repository scope, checks get-by-ID and source filters, uses read-only connections with consistent snapshots, and never captures or migrates. The explicit foreground capture command imports Claude/Codex histories independently of Claude hooks, reports backlog/errors, rotates unfinished sources fairly, observes appends and stops cleanly. No unattended service was installed.

**P61/P62:** 671 runtime tests pass in 10.64 seconds. Official MCP SDK 2.1.1 negotiated protocol 2025-11-25 and passed 15 tool calls (maximum 2.23 ms in this synthetic fixture): both agents, exact Unicode pagination, scope isolation, absent answers, scoped status/brief, unchanged database bytes after reads, and newly captured Codex evidence visible through the existing reader. Both server and capture ran with Python site packages disabled. Real Claude Code 2.1.121 reported the MCP endpoint Connected. These are transport/evidence checks, not authenticated model handoffs or human retrieval-quality scores. Receipts are under `recall-review-2026-09-05/cross-agent/`; `docs/gpt-expansion.md` records the supported client/source matrix and remaining boundaries. Codex project configuration is prepared for Documents; its installation receipt and final distribution hashes live in that directory's STATUS.md. Fresh task/model discovery remains P17, authenticated Claude use remains P19, and actual cross-host model handoffs remain P62.

**P21:** The live store was copied through SQLite's backup API into `cross-agent/live-recall-20260906-005742.db` (31,862,784 bytes, private file mode). The source is already schema 9. Restore into a separate scratch target passed the full schema/FTS/integrity verifier and preserved every original row/column hash: 46 legacy sessions, 4,109 exchanges, 3,678 tags, 102 original invocations, three durable sources and 5,809 blocks. Restore added only its expected invocation receipt. The live database was not migrated or captured into; no active session was reloaded. See `live-backup-restore.json`.

**Outstanding gates:** P13 remains accepted. P10's unchanged 50-case packet still needs actual human label decisions before evaluation. P17 needs fresh Codex MCP discovery/model use, P19/P22 need the working-shell smoke/compaction/activation receipts, and P62 needs actual model handoffs. P59 remains a separate ChatGPT web/export decision; P52 remains the documented future revision design. All publication rows remain last and held. The Fable activation handoff includes a focused MCP test supplement; no general review cycle is requested.

### 2026-09-06 (Fable): wrap-up review on 2c31733, receipts under `recall-review-2026-09-05/fable-wrap-up/`

Tested: dev `main` 2c31733 (671 tests, both manifests valid, archive sha `d7750a18…` = BUILD.json); Claude Code executable 2.1.263 at `~/.nvm/versions/node/v22.17.1/bin/claude` (Astra's earlier probe used 2.1.121 at `/opt/homebrew/bin/claude`); Python 3.14.4.

**P19 (fresh headless session 12de670b-a28d-497d-a556-55619f1b7ff5, dev plugin, synthetic fixture store, no MCP):** tool calls: Skill `recall:recall` → `recall_memory.py search "delivery label decision"` → `get 746a700f7f6d2071649c093e341844be --start 0 --neighbors 1`; final answer named `amber-sparrow`, "avoids the legacy label collision", cited the block. `/compact` on the resumed session: `compact_boundary` (manual, 16,417 → 2,895 tokens, 50.8 s); `SessionStart:compact` hook response carried `additionalContext` beginning "[Context Compacted] Verbatim excerpts from this session's durable index (4 text blocks)" with three `get <id> --start N` citations. Post-compaction question: the model ran search and get again and cited the block. Cost of the three runs: $0.53. Hooks wrote only to the fixture store (2 sources); the live store's session count is unchanged (46).

**P62 Claude side (fresh headless session, only the host-fixture MCP config, no plugin):** ToolSearch → `recall_search` ×2 → `recall_get` ×2; final answer cited `d505222763f9cde3ac4a7abb3e5775a7` (accepted `amber-sparrow`, Claude source) and `ba03076fb854e88c68991a04418a9a37` (rejected `violet`, `cargo test --release`, Codex source) and noted that neither block names the colliding label. Cost $0.23.

**P22:** this working session's rendered skill body resolves `${CLAUDE_PLUGIN_ROOT}` to the marketplace directory and still carries the 2.4.0 skill text; the live store shows this session captured durably (1,754 blocks), so its hooks are 2.5.0 code. One `invocations` row was added by that skill call (104 → 105).

**Wording review:** README, PRIVACY, CHANGELOG, SKILL, `docs/gpt-expansion.md` and the local blog make no claim of automatic capture, "all agents", immutable citations, native 2026 MCP, human evaluation or Funes parity; the capability matrix states what is verified. The blog does not mention the cross-agent work at all. One cosmetic point: `docs/gpt-expansion.md` is titled "Cross-agent Recall".



### 2026-09-06: unprompted skill use in another Codex task; P63 scope/capture gap

**P17 evidence:** the maintainer's screenshot is corroborated by a read-only inspection of the active `triton-msl` task: no Recall mention in its initiating message, installed skill read, then actual CLI search `normalization run_gate seed193193` with exit 0. This proves spontaneous skill selection and invocation during ordinary work. It does not yet prove useful recovery: the command's cwd was Documents and its returned coverage contained only the Recall Codex task; its two hits were unrelated Recall passages matching “normal”. No get call appeared in the inspected active-turn snapshot. Receipt: `recall-review-2026-09-05/restart-check/triton-spontaneous-use.json`.

| ID | Status | Work and completion criterion |
|---|---|---|
| P63 | Skill guidance implemented and installed; explicit target --cwd and returned coverage required when task cwd is a parent directory. CLI scope/missing-coverage reproduction passes; fresh natural model scope-selection receipt recorded in final integration | Make the skill resolve the intended working repository when a desktop task lives in Documents but operates on a nested repository/worktree. Check indexed coverage and use explicit target scope as needed; do not silently broaden access or rescope unrelated history. Verify a normal triton-history question searches the intended repository and either retrieves pertinent original evidence or clearly reports missing capture. The Documents-scoped MCP reader is fixed at launch; distinguish its scope from the CLI's per-command cwd. Decide the smallest appropriate skill/onboarding correction with a focused reproduction, then update the existing final validation/handoff rows. |


### 2026-09-06 (Astra): final Fable integration and fresh Codex verification

Fable's `fable/wrap-up-2026-09-06` branch was fast-forwarded into main through `d83cb2c`, retaining attribution and both commits. The independent triton scope finding already owned P63; Fable's host-record finding is P65, its error wording remains P64, and the separate legacy behavior is P66. No finding was dropped in the numbering reconciliation.

**P65 upgrade correction:** two new regressions failed on Fable's fix: unchanged and edited existing summary blocks retained role `user` after rebuild because both upsert branches failed to update role metadata. `_store_block` now refreshes role/timestamp in both branches. Both regressions pass; replaying Fable's actual smoke transcript against a copy of its existing fixture excludes three metadata records, labels its summary `host`, and emits recovery/brief evidence without either the skill body or host-summary citations. Source/schema are not silently rebuilt in live stores. Privacy/README state the explicit-rebuild requirement and distinguish Claude host summaries from excluded Codex compaction summaries.

**P62 Codex:** bundled Codex CLI 0.153.1 ran a fresh ephemeral session with a read-only sandbox, existing authentication and only the scratch fixture MCP configuration (prior conversation and expected answers not supplied). Task `01a077b6-aae6-7303-ba0a-3a902d9a5eb5`: status, search and two get calls; final answer correctly cites both original blocks, characters 0-101 and 0-102, for amber-sparrow, rejected violet, and cargo test --release. It correctly says the evidence does not identify the specific collision or provide command output. Exit 0, 30.73 seconds. This pairs with Fable's fresh Claude receipt and closes the model handoff criterion on this fixture; P10 remains separate.

**P63:** the installed Codex skill now uses explicit target-repository `--cwd` from task paths, checks returned source coverage, distinguishes a task title/parent shell cwd from repository identity, and explains fixed MCP scope. A synthetic parent-folder reproduction returns the unrelated match under the parent scope, the actual gate under the explicit target, and empty/zero coverage for an uncaptured target; no automatic global broadening or history rescope. Natural model check details are in `final-integration/codex-scope-*.json`.

**Validation:** 680 runtime tests pass in 10.55 seconds. The current 332.3 MB triton transcript capture probe passes: 163 passes, 13.50 s full import, 186.1 ms worst pass, 3.4 ms steady, 41.3 MB RSS and 0.314 store/source ratio. This is a newer transcript than the earlier 330.3 MB run, not a controlled before/after speedup claim. Full compaction fixture gates and independent SDK probe also pass. The 43,618,304-byte pre-capture backup restores into a disposable copy with schema 9 and every original row/column hash preserved, plus the expected restore invocation. No live migration/rebuild or active-session reload was performed.

Receipts: `/Users/bledden/Documents/recall-review-2026-09-05/final-integration/`. Final committed identity and distribution hashes are in release BUILD.json; do not use an earlier measurement's ref as the new artifact identity. P10 human decisions and P22 current-session skill refresh remain open. Fable considers P10 non-blocking for a release with no quality claim, but it remains an obligation of this total update-window plan; it is not marked complete or human-reviewed. Publication remains held.

| ID | Status | Work and completion criterion |
|---|---|---|
| P66 | Known legacy limitation; implementation not scheduled in this candidate | The legacy exchange builder retains capped Claude host-rendered prompts (including skill bodies and synthetic continuation text). Durable host-record behavior is fixed under P65. Keep the legacy distinction public and decide a future compatibility change separately: skipping metadata changes turn grouping and requires explicit exchange/capture regressions. No claim that legacy exchanges exclude all host instructions. |


**P63 natural model verification:** after installing the updated skill, fresh ephemeral Codex task `01a077bb-842d-7f73-a4b4-69e7c7cc1b67` first selected the correct `--cwd` but the test's read-only shell prevented the CLI's normal SQLite bookkeeping; it recovered via a static read-only workaround. That trial is preserved, not reported as a clean CLI pass. A repeat with only the synthetic fixture directory writable again chose Recall without the prompt naming it, read the skill, passed the actual target path to search, checked the returned source, got the original block, and cited the correct gate procedure. Both ordinary CLI calls exited 0; no expected answer was in the prompt. This closes the scoped-use fixture criterion. Exact successful task ID, commands, prompt and answer are in `final-integration/codex-scope-model-check.json`; no triton production task/history was modified.


### 2026-09-06 (Astra): Claude Mac chat and Cowork expansion

The maintainer explicitly requested any necessary changes for Claude Mac chat and
Cowork. This adds P67–P70 to the active total plan; it does not replace P10, P22 or
the publication hold. While other sessions finish, the maintainer is waiting to
quit/restart the app. No session was interrupted and no app was restarted.

| ID | Status | Work and completion criterion |
|---|---|---|
| P67 | Implemented and app-tested; distinct plugin/Desktop connector names added after route ambiguity was observed | Add a scoped app reader preparer: explicit existing DB/repository, absolute Python 3.9+/FTS5 preflight, Desktop chat config snippet and local Cowork plugin ZIP with root manifest/MCP configuration and retrieval-only skill. No history, credentials or Code capture hooks bundled. Preserve the Code path and route available Recall MCP tools before shell commands. Correct unsupported Cowork equivalence and ZIP-only public claims. |
| P68 | Fixture gates pass in Desktop Chat and Mac-connected Cowork (Astra receipts verified by Fable). Everyday readers for both scopes are prepared at `~/.claude/context-recall/app-readers/` against the live store, both answer over stdio, and the live store now carries each scope's history (evidence log 2026-09-06 activation). Activation itself awaits the maintainer: merge `desktop-config-both.json` and restart Desktop; upload the two reader ZIPs in Cowork | Actual fresh contexts verified natural skill/tool discovery, both Claude/Codex citations, same-session new evidence and foreign-ID refusal. The app is running with the synthetic-only Desktop entry and approved test plugin; distinct connector names prove the plugin route. Receipts below and in claude-app/live-check. Prepared real-project readers remain uninstalled pending the maintainer’s selected scope. |
| P69 | Two real local Cowork prefixes imported and exact first pages verified; automatic capture and Desktop chat ingestion remain open | Existing local Cowork uses Claude-shaped project JSONL in the app support directory: two selected prefixes, 7,535 and 27,690 bytes, index to EOF with no malformed/unsupported records, seven total retained blocks and seven exact retrieval checks. Scratch store only; originals and live store untouched. Verify source identity, host-vs-VM project mapping and new-task capture before claiming ongoing Cowork support. Desktop chat has no implemented export adapter/capture path; establish an explicit supported source format before implementing or declaring that capability. Do not scan unrelated account/browser databases. |
| P70 | Connected-Mac bridge verified; standalone access without the Mac remains an open conditional design | Actual Cowork remote-devices tools reached both the host reader and the distinct plugin reader. Do not infer inability to access host tools from the cloud/sandbox label; the process runs on the connected Mac. Without that device bridge, an explicit scoped export or separately approved authenticated connector design would be needed. No public listener, whole-store upload or automatic account-history access is enabled. |

**Validation:** 687 runtime tests pass in 11.44 seconds, including seven new app
package cases. Both generated launches run in an unrelated working directory with
a minimal PATH and a deliberately wrong RECALL_DB, using explicit arguments;
search/get/brief/status succeed across two agents, another repository's known
block is rejected, and source DB bytes stay unchanged. The ZIP reader is tested
from a separate extracted installation with spaces and ?/# path characters.
Neither protocol emulation nor manifest validation is reported as live app proof.

**Research:** docs/claude-app.md links current official plugin, Desktop config,
Cowork architecture and connector-routing documentation. The generic Code plugin
cannot promise access to the host DB from a Cowork VM. App readers are intentionally
retrieval-only; preparing the package does not capture the current conversation.
Receipts and the private synthetic validation package are under
`/Users/bledden/Documents/recall-review-2026-09-05/claude-app/`.


### 2026-09-06 (Astra): actual Claude Desktop Chat receipt

After the maintainer relaunched and authorized continuation, computer use worked.
Claude Desktop 1.46388.4 initially still showed no local MCP servers. An explicit
Claude Desktop quit/relaunch loaded recall-validation; the log records initialize,
notifications/initialized and tools/list success. The terminal Claude sessions were
not reloaded.

**P68 Chat:** a fresh Sonnet 5 Medium chat received the natural test question with
no Recall name and no expected answer. It discovered the reader, called search and
two get operations, quoted both original Claude/Codex blocks and cited their IDs.
Connection, discovery and retrieval pass. The first answer omitted character
offsets and called compatible records conflicting; one explanatory sentence also
misstated accepted amber-sparrow as rejected, although its quotations and concluding
facts were correct. These are retained answer-quality caveats, not a clean human
quality score or a reason to silently alter this fixture.

A second request in the same chat exercised status, brief and get after external
capture appended a new synthetic source. It returned copper-otter-482 and the
recorded pytest command from block ad658ffdece276c4ef0d90538f635bf4, with the verified
0–120 character range. Status reported three scoped sources. A get for the known
out-of-scope block 8c52de0669731e1a3c4254636c796627 returned exactly “Unknown block in
this repository”. Freshness and isolation pass in the actual app. Only the
synthetic fixture was appended, with a pre-change SQLite backup; the live Recall
store was untouched. This does not establish capture of this Chat conversation.

Chat: https://claude.ai/chat/855b3fc9-944b-4530-ac60-ce7428060187 . Receipts:
`recall-review-2026-09-05/claude-app/live-check/chat-initial.json`,
`chat-follow-up.json`, `chat-mcp.log`, `fixture-append.json`.
Cowork installation/model use remains the other P68 gate; P69/P70, P10/P22 and the
publication hold retain their separate criteria.


### 2026-09-06 (Astra): Cowork bridge and distinct plugin route verified

**P68:** the maintainer explicitly approved installation of the synthetic test
plugin. Cowork task `cse_01PBS6t34tQ99TuV5FxsdaZ3` selected
`recall-validation:recall` without the initiating question naming Recall and used
status/search/two gets with correct source IDs and 0–101 / 0–102 character ranges.
A same-task follow-up retrieved the externally appended marigold-ibis-613 block
at 0–116 and received “Unknown block in this repository” for the known foreign
block. The model correctly declined to prove from its limited view whether that
foreign ID exists; the evaluator's fixture setup establishes that fact.

**P67/P70 correction from actual behavior:** the selected tools were
`mcp__remote-devices__recall-validation__...`. The original Desktop entry and
plugin connector shared a name, so that receipt alone did not isolate the plugin
route. The preparer now gives the plugin connector a `-plugin` suffix and the
skill prefers that named reader. The test plugin was updated with identical reader
code and identical fixture scope. Fresh Cowork task
`cse_01XCevZg6gZg5qwcJ5F9ToUB` selected the skill and used
`mcp__remote-devices__plugin_recall-validation_recall-validation-plugin__...`
for status/search/get, with both correct citations. A later same-task query read
the newly captured quartz-lark-907 block at 0–66 and refused the foreign block;
brief was exercised too. This proves the distinct plugin route, freshness and
boundary behavior in this app. App logs separately show both local servers
negotiating MCP 2025-11-25 and advertising four tools.

The current Cowork UI identifies its device as Claude Desktop (macOS). The exact
location of the model/agent loop was not inferred from its `cse_` URL. Documentation
and skill wording now distinguish a local server process from a remote-devices
bridge reaching it; categorical claims that Cowork cannot access the host reader
were too broad for observed app 1.46388.4. No public listener or cloud-hosted server
was added. Standalone off-device access without this Mac is still unimplemented;
that conditional path remains P70, not a blocker to the verified Mac workflow.

**Everyday activation:** two packages are prepared locally for the already-indexed
Recall and triton-msl repositories, one source each. Neither is installed or
connected yet. The maintainer's pending choice selects Recall, triton-msl or two
separate readers. Existing app entries remain synthetic-only until that choice.
No unrequested rescope, bulk import, daemon, live-store migration or Chat capture.

| ID | Status | Work and completion criterion |
|---|---|---|
| P71 | Observed model-answer caveats recorded; feed into human evaluation, not declared fixed by a subsequent trial | Initial Chat and Cowork answers called compatible records conflicting; Chat also had a mistaken rejection phrase and omitted offsets. A later distinct-plugin trial correctly called the records consistent and cited exact ranges. Preserve all trials, do not claim connector naming caused a quality fix, and keep P10's broader human labels/quality work separate from successful transport and retrieval. No retrieval algorithm tuning on this fixture. |
| P72 | Fable branch integrated through 380b4ac; further capture/agent regressions corrected by Astra under P73; repaired live store verified in scratch copy | Found during the everyday-scope history import: `index DIR` swept per-session subdirectories, whose subagent transcripts carry the parent's `sessionId`, so 49 (recall) and 991 (triton-msl) files were matched to the parent source, read against its cursor, and marked it `source_changed` with the subagent file's size; a workflow `journal.jsonl` was registered as source `claude:journal`. Fix: the sweep indexes only top-level main transcripts by default; `--recursive` opts in, keys subagent files as `claude:<sid>/<stem>`, and skips JSONL whose first records are not conversation messages; `index_file` refuses a file that claims an already-registered source whose registered file still exists (`path_conflict`) instead of reinterpreting it. Four tests. Live store: the three mis-marked sources were re-indexed at their own paths (complete again) and `claude:journal` pruned. |

Receipts: `claude-app/live-check/cowork-initial.json`, `cowork-plugin-route.json`,
`app-reader-connection-events.log` and exact synthetic append receipts. The latest
full test output is `claude-app/live-check/full-suite.txt`. P13 remains accepted;
P10/P22/P69 and other recorded deferrals remain; publication is held and last.

### 2026-09-06 (Fable): Claude app validation review and everyday-scope activation

Verified against Astra's receipts (`claude-app/live-check/`): Desktop Chat and Mac-connected Cowork trials on app 1.46388.4 (Sonnet 5 Medium) discovered the tools without the prompt naming Recall, cited `d505222763f9cde3ac4a7abb3e5775a7` [0,101] and `ba03076fb854e88c68991a04418a9a37` [0,102], refused the foreign block, and saw evidence appended after the session started (`ad658ffdece276c4ef0d90538f635bf4`, 120 chars; Cowork markers through both the `recall-validation` and the `-plugin` routes, namespace `mcp__remote-devices__plugin_recall-validation_recall-validation-plugin__`). Local state re-verified: main 380f67d, 687 tests, both manifests valid, archive `3739c81a…` = BUILD.json, installed cache = marketplace copy ad77352, Desktop config holds only the synthetic `recall-validation` entry, app version 1.46388.4 from Info.plist. Answer-quality caveats (P71) stand as recorded.

Activation work by Fable (live store, after a fresh backup): explicit `--rebuild` of the three live Claude sources applied P65 (31 retained skill bodies removed, 47 compaction summaries now role `host`; 43700fd9: 30 stale, a4e70c78: 36, 70db28b4: 75 stale removed and the triton transcript indexed to end of file, 22,531 blocks); history import of `-Users-bledden-Documents-claude-recall-plugin` (22 main transcripts, 37 MB) and `-Users-bledden-Documents-triton-metal` (one 546 MB transcript). Store after: 34,277 blocks, 46,817 passages, 25 sources all complete (22 in the recall scope, 1 triton-msl, 1 agent-gauntlet, 1 Codex), 128 MB. The brief for the recall scope no longer surfaces a skill body. Both everyday readers, launched exactly as Desktop would (`python3.14 -S … --repo-id …`), report their scope and answer searches (recall: 22 sources, 3,424 passages; triton-msl: 1 source, 40,328 passages). Readers regenerated into `~/.claude/context-recall/app-readers/{recall-project,recall-triton-msl}` (stable home; ZIP sha256 `c875344b…` and `2b6275b1…`) with a merged `desktop-config-both.json`. Nothing installed, no app restarted, no session reloaded, nothing pushed.

Recommendation on the pending choice: two separate readers, one per repository (scope isolation is per reader; the app lists both and the model selects by context; cost is two idle stdlib processes). Remaining maintainer steps: merge `desktop-config-both.json` into `claude_desktop_config.json` (backup first) and restart Claude Desktop when convenient; upload both ZIPs in Cowork > Customize > Plugins and enable their MCP component; then run the acceptance checks in `docs/claude-app.md` against a real question in each scope.



### Astra: P72 integration and Codex/independent-capture follow-through

Fable's two commits through 380b4ac were fast-forwarded into main with attribution.
The original four tests pass. Three additional reproductions fail on that branch:
Codex directory imports discover zero files both at top level and under the native
year/month/day tree, because the content filter defaults to Claude and the new
flat sweep loses the Codex layout; the independent capture worker still indexes
Claude subagents and a workflow journal by default. The shared directory iterator
now preserves agent-specific layouts, filters with the selected agent, and is
used by both CLI index and the independent worker. The worker has an explicit
--recursive option for Claude, and a fourth new test proves separate child keys,
journal skipping and unchanged-file skipping on a recursive capture.

| ID | Status | Work and completion criterion |
|---|---|---|
| P73 | Fixed and tested during P72 integration | Preserve Codex top-level and dated-layout imports; apply the Claude main-transcript/default-recursion policy to independent capture as well as index DIR. Use the selected adapter for transcript detection and keep subagent keys distinct. Three pre-fix failures are retained; all eight directory-sweep cases and existing capture tests pass. Documentation states layout rules and the 30-record discovery probe limit; explicit files remain available for long metadata preambles. |

695 tests pass in 11.06 s. A fresh read-only SQLite backup of the live store was
verified in a scratch copy: 25 sources, all stored states complete, 22 Recall
sources, one triton-msl source, 34,291 retained blocks (grown since Fable's 34,277
receipt), no journal source, clean schema/FTS and integrity. No live migration,
rebuild, prune or rescope was performed by Astra. The pending everyday-reader scope
choice still controls activation; the pasted recommendation is not recorded as a
maintainer selection. Both staged readers are refreshed after integration. No
app restart or publication is performed for this integration.

Receipts: `/Users/bledden/Documents/recall-review-2026-09-05/p72-integration/`.
P10, P22, actual app capture P69, optional standalone access P70, answer caveats P71
and all held publication steps retain their recorded status.

### Astra: authorized everyday activation, diagnostics and token analysis

The maintainer explicitly selected both readers and asked to address remaining
work, add optional troubleshooting telemetry, measure token usage, and refresh the
Funes comparison. Both Desktop entries have been merged into the existing config
after an exact-content check and private backup. A running Code task prevents an
app quit/restart at this stage; a view reload is not counted as a process restart.
The Recall-project Cowork reader is installed and its local MCP component is
enabled. The second reader and final package refresh/acceptance receipts are
tracked in `everyday-activation/`; installation is not called complete until the
UI confirms it. Human evaluation remains with the maintainer throughout the day.

| ID | Status | Work and completion criterion |
|---|---|---|
| P74 | Implemented; privacy, rotation, concurrency, unavailable-log and packaged-reader tests pass | Explicit `--diagnostics PATH` for MCP and independent capture; off by default, no env fallback, no uploads, allowlisted numeric/category events, no queries/text/identifiers/errors. Two 1 MiB segments and a lock file, private destinations, nonblocking lock and best-effort failure. Documentation distinguishes local metrics from provider billing/quality and from uninstrumented hooks/legacy commands. A local 1,000-event probe measured 45.9 microseconds median enabled versus 0.17 microseconds disabled; not a universal disk-latency bound. |
| P75 | Measured and optimized; 708 full-suite tests pass; fresh synthetic Claude MCP run succeeds | On the frozen two-scope snapshot, repeated full coverage contributed about 5,600 avoidable o200k_base tokens per Recall-project search. Compact coverage reduces median five-hit search + 2,000-character get from 9,997 to 4,391 tokens (56%); triton-msl from 2,502.5 to 2,107 (16%). Full status remains on demand. Tokenizer proxies are not Claude billing, and these operational probes are not human-labelled retrieval evaluation. Fresh Claude search/search/get/get answered the fixture correctly with exact citations: 918 output tokens, 8,661 cache-created input, 12,469 cache-read input, 6 uncached main-model input; total reported list-basis cost $0.1168145 including a small auxiliary model call. No causal savings comparison or dollar promise. |
| P76 | Supported option documented; parked pending an observed workflow need | Current official OpenAI hook docs and installed Codex 0.153.1 expose lifecycle hooks with transcript_path. Existing foreground capture remains functional. The maintainer explicitly rejects a Funes-parity roadmap: implement lifecycle capture only if evaluation shows the current refresh workflow causes repeated missing-history failures. Any later design must preserve exact-session scope, parent/subagent identity, host trust review and bounded work. No hooks are installed or silently trusted. |

P69's remaining limitation is not resolved by installing a reader: current app
retrieval has no proven automatic source mapping/capture for new Chat/Cowork
conversations. Existing local Cowork prefixes remain a separate scratch-import
receipt. P52/P59/P66/P70 retain their future/conditional dispositions. P10 has not
been run or marked accepted by Astra. P22 requires refreshing pre-install working
terminal sessions when convenient. All publication remains held and last.

**Maintainer direction:** Recall should keep its own lane. [Product direction](product-direction.md)
sets lightweight local evidence recovery, inspectable citations, workflow continuity,
deliberate scope and practical session organization as the decision criteria.
Competitor parity alone does not promote any deferred row into implementation.

### P77: Codex retrieval permission failure (maintainer report)

The triton-msl task's exact query failed while opening the live database. CLI
retrieval previously opened a writer (WAL setup/migrations) and wrote invocation
counters. Search/get/brief/status/sources/export/backup now open an existing
current-schema store with normal SQLite mode=ro and query_only; they neither
migrate nor record counters. Missing stores are not created. Normal WAL reads
preserve visibility of concurrent commits. SQLite may still need accessible WAL
sidecars: the host sandbox can deny these even for a logical read. The CLI now
labels that access failure and the generated Codex skill explains a same-scope
read retry through the host approval mechanism or an available matching MCP
reader. No permission changes, immutable snapshot workaround or automatic rebuild.
The exact reported query succeeds through approved host access and returns the
intended triton-msl scope. This closes the writer defect, not a promise that every
host sandbox permits direct SQLite reads. Eleven regression cases cover all seven
read commands, missing/old stores, concurrent committed WAL and access diagnostics.
The full suite passes: 719 tests in 13.84 seconds. Skill frontmatter quoting was
corrected and the generated/installed skill passes the skill validator.

**Embedding clarification (P14):** optional semantic build/search is implemented.
The explicitly named live store was checked September 6: 25 sources, no semantic
configuration and zero vectors. Earlier semantic builds were evaluation fixtures;
current MCP readers expose lexical search. Lightweight means measured resource
cost relative to recovery benefit, not an exclusion of embedding models. Keep the
optional backend available and reassess cold/warm latency, peak memory, storage,
refresh cost, token use and human-reviewed retrieval quality before changing the
default or extending the reader contract. P10 human labels remain pending.

### P68/P71: both everyday Cowork readers activated

Both tested reader ZIPs from runtime c3f67aa are uploaded and enabled. A new
Mac-connected Cowork task (`cse_01LvRcUxy2KPeadbspK4aJYC`) discovered both
integrations, used status/search/get, recovered P38's accepted rebuild limitation
and triton's 174 v2 hold after 211, and distinguished historical decisions from
current state while reporting source backlogs. Six of seven cited-window anchor
checks passed. One asserted documentation sentence was absent from its range;
the record was a tool invocation with replacement text, so calling it shipped
was also unsupported. This extends P71's model-answer caveat; it is not a clean
exact-quotation pass or a human quality score. A correction follow-up is recorded
in the receipt. Both literal Desktop launch commands pass own/foreign-scope probes.
The Desktop config contains both readers with optional local diagnostics, but a
process restart/fresh Chat real-project acceptance remains pending while other
Code task activity is observed. No working task was interrupted. Full handoff and
measurements: `~/Documents/recall-review-2026-09-05/everyday-activation/REVIEW-AND-HANDOFF.md`.

**P68 activation completion, September 6:** after the Code indicator became idle
and the Cowork validation finished, Astra quit and relaunched Claude. Fresh
Desktop Chat `4d5a44b7-1e6a-45f7-8104-6e90f2a059f6` used both configured readers
with per-call approval and recovered both real decisions with supported cited
ranges. It answered from search passages; no separate get call is claimed for
that Chat run. The three cited windows were independently checked. Both everyday
Chat and Mac-connected Cowork readers are now functionally active. P71's Cowork
quotation/provenance caveat, P10 human evaluation, P22 older terminal text refresh,
P69 app capture limits and all held publication steps remain as recorded. The
final receipt supersedes the earlier restart-pending note above.

### P78: Fable's P74/P75/P77 review integrated

Fable's `e6ac4a0` patch adds compact CLI search/brief coverage shared with MCP,
`--full-coverage` for per-source detail, and a structured `store_missing` error.
Astra incorporated the branch's already-present worktree correction (`el` →
`elif`) without changing that worktree. Fable's six live reads preserved the
invocation counter (119 → 119); schema-8, missing-store, WAL snapshot and
sandbox-sidecar probes confirmed P77's contract. His logger probes confirmed
P74's allowlist, permissions, refusal, rotation and nonblocking-lock behavior.

Astra additionally made CLI search/brief semantic counts match the selected
repository/source via a shared counter, rather than carrying whole-store counts
under a scoped result. A regression includes a foreign repository and an exact
source filter in compact/full search and brief. The installed/generated Codex
skill no longer assumes coverage.sources is present. README and both relevant
skills state that doctor needs write access even without --repair: connection
setup may migrate, integrity checks use FTS insert commands, and it records an
invocation. Status/sources remain the read-only diagnostic path.

An additional error-boundary case ensures a missing optional search dependency
is not misreported as a missing store; store_missing is reserved for opening the
store itself. 724 tests pass on the final integration. Six fixed operational queries against the frozen
P72 scratch store (pure relevance to avoid timing drift) preserve identical hits
and reduce median CLI search output from 9411.5 to 3284.5 o200k_base tokens. These
are output-size proxies, not billing or human quality measures. No P10 packet was
read or used. Measurements and distribution receipts are under
`~/Documents/recall-review-2026-09-05/p78-integration/`.

P71/P10 remain open as recorded. Optional semantic retrieval and its current
live-store activation status are unchanged. Publication stays held and last.

### September 7: P94 usage repairs and Claude log review

See [retrieval troubleshooting](retrieval-troubleshooting.md) and local
`usage-repairs/REVIEW.md`. A SQLite backup precedes the seven explicitly selected
source refreshes; no transcript edits or unrelated history sweep. 765 tests pass.
No schema change. The original arrwDB session now answers the previously uncovered
question, and the triton Codex session is pinned to its actual Git scope.

P76 is reopened by this evidence: manual import cured the immediate gap, but the
Codex capture path was not running and did not register the task. Integrate a
user-enabled continuing capture workflow with P88–P93's trusted session routing
and suppression policy; verify new sessions and appends without Claude dependency.
The current explicit foreground watcher is supported; no service or host hook was
silently installed. Do not call this automatic freshness solved by one backfill.

P94 follow-through: measure bounded reads in fresh model trials after privacy/capture
integration and final reader replacement. Existing synthetic/parser tests and the
source-grounded before/after queries certify their narrower behaviors. Publication
is still held, and P10 remains accepted without a blanket repeat.

P94 installation follow-through also found and fixed an unnecessary writer open in
`install-codex-skill`: installing the skill now needs only its destination access,
not permission to open, initialize or migrate SQLite. A no-store-access regression
passes. Claude manifests and the generated Codex skill use their respective validators.

Final Claude shape audit: 10,815 host bookkeeping records (worktree state,
relocation, bridge state, file history, frame links, cost state and latch state)
plus four model-fallback notices were counted as unsupported in the triton source.
They carry no conversation prose. The adapter now classifies these observed
shapes as metadata, preserves mixed prose and still reports unknown kinds.
