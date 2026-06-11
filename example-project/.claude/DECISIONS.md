# Decisions

A running log of structural decisions for this project. Newest first.

> **Note:** This is the `example-project/` showcase — a mock consumer of the
> `claude-skills-library` factory. The entries below illustrate what a real
> project's decision log looks like; they are examples, not live history.

## Example entry — adopting the `.claude/` layout

**Context.** We wanted Claude Code to behave consistently across the team without
re-explaining the stack every session.

**Decision.** Adopt the typed `.claude/` layout: domain skills under `skills/`,
whole-stack briefs under `context/`, and the four flexible layers
(`hooks/`, `commands/`, `agents/`, `workflows/`) scaffolded for later. `CLAUDE.md`
stays short and points into `context/`.

**Rationale.** Keeps every session lean (only `CLAUDE.md` always-loads) while making
deep expertise available on demand. Empty layers are left as READMEs, not
fabricated, so the structure documents intent without inventing content.
