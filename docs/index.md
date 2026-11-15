# TCEA

**A general transaction layer for AI agents.**

Any consequential agent action, modeled as a governed transaction: signed intent →
scoped capability token → pre-execution policy decision (approved / denied /
escalated) → outcome verification → tamper-evident receipt + hash-chained ledger, in
a canonical cross-implementation format any verifier can recompute.

Verifiable agent payment is a special case of verifiable agent action. TCEA is a
reference design for the general layer.

## Read

- **Positioning paper** — *The General Transaction Layer for AI Agents* —
  [doi.org/10.5281/zenodo.24057182](https://doi.org/10.5281/zenodo.24057182) (CC BY 4.0)
- **Specification** — the RFC corpus in [`spec/`](https://github.com/tcea-dev/tcea/tree/main/spec)
- **Runtimes** — Go, Python, Rust in [`runtimes/`](https://github.com/tcea-dev/tcea/tree/main/runtimes)
- **Conformance** — vectors, harness, profiles in [`conformance/`](https://github.com/tcea-dev/tcea/tree/main/conformance)

## Open-core

Protocol and runtimes are open (Apache-2.0); the specification is CC BY 4.0; the
TCEA certification mark is reserved. Anyone may implement and extend; only conforming
implementations may claim certification.

---
*GitHub Pages source for `github.com/tcea-dev/tcea` — enable Pages on the `tcea`
repo, branch `main`, folder `/docs`.*
