# Conformance

This directory is what makes the TCEA certification mark mean something. It holds the
canonical test vectors, the harness that runs every runtime against them, and the
conformance profiles a statement is issued against.

| Path | What it holds |
|---|---|
| [`golden-vectors/`](golden-vectors/) | Canonical CJSON vectors — one source of truth, shared across all three runtimes |
| [`harness/`](harness/) | Runs each runtime against the vectors and compares results in CI |
| [`profiles/`](profiles/) | Version- and profile-specific conformance definitions and pass criteria |

## ⚠ The F10 gate (read before enabling CI)

The harness's headline check is **cross-language agreement**: that Go, Python, and
Rust produce byte-identical canonical serializations for every vector. Finding
**F10** (see `../SECURITY.md`) means they currently do **not**, for certain values.

Therefore the cross-language conformance job **will fail until the v1.1.7
reconciliation closes F10** — by design, not by accident. This is the one place the
open-core launch is genuinely gated:

A public repository whose headline guarantee is cross-implementation verifiability
must **not** ship with that check red on day one — it would undercut the framework's
entire credibility.

### Decision of record: phased launch

This project launches **phased**. The cross-language conformance job stays
**disabled** until the `v1.1.7` reconciliation closes F10; the open finding is
tracked (see [`ISSUE-F10.md`](../ISSUE-F10.md)) and disclosed in `../SECURITY.md`.
Single-runtime conformance (one runtime against the vectors, no cross-language
comparison) is **not** gated by F10 and is the active check at launch. When v1.1.7
lands and the domain scan passes, the cross-language job is enabled and this note
updated. Rationale and the alternative considered are recorded in `../CHANGELOG.md`.

## Import checklist (before first push)

- [ ] Import golden vectors from the ratified release.
- [x] Launch shape decided: **phased** — cross-language job disabled pending F10,
      tracked in `../ISSUE-F10.md`; single-runtime job is the active check.
- [ ] Each profile names its spec version, required surfaces, and pass criteria.
