# Agent Control source-separation evidence — 2026-09-12

This archive precedes the source-repository history rewrite that removes historical heavyweight qualification artifacts from ordinary Agent Control clones.

## Preserved assets

| Asset | Size | SHA-256 |
| --- | ---: | --- |
| `agent-control-pre-separation.bundle` | 276,056,956 bytes | `6bca20655d2296d032dfadacbc28fc1cf9e3989891a176f482d9eab82577b15b` |
| `agent-control-candidate-146ba9d-heavy-evidence.tar.zst` | 184,885,992 bytes | `1704b027da092e6e8511893079b0f62145b2589e7a11dc0da27578fae9b54634` |
| `candidate-146ba9d-evidence.json` | 148,772 bytes | `a49ec8370ac887047652967c1ddbbebd891f5e67d70741145344292e4c3092f2` |
| `agent-control-remediation-pre-rewrite.bundle` | 29,321 bytes | `bb8cd73bccd070a5ca9aeeb0d41f542f2755aac5ab64a7087fb4e5882fa0bcba` |
| `history-rewrite-commit-map-20260912.tsv` | 47,851 bytes | `a68e9997e8887450399298bb69ac7b222232eb05211ab3d5137ddddf1563010f` |
| `history-rewrite-ref-map-20260912.tsv` | 11,796 bytes | `3af66545f9c3acf3b2eda24347c5673355763ba8f836590b1f9471fd4b843855` |
| `filtered-history-full-check.log` | 133,675 bytes | `2db8c0d48d62c8255059e822161ea60f40145a37ba40fa67544c4e8ecbaeca64` |

The candidate evidence archive contains 417 files totalling 206,327,212 uncompressed bytes. The full Git bundle preserves the original public history and refs before rewriting.

The five `*.png` assets are the original 4.5 README screenshots published individually so the source README can continue to display the qualified dashboard without embedding those binaries in every clone. Their original paths and hashes remain in the candidate manifest.

The complete bundle plus the small remediation bundle reconstruct the final pre-rewrite branch state. The latter declares `146ba9d2699ca9e1570762dea01e9b84da9374a8` as its prerequisite.

## Post-rewrite normal-clone acceptance

Candidate `413f8d3e572e0e777076a79177262493c603d592` passed a genuinely clean Android 15 / Termux installation using the documented normal full-clone path. Git reported 5.93 MiB received, compared with approximately 263.26 MiB before remediation. Bootstrap check, installation and idempotent reinstall passed. The final controller suite passed 1,328/1,328 and the Android suite passed 1,327 with zero failures and one platform-inapplicable Linux-PTY skip out of 1,328.

The associated manifest and raw command/test logs are attached to this evidence release. This acceptance qualifies source distribution and installation only; it does not create or authorize `v4.5.0`.

## Audit boundary

This release preserves evidence; it is not an Agent Control product release and does not alter the recorded qualification verdicts. The paused `v4.5.0` release is not created by this operation.
