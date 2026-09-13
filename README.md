# Spec-Driven Company

A company where the truth lives in written specs, agents execute them, and status is visible without asking anyone.

This repository contains no code. Only the specs: the rules every AI coding agent reads first, and the documents a project grows from. Your agent installs everything else.

## Install: paste into your agent

Open your coding agent (Codex, Claude Code, Cursor, Copilot, Gemini CLI, any other) and paste the prompt for your situation. Not into the terminal, into the agent. Each prompt ends with a report: read it, open the links, and give the next task.

**1. Empty folder, your own stack.** Nothing gets installed. You tell the agent what to build with the next task.

```text
Set up Spec-Driven Company in this folder. Download AGENTS.md, CLAUDE.md, docs/README.md and docs/journal.md from https://raw.githubusercontent.com/eugeneshilow/spec-driven-company/main/ and save them here under the same paths. Read AGENTS.md and follow it from now on. Fill in docs/README.md and the first entry that is already in docs/journal.md; in the Stack section of AGENTS.md write "none yet". This is a local setup: no remote, no pull request, no deployment. Done when no placeholders in square brackets are left in the three files (links do not count). Report.
```

Then say what to build, for example: "Build a Telegram bot in Python with aiogram. Stop before the token." The rules take it from there: spec before code, the check before every commit, a stop at keys.

**2. Existing project.** Your code, your rules and your stack stay. The method comes on top.

```text
Set up Spec-Driven Company in this project. Download AGENTS.md, CLAUDE.md, docs/README.md and docs/journal.md from https://raw.githubusercontent.com/eugeneshilow/spec-driven-company/main/. Save each under the same path if that file does not exist here. If it exists, merge: use the downloaded structure and place every existing rule, word for word, into the section where it belongs; where two rules conflict keep the existing one and list the conflict in the report. Fill in the Stack section of AGENTS.md from what the project already uses: what it is made of, the check command, the run command; if there is no single check command, name the ones that exist. Install nothing, create no scripts. Fill in docs/README.md and the first entry of docs/journal.md from what the project already has; where nothing is known write "none yet", invent nothing. Work in a branch, as AGENTS.md says; if there is no remote, stop at the commit and give the command to merge. Done when no placeholders in square brackets are left in the three files (links do not count). Report.
```

**3. Empty folder, ready stack.** A web app with a database and an admin page where the status of the project is visible, built by your agent from the recipe inside the prompt. This is the stack vibecoding.ru runs on: Next.js, Tailwind, Convex. No versions are pinned: the agent installs what is current on the day you run it.

<details>
<summary>The prompt with the recipe. Open, copy the whole block, paste.</summary>

```text
Set up Spec-Driven Company in this folder with the Next.js and Convex stack. Download AGENTS.md, CLAUDE.md, docs/README.md and docs/journal.md from https://raw.githubusercontent.com/eugeneshilow/spec-driven-company/main/ and save them here under the same paths. Read AGENTS.md and follow it from now on. Then build the app by the recipe below. This is a local setup: work in this folder, no remote, no pull request, no deployment; if the folder is not a git repository, init it and end with one commit on main (AGENTS.md allows this for the first setup).

What is in it: Node.js current LTS and pnpm; Next.js with the App Router and TypeScript; Tailwind CSS; Convex for the database and server functions; Vitest for tests, ESLint and Prettier for the check. Deployment target is Vercel, not part of this setup. Use the Node and pnpm already installed if they are compatible; install only what is missing, upgrade nothing that works (a peer dependency that a new package demands is not an upgrade).

Build, in this order:
1. Create the Next.js app with TypeScript, Tailwind, ESLint and the App Router. The generator refuses a folder that is not empty and writes its own AGENTS.md, so scaffold into a temporary subfolder named scaffold-tmp with the agents file and git disabled, move the files up, delete the subfolder, and drop the template art: the generated README.md (the project's page is docs/README.md), the svg files in public/ and the Google font wiring. AGENTS.md, CLAUDE.md and docs/ stay as downloaded except the parts you are told to fill in: switch off both things that write Next's own rules into AGENTS.md, the generator flag and the config option that lets next dev regenerate it (agentRules: false), and list AGENTS.md and CLAUDE.md in .prettierignore.
2. Add Prettier and Vitest. Add one script "check" that runs the formatter check, the linter, the type check and the tests, in that order, and writes its result (green or red, with the time) to a small ignored file, so the admin page can show it. The type check needs Next's generated route types, so generate them inside the check before the type step.
3. Page /: the project name from docs/README.md, one sentence about what it is, and a link to /admin. Plain, readable, no template art.
4. Page /admin: the glass. It renders docs/README.md and docs/journal.md from the files as HTML (any small markdown library is fine), lists every decision (journal headings that carry ⚖️) with its date and name, and shows the result of the last check run from the file the check writes. Reading the files at request time is enough; no database is needed for this page.
5. One test: /admin lists at least the first decision from the journal. Make the check green.
6. Install Convex. Add the schema file and a client provider that renders the app without Convex while its URL variable is empty, and an .env.local.example that names the variables the Convex CLI will fill; make sure .gitignore does not hide the example file. Do not write server functions yet: their generated types appear only after a deployment exists. Do not run the Convex login: it creates a cloud deployment on the human's account, and that is an access decision. Prepare everything and stop with one line: "Convex is wired; run npx convex dev and log in when you want the database live."
7. Fill in the Stack section of AGENTS.md: what it is made of, the check command, the run command with the address. Fill in docs/README.md; the project name is the folder name unless told otherwise; invent no product requirements. Fill in the first entry that is already in docs/journal.md and add a second one above it, as a decision: Convex is wired but not logged in; what was installed, what was skipped, what the human does next.
8. Start the dev server, make one commit on main, and report.

Stop before: the Convex login (access), any deployment (publishes outside), any key in a file (keys; the file with the keys is .env.local, never committed).

Done when http://localhost:3000 answers with the project page, http://localhost:3000/admin answers and shows the journal with the first decision, the check is green, and no placeholders in square brackets are left in AGENTS.md, docs/README.md and docs/journal.md (links do not count). Report the two addresses, the check result, the commit, and the one line about Convex.
```

</details>

## What you get

- `AGENTS.md` — the rules: where the truth lives, how to work, git, the stack and the check, risk zones, decisions, structure, production, the report, the loop. Its Stack section is the one place that says what your project is made of and how to check and run it.
- `CLAUDE.md` — one line that points Claude Code to `AGENTS.md`. Other agents read `AGENTS.md` directly.
- `docs/README.md` — the one page of your project: what it is, decisions, where things are.
- `docs/journal.md` — decisions and why, append-only, newest first. The first entry is already there: you adopted the method.

## See it working

Open [vibecoding.ru](https://vibecoding.ru) right now. Everything there, the code, the pages, the news, the cards, is written by agents. One hundred percent, not ninety-nine. The author did not write a line. He wrote the rules and accepted the work. The operator opens three things and nothing else: `docs/`, `AGENTS.md` with `CLAUDE.md`, and the file with the keys. How it runs, live: [vibecoding.ru/open](https://vibecoding.ru/open).

## Why

Agents give one person the power of a team. Without a system they produce mess and need a permanent babysitter. Spec-Driven Company is the system: spec, pipeline, glass. The concept, in Russian, lives at [vibecoding.ru/sdc](https://vibecoding.ru/sdc). This repository is the practice.

Why no code here: code has versions, and versions need maintenance. A recipe in words does not go stale when a library does. Your agent reads it and uses whatever is current on the day you run it.

## Language

Everything in this repository is in English: files, commits, issues. Translations may live in their own place later.

## License

[CC BY 4.0](LICENSE). Use it, copy it, change it, sell what you build with it. Keep the attribution line at the bottom of `AGENTS.md`.

Author: Eugene Shilov, [vibecoding.ru](https://vibecoding.ru).
