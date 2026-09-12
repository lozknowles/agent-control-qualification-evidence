# Agent Control qualification evidence archive

This repository preserves the heavyweight qualification evidence that is intentionally excluded from normal clones of [`lozknowles/agent-control`](https://github.com/lozknowles/agent-control).

The separation keeps the product repository suitable for ordinary installation while retaining the original evidence, cryptographic identities, and Git provenance needed for audit.

## Source-separation checkpoint

- Source repository: `lozknowles/agent-control`
- Pre-separation candidate: `146ba9d2699ca9e1570762dea01e9b84da9374a8`
- Frozen 4.5 candidate represented by that history: `d229ce4b7dd3bd704a331f81ca59600541430682`
- Archive date: `2026-09-12`

The `source-separation-20260912` release contains:

- `agent-control-pre-separation.bundle` — a complete pre-rewrite Git bundle preserving the original public branches, tags, commits, and objects;
- `agent-control-candidate-146ba9d-heavy-evidence.tar.zst` — heavyweight evidence present in the pre-separation 4.5 closure candidate;
- `candidate-146ba9d-evidence.json` — per-file original path, byte size, Git blob ID, SHA-256, and selection reason;
- `candidate-146ba9d-files.tsv` — the same file index in tabular form;
- `SHA256SUMS` — archive checksums.

The committed `manifests/` directory is deliberately lightweight. Release assets hold the large files; they are not committed to this archive repository's Git history.

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

The source-repository rewrite changes commit IDs. The complete old/new mapping is published here after the source refs are rewritten. Historical evidence is never reclassified as a result from a newer candidate.

## Security boundary

This archive contains public qualification artifacts formerly tracked by the public source repository. Credentials, tokens, cookies, pairing codes, and private authentication material are not intended to be present. Do not add secrets or machine credential stores to this repository or its releases.
