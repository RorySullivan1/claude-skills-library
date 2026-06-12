# Rule: code conventions

How changes are made in this project. Always in force.

- **Branch per change.** No direct commits to the default branch; one branch per
  unit of work.
- **Conventional-commit-style messages.** Imperative subject, typed prefix
  (`feat:`, `fix:`, `docs:`…).
- **Format before commit.** Run the project's configured formatter/linter on Python
  before committing; do not commit unformatted code.
- **Skill folder == `name:` frontmatter.** A skill lives at `skills/<name>/SKILL.md`
  where `<name>` equals its `name:` value.
