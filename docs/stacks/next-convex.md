# Stack: Next.js + Convex

The stack vibecoding.ru runs on. A web app with a database and an admin page where the status of the project is visible. This file is a spec: the agent reads it and installs what is current. No versions are pinned here on purpose.

## What is in it

- **Node.js**, current LTS, and **pnpm** as the package manager.
- **Next.js** with the App Router and TypeScript.
- **Tailwind CSS** for styling.
- **Convex** for the database and server functions.
- **Vitest** for tests, **ESLint** and **Prettier** for the check.
- Deployment target: **Vercel**. Not part of this setup; it is the first task after.

## What the agent builds

1. Install Node LTS and pnpm if missing. Create the Next.js app in this folder with TypeScript, Tailwind, ESLint and the App Router. Do not overwrite `AGENTS.md`, `CLAUDE.md` or `docs/`.
2. Add Prettier and Vitest. Add one script `check` that runs the formatter check, the linter, the type check and the tests, in that order. Write that command into `docs/README.md` under "How to check".
3. Page `/`: the project name from `docs/README.md`, one sentence about what it is, and a link to `/admin`. Plain, readable, no template art.
4. Page `/admin`: the glass. It renders `docs/README.md` and `docs/journal.md` from the files as HTML, lists every decision (journal headings that carry ⚖️) with its date and name, and shows the result of the last `check` run if one is recorded. Reading the files at request time is enough; no database is needed for this page.
5. One test: `/admin` lists at least the first decision from the journal. Make the check green.
6. Install Convex and add the minimal wiring the docs of Convex prescribe for Next.js. Do not run the Convex login. Logging in creates a cloud deployment on the human's account: this is an access decision, so prepare everything and stop with one line: "Convex is wired; run `npx convex dev` and log in when you want the database live."
7. Write `docs/README.md`: what this is, where things are, how to check, how to run. Add a journal entry: what was installed, what was skipped, what the human must do next.
8. Start the dev server and report.

## Where the agent stops

- Before the Convex login (access).
- Before any deployment (publishes outside).
- Before adding any key to a file (keys). The file with the keys is `.env.local`; it is never committed.

## Done criterion

- `http://localhost:3000` answers with the project page.
- `http://localhost:3000/admin` answers and shows the journal with the first decision.
- `pnpm check` is green.
- `docs/README.md` has "How to check" and "How to run" filled in.
- The report says what was installed, what was skipped, and the one line about Convex.
