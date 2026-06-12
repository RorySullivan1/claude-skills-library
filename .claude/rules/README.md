# rules/ — always-binding constraints (factory scope)

Themed markdown files, each holding constraints that are **always in force**.
`CLAUDE.md` declares these mandatory, so Claude honors them every session without
being asked. Keep each file short and one-theme; add a new file for a new theme
rather than growing one into a catch-all.

## The boundary

- **`rules/` (here)** — short, always-binding constraints. Not optional, not
  situational.
- **`../context/`** — on-demand reference; deep-read only when relevant to the task.
- **`../memory/`** — append-only session journal; informative history, never
  authoritative over a rule.

## Conventions

- One file per theme, kebab-case (`repo-structure.md`).
- State each rule as a terse imperative. If a rule needs paragraphs of
  justification, that rationale belongs in `../memory/` or `../context/` — the rule
  itself stays a one-liner.

## Manifest

| File | Theme |
|---|---|
| `repo-structure.md` | Factory-vs-product layout and how the repo is organized. |
| `asset-conventions.md` | How skills, context docs, and other assets are named and edited. |
