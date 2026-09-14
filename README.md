# Agent Control qualification evidence archive

This repository preserves the heavyweight qualification evidence that is intentionally excluded from normal clones of [`lozknowles/agent-control`](https://github.com/lozknowles/agent-control).

The separation keeps the product repository suitable for ordinary installation while retaining the original evidence, cryptographic identities, and Git provenance needed for audit.

## Source-separation checkpoint

- Source repository: `lozknowles/agent-control`
- Pre-separation candidate: `146ba9d2699ca9e1570762dea01e9b84da9374a8`
- Frozen 4.5 candidate represented by that history: `d229ce4b7dd3bd704a331f81ca59600541430682`
- Archive date: `2026-09-12`
- Source-remediation commit before rewriting: `c50fcfae87404c0e83609c63964ae2922bd94c66`
- Source-remediation commit after rewriting: `0cd4d5fb02b3d5391e4a2ff677f7e0c895f91708`

The `source-separation-20260912` release contains:

- `agent-control-pre-separation.bundle` — a complete pre-rewrite Git bundle preserving the original public branches, tags, commits, and objects;
- `agent-control-candidate-146ba9d-heavy-evidence.tar.zst` — heavyweight evidence present in the pre-separation 4.5 closure candidate;
- `candidate-146ba9d-evidence.json` — per-file original path, byte size, Git blob ID, SHA-256, and selection reason;
- `candidate-146ba9d-files.tsv` — the same file index in tabular form;
- `SHA256SUMS` — archive checksums.
- `agent-control-remediation-pre-rewrite.bundle` — the small source-remediation commit layered on the complete pre-separation archive;
- `history-rewrite-commit-map-20260912.tsv` — complete old-to-new commit mapping;
- `history-rewrite-ref-map-20260912.tsv` — old-to-new public branch and tag targets;
- `filtered-history-full-check.log` — the 1,325-test validation of a fresh checkout of the rewritten source history.

The committed `manifests/` directory is deliberately lightweight. Release assets hold the large files; they are not committed to this archive repository's Git history.

## Virgin Android installation result

The same evidence release also preserves the final normal-clone installation qualification performed after source separation:

- implementation candidate `413f8d3e572e0e777076a79177262493c603d592`;
- normal, non-shallow, non-partial clone reported 5.93 MiB received;
- exact Git pack 6,215,934 bytes plus 194,888-byte index;
- 20,215,937-byte checkout before dependencies;
- bootstrap check, fresh install and idempotent reinstall passed;
- controller validation passed 1,328/1,328;
- Android/Termux validation passed 1,327, failed 0, skipped 1 Linux-only PTY test out of 1,328.

The release assets named `agent-control-attempt-8-*`, `final-controller-check.log` and `agent-control-4.5-virgin-moto-install-20260912.json` are the immutable supporting record. The source repository contains only the small machine-readable manifest and human-readable summary.

## Verification

Download the release assets, then verify them with:

```bash
sha256sum -c SHA256SUMS
git bundle verify agent-control-pre-separation.bundle
```

To inspect the candidate evidence without changing the archive:

```bash
tar --zstd -tf agent-control-candidate-146ba9d-heavy-evidence.tar.zst
```

The source-repository rewrite changes commit IDs. The complete mappings and the detailed procedure are published here before the rewritten source refs are installed. Historical evidence is never reclassified as a result from a newer candidate. See [`HISTORY-REWRITE.md`](HISTORY-REWRITE.md).

## Security boundary

This archive contains public qualification artifacts formerly tracked by the public source repository. Credentials, tokens, cookies, pairing codes, and private authentication material are not intended to be present. Do not add secrets or machine credential stores to this repository or its releases.

## Agent Control 4.7 desktop and mobile usability

[Paused 4.7 recordings and checksums](https://github.com/lozknowles/agent-control-qualification-evidence/releases/tag/agent-control-4.7.0-dashboard) · [Qualification manifest](manifests/agent-control-4.7.0-dashboard.json). Two real governed jobs demonstrate active process drill-down, running activity/timer, reconciled token usage and retained readable history. Usage views pause for at least two seconds. Mobile is viewport emulation; neither recording claims physical voice qualification. Video assets stay outside normal product source pulls.
