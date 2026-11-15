<!--
Ready-to-open GitHub issue. Create it in the `tcea` repo after first push, then
replace the `ISSUE-F10.md` references elsewhere with the issue's real number (#N).
Suggested labels: blocker, conformance, spec:v1.1.7
-->

# F10 — cross-language canonicalization divergence (blocks cross-language conformance)

**Status:** OPEN · **Blocks:** the cross-language conformance CI job · **Target fix:** v1.1.7 reconciliation

## Summary

The Python, Go, and Rust runtimes do not produce byte-identical TCEA-CJSON
(RFC-005) canonical serializations for all inputs. Because cross-implementation
receipt integrity depends on every verifier recomputing the **same** canonical
bytes, this blocks any claim of cross-implementation receipt portability, and the
cross-language conformance job is disabled until it is closed.

## Known divergent inputs (observed, not exhaustive)

- `1.0` (integer-valued float formatting)
- `1e-7` (small-magnitude float / exponent form)
- `-0.0` (signed zero)
- `U+2028` / `U+2029` (line / paragraph separators in strings)

These are examples. **Do not fix only these** — see acceptance criteria.

## Why it is gated, not hidden

Single-runtime deployments are unaffected: one implementation computes every hash,
so there is no cross-language comparison to diverge (this is why the MDR integration
is unaffected). The public repo, however, offers cross-implementation verifiability
as its headline property, so the cross-language check must be green before it runs
publicly. Until then it is disabled and this issue is the public record of why.

## Resolution plan (v1.1.7)

1. Define **one** canonical number form and **one** canonical string form in
   RFC-005, unambiguously (number formatting incl. signed zero and exponents;
   string escaping incl. U+2028/U+2029).
2. Bring all three runtimes to that definition.
3. Verify by a **domain scan**, not point tests (per `CLAUDE.md` corollary 1):
   generate a corpus spanning number edge cases, unicode separators, nesting, and
   key ordering, and assert byte-identical output across Go, Python, and Rust over
   the whole corpus.

## Acceptance criteria (all required to close)

- [ ] RFC-005 states a single canonical form for numbers and strings, no optionality.
- [ ] A domain-scan harness exists under `conformance/harness/` and runs in CI.
- [ ] Go, Python, and Rust produce byte-identical output across the **entire** scan,
      not just the four inputs above.
- [ ] The cross-language CI job is enabled and green; `conformance/README.md` and
      `SECURITY.md` are updated to reflect closure.
- [ ] CHANGELOG records the v1.1.7 freeze and the closing evidence.
