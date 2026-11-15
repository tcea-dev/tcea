# TCEA — Go runtime

Production-grade reference runtime; the most spec-conformant of the three. In a
single-runtime deployment it is the sole hash producer, which makes that deployment
F10-immune (see `../../SECURITY.md`).

**Import target.** Copy from the ratified release; state the runtime version and the
spec corpus version it targets here before first push.

- Runtime version: `TBD`
- Targets spec corpus: `v1.1.4` (Freeze 1.2)
- Build/test: `go build ./... && go test ./...`
