# Certification

Certification is the one part of TCEA that is **reserved**. Everything else — the
protocol, the spec, the runtimes — is open for anyone to use, implement, and extend.
This document states what the two TCEA marks mean and do not mean. The marks
themselves are governed by `TRADEMARK.md`.

## What may be claimed freely (no permission needed)

- That an implementation **implements** TCEA, or a named RFC (e.g. "implements
  TCEA RFC-001 canonical objects").
- That software is **compatible with** or **based on** TCEA.
- That an implementation is **TCEA Conformant** to a named profile and version —
  when it actually passes that published profile against the public harness. This is
  self-demonstrable and needs no grant (see `TRADEMARK.md`).
- Quoting or building on the specification, under CC BY 4.0 with attribution.

These are factual, verifiable claims. They are not certification — **TCEA Certified**
requires a granted conformance statement (below).

## What certification is

A conformance statement is what backs the reserved **TCEA Certified** mark; the
self-demonstrable **TCEA Conformant** claim above needs no statement. A TCEA
**conformance statement** asserts that a specific implementation, at a specific
version, satisfies a named **conformance profile** when run against the published
golden vectors and harness. A conformance statement is:

- **Profile-specific** — scoped to a named profile, never "TCEA-certified" at large.
- **Version-specific** — tied to one spec corpus version and one implementation version.
- **Evidence-backed** — issued only against a reproducible harness run, with the
  evidence recorded.
- **Independently reproducible** — anyone with the implementation, the vectors, and
  the harness can recompute the result.
- **Revocable** — withdrawn if the evidence is found wrong or the implementation
  changes out of conformance.

## What certification is NOT

A conformance statement is **explicitly non-endorsing**. It does **not** assert that
an outcome, product, or organization is safe, fair, legal, correct in the world, or
wise. It asserts only that declared procedures, lifecycle events, and evidence
relationships conform to a profile. Structural assurance and semantic adequacy are
different guarantees; conflating them is the failure this design exists to avoid.

## Who may issue it

Until a certification body is named, the maintainer issues conformance statements
against published profiles, and every statement carries its reproducible evidence so
it can be checked without trusting the issuer. The right to use the **Certified**
mark to advertise a conformance statement is granted per `TRADEMARK.md`; claiming
**Conformant** needs no grant, since it is self-demonstrable; and the right to
*implement the protocol* is not gated by anything in this file.

## Profiles

Conformance profiles live in [`conformance/profiles/`](conformance/profiles/). A
profile names the spec version, the vectors, the required surfaces, and the pass
criteria. A **Conformant** or **Certified** claim that does not name a profile in
that directory is not valid.
