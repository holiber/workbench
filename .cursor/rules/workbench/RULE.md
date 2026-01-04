# Workbench – Cursor Rules

Before implementing or pushing any changes in this repository:

1. You MUST read and follow the rules defined in `CONTRIBUTING.md`.
2. Treat `CONTRIBUTING.md` as the single source of truth.
3. Do NOT reimplement, duplicate, or reinterpret those rules here.

---

## Enforcement

- If a change violates `CONTRIBUTING.md`, it must be considered incorrect.
- If any assumption is unclear:
  - Create or comment on an issue to clarify.
  - Prefer the strictest interpretation of the rules until clarified.
- Do NOT modify files under `.cursor/rules/**` unless explicitly instructed.

---

## Scope

These rules apply to all changes made by Cursor Agent.

When in doubt: stop and re-check `CONTRIBUTING.md`.

---

## Bugs

If you encounter a bug that is **outside the scope of the current issue**:
- Do NOT fix it opportunistically.
- Create a new issue describing the bug and reference it.
- Continue working only on the original task unless explicitly instructed otherwise.

---

## Agent Status Reporting (Required)

You MUST always report your current status by adding a status badge:

- At the **top of the Issue description**
- At the **top of the Pull Request description**

The badge MUST include:
- Your agent id
- Current status
- Current time

When a PR is created, the Issue description MUST be updated to include a link to that PR.

### Status badge examples

**On it**
![🤖 agent duckster: on it! · 14:15](https://img.shields.io/badge/🤖%20agent%20duckster-on%20it!%20%C2%B7%2014%3A15-%23007ec6?style=flat&labelColor=eeeeee)

**Rebasing**
![🤖 agent duckster: rebasing… · 14:15](https://img.shields.io/badge/🤖%20agent%20duckster-rebasing%E2%80%A6%20%C2%B7%2014%3A15-yellow?style=flat&labelColor=eeeeee)

**Waiting for CI**
![🤖 agent duckster: waiting%20ci… · 14:15](https://img.shields.io/badge/🤖%20agent%20duckster-waiting%20ci%E2%80%A6%20%C2%B7%2014%3A15-yellow?style=flat&labelColor=eeeeee)

**Fixing CI**
![🤖 agent duckster: fixing%20ci… · 14:15](https://img.shields.io/badge/🤖%20agent%20duckster-fixing%20ci%E2%80%A6%20%C2%B7%2014%3A15-orange?style=flat&labelColor=eeeeee)

**Done**
![🤖 agent duckster: done in 16min · 14:31](https://img.shields.io/badge/🤖%20agent%20duckster-done%20in%2016min%20%C2%B7%2014%3A31-brightgreen?style=flat&labelColor=eeeeee)

**Timed out**
![🤖 agent duckster: timed%20out%20after%2040%20min · 14:55](https://img.shields.io/badge/🤖%20agent%20duckster-timed%20out%20after%2040%20min%20%C2%B7%2014%3A55-red?style=flat&labelColor=eeeeee)

**Failed**
![🤖 agent duckster: failed%20-%20no%20internet · 14:55](https://img.shields.io/badge/🤖%20agent%20duckster-failed%20--%20no%20internet%20%C2%B7%2014%3A55-red?style=flat&labelColor=eeeeee)

If you are reading this and have not yet posted a status badge for the current task — **do it immediately**.

---

## After pushing changes

After pushing new commits:

1. Ensure the Pull Request description is accurate and up to date.
2. Re-check the related issue for new comments or updates.
3. Wait at least 30 seconds for CI to start.
4. Check CI status and update your status badge accordingly.

