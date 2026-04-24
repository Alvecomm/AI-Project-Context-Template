# IDE Guides

These guides show how to configure popular IDEs and AI coding tools to work
with the Alvecomm context system.

The goal in every case is the same: ensure the agent consistently sees the
repository's source-of-truth files and applies the coding skill constraints.

---

## Core files every tool needs access to

- `Rules/AI_RULES.md` - authoritative behavior rules
- `Rules/AI_CONTEXT.md` - project overview and invariants
- `Rules/ARCHITECTURE.md` - structural truth
- `Rules/TASKS.md` - active task
- `Skills/` - coding constraints (think-first, simplicity, surgical-changes, goal-driven)

---

## Tools with automatic context loading

These tools read agent entry point files automatically - no session starter needed:

| Tool | File auto-read |
|---|---|
| Claude Code | `CLAUDE.md` |
| opencode | `AGENTS.md` |
| Codex CLI | `AGENTS.md` |
| Gemini CLI | `AGENTS.md` |

---

## Tools requiring manual setup

These tools need a system prompt or session starter configured:

- [Antigravity](./Antigravity.md)
- [Cursor](./Cursor.md)
- [VS Code](./VSCode.md)
- [JetBrains](./JetBrains.md)
- [Zed](./Zed.md)

Each guide includes a ready-to-use system prompt and session starter.

---

## Universal session starter

If your tool is not listed above, use this at the start of every session:

> Read and strictly follow `Rules/AI_RULES.md`, `Rules/AI_CONTEXT.md`,
> and `Rules/ARCHITECTURE.md`. Load all skill constraints from `Skills/`.
> Apply changes as unified diffs. Confirm the active task from
> `Rules/TASKS.md` before starting. Ask before guessing.
