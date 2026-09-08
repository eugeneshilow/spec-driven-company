# Spec-Driven Company

A company where the truth lives in written specs, agents execute them, and status is visible without asking anyone.

This repository contains no code. Only the specs: the rules every AI coding agent reads first, and the documents a project grows from. Your agent installs everything else.

## Install: paste into your agent

Open your coding agent (Codex, Claude Code, Cursor, Copilot, Gemini CLI, any other) in an empty folder or in your existing project and paste one of these. Not into the terminal, into the agent.

**1. Vanilla.** Nothing gets installed. Works for any project, any language, any stack.

```text
Set up Spec-Driven Company in this folder. Download AGENTS.md, CLAUDE.md, docs/README.md and docs/journal.md from https://raw.githubusercontent.com/eugeneshilow/spec-driven-company/main/ and save them here under the same paths. Read AGENTS.md and follow it from now on. Then fill docs/README.md with what this project is, write the first entry in docs/journal.md, and report.
```

**2. With a stack.** The same, plus a working web app and an admin page, built by your agent from a written spec. This is the stack vibecoding.ru runs on: Next.js, Tailwind, Convex.

```text
Set up Spec-Driven Company in this folder with the Next.js and Convex stack. Download AGENTS.md, CLAUDE.md, docs/README.md, docs/journal.md and docs/stacks/next-convex.md from https://raw.githubusercontent.com/eugeneshilow/spec-driven-company/main/ and save them here under the same paths, except the stack file: save it as docs/stack.md. Read AGENTS.md and follow it from now on. Then follow docs/stack.md. Stop when http://localhost:3000 and http://localhost:3000/admin are up, and report.
```

Both prompts end with a report from your agent. Read it, open the links, and give the next task.

## What you get

- `AGENTS.md` — the rules: where the truth lives, how to work, git, the check, risk zones, decisions, structure, production, the report, the loop.
- `CLAUDE.md` — one line that points Claude Code to `AGENTS.md`. Other agents read `AGENTS.md` directly.
- `docs/README.md` — the one page of your project: what it is, decisions, where things are, how to check.
- `docs/journal.md` — decisions and why, append-only, newest first. The first entry is already there: you adopted the method.
- `docs/stack.md` (stack prompt only) — the spec your agent built the app from. Change it, and the agent changes the app.

## Stacks

A stack is a spec in words, not a template with versions. Agents read it and install whatever is current. The list lives in [`docs/stacks/`](docs/stacks/README.md). Add yours with a pull request: one file, the same shape.

## See it working

Open [vibecoding.ru](https://vibecoding.ru) right now. Everything there, the code, the pages, the news, the cards, is written by agents. One hundred percent, not ninety-nine. The author did not write a line. He wrote the rules and accepted the work. The operator opens three things and nothing else: `docs/`, `AGENTS.md` with `CLAUDE.md`, and the file with the keys. How it runs, live: [vibecoding.ru/open](https://vibecoding.ru/open).

## Why

Agents give one person the power of a team. Without a system they produce mess and need a permanent babysitter. Spec-Driven Company is the system: spec, pipeline, glass. The concept, in Russian, lives at [vibecoding.ru/sdc](https://vibecoding.ru/sdc). This repository is the practice.

Why no code here: code has versions, and versions need maintenance. A spec in words does not go stale when a library does. Your agent reads the spec and uses whatever is current on the day you run it.

## Language

Everything in this repository is in English: files, commits, issues. Translations may live in their own place later.

## License

[CC BY 4.0](LICENSE). Use it, copy it, change it, sell what you build with it. Keep the attribution line at the bottom of `AGENTS.md`.

Author: Eugene Shilov, [vibecoding.ru](https://vibecoding.ru).
