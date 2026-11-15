# Governance

How TCEA versions, freezes, and ratifies changes. This document is normative for
the process, not the protocol.

## Roles

TCEA is, at present, a single-maintainer project (Godwin Orji, the specification
author). Decisions of record are the maintainer's. This document exists so that the
process is legible and reproducible by others, and so the project can add
maintainers without reinventing its rules.

## Versioning

- The **specification corpus** is versioned as a whole (e.g. `v1.1.4`). A version
  is a set of RFC documents frozen together as a **Specification Corpus Freeze**.
- **Runtimes** carry their own version and declare which spec corpus version they
  target. A runtime is never assumed conformant to a version it does not name.
- A version string is semantic where it can be, but the corpus freeze — not the
  number — is the unit of record.

## Freeze discipline

1. A corpus freeze fixes the bytes of every document in it. Frozen bytes do not
   change.
2. A correction to frozen material opens a **new version**; it never edits the old
   one. Superseded versions are retained, not deleted.
3. A release tag archives to Zenodo with a version DOI (the concept DOI resolves to
   the latest). The tag, the freeze, and the archive refer to the same bytes.

## Ratification of a change

A change to the spec corpus is ratified when, in order:

1. The change is written against a specific prior freeze.
2. Every falsifiable claim it makes is verified by execution (see `CLAUDE.md`),
   including a domain scan for any for-all claim.
3. The conformance harness passes for every runtime that targets the new version —
   or the change is explicitly scoped to not require it, and that scope is recorded.
4. The new corpus is frozen, tagged, and archived.

A change that cannot pass step 2 or 3 is not ratified. It may be recorded as an
**open finding** (see `SECURITY.md`) with honest status, but it does not advance the
version to "passing."

## Open findings and the version line

An open finding may block a version from being called conformant on a given surface
without blocking unrelated work. The current line:

- **Baseline:** `v1.1.4`, Specification Corpus Freeze 1.2.
- **Open:** finding **F10** (cross-language canonicalization divergence) blocks
  cross-implementation conformance. The `v1.1.7` reconciliation closes it.
- Single-runtime deployments are unaffected by F10 (one implementation computes
  every hash, so there is no cross-language comparison to diverge).

## Decision records

Consequential decisions — adopting a version, retiring a fork, changing a license
or the mark policy — are recorded in `CHANGELOG.md` with the date and the reason, so
the project's history is auditable from the repository alone.
