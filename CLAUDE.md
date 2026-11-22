# CLAUDE.md — the engineering constitution

This file is the standing instruction set for any agent or contributor doing work
in this repository. It is also the project's **CI contract**: automated checks
enforce it, and a pull request that violates it does not merge.

## The prime rule

**Every falsifiable claim is verified by execution before it is recorded.**

A claim is falsifiable if a program could, in principle, show it false. Such a
claim does not enter the spec, a README, a CHANGELOG, a conformance record, or a
commit message until an execution that could have failed did not. "It should
work," "this is equivalent," "all implementations agree" — none of these are
recorded until run.

## Corollaries (each earned from a real defect)

1. **For-all claims require domain scans, not point tests.** A claim about *all*
   inputs is not established by one example. Canonicalization agreement across
   languages was asserted on a point test and was false on a domain scan
   (finding F10: `1.0`, `1e-7`, `-0.0`, `U+2028`/`U+2029` diverged). Any
   "for every / always / all conformant" claim must be backed by a scan over the
   relevant domain, or it is marked provisional.

2. **No vacuous assertions.** A test whose assertion can pass without exercising
   the property under test is not a test (e.g. an ``== <constant> or True` ``
   assertion, plus a wrong constant). Assertions must be able to fail.

3. **Status reflects execution, not intention.** A document may say PASSED,
   LOCKED, or COMPLETE only when the artifacts it refers to actually have that
   state on disk. Decision records and artifacts are reconciled, not trusted.

4. **Freeze discipline.** Once a spec version is frozen, its bytes do not change.
   Corrections open a new version (see GOVERNANCE.md). A freeze is a boundary, not
   a suggestion.

## For code agents

- Run what you change. Paste the command and its real output into the PR.
- When an upstream artifact is untrusted (a downloaded corpus, a third-party
  runtime), work on a copy, pass paths as arguments, and run readers in isolated
  mode. Do not import from the artifact's directory.
- If you cannot verify a claim by execution in this environment, say so and mark
  it provisional. Do not launder an unverified claim into a recorded one.
