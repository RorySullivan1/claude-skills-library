# rules/ — always-binding constraints

Themed markdown files, each holding constraints that are **always in force**.
`CLAUDE.md` declares these mandatory, so Claude honors them every session without
being asked. Keep each file short and single-theme.

> This is the `example-project/` showcase. The rules below are illustrative — they
> demonstrate the pattern, drawn from this example project's stated constraints and
> conventions.

## The boundary

- **`rules/` (here)** — short, always-binding constraints. Not optional.
- **`../context/`** — on-demand reference; deep-read only when relevant.
- **`../memory/`** — append-only session journal; informative, never authoritative
  over a rule.

## Conventions

- One file per theme, kebab-case. State each rule as a terse imperative; push long
  justification into `../memory/` or `../context/`.

## Manifest

| File | Theme |
|---|---|
| `environment-constraints.md` | Deployment/runtime limits that bound viable solutions. |
| `code-conventions.md` | Branching, formatting, and naming rules. |
