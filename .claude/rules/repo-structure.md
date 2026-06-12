# Rule: repo structure

The repo is a **factory** with two halves. Keep them separate.

- **Factory vs. product.** Author meta-tooling (how to build assets) under the root
  `.claude/`. The produced assets and their showcase live under `example-project/`.
  Never put domain/product assets in the root `.claude/`.
- **No `src/`.** This is an asset library, not an application. Do not add a `src/`
  directory.
- **Stubs are scaffolded, never fabricated.** An empty layer gets a README
  describing its purpose. Do not invent example content to fill structure — wait
  for a concrete need.
- **Preserve history on moves.** Relocate or rename files with `git mv`, leaving
  bodies unchanged unless the task is explicitly to edit them.
- **One source of truth for history and rules.** Session history lives in
  `.claude/memory/`; binding constraints live in `.claude/rules/`. Do not
  reintroduce a `DECISIONS.md`.
