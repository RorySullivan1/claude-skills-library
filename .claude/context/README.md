# context/ — authoring standards (factory scope)

This is the **factory** `context/` layer. It does **not** hold the stack briefs —
those ship in `../../example-project/.claude/context/`. This layer will hold the
**authoring standards and conventions** the factory itself follows: the rules a
meta-skill or review command would cite when producing or auditing an asset.

## What goes here

Reference docs about *making good assets*, e.g.:

- `skill-conventions.md` — frontmatter rules, `description:` triggering style,
  folder-name == `name:`, what makes a `SKILL.md` load at the right time.
- `asset-taxonomy.md` — the hooks ▸ workflows ▸ commands ▸ agents ▸ skills model
  and how to choose between layers.
- `house-style.md` — tone, formatting, and structure conventions for authored docs.

## Status

**Empty stub.** No authoring standards written yet. Add a `*.md` brief here when we
codify the first convention.
