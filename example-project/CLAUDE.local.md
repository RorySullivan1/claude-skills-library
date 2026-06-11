<!--
  CLAUDE.local.md — personal, machine-local memory. Loads alongside CLAUDE.md.

  In a REAL project this file is gitignored and never committed: it's for
  shortcuts, paths, and preferences that are yours alone. It is checked in HERE
  only because example-project/ is a reference you read — so you can see what one
  looks like. When you copy this skeleton into your own repo, add CLAUDE.local.md
  to that repo's .gitignore and put your own machine-local notes in it.
-->

# Personal notes — example-project

## Shortcuts
- `bd` → build the add-in and stage the ClickOnce package.
- `pt` → run the Python tooling test suite.

## Local paths & environment
- Add-in solution: `C:\work\example-project\src\AddIn\AddIn.sln`.
- Python venv: `.venv` (interpreter pinned in `tools/.python-version`).
- Test workbook lives outside the repo at `C:\work\fixtures\sample.xlsx`.

## Reminders to self
- Re-register the dev cert after a machine reboot before debugging the add-in.
- ClickOnce publish version must be bumped before each test deployment.
