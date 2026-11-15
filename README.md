# TCEA — Trusted Cognitive Execution Architecture

**A general transaction layer for AI agents.** TCEA models any consequential
agent action as a governed transaction: a signed intent, a scoped and expiring
capability token, an explicit pre-execution policy decision (approved / denied /
escalated), outcome verification against declared criteria, and a tamper-evident
outcome receipt plus hash-chained decision ledger — serialized in a canonical,
cross-implementation format any conformant verifier can recompute independently.

Verifiable agent *payment* (e.g. Google AP2, FIDO agentic-payment work) is a
special case of verifiable agent *action*. TCEA is a reference design for the
general layer the payment case specializes.

> Positioning paper: *The General Transaction Layer for AI Agents* —
> DOI [10.5281/zenodo.24057182](https://doi.org/10.5281/zenodo.24057182) (CC BY 4.0).

---

## Repository map

| Path | What it holds |
|---|---|
| [`spec/`](spec/) | The normative RFC corpus (RFC-001…005) — the frozen, versioned heart |
| [`runtimes/`](runtimes/) | Reference runtimes: [`go/`](runtimes/go), [`python/`](runtimes/python), [`rust/`](runtimes/rust) |
| [`conformance/`](conformance/) | Golden vectors, the cross-language harness, and conformance profiles |
| [`docs/`](docs/) | Project site source (GitHub Pages) |

## Open-core, in three licenses

The split *is* the model — one thing is reserved, everything else is open:

- **Code** (runtimes, conformance tooling) — **Apache-2.0** ([`LICENSE-CODE`](LICENSE-CODE)). Includes a patent grant.
- **Specification** (the RFC corpus) — **CC BY 4.0** ([`LICENSE-SPEC`](LICENSE-SPEC)). Matches the paper.
- **The TCEA certification mark** — **reserved, not licensed** ([`CERTIFICATION.md`](CERTIFICATION.md), [`TRADEMARK.md`](TRADEMARK.md)).

Anyone may implement and extend the protocol. Only conforming implementations may
claim its certification. A conformance statement is never a claim of safety,
fairness, legality, or wisdom — only that declared procedures and evidence match a
named profile.

## Status

Pre-release. The governance scaffold is in place; the spec corpus and runtimes are
imported from the ratified release (baseline **v1.1.4**, Specification Corpus Freeze
1.2). **The cross-language conformance harness is gated on the v1.1.7 reconciliation
that closes finding F10 (cross-language canonicalization divergence)** — see
[`conformance/README.md`](conformance/README.md) and [`SECURITY.md`](SECURITY.md). Until
then, single-runtime use is unaffected; cross-implementation receipt portability is
not yet claimed.

## The prime rule

Every falsifiable claim is verified by execution before it is recorded. For-all
claims require domain scans, not point tests. This is the project's core discipline
and its CI contract — see [`CLAUDE.md`](CLAUDE.md) and [`CONTRIBUTING.md`](CONTRIBUTING.md).

---

*Authored by Godwin Orji · ORCID [0009-0005-0213-1009](https://orcid.org/0009-0005-0213-1009).*
*Org: `github.com/tcea-dev` · main repo `tcea`.*
