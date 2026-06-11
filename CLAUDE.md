# claude-skills-library

A **factory for Claude Code tooling.** This repo is where reusable `.claude/`
assets — skills, context briefs, hooks, commands, agents, workflows — are
*designed*, then handed off to downstream projects that actually run them. It is
**not an application** and has no `src/`. It has two halves with two distinct jobs:

```
.claude/            ← the FACTORY's design environment (how we author assets)
example-project/    ← a MOCK consumer project (what a produced .claude/ looks like)
```

## The two halves

### `.claude/` — the design environment

The factory's own `.claude/` is tooling for *building* assets, not the assets
themselves. It mirrors the standard layer taxonomy (`skills/`, `context/`,
`hooks/`, `commands/`, `agents/`, `workflows/`), but each layer here is scoped to
**authoring** the matching downstream asset type — e.g. `skills/` will hold
meta-skills that guide how to write a good `SKILL.md`, `context/` will hold the
authoring standards and conventions. Today these layers are **stubs** (a README
per layer describing what it will become); no meta-tooling is fabricated until a
concrete need appears. See `.claude/README.md`.

### `example-project/` — the produced layout

A mock downstream repo that shows what the factory ships. It's laid out exactly
like a real project a developer would copy:

```
example-project/
├── CLAUDE.md            ← the project's session contract
├── CLAUDE.local.md      ← sample personal notes (gitignored in a real repo)
└── .claude/
    ├── skills/          ← 10 domain skill bundles (the worked examples)
    ├── context/         ← 5 stack-brief docs + manifest
    ├── hooks/ commands/ agents/ workflows/   ← scaffolds, ready to fill
    ├── settings.json · README.md · DECISIONS.md
```

The skills and context docs that used to live at the repo root now live here, as
the canonical worked examples. To bootstrap a new project, copy `example-project/`
(or just the `.claude/<asset>` folders you want) into the target repo.

## The skills (in `example-project/.claude/skills/`)

Each skill is a self-contained bundle at `skills/<name>/SKILL.md`. The folder name
always equals the skill's `name:` frontmatter value.

| Skill | Purpose |
|---|---|
| `VSTO-development` | Write/architect/debug VSTO Office add-ins (C#/VB.NET) |
| `VSTO-distribution` | Package & deploy VSTO add-ins (ClickOnce, MSI/WiX, GPO) |
| `VSTO-maintenance` | Troubleshoot & maintain deployed VSTO add-ins |
| `VSTO-review` | Review VSTO code (COM lifecycle, event hygiene, threading) |
| `python-development` | Write new Python code |
| `python-review` | Review Python code for bugs/security/design |
| `python-maintenance` | Debug, refactor, modernize existing Python |
| `python-deployment` | Package, containerize, ship Python to production |
| `technical-documentation-drafter` | Developer-facing docs (`docs/` folder) |
| `user-guide-drafter` | End-user, non-technical documentation |

## The context docs (in `example-project/.claude/context/`)

Five longer-form, CLAUDE.md-style system prompts — one per language/stack — that
predate the skill split. They're reference material: drop one into a project's
`CLAUDE.md` (or `.claude/context/`) to give Claude a full operating brief for that
stack. See `example-project/.claude/context/README.md`.

## Conventions

- **Skill folder = `name:` frontmatter.** Renaming a skill means renaming both.
- **Context docs are kebab-case** (`c-csharp-project-instructions.md`).
- **Contents are authoritative as-is.** When updating a skill, edit its `SKILL.md`
  in place; don't fork copies.
- **Factory vs. product.** Author the *how-to* (meta-tooling) under `.claude/`;
  the produced assets and their showcase live under `example-project/`.

## Using an asset elsewhere

- **A skill:** copy `example-project/.claude/skills/<name>/` into the target
  project's `.claude/skills/`.
- **A context doc:** copy the file into the target's `.claude/context/`, or paste
  its body into that project's `CLAUDE.md`.
- **The whole pattern:** copy `example-project/` as a starting point — its
  `CLAUDE.md`, `CLAUDE.local.md`, and `.claude/` scaffold are a ready-to-fill repo
  skeleton. See `example-project/.claude/README.md` for what each layer is for.
