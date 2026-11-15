# Specification corpus

The normative heart of TCEA. These documents are **imported from the ratified
specification corpus freeze** (baseline v1.1.4, Freeze 1.2) — they are not authored
here. Do not edit a frozen RFC in place; corrections open a new version
(`../GOVERNANCE.md`).

Licensed CC BY 4.0 (`../LICENSE-SPEC`).

## RFC corpus

| RFC | Title | Covers |
|---|---|---|
| RFC-001 | Canonical objects | Intent Object, capability token, Outcome Receipt, Decision Ledger entry |
| RFC-002 | State machine | Transaction lifecycle and states; actor attribution on every transition (§13) |
| RFC-003 | Policy admission | The admission trichotomy: Approved / Denied / Escalated |
| RFC-004 | CABI | Capability / authority binding interface |
| RFC-005 | TCEA-CJSON | Canonical serialization — the format whose cross-language agreement is finding F10 |

`declarations/` holds the corpus declarations and conformance declarations that
accompany the RFCs.

## Import checklist (before first push)

- [ ] Copy RFC-001…005 and declarations from the v1.1.4 freeze, bytes unchanged.
- [ ] Record the source freeze and each document's hash in `../CHANGELOG.md`.
- [ ] Do **not** import anything whose status is asserted but not execution-verified.
