# AGENTS.md

Rules for every agent working in this repository. Read this file first: it is the map.

Spec-Driven Company (SDC) in one line: the truth lives in written specs, agents execute them, and status is visible without asking anyone.

## Before anything: classify the task

Every task is one of three kinds. Decide before reading files or touching git.

1. **Talk.** Explain, discuss, advise. Do not touch git.
2. **Read.** Read files, change nothing. Update `main` first, then read.
3. **Write.** Anything that may change the repository, including one line of docs. Preflight, separate branch, never write to `main`.

## Where the truth lives

- `docs/README.md` — one page: what this project is, the decisions made, where things are, how to check it.
- `docs/journal.md` — decisions and why: what was decided, what was rejected, in whose words. Append-only, newest first.
- `docs/<zone>.md` — the canon of one zone: how it works right now. One rule, written once, edited by replacement.

The pair at the root of `docs/` belongs to the whole project. Every subfolder of `docs/` carries its own pair: `README.md` (the summary of the folder) and `journal.md` (the thinking behind it). A new folder is born with both. A zone file is born with the zone's first rule; do not create empty ones.

If a rule is not written at an address, it does not exist. "Ask the person who remembers" is not an address.

Three kinds of truth, three homes. Decisions of meaning (what we build, for whom, in which voice) live in `docs/`. Tooling conventions (linter, formatter, versions) live in their config files; do not copy them into docs. Live data and status (users, orders, sensor states) live in the database; docs describe how it works, never what it currently says.

## How to work

1. **Work in a separate branch or worktree.** Nothing is written to `main` directly. Changes reach `main` through a pull request.
2. **No task without a done criterion.** If there is no way to check that the task is done, ask. Do not start.
3. **Spec before code.** Requirements, plan and design in one document before the first line of code.
4. **Canon before code.** A rule changes in `docs/` first, then in code and tests, in the same change. Never "code now, docs later".
5. **Tests hold the rules.** A rule that has already cost time or money gets a test. If you break a test, fix it before saying "done".
6. **Prepare, do not execute, in risk zones.** See the table below. A human presses the button.
7. **Report the outcome, not the effort.** Say what you did, what you did not do, and what you could not verify.

## Git

- No repository yet? `git init`, commit the setup on `main`, and say so in the report. This is the only direct write to `main` a project ever gets. A remote and pull requests come with the first code.
- Preflight for every write task: `git status`, `git fetch`, fast-forward `main`, then a new branch from fresh `main`. If `main` is dirty or ahead of origin, stop and say so.
- Branch name: `<agent>-<YYYY-MM-DD>-<topic>`, for example `codex-2026-09-02-signup-form` or `claude-2026-09-02-signup-form`.
- Commit at every whole step. A commit is a point you can return to. Only this task's changes go in; never secrets, never someone else's work in progress.
- Push the branch and open a pull request. Code always goes through a pull request. A change that touches only `docs/` and this file may be merged to `main` directly, unless `docs/README.md` says otherwise.
- After merge: update `main`, delete the branch and the worktree.

## The check

The project's check command lives in `docs/README.md` under "How to check" (formatter, linter, types, tests, in one line). Run it before every commit. Red means not done, whatever the reason. A warning that was already there is not a reason to call a human. No code yet? Write "none yet" there; do not invent a check for a project that has nothing to check.

## Risk zones: prepare, do not execute

| Always | Ask first | Never |
|---|---|---|
| work in a branch, write the spec, run the check, report | anything that moves money, touches keys or access, stores or sends personal data, publishes outside the repository, changes production settings | delete data, rewrite someone else's changes, force-push to `main`, put secrets into files or logs |

"Ask first" means: do everything up to the button, then stop and hand over one line with the choice. Do not start the discussion in the middle of the work.

## Decisions

A decision is a choice that could be reopened tomorrow. It is recorded in `docs/journal.md` as an entry with a stable name:

```
## 2026-09-02 15:01 · <agent> · ⚖️ signup-without-password · Sign-up by email link only

**Decided.** ...
**Rejected.** ... and why.
**Owner's words.** "..."
```

"Owner's words" is a quote from the human. If no human spoke and the task came as a pasted prompt, quote the prompt.

Rules around decisions:

- One rule has one home. Other documents link to it; they do not copy it.
- The canon changes by replacement. The old rule is deleted in the same commit; history lives in the journal and in git.
- Before proposing a change to architecture, URLs, data schema or process, read the journal for that zone. Decided questions are not reopened without the owner asking.
- Thinking that happened in chat and is not in the journal is unfinished work, like code without a commit.

When you find that you acted against a written rule, fix the cause before the symptom, top down: the rule is not written, write it; it is written in the wrong place, move it; it is written but nobody found it, make it findable from the place where the task starts. "I will be more careful" is not a fix.

## Structure

Seven is a trigger, not a target. Fewer things is better; a level should be readable at one glance. When the eighth file, folder, table, variable or script appears at one level, raise the question of grouping, and group only by meaning, never for the number. Two files of the same kind at one level is an early warning: ask whether they want a folder with a `README.md`.

`docs/README.md` stays at one page. If it grows, something under it wants its own folder.

## Production

Anything that will run without a human, a form, a webhook, a scheduled job, an integration, a new data source, is born with four things in one change:

1. the element itself;
2. its canon in `docs/`: where the input comes from, where it writes, known edges;
3. its glass: a place where its status is visible, a page or a line on an existing page;
4. its immunity: an outside check that fails loudly when the element is broken ("the form renders and the endpoint answers 200"), not a business metric.

Content and layout without a new flow of data or money are outside this rule.

## Report

Every write task ends with the same block, so the human can read it in ten seconds:

```
---
Outcome: merged | pull request open | committed (first setup only) | blocked
Link: <pull request or commit>
Files: <path> +a/-b, one per line
Not verified: <what you could not check and why>, or "nothing"
Next: one step that moves the project most, and why
```

## The loop

task in words → work → acceptance by the criterion → ship → observe → next task

Every unit of work is one full turn of this loop. The same loop runs at every scale: a feature, a product, a business zone, the company. Observation of the last turn is where the next task comes from.

---

Based on [Spec-Driven Company](https://github.com/eugeneshilow/spec-driven-company) by Eugene Shilov, CC BY 4.0. Keep this line when you copy the file.
