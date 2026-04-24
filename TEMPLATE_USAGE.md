# Template Usage (IDE Guides)

This repository makes AI-assisted development more reliable by storing project
context in versioned files. The repository becomes the source of truth for both
humans and AI agents - not the chat window.

---

## Core files

| File | Purpose |
|---|---|
| `CLAUDE.md` | Claude Code entry point - auto-read at every session start |
| `AGENTS.md` | Universal agent entry point for all other tools |
| `Rules/AI_RULES.md` | Authoritative behavior rules for every AI agent |
| `Rules/AI_CONTEXT.md` | Short, always-relevant project context |
| `Rules/ARCHITECTURE.md` | Structural truth - modules, data flow, boundaries |
| `Rules/TASKS.md` | Active task, backlog, completed work |
| `Rules/DECISIONS.md` | Architectural and product decisions log |
| `Skills/think-first.md` | Reason before acting - surface ambiguity early |
| `Skills/simplicity.md` | Minimum code that solves the problem |
| `Skills/surgical-changes.md` | Touch only what the task requires |
| `Skills/goal-driven.md` | Define success criteria before executing |

Keep these files up to date as the project evolves. Stale context is worse
than no context - it gives the agent false confidence.

---

## Setup by tool

### Claude Code and opencode
No manual setup needed. `CLAUDE.md` is read automatically at every session
start. The agent will:
1. Read your context files in order
2. Confirm the active task from `Rules/TASKS.md`
3. Apply all `Skills/` constraints
4. Execute and update context files when done

### Cursor
Pin `Rules/AI_CONTEXT.md` and `Rules/ARCHITECTURE.md` in Notepads for
persistent context across conversations. Add the following to your Cursor
rules or system prompt:

> Follow `Rules/AI_RULES.md` as the highest authority. Read `Rules/AI_CONTEXT.md`
> and `Rules/ARCHITECTURE.md` before every task. Apply all skills from `Skills/`.
> Output unified diffs. Ask before guessing.

See [IDEs/Cursor.md](./IDEs/Cursor.md) for full setup.

### All other tools
Use the session starter below. See the `IDEs/` folder for tool-specific guides.

---

## Session starter (for tools that don't auto-load context)

Copy and paste this as the first message in every new AI session:

> Read and strictly follow `Rules/AI_RULES.md`, `Rules/AI_CONTEXT.md`,
> and `Rules/ARCHITECTURE.md`. Apply all skills from the `Skills/` folder.
> Apply changes as unified diffs. If context is missing, ask before coding.

---

## Workflow

### Per session
1. Start a new AI session
2. Agent reads context files (automatic with Claude Code / opencode)
3. Confirm the active task from `Rules/TASKS.md`
4. Execute the task
5. Agent updates `Rules/TASKS.md` on completion
6. Log any architectural decision in `Rules/DECISIONS.md`
7. End the session - start fresh for the next task

### One task per session
Keep one active task at a time in `Rules/TASKS.md`. Focused sessions produce
better output, use fewer tokens, and are easier to review.

### Planning vs execution
Use a strong reasoning model for planning - produce a plan, write it to
`Rules/TASKS.md`, then switch to a faster model for execution. The repository
provides context so the execution model doesn't need planning overhead.

---

## Keeping context files accurate

| File | Update when |
|---|---|
| `Rules/AI_CONTEXT.md` | Stack, scope, or invariants change |
| `Rules/ARCHITECTURE.md` | New modules, changed data flow, new boundaries |
| `Rules/TASKS.md` | Task starts, completes, or scope changes |
| `Rules/DECISIONS.md` | Any architectural or product decision is made |

Flag `Rules/ARCHITECTURE.md` changes to the developer before applying them -
this file represents long-term structural truth and should not change silently.

---

## IDE-specific setup

- [Antigravity](./IDEs/Antigravity.md)
- [Cursor](./IDEs/Cursor.md)
- [VS Code](./IDEs/VSCode.md)
- [JetBrains](./IDEs/JetBrains.md)
- [Zed](./IDEs/Zed.md)
