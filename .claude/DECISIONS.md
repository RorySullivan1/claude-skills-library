# Decisions

A running log of structural decisions for this repo. Newest first.

## 2026-06-11 — Split into a factory (`.claude/`) and a mock consumer (`example-project/`)

**Context.** After adopting the `.claude/` layout (below), the domain skills and
context docs sat in the repo's *own* `.claude/`, implying this repo runs them. It
doesn't — they're *products*. The repo's real job is to **author** reusable Claude
Code assets for downstream projects. The single-`.claude/` framing conflated the
design environment with its output.

**Decisions.**

1. **The repo is a factory with two halves.** Root `.claude/` is the factory's
   **design environment** (meta-tooling for *authoring* assets); `example-project/`
   is a **mock consumer project** showing what a produced `.claude/` looks like.
2. **Domain assets move to `example-project/`.** The 10 skills and 5 context briefs
   (plus the taxonomy README and the four scaffold-layer READMEs — all
   consumer-oriented) relocate to `example-project/.claude/` via `git mv`. They are
   the canonical worked examples and the thing a developer copies.
3. **Root `.claude/` keeps the same layer taxonomy as stubs, re-scoped to
   authoring.** Each layer's README now describes the meta-tool it will hold
   (meta-skills, authoring commands/agents/workflows, authoring guardrail hooks,
   authoring standards in `context/`). No meta-tooling is fabricated yet.
4. **`templates/` is dissolved into `example-project/`.** The two template files
   "pop out" as the example project's real `CLAUDE.md` and `CLAUDE.local.md`, so the
   showcase is a faithful, copy-me repo skeleton rather than a separate templates
   folder.
5. **`example-project/CLAUDE.local.md` is tracked as a labeled sample.** By
   convention this file is gitignored/personal; here it is committed deliberately as
   a visible reference. Root `.gitignore` is anchored (`/CLAUDE.local.md`) so it only
   ignores the factory's own root-level personal file, not the example's.

**Mechanics.** All relocations used `git mv` (history preserved, bodies unchanged).
No `src/` directory — the consumer half is named `example-project/` per its role.

## 2026-06-11 — Adopt the `.claude/` infrastructure layout

**Context.** The repo was a flat collection of 15 markdown files at the root — 10
skills (with `name:`/`description:` frontmatter) and 5 CLAUDE.md-style
project-instruction docs — with no organizing structure, no `CLAUDE.md`, and no
`.gitignore`. We adopted the typed `.claude/` project-infrastructure pattern
(`context/`, `hooks/`, `skills/`, `commands/`, `agents/`, `workflows/`).

**Decisions.**

1. **Empty layers are scaffolded, not fabricated.** `hooks/`, `commands/`,
   `agents/`, and `workflows/` each get a README explaining the layer's purpose.
   No example content is invented — they stay empty until a real need appears.
2. **Project-instruction docs live in `.claude/context/`.** The 5 frontmatter-less
   CLAUDE.md-style stack briefs (VSTO, C/C#, C++, Python, VBA) are reference
   context, not skills, so they belong under `context/`.
3. **`CLAUDE.md` is a library guide; the reusable pattern lives in `templates/`.**
   This repo is a library, so its `CLAUDE.md` documents the library itself.
   `templates/CLAUDE.md.template` is the portable starter that teaches the
   infrastructure pattern for use in other projects.

**Mechanics.** Files were relocated with `git mv` to preserve history; their bodies
were left byte-for-byte unchanged. Skill folders are named after each skill's
`name:` frontmatter value. No `src/` directory — this is a pure asset library.
