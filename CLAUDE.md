# CLAUDE.md
> Claude Code entry point for the Alvecomm AI Project Context Template.
> This file is auto-read by Claude Code at session start.

You are working inside a repository that uses the **Alvecomm context system**.
Before writing a single line of code, read these files in order:

1. `AI_CONTEXT.md` — what this project is, its stack, its invariants
2. `ARCHITECTURE.md` — structural boundaries, modules, data flow
3. `Rules/AI_RULES.md` — how you must behave as a coding agent
4. `TASKS.md` — what is active right now and what is done

Then check:
- `DECISIONS.md` — past decisions you must not contradict
- `Skills/` — coding skill constraints that apply to this project

---

## How to use this system

### Starting a session
State out loud which files you have read and confirm the active task from `TASKS.md` before doing anything else.

### During a session
- Work on **one task at a time**
- Apply changes as unified diffs unless told otherwise
- If context is missing or ambiguous, **ask before coding** — never assume
- After completing a task, update `TASKS.md` and log the decision in `DECISIONS.md` if anything architectural was decided

### When to update context files
| File | Update when |
|---|---|
| `AI_CONTEXT.md` | Stack changes, new invariants, scope changes |
| `ARCHITECTURE.md` | New modules, changed data flow, new boundaries |
| `TASKS.md` | Task starts, completes, or scope changes |
| `DECISIONS.md` | Any architectural or product decision is made |

### What never to do
- Do not start coding before reading the context files
- Do not update `ARCHITECTURE.md` without flagging it to the developer first
- Do not carry decisions from a previous session — re-read files each time
- Do not add dependencies, abstractions, or features that were not asked for

---

## Skills in use
This project uses coding skill constraints located in `Skills/`.
Apply them to every code change:
- `Skills/simplicity.md` — write minimal, clean code
- `Skills/surgical-changes.md` — touch only what you must
- `Skills/think-first.md` — reason before acting
- `Skills/goal-driven.md` — define success before executing