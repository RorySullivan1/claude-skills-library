# memory/ — per-session journal (factory scope)

Timestamped, per-session notes: brief bullets recording what was done, what was
decided (with one-line rationale), and what was left open. This is the repo's
**append-only history** — consult it to answer "what happened and why", never to
override a rule.

## The boundary

- **`../rules/`** — short, always-binding constraints. CLAUDE.md declares them
  mandatory; Claude honors them every session without being asked.
- **`../context/`** — on-demand reference; Claude deep-reads only when relevant.
- **`memory/` (here)** — append-only session journal; informative, never
  authoritative over rules.

## Conventions

- **One file per working session:** `YYYY-MM-DD-<topic>.md`, kebab-case topic.
  Append `-HHMM` before the topic if a day has multiple sessions
  (`2026-06-12-1430-rules-refactor.md`).
- **Format:** one `#` heading, then brief bullets only — what was done, decisions
  made (each with a one-line why), open threads. Not prose essays, not a changelog
  of every edit.
- **Write an entry** at the end of any significant session, or right after a
  notable decision. Skip trivial sessions.
- **Entries are immutable.** History is corrected by appending a new entry, not by
  rewriting an old one.

## Future enforcement

A `SessionStart` hook could surface the most recent entries automatically at the
start of each session — a natural fit for `../hooks/` when the need is concrete.
Not built yet (rules: nothing is fabricated ahead of need).
