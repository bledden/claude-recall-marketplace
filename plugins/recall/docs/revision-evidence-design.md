# Revision evidence: current contract and future design (P38/P52)

The 2.5 contract is a mutable, local recovery index. A block ID identifies a
logical source block; an explicit rebuild can replace its text before the source
reaches EOF. Unvisited old blocks remain until EOF. Readers can therefore observe
a mixture during rebuild. Search/get/brief now expose content hashes and get can
verify the prior hash and an exact quote in a returned window. A failed check
requires a fresh read and corrected citation. This detects a changed citation;
it does not retain its old contents or provide an immutable audit trail.

## If immutable saved citations become a requirement

Use `(logical_block_id, content_hash)` as a revision identity, with immutable
redacted text and its own passage rows. Add source generations and an active
generation pointer. Capture builds a candidate generation; only a complete,
validated EOF checkpoint promotes it in one transaction. Readers pin the active
generation for each operation. Incremental appends can publish complete passes,
while a source replacement must keep its old generation readable until promotion.

`get --revision HASH` must return that exact retained revision or an explicit
expired/not-retained result. A bare ID keeps the current-read behavior. Search
must not mix generations within one response. Source byte cursors, exclusions,
FTS content and vector fingerprints belong to the candidate generation and are
promoted together. Compaction uses a pinned generation and cites revisions.

Before implementing, choose a retention limit for superseded revisions, a way to
pin saved citations, and garbage-collection behavior. Prune must remove all source
revisions; backups must include generation pointers and pinned revisions. Export
must say whether it includes current text only or revision history. Never imply
that SQLite deletion removes originals, backups or SSD remnants.

Migration would require a new schema version, assigning existing blocks to one
active generation. Acceptance tests must interrupt every generation transition,
cover concurrent readers/writers, edited/deleted/duplicate message IDs, old-revision
pagination, failed EOF/partial JSONL, garbage collection, restore, and both FTS
indexes. Measure transient disk growth, migration time and capture budgets on
large transcripts before offering this contract.

## Disposition for this update

Design recorded; implementation intentionally excluded from 2.5. The product
promises inspectable recovery, not immutable auditing. The present defect was a
wrong quotation and an unsupported claim about a requested patch; exact checking
and provenance address those without pretending to preserve old revisions. Reopen
when a concrete saved-citation or atomic-rebuild requirement needs the stronger
contract. This is an explicit product boundary, not an unfinished 2.5 patch.
