# 2026-06-12 — First factory meta-skill: `agent-authoring`

*Migrated from the retired `DECISIONS.md`.*

- Shipped `.claude/skills/agent-authoring/SKILL.md`, the factory's first meta-skill.
  Why: the `skills/` layer was a stub — meta-skills were described but none existed.
- It teaches how to author Claude Code subagents (`.claude/agents/<name>.md`):
  writing a triggering `description`, scoping the `tools` allowlist, choosing the
  default permission posture (`permissionMode`), picking the `model`, and writing
  the system-prompt mandate.
- Decided: ground content in the durable agent fields
  (`name`/`description`/`tools`/`permissionMode`/`model`) and defer the volatile
  long tail to `/agents` and the official sub-agents docs, so it doesn't drift
  between Claude Code versions.
- Scope: meta-skill only — no companion `draft-agent` authoring agent, no
  `skill-authoring` meta-skill yet (the new skill defers to it as future work).
- Shipped as PR #2 (merged).
