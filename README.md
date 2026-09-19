*English ∙ [Русский](lang/ru/README.md) ∙ [Español](lang/es/README.md)*

# Spec-Driven Company

A company where the truth lives in written specs, agents execute them, and status is visible without asking anyone.

This repository contains no code. Only the specs: the rules every AI coding agent reads first, and the documents a project grows from. Your agent installs everything else.

## Install: paste into your agent

Open your coding agent (Codex, Claude Code, Cursor, Copilot, Gemini CLI, any other) and paste the prompt for your situation. Not into the terminal, into the agent. Each prompt ends with a report: read it, open the links, and give the next task.

Every prompt builds the same layout. You create one folder and open it in your agent; the agent makes the rest:

```text
my-app/          the project folder: open this one in your agent
├─ AGENTS.md     pointer: the rules are in main/
├─ CLAUDE.md     pointer for Claude Code
├─ main/         the repository, a clean mirror of main; never edited by hand
└─ _wt/          one worktree per task, named after its branch; deleted after merge
```

If the folder lives on a cloud drive (Dropbox, iCloud, OneDrive), exclude `_wt/` and every `node_modules` from sync, or keep projects outside the drive.

**1. Empty folder, your own stack.** Nothing gets installed. You tell the agent what to build with the next task.

```text
Set up Spec-Driven Company in this folder. This folder is the project folder: create main/ and _wt/ in it. Download AGENTS.md, CLAUDE.md, CODEX.md, docs/README.md and docs/journal.md from https://raw.githubusercontent.com/eugeneshilow/spec-driven-company/main/ and save them into main/ under the same paths. In this folder write two pointer files: AGENTS.md with the text "This is the project folder. The repository is main/; worktrees live in _wt/, one per task. Read main/AGENTS.md first and follow it. Nothing is edited in main/ by hand." and CLAUDE.md with the single line "@main/AGENTS.md". Read main/AGENTS.md and follow it from now on. Fill in main/docs/README.md and the first entry that is already in main/docs/journal.md; in the Stack section of main/AGENTS.md write "none yet" in all three lines. Then git init -b main in main/ and make one commit on main; AGENTS.md allows this for the first setup. This is a local setup: no remote, no pull request, no deployment. Done when main/ holds the five files with no placeholders in square brackets left (links do not count), _wt/ exists, the two pointer files are here, and git log in main/ shows one commit. Report.
```

Then say what to build, for example: "Build a Telegram bot in Python with aiogram. Stop before the token." The rules take it from there: spec before code, the check before every commit, a stop at keys.

**2. Existing project.** Your code, your rules and your stack stay. The method comes on top.

```text
Set up Spec-Driven Company in this project. This folder becomes the project folder: create a subfolder main/ and move everything else that is here into it, the .git folder included, so the repository with its history now lives in main/; create _wt/ next to it. In this folder write two pointer files: AGENTS.md with the text "This is the project folder. The repository is main/; worktrees live in _wt/, one per task. Read main/AGENTS.md first and follow it. Nothing is edited in main/ by hand." and CLAUDE.md with the single line "@main/AGENTS.md". Download AGENTS.md, CLAUDE.md, CODEX.md, docs/README.md and docs/journal.md from https://raw.githubusercontent.com/eugeneshilow/spec-driven-company/main/. Save each into main/ under the same path if that file does not exist there. If it exists, merge: use the downloaded structure and place every existing rule, word for word, into the section where it belongs; where two rules conflict keep the existing one, drop the downloaded one, and list the conflict in the report. If the default branch is master, rename it to main first. Fill in the Stack section of main/AGENTS.md from what the project already uses: what it is made of, the check command, the run command; if there is no single check command, name the ones that exist. Install nothing, create no scripts. Fill in main/docs/README.md and the first entry of main/docs/journal.md from what the project already has; where nothing is known write "none yet", invent nothing. Do this in a worktree under _wt/, as main/AGENTS.md says; the change touches only rules and docs, so merge it into main yourself, remove the worktree, and if there is a remote push main. Done when no placeholders in square brackets are left in main/AGENTS.md, main/docs/README.md and main/docs/journal.md (links do not count), the two pointer files are here, and the project runs from main/ as it did before. Report.
```

**3. Empty folder, ready stack.** Pick a row, open its prompt below the table, copy the whole block, paste. The recipe lives inside the prompt; no versions are pinned: the agent installs what is current on the day you run it.

| Stack | What you get | Where it runs |
|---|---|---|
| Next.js · Tailwind · Convex | a web app with a database and an admin page where the status of the project is visible; the stack vibecoding.ru runs on | on your machine only |
| Next.js · Tailwind · Convex · GitHub · Vercel | the same app, plus a private repository, a check on every pull request, a production address that redeploys on every merge, and the database in the cloud | online; three logins are yours: GitHub, Vercel, Convex |

<details>
<summary>Local prompt: Next.js · Tailwind · Convex. Open, copy the whole block, paste.</summary>

```text
Set up Spec-Driven Company in this folder with the Next.js and Convex stack. This folder is the project folder: create main/ and _wt/ in it. Download AGENTS.md, CLAUDE.md, CODEX.md, docs/README.md and docs/journal.md from https://raw.githubusercontent.com/eugeneshilow/spec-driven-company/main/ and save them into main/ under the same paths. In this folder write two pointer files: AGENTS.md with the text "This is the project folder. The repository is main/; worktrees live in _wt/, one per task. Read main/AGENTS.md first and follow it. Nothing is edited in main/ by hand." and CLAUDE.md with the single line "@main/AGENTS.md". Read main/AGENTS.md and follow it from now on. Then build the app by the recipe below, inside main/. This is a local setup: no remote, no pull request, no deployment; git init -b main in main/ and end with one commit on main (AGENTS.md allows this for the first setup). Every task after this setup goes to a worktree under _wt/, as main/AGENTS.md says.

What is in it: Node.js and pnpm; Next.js with the App Router and TypeScript; Tailwind CSS; Convex for the database and server functions; Vitest for tests, ESLint and Prettier for the check. Deployment target is Vercel, not part of this setup. Take current stable releases, LTS where there is one, never a pre-release. Use the Node and pnpm already installed if they are compatible with this stack; if no compatible Node is present, install the current LTS. Install only what is missing, upgrade nothing that works (a peer dependency that a new package demands is not an upgrade).

Build, in this order:
0. Before the first command, fill in main/docs/README.md from this recipe: the project name is the folder name unless told otherwise, what it is made of, what is done when. Invent no product requirements. AGENTS.md wants the spec before the code; this recipe is the spec. After the build, correct it to what was actually built.
1. Create the Next.js app in main/ with TypeScript, Tailwind, ESLint and the App Router. The generator refuses a folder that is not empty and writes its own AGENTS.md, so scaffold into a temporary subfolder main/scaffold-tmp with the agents file and git disabled, move the files up into main/, delete the subfolder, and drop the template art: the generated README.md (the project's page is docs/README.md), the svg files in public/ and the Google font wiring. AGENTS.md, CLAUDE.md, CODEX.md and docs/ stay as downloaded except the parts you are told to fill in: switch off both things that write Next's own rules into AGENTS.md, the generator flag (--no-agents-md, or whatever the current --help calls it) and the config option that lets next dev regenerate it (agentRules: false), and list AGENTS.md, CLAUDE.md and CODEX.md in .prettierignore.
2. Add Prettier and Vitest. Add one script "check" that runs the formatter check, the linter, the type check and the tests, in that order, and writes its result (green or red, with the time) to a small ignored file, so the admin page can show it. The type check needs Next's generated route types, so generate them inside the check before the type step.
3. Page /: the project name from docs/README.md, one sentence about what it is, and a link to /admin. Plain, readable, no template art.
4. Page /admin: the glass. It renders docs/README.md and docs/journal.md from the files as HTML (any small markdown library is fine), lists every decision (journal headings that carry ⚖️) with its date and name, and shows the result of the last check run from the file the check writes. Reading the files at request time is enough; no database is needed for this page.
5. One test: /admin lists at least the first decision from the journal. Make the check green.
6. Install Convex. Add the schema file with no tables yet, a client provider that renders the app without Convex while its URL variable is empty, and an .env.local.example that names the variables the Convex CLI will fill (CONVEX_DEPLOYMENT and NEXT_PUBLIC_CONVEX_URL); make sure .gitignore does not hide the example file. Do not write server functions yet: their generated types appear only after a deployment exists. Do not run the Convex login: it creates a cloud deployment on the human's account, and that is an access decision. Prepare everything and stop with one line: "Convex is wired; run npx convex dev and log in when you want the database live."
7. Fill in the Stack section of AGENTS.md: what it is made of, the check command, the run command with the address. Bring docs/README.md in line with what was built. Fill in the first entry that is already in docs/journal.md and add a second one above it, as a decision: Convex is wired but not logged in; what was installed, what was skipped, what the human does next.
8. Start the dev server from main/, make one commit on main, and report.

Stop before: the Convex login (access), any deployment (publishes outside), any key in a file (keys; the file with the keys is .env.local, never committed).

Done when http://localhost:3000 (or the port you chose, if 3000 is taken) answers with the project page, /admin answers and shows the journal with the first decision, the check is green, no placeholders in square brackets are left in main/AGENTS.md, main/docs/README.md and main/docs/journal.md (links do not count), _wt/ exists and the two pointer files are here. Report the two addresses, the check result, the commit, and the one line about Convex.
```

</details>

<details>
<summary>Online prompt: Next.js · Tailwind · Convex · GitHub · Vercel. Open, copy the whole block, paste.</summary>

```text
Set up Spec-Driven Company in this folder with the Next.js and Convex stack and take it online: a private GitHub repository, Vercel, and Convex in the cloud. This folder is the project folder: create main/ and _wt/ in it. Download AGENTS.md, CLAUDE.md, CODEX.md, docs/README.md and docs/journal.md from https://raw.githubusercontent.com/eugeneshilow/spec-driven-company/main/ and save them into main/ under the same paths. In this folder write two pointer files: AGENTS.md with the text "This is the project folder. The repository is main/; worktrees live in _wt/, one per task. Read main/AGENTS.md first and follow it. Nothing is edited in main/ by hand." and CLAUDE.md with the single line "@main/AGENTS.md". Read main/AGENTS.md and follow it from now on. Then build the app by the recipe below, inside main/. The local part ends with git init -b main in main/ and one commit on main (AGENTS.md allows this for the first setup); everything after the push goes through a worktree under _wt/ and a pull request, as main/AGENTS.md says.

By pasting this prompt I authorize: a private GitHub repository named after the project folder, a Vercel project connected to it, and Convex deployments on my account. Three logins are mine: before the first command that needs one, check gh auth status and vercel whoami; where a login is missing, run gh auth login or vercel login and wait for me; the Convex command opens the browser itself. No account yet? I create it on the same page the login opens; that is the same step. Every time you stop for me, write it in one shape: first line the one action; then the exact link and the clicks in order; then what to paste or say back; for a login, the link and the code the command printed; nothing else above it.

What is in it: Node.js current LTS and pnpm; Next.js with the App Router and TypeScript; Tailwind CSS; Convex for the database and server functions; Vitest for tests, ESLint and Prettier for the check; GitHub for the repository and the check on pull requests; Vercel for hosting. Take current stable releases, LTS where there is one, never a pre-release. Use the Node and pnpm already installed if they are compatible; install only what is missing, upgrade nothing that works (a peer dependency that a new package demands is not an upgrade).

Build, in this order:
0. Before the first command, fill in main/docs/README.md from this recipe: the project name is the folder name unless told otherwise, what it is made of, what is done when. Invent no product requirements. AGENTS.md wants the spec before the code; this recipe is the spec. After the build, correct it to what was actually built.
1. Create the Next.js app in main/ with TypeScript, Tailwind, ESLint and the App Router. The generator refuses a folder that is not empty and writes its own AGENTS.md, so scaffold into a temporary subfolder main/scaffold-tmp with the agents file and git disabled, move the files up into main/, delete the subfolder, and drop the template art: the generated README.md (the project's page is docs/README.md), the svg files in public/ and the Google font wiring. AGENTS.md, CLAUDE.md, CODEX.md and docs/ stay as downloaded except the parts you are told to fill in: switch off both things that write Next's own rules into AGENTS.md, the generator flag (--no-agents-md, or whatever the current --help calls it) and the config option that lets next dev regenerate it (agentRules: false), and list AGENTS.md, CLAUDE.md and CODEX.md in .prettierignore.
2. Add Prettier and Vitest. Add one script "check" that runs the formatter check, the linter, the type check and the tests, in that order, and writes its result (green or red, with the time) to a small ignored file, so the admin page can show it. The type check needs Next's generated route types, so generate them inside the check before the type step.
3. Page /: the project name from docs/README.md, one sentence about what it is, and a link to /admin. Plain, readable, no template art.
4. Page /admin: the glass. It renders docs/README.md and docs/journal.md from the files as HTML (any small markdown library is fine), lists every decision (journal headings that carry ⚖️) with its date and name, shows the result of the last check run from the file the check writes, and shows the commit hash and the production address when Vercel's build variables provide them (VERCEL_GIT_COMMIT_SHA, VERCEL_PROJECT_PRODUCTION_URL), "local" otherwise. Reading the files at request time is enough; no database is needed for this page.
5. One test: /admin lists at least the first decision from the journal. Make the check green.
6. Install Convex. Add the schema file with no tables yet, a client provider that renders the app without Convex while its URL variable is empty, and an .env.local.example that names the variables the Convex CLI will fill (CONVEX_DEPLOYMENT and NEXT_PUBLIC_CONVEX_URL); make sure .gitignore does not hide the example file. Then run npx convex dev --once: it logs me in, creates the dev deployment and writes .env.local, which is never committed. Do not write server functions yet.
7. Fill in the Stack section of main/AGENTS.md: what it is made of, the check command, the run command with the address. Bring docs/README.md in line with what was built. Fill in the first entry that is already in docs/journal.md.
8. Start the dev server from main/, check that / and /admin answer, make one commit on main.
9. GitHub: from main/, create a private repository named after the project folder and push main (gh repo create <name> --private --source=. --push).
10. From here on, work in one worktree under _wt/ on a branch <agent>-<date>-go-online and finish with one pull request. In it: .github/workflows/check.yml that installs pnpm and runs the check command on every pull request and on every push to main; vercel.json with the build command "npx convex deploy --cmd 'pnpm build'", which deploys Convex to production and sets the database URL for the build; docs/deploy.md, the canon of the way out: repository, the check, Vercel, Convex, where the keys live, how to roll back; .github/workflows/prod-alive.yml that requests the address in the repository variable PROD_URL every hour and fails loudly when it does not answer 200; a Deploy line in the Stack section ("push to main → Vercel"); and a second journal entry above the first, as a decision: the project is online, what was created where, what the human does next.
11. Vercel: from main/, run vercel link --yes --project <name of the project folder> (not the folder main/), then vercel git connect so every push to main deploys; if it asks to install the Vercel app on GitHub, give me the link it printed and wait. Convex production needs a deploy key that only I can create: get the dashboard address with npx convex dashboard --no-open, then stop with exactly this: "Create a production deploy key and paste it as your next message. Where: <that link> → Settings → Deploy Keys → Generate production deploy key → copy." Add what I paste with vercel env add CONVEX_DEPLOY_KEY production; never write it to a file.
12. Open the pull request, wait for the check, merge it (I said so by pasting this prompt), fast-forward main in main/, remove the worktree and the branch. The merge deploys. Wait for the deployment, take the production address, set it as the repository variable PROD_URL (gh variable set PROD_URL), and request the address once yourself.
13. Report.

Stop before: making the repository public, deleting anything, writing any key into a file (the file with the local keys is .env.local, never committed).

Done when http://localhost:3000 (or the port you chose, if 3000 is taken) answers with the project page locally, the repository exists with main pushed, the pull request's check ran green and the pull request is merged, the production address answers 200 with the project page and its /admin shows the journal with two decisions, no placeholders in square brackets are left in main/AGENTS.md, main/docs/README.md and main/docs/journal.md (links do not count), _wt/ is empty again and the two pointer files are here. Report the repository address, the production address, the check run, the commit, and what remains for me.
```

</details>

## What you get

- `AGENTS.md` — the rules: where the truth lives, how to work, answers the human can use, git, the stack and the check, risk zones, decisions, structure, production, the report, the loop. Its Stack section is the one place that says what your project is made of and how to check and run it.
- `CLAUDE.md` — one line that points Claude Code to `AGENTS.md`. Other agents read `AGENTS.md` directly.
- `CODEX.md` — what is specific to Codex on top of `AGENTS.md`: links and media in Codex Desktop. It never weakens the rules.
- `docs/README.md` — the one page of your project: what it is, decisions, where things are.
- `docs/journal.md` — decisions and why, append-only, newest first. The first entry is already there: you adopted the method.
- Two pointer files in the project folder, `AGENTS.md` and `CLAUDE.md`, are written by the prompt, not downloaded: they send any agent opened at the project folder to `main/`.

## See it working

Open [vibecoding.ru](https://vibecoding.ru) right now. Everything there, the code, the pages, the news, the cards, is written by agents. One hundred percent, not ninety-nine. The author did not write a line. He wrote the rules and accepted the work. The operator opens three things and nothing else: `docs/`, `AGENTS.md` with `CLAUDE.md` and `CODEX.md`, and the file with the keys. How it runs, live: [vibecoding.ru/open](https://vibecoding.ru/open).

## Why

Agents give one person the power of a team. Without a system they produce mess and need a permanent babysitter. Spec-Driven Company is the system: spec, pipeline, glass. The concept, in Russian, lives at [vibecoding.ru/sdc](https://vibecoding.ru/sdc). This repository is the practice.

**Why no code here.** Code has versions, and versions need maintenance. A recipe in words does not go stale when a library does. Your agent reads it and uses whatever is current on the day you run it.

**Why the agent does everything, even what a script could do in a second.** Because the scarce thing is your time and attention, not tokens. Setting a project up by hand is twenty small decisions and an hour; pasting a prompt is one decision and ten minutes of the agent's time, at a token cost that keeps falling. Two things keep this trade honest: every prompt ends with a done criterion the agent has to meet, and the prompts are re-run with clean agents after every change to the recipe.

**Why this installer cannot go stale.** It has nothing that ages: no versions, no flags, no lockfile. The agent takes today's stable releases (LTS where there is one, never a pre-release) and reads today's `--help` instead of yesterday's options. When a library changes its shape, the recipe still says what to reach, and the agent finds the new way there.

## Languages

The English files at the root are the source. Translations live in `lang/<code>/` and mirror the file paths one to one: `lang/ru/AGENTS.md` is `AGENTS.md` in Russian, and the prompts in `lang/ru/README.md` download the Russian files, so the agent keeps docs, journal and reports in that language. A change to an English file and to its translations ships in one pull request; the agent translates. Commits, issues and this README stay in English. Want another language? Add `lang/<code>/` with the same six files, or tell your agent: "translate the downloaded files into <language>, keep the structure and the attribution line".

## License

[CC BY 4.0](LICENSE). Use it, copy it, change it, sell what you build with it. Keep the attribution line at the bottom of `AGENTS.md`.

Author: Eugene Shilov, [vibecoding.ru](https://vibecoding.ru).
