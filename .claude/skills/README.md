# skills/ — meta-skills (authoring scope)

This is the **factory** `skills/` layer. It does **not** hold domain skills — those
ship in `../../example-project/.claude/skills/`. This layer will hold *meta-skills*:
expertise on **how to author skills well**.

## What goes here

Skills that guide the construction of other assets, e.g.:

- A `skill-authoring` skill — how to scope a skill, write a triggering
  `description:`, structure `SKILL.md`, and keep the folder name == `name:`.
- A `context-vs-skill` skill — deciding when knowledge belongs in a skill, a
  context brief, a command, or a hook.

## Format

Same as any skill: one folder per skill containing `SKILL.md`, folder name equal to
the `name:` frontmatter value.

## Status

**Empty stub.** No meta-skills written yet. Add `skill-authoring/SKILL.md` (or
similar) when we codify the first authoring playbook.
