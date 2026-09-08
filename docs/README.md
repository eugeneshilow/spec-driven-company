# [Project name — the folder name if nobody told you]

One page. What this project is, what has been decided, where things are, how to check it. Replace every bracket. Keep it at one page: if it grows, something under it wants its own folder.

## What this is

[Two or three sentences: what the project does, for whom, and what "working" means.]

## Decisions

Decisions live in [journal.md](journal.md), newest first, each with a stable name. The ones that shape everything else:

- [⚖️ name — one line]

## Where things are

- `docs/` — the truth: this page, the journal, one file per zone.
- `AGENTS.md` — the rules every agent reads first.
- [`src/` or wherever the code lives — one line]
- [the file with the keys — its name and the note that it is never committed]

## How to check

One command that runs the formatter, the linter, the types and the tests. Agents run it before every commit; red means not done. No code yet: write "none yet".

```text
[your check command, for example: pnpm check, or: none yet]
```

## How to run

```text
[your run command and the address, for example: pnpm dev → http://localhost:3000]
```

## Zones

One file per zone of the project, each the canon of how that zone works right now.

- [zone.md — one line; a zone file appears with the zone's first rule, never empty]

## Status

Where the live status is visible: [a page, a dashboard, a command]. Docs describe how things work; they never hold the current numbers.
