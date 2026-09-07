# Spec-Driven Company

A company where the truth lives in written specs, agents execute them, and status is visible without asking anyone.

This repository is the starter. It begins with one file, [`AGENTS.md`](AGENTS.md): the rules every AI coding agent reads before touching your project. Everything else grows from it.

## Start here

1. Copy `AGENTS.md` into the root of your repository.
2. If you use Claude Code, add `CLAUDE.md` with a single line: `@AGENTS.md`. Codex, Cursor and most other agents read `AGENTS.md` directly.
3. Give your agent the next task. It now works in a branch, asks for a done criterion, writes the spec before the code, and stops at money, keys and customer data.

That is the whole first step. No libraries, no scripts, no framework.

## What grows next

The starter grows one file at a time, in the order a real project needs them:

- `docs/README.md` — the one-page summary of your project (where the truth lives).
- `docs/journal.md` — decisions and why, append-only.
- `docs/<zone>.md` — the canon of one zone: bookings, payments, notifications, letters.
- a gate in CI that refuses broken rules, and a passport for everything that runs in production.
- `docs/handoff.md` — seven lines by which the next operator enters the machine without you.

## Why

Agents give one person the power of a team. Without a system they produce mess and need a permanent babysitter. Spec-Driven Company is the system: spec, pipeline, glass. The concept, in Russian, lives at [vibecoding.ru/sdc](https://vibecoding.ru/sdc). This repository is the practice.

## Language

Everything in this repository is in English: files, commits, issues. Translations may live in their own place later.

## License

[CC BY 4.0](LICENSE). Use it, copy it, change it, sell what you build with it. Keep the attribution line at the bottom of `AGENTS.md`.

Author: Eugene Shilov, [vibecoding.ru](https://vibecoding.ru).
