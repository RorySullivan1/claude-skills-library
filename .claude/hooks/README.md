# hooks/ — authoring guardrails (factory scope)

The **factory** `hooks/` layer. Deterministic scripts the harness runs *while we
author assets in this repo* — the enforcement floor for the factory itself, not
hooks shipped to a consumer project. The model cannot skip them.

## What goes here

Checks that must always run when editing assets here, e.g.:

- `PostToolUse` → validate that a skill folder name matches its `name:` frontmatter.
- `PostToolUse` → lint/format authored markdown.
- `PreToolUse` → guard the branch name / block stray writes.

## Format

One executable script per hook, wired in `../settings.json` under `hooks` by event
(`PreToolUse`, `PostToolUse`, `SessionStart`, …). A non-zero `PreToolUse` vetoes the
call.

## Status

**Empty stub.** No authoring hooks defined yet.
