# Trademark and mark use

The open-source licenses in this repository (`LICENSE-CODE`, `LICENSE-SPEC`) grant
rights to the **code** and the **specification**. They do **not** grant any right to
the **TCEA name** or the **TCEA marks**. Those are reserved. This is standard
open-core practice: the software is free; the marks that signal attested
certification are controlled, because their value is that they cannot be self-applied.

## The two marks

TCEA distinguishes two claims, held to different bars:

- **TCEA Conformant** — a **factual, self-demonstrable** claim: an implementation, at
  a named version, passes a **published conformance profile** (see `CERTIFICATION.md`)
  when run against the public harness and golden vectors. Anyone can re-run the
  harness and check it, so this claim needs **no grant** — only that it be true,
  current, and scoped to the profile and version it passed (e.g. "TCEA Conformant —
  Profile P1, spec v1.1.x"). It asserts conformance to the spec and nothing more: not
  safety, endorsement, or fitness. A false, stale, or unscoped "Conformant" claim is
  misuse.

- **TCEA Certified** — an **attested** claim: the TCEA certification program has
  reviewed an implementation's evidence and **issued a conformance statement** for it
  (see `CERTIFICATION.md`). This mark, and any **certification badge or logo**, are
  **reserved** and may be used only while such a statement is current. "Certified"
  signals that the program vouches for the reviewed evidence; "Conformant" does not.

In short: **Conformant is earned by passing and is self-demonstrable; Certified is
granted by the program and is reserved.**

## Permitted without permission (nominative use)

You may use the word "TCEA" truthfully to refer to the project, including:

- "Implements TCEA" / "implements TCEA RFC-001".
- "Compatible with TCEA" / "based on TCEA" / "works with TCEA".
- **"TCEA Conformant"** when it is true — your implementation passes the current
  published profile, and you name the profile and version.
- Naming TCEA in documentation, talks, comparisons, and academic citation.

You do not need permission for any factual, accurate reference to the project.

## Reserved — requires a granted conformance statement

You may **not**, without a current conformance statement issued under
`CERTIFICATION.md`:

- Call a product **"TCEA Certified"** or display the TCEA **certification mark or badge**.
- State or imply that TCEA, its maintainer, or a certification body **endorses**,
  **approves**, or **vouches for** a product, outcome, or organization.
- Use "TCEA" in a product name, company name, domain, or logo in a way likely to
  suggest official status, certification, or endorsement.

## Attribution

The specification is CC BY 4.0: reuse it with attribution to *Godwin Orji, TCEA*, and
a link to the canonical source and DOI. Attribution is not endorsement, and may not
be presented as such.

## Reporting misuse / requesting a grant

Contact the maintainer at the project research address to request a conformance
statement, the right to use the certification mark, or to report misuse (including a
false "Conformant" claim).
