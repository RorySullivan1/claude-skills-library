# 2026-06-11 — Split into a factory (`.claude/`) and a mock consumer (`example-project/`)

*Migrated from the retired `DECISIONS.md`.*

- Reframed the repo as a **factory with two halves**: root `.claude/` is the
  factory's design environment (meta-tooling for *authoring* assets);
  `example-project/` is a mock consumer project showing a produced `.claude/`.
  Why: the single-`.claude/` framing conflated the design environment with its
  output and implied this repo runs the domain assets.
- Moved the 10 skills, 5 context briefs, the taxonomy README, and the four
  scaffold-layer READMEs into `example-project/.claude/` via `git mv`. They are the
  canonical worked examples a developer copies.
- Root `.claude/` kept the same layer taxonomy as stubs, re-scoped to authoring.
- Dissolved `templates/` into `example-project/`: the two templates "popped out" as
  the example's real `CLAUDE.md` and `CLAUDE.local.md` — a faithful copy-me skeleton.
- Decided: `example-project/CLAUDE.local.md` is tracked as a labeled sample; root
  `.gitignore` anchored (`/CLAUDE.local.md`) so it only ignores the factory's own
  personal file.
- Mechanics: all relocations via `git mv` (history preserved, bodies unchanged);
  no `src/` — the consumer half is named `example-project/`.
- Shipped as PR #1 (merged).
