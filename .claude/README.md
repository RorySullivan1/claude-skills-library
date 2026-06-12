# `.claude/` — the factory's design environment

This is **not** a consumer `.claude/`. The assets a project runs (skills, hooks,
workflows, …) live in `../example-project/.claude/`. *This* directory is the
tooling we use to **author** those assets — it answers "how do we build a good
skill / hook / workflow?", not "do the domain work."

It mirrors the standard layer taxonomy so the meta-tooling is organized the same
way the products are. Each layer here is scoped to authoring its matching
downstream asset type.

## The layers (authoring scope)

```
hooks      ← enforcement for the factory itself (lint/validate authored assets)
─────────────────────────────────────────────────────────────────────────
workflows  ▸  commands  ▸  agents  ▸  skills
(author pipelines) (one-shot authoring prompts) (authoring subagents) (meta-skills)
```

- **skills/** — Meta-skills: domain expertise on *writing assets* — how to craft a
  `SKILL.md`, frontmatter conventions, when something should be a skill vs. a
  context doc vs. a command.
- **agents/** — Isolated subagents for authoring jobs (e.g. draft-a-skill,
  audit-an-asset) that return a summary without polluting the main session.
- **commands/** — Single-shot authoring prompts (`/new-skill`, `/validate-asset`).
- **workflows/** — Multi-step authoring orchestrations (scaffold → draft → review →
  place into `example-project/` or a downstream repo).
- **hooks/** — Deterministic checks the harness runs while authoring — e.g. verify
  a skill folder name matches its `name:` frontmatter, lint markdown. Wired in
  `settings.json`.

## Supporting files

- **context/** — Authoring standards and conventions the factory itself follows
  (the rules a meta-skill would cite). See `context/README.md`.
- **rules/** — Always-binding constraints for the factory (`CLAUDE.md` declares them
  mandatory). See `rules/README.md`.
- **memory/** — Append-only session journal: what was done and why. The decision
  history once kept in `DECISIONS.md` now lives here. See `memory/README.md`.
- **settings.json** — Permissions, model, and hook configuration for this repo.

## Status

Every layer here is an **intentional stub** — one README describing what the layer
will hold once we write the first meta-tool. No authoring tooling is fabricated
yet. The taxonomy is in place so each piece has an obvious home when a concrete
need appears. For the *consumer-facing* explanation of these same layers (what
they mean in a project that runs them), see
`../example-project/.claude/README.md`.
