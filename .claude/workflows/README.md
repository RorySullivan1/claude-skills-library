# workflows/ — authoring pipelines (factory scope)

The **factory** `workflows/` layer. Multi-step orchestrations for **producing
assets** end to end — where a command is one shot, a workflow runs the whole build.

## What goes here

- `author-skill` — scaffold → draft `SKILL.md` → audit against conventions → place
  the finished bundle into `example-project/.claude/skills/` (or a downstream repo).
- `harvest-context` — turn a stack brief into a context doc, validate, file it.

## Format

One markdown file per workflow: `<name>.md` — ordered steps, the agents/commands
each step invokes (reference `../agents/` and `../commands/`), inputs/outputs, and
stop conditions.

## Status

**Empty stub.** No authoring workflows defined yet.
