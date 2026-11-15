# Reference runtimes

Three reference implementations of the TCEA protocol. Each is **imported from the
ratified release**, carries its own version, and declares which spec corpus version
it targets. Licensed Apache-2.0 (`../LICENSE-CODE`).

| Runtime | Role | Notes |
|---|---|---|
| [`go/`](go/) | Production-grade; the most spec-conformant runtime | Sole hash producer in single-runtime deployments (F10-immune there) |
| [`python/`](python/) | Reference runtime | Readability-first; the canonical teaching implementation |
| [`rust/`](rust/) | Reference runtime | — |

## Cross-language status

The three runtimes do **not** yet produce byte-identical canonical serializations
for all inputs — finding **F10** (see `../SECURITY.md`). Until the v1.1.7
reconciliation closes it, cross-implementation receipt portability is not claimed,
and the conformance harness that compares them is gated (`../conformance/README.md`).

## Import checklist (before first push)

- [ ] Copy each runtime from the release at its named version.
- [ ] Each runtime's README states its version and the spec version it targets.
- [ ] `go test` / `pytest` / `cargo test` run green locally; paste output into the PR.
