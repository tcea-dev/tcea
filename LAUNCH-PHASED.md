# Phased launch runbook

The launch shape is **phased** (decision of record: `CHANGELOG.md`, 2026-11-10).
Publish what is verified now; keep the cross-language conformance claim gated behind
F10 until v1.1.7. This runbook is the ordered path from scaffold to public.

Legend: **[you]** owner-gated (only you can do it) · **[push]** turnkey once the
handle is set · **[gated]** waits on v1.1.7 / F10.

## Phase 0 — decide the two things that block everything

1. **[done] GitHub org handle confirmed: `tcea-dev`** (`tcea` was taken). The org is
   `github.com/tcea-dev`, owned by the personal account `gorji-research`; `<ORG>` has
   been substituted throughout the scaffold.
2. **[you] Finalize the certification-mark wording** in `TRADEMARK.md` (currently
   provisional). Mark use is reserved, so the string should be settled before it is
   public.

## Phase 1 — stand up the public home (no F10 dependency)

3. **[push]** Create the org and two repos: `tcea` (main) and `.github` (org profile).
4. **[push]** Push this scaffold to `tcea`; push `profile/README.md` to `.github`.
5. **[push]** Enable GitHub Pages on `tcea`: branch `main`, folder `/docs`.
6. **[done]** F10 tracking issue opened as #1; file references repointed to it.
7. **[push]** Wire the Zenodo↔GitHub integration so tagged releases auto-archive with
   a version DOI under the paper's concept DOI (10.5281/zenodo.24057182).

At the end of Phase 1 the project is public: spec, governance, the open-core
licensing, and an honest open-finding register — all behind the fresh DOI.

## Phase 2 — import the verified corpus (single-runtime only)

8. **[push]** Import the RFC corpus (RFC-001…005) and declarations from the ratified
   **v1.1.4 / Freeze 1.2** release, bytes unchanged; record source hashes in CHANGELOG.
9. **[push]** Import the three runtimes at their named versions.
10. **[push]** Enable the **single-runtime** conformance job (not F10-gated): each
    runtime against the golden vectors. Keep the **cross-language** job disabled.
11. **[push]** Tag the first public release; let Zenodo mint its version DOI.

## Phase 3 — close the gate (v1.1.7)  [gated]

12. **[gated]** Execute the v1.1.7 reconciliation per `ISSUE-F10.md`: one canonical
    number/string form, all three runtimes brought to it, verified by a **domain
    scan**. Needs a local Go/Rust toolchain.
13. **[gated]** Enable the cross-language conformance job; confirm green over the full
    scan. Update `conformance/README.md`, `SECURITY.md`, and close the F10 issue.
14. **[gated]** Tag v1.1.7; the cross-implementation verifiability claim is now earned,
    not asserted.

## The invariant

Nothing in Phases 1–2 claims cross-language receipt portability. The README already
hedges ("not yet claimed"); keep it that way until Phase 3 is green. Publishing the
honest, single-runtime-verified subset now is the whole point of the phased choice —
it trades an all-green day-one story for public presence now, and loses nothing,
because closing F10 later reaches the identical endpoint.
