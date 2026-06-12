# Rule: asset conventions

How assets in this repo are named, structured, and changed.

- **Skill folder == `name:` frontmatter.** A skill lives at `skills/<name>/SKILL.md`
  where `<name>` exactly equals the skill's `name:` value. Renaming a skill means
  renaming both.
- **Context docs are kebab-case** (`c-csharp-project-instructions.md`).
- **Memory files are dated** (`YYYY-MM-DD-<topic>.md`); rule files are themed and
  kebab-case (`asset-conventions.md`).
- **Edit assets in place.** When updating a skill or doc, edit it directly — never
  fork a copy alongside the original.
- **Skill `description:` must be trigger-laden.** It drives delegation, so lead with
  the use case and name concrete trigger phrases.
- **Ground volatile facts by referring out.** For details that drift between tool
  versions (e.g. the full list of agent frontmatter fields), point to the
  authoritative docs rather than hard-coding them.
