# AGENTS.md
> Universal agent entry point. Works with Claude Code, Codex, Gemini CLI,
> Cursor, Windsurf, opencode, and any agent that reads AGENTS.md.

This repository uses the **Alvecomm context system** - a structured set of
versioned Markdown files that act as durable project memory for AI agents.

---

## Read these files before doing anything

| Order | File | Purpose |
|---|---|---|
| 1 | `AI_CONTEXT.md` | Project overview, tech stack, scope, invariants |
| 2 | `ARCHITECTURE.md` | Module structure, data flow, component boundaries |
| 3 | `Rules/AI_RULES.md` | Behavioral rules you must follow as a coding agent |
| 4 | `TASKS.md` | Active task, backlog, completed work |
| 5 | `DECISIONS.md` | Past decisions — do not contradict these |

Apply all skill constraints from `Skills/` to every code change.

---

## Core behavioral rules (summary)

Full rules are in `Rules/AI_RULES.md`. The non-negotiables:

**Think first.** State your assumptions explicitly before coding. If something
is ambiguous, ask - do not guess and proceed silently.

**Stay minimal.** Write the least code that solves the problem correctly.
No speculative features, no unrequested abstractions, no extra dependencies.

**Be surgical.** Change only what the task requires. Do not improve, refactor,
or reformat code that is outside the scope of the current task.

**Define success.** Before executing a multi-step task, state a brief plan
with verifiable success criteria for each step. Loop until verified.

---

## Session protocol

1. Confirm which context files you have read
2. Confirm the active task from `Rules/TASKS.md`
3. Execute according to `Rules/AI_RULES.md` and `Skills/`
4. Update `Rules/TASKS.md` when the task is complete
5. Log any architectural decision in `Rules/DECISIONS.md`
6. End the session - start fresh for the next task

---

## Updating context files

These files are living documents. Keep them accurate.

| File | Update when |
|---|---|
| `Rules/AI_CONTEXT.md` | Stack, scope, or invariants change |
| `Rules/ARCHITECTURE.md` | Modules or data flow change - flag to developer first |
| `Rules/TASKS.md` | Task starts or completes |
| `Rules/DECISIONS.md` | Any decision affecting architecture or product direction |
