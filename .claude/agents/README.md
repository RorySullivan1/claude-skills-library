# agents/ — authoring subagents (factory scope)

The **factory** `agents/` layer. Not domain agents — these are isolated subagents
for **authoring jobs**: focused workers that help build assets and return only a
summary, keeping the main authoring session clean.

## What goes here

- A `draft-skill` agent — takes a task description, returns a first-pass `SKILL.md`.
- An `asset-auditor` agent — reads a skill/hook/workflow and reports convention
  violations without bleeding the whole file into context.

## Format

One markdown file per agent: `<name>.md`. Frontmatter (`name`, `description`, and
optionally `tools`, `model`); the body is the agent's mandate.

## Status

**Empty stub.** No authoring agents defined yet.
