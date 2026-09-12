# Agent Control source-history separation — 2026-09-12

## Purpose

The virgin Moto installation downloaded approximately 263.26 MiB twice and could not complete a normal clone. Object analysis found 399,581,425 uncompressed bytes across 4,448 historical blobs, including 322,819,534 bytes of heavyweight qualification evidence. Removing files only from the current tree would not fix an ordinary clone because the historical blobs would remain reachable.

The remedy preserves the complete old repository and candidate evidence externally, then rewrites the public source branches and tags to remove historical qualification working trees and evidence media. Product source, documentation, tests, schemas, lightweight fixtures and release operator-guide PDFs remain in the source history.

## Preservation

- Complete pre-separation public history: `agent-control-pre-separation.bundle`
- Source-only remediation layered on that history: `agent-control-remediation-pre-rewrite.bundle`
- Candidate heavyweight evidence: `agent-control-candidate-146ba9d-heavy-evidence.tar.zst`
- Per-file provenance: `candidate-146ba9d-evidence.json` and `candidate-146ba9d-files.tsv`
- Commit and ref lineage: `history-rewrite-commit-map-20260912.tsv` and `history-rewrite-ref-map-20260912.tsv`
- Cryptographic identities: `SHA256SUMS`

Nothing in this operation changes a historical qualification verdict.

## Rewrite policy

The rewrite uses official `git-filter-repo` 2.47.0 in two deterministic passes:

1. remove tracked blobs larger than 1 MiB;
2. remove all historical `qualification/` and `docs/images/` paths plus media/archive files under `docs/evidence/`.

The source-distribution test applies the same boundary to all future changes. Product PDFs under `assets/releases/` and the lightweight harness mutation fixtures remain tracked.

## Validated result

- Pre-rewrite source-remediation commit: `c50fcfae87404c0e83609c63964ae2922bd94c66`
- Rewritten source-remediation commit: `0cd4d5fb02b3d5391e4a2ff677f7e0c895f91708`
- Candidate tree before and after: `77308f24ae786f531b845e9325c90d727707b102`
- Rewritten Git pack: 5.69 MiB
- Fresh checkout including `.git`: 19,855,453 bytes before dependencies
- Forbidden historical evidence paths: 0
- Historical blobs larger than 1 MiB: 0
- Fresh rewritten checkout validation: 1,325/1,325 tests passed

## Contributor transition

Existing clones refer to the archived commit graph. After the source refs are rewritten, contributors should preserve any unpublished work, make a fresh normal clone, and reapply their own commits by patch or cherry-pick using the mapping as a guide. Partial or shallow clone is not the product installation path.

The paused Agent Control `v4.5.0` release is not created by this source-distribution remediation.
