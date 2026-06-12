# 2026-06-11 — Adopt the `.claude/` infrastructure layout

*Migrated from the retired `DECISIONS.md`.*

- Restructured the repo from 15 flat root markdown files (10 frontmatter skills,
  5 CLAUDE.md-style stack briefs) into the typed `.claude/` layout: `skills/`,
  `context/`, `hooks/`, `commands/`, `agents/`, `workflows/`.
- Decided: empty layers get explanatory READMEs only — no example content
  invented; they stay empty until a real need appears.
- Decided: the 5 project-instruction docs are reference context, not skills →
  `.claude/context/`.
- Decided: `CLAUDE.md` documents the library itself; the portable starter pattern
  went to `templates/` (later dissolved — see the factory/example split entry).
- Mechanics: all moves via `git mv` (history preserved, bodies byte-for-byte
  unchanged); skill folders named after each skill's `name:` frontmatter; no `src/`.
- Open thread at the time: the domain assets still sat in the repo's own
  `.claude/`, implying this repo runs them — resolved the same day by the
  factory/example split.
