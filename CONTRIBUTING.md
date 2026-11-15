# Contributing to TCEA

Contributions are welcome. The one non-negotiable is the prime rule in `CLAUDE.md`:
**every falsifiable claim is verified by execution before it is recorded.** A pull
request is a claim; CI and review treat it as one.

## Two kinds of change, two paths

**Code changes** (runtimes, conformance tooling, docs prose):

1. Fork, branch, make the change.
2. Run what you changed. Put the exact command and its real output in the PR.
3. For any "always / for every / all conformant" claim, include a **domain scan**,
   not a single example (see corollary 1 in `CLAUDE.md`).
4. Sign off your commits (`git commit -s`) to certify you have the right to
   contribute the change (Developer Certificate of Origin).

**Specification changes** (anything under `spec/`):

Spec material is frozen and versioned (see `GOVERNANCE.md`). You do **not** edit a
frozen RFC in place. A spec change is proposed against a named freeze, ratified by
execution, and lands as a **new version**. Open an issue first — spec changes are
governance events, not ordinary PRs.

## What CI enforces

- The conformance harness runs each runtime against the golden vectors.
- Assertions must be able to fail (no vacuous tests — corollary 2 in `CLAUDE.md`).
- A document that claims a status (PASSED/LOCKED/COMPLETE) is checked against the
  artifacts it names.

## Honesty beats green

A PR that says "this does not fully pass, here is the domain where it fails" is more
valuable than one that hides a gap to make CI green. Record the open finding; do not
launder it. The project was built out of catching exactly that kind of laundering.

## Reporting security issues

Do not open a public issue for a vulnerability. See `SECURITY.md`.
