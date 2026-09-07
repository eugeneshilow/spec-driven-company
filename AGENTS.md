# AGENTS.md

Rules for every agent working in this repository. Read this file first: it is the map.

Spec-Driven Company (SDC) in one line: the truth lives in written specs, agents execute them, and status is visible without asking anyone.

## Where the truth lives

- `docs/README.md` — one page: what this project is, the decisions made, where things are.
- `docs/<zone>.md` — the canon of one zone: how it works right now. One rule, written once, edited by replacement.
- `docs/journal.md` — decisions and why: what was decided, what was rejected, in whose words. Append-only, newest first.

If a rule is not written at an address, it does not exist. "Ask the person who remembers" is not an address.

## How to work

1. **Work in a separate branch or worktree.** Nothing is written to `main` directly. Changes reach `main` through a pull request.
2. **No task without a done criterion.** If there is no way to check that the task is done, ask. Do not start.
3. **Spec before code.** Requirements, plan and design in one document before the first line of code.
4. **Canon before code.** A rule changes in `docs/` first, then in code and tests, in the same change. Never "code now, docs later".
5. **Tests hold the rules.** A rule that has already cost time or money gets a test. If you break a test, fix it before saying "done".
6. **Prepare, do not execute, in risk zones:** money, access and keys, customer data, anything published outside. A human presses the button.
7. **Report the outcome, not the effort.** Say what you did, what you did not do, and what you could not verify.

## The loop

task in words → work → acceptance by the criterion → ship → observe → next task

Every unit of work is one full turn of this loop. The same loop runs at every scale: a feature, a product, a business zone, the company.

---

Based on [Spec-Driven Company](https://github.com/eugeneshilow/spec-driven-company) by Eugene Shilov, CC BY 4.0. Keep this line when you copy the file.
