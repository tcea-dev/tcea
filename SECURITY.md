# Security and open findings

## Reporting a vulnerability

Please report security issues **privately** to the project research address rather
than opening a public issue. Include what you observed, how to reproduce it, and the
version/commit. You will get an acknowledgement; fixes follow the freeze-and-version
discipline in `GOVERNANCE.md`.

## Known open findings (honest disclosure)

TCEA records open findings in the open. The following is known and tracked:

### F10 — cross-language canonicalization divergence  (OPEN)

The Python, Go, and Rust runtimes do not produce byte-identical canonical
serializations for certain values (observed: `1.0`, `1e-7`, `-0.0`, and the line/
paragraph separators `U+2028`/`U+2029`). Because the integrity of a cross-
implementation receipt depends on every verifier recomputing the **same** canonical
bytes, this blocks **cross-implementation receipt portability**.

- **Impact:** a receipt produced by one runtime may fail integrity recomputation on
  another. Cross-language conformance is therefore not yet claimed.
- **Not affected:** single-runtime deployments. When one implementation computes
  every hash in a chain, there is no cross-language comparison to diverge, so the
  chain is internally consistent.
- **Resolution:** the `v1.1.7` reconciliation defines one canonical number and
  string form and brings all three runtimes to it, under a domain scan rather than a
  point test. The cross-language conformance harness is gated on this fix.

Reporting that a claimed cross-language property does not hold is a contribution, not
an attack — see `CONTRIBUTING.md`.
