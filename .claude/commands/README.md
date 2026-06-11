# commands/ — authoring commands (factory scope)

The **factory** `commands/` layer. Single-shot prompt templates for **authoring**
assets — the saved prompts we'd otherwise retype when building a new skill, hook,
or context brief. Invoked as `/<name>`.

## What goes here

- `/new-skill` — scaffold a `skills/<name>/SKILL.md` with correct frontmatter.
- `/validate-asset` — check one asset against the authoring conventions.
- `/new-context` — scaffold a context brief from the house template.

## Format

One markdown file per command: `<name>.md` (the filename is the command name). The
body is the prompt; use `$ARGUMENTS` / `$1`, `$2`, … for parameters.

## Status

**Empty stub.** No authoring commands defined yet.
