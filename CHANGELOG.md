# Changelog

All notable changes and decisions of record for TCEA. Dates are UTC. Format follows
the spirit of Keep a Changelog; the unit of record is the specification corpus freeze
(see `GOVERNANCE.md`).

## [Unreleased]

### Added
- Public open-core repository scaffold: README, dual licensing (Apache-2.0 code /
  CC BY 4.0 spec), reserved certification mark, governance, contribution, and
  security policy; `CLAUDE.md` engineering constitution; conformance CI stub.

### Decisions
- 2026-11-10 — **Launch shape set to phased.** Publish spec, governance, and
  single-runtime material now, behind the Zenodo DOI; keep the cross-language
  conformance job disabled, tracked in issue #1, until the v1.1.7
  reconciliation closes F10. Alternative considered: reconcile-first (close F10,
  then launch all-green at once) — set aside to avoid re-creating a "publish when
  perfect" hold while F10's fix is unstarted and toolchain-dependent. Reversible:
  closing F10 and flipping the cross-language job green is the same endpoint.
- 2026-11-08 — Positioning paper *The General Transaction Layer for AI Agents*
  published to Zenodo under CC BY 4.0; concept DOI 10.5281/zenodo.24057182.
- 2026-10 — Go-to-market set to open-core: open protocol + runtimes, reserved
  certification mark.

### Pending
- Import of the ratified spec corpus and runtimes at the published version.
- `v1.1.7` reconciliation to close finding **F10** (gates cross-language
  conformance; see `SECURITY.md`).
- Finalize the certification-mark wording (see `TRADEMARK.md`).
- arXiv (cs.CY / cs.CR) submission of the positioning paper — pending endorsement.

## Baseline

- **v1.1.4** — ratified release, Specification Corpus Freeze 1.2. The baseline from
  which the public corpus is imported.
