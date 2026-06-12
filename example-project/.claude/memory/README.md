# memory/ — per-session journal

Timestamped, per-session notes: brief bullets recording what was done, what was
decided (with one-line rationale), and what was left open. This is the project's
**append-only history** — consult it for "what happened and why", never to override
a rule.

> This is the `example-project/` showcase. The entry below is illustrative — it
> shows what a real session journal looks like, not live history.

## The boundary

- **`../rules/`** — short, always-binding constraints, honored every session.
- **`../context/`** — on-demand reference; deep-read only when relevant.
- **`memory/` (here)** — append-only session journal; informative, never
  authoritative over a rule.

## Conventions

- **One file per working session:** `YYYY-MM-DD-<topic>.md`, kebab-case topic.
  Append `-HHMM` before the topic if a day has multiple sessions.
- **Format:** one `#` heading, then brief bullets only — what was done, decisions
  (each with a one-line why), open threads. Not prose; not a per-edit changelog.
- **Write an entry** at the end of a significant session or after a notable
  decision. Skip trivial sessions.
- **Entries are immutable** — correct history by appending, not rewriting.
