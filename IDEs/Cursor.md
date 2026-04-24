# Cursor Setup

Cursor is well-suited for this template because it supports workspace rules,
Notepads for persistent context, and repo-wide file retrieval.

---

## How the context system works in Cursor

Cursor does not auto-read `CLAUDE.md` or `AGENTS.md`. You need to point it
at the right files manually - but once set up, it works reliably across sessions.

---

## Setup

### 1. Add a Cursor rule

In Cursor Settings → Rules, add a project rule with this content:

```
Before every task:
- Read and strictly follow Rules/AI_RULES.md
- Read Rules/AI_CONTEXT.md and Rules/ARCHITECTURE.md as project truth
- Load skill constraints from Skills/think-first.md, Skills/simplicity.md,
  Skills/surgical-changes.md, and Skills/goal-driven.md
- Check the active task in Rules/TASKS.md

Output format: unified diffs only.
Ask before guessing when context is missing.
Do not start coding until you have confirmed the active task.
```

### 2. Pin files in Notepads

Create a Notepad called **Project Context** and paste the contents of:
- `Rules/AI_CONTEXT.md`
- `Rules/ARCHITECTURE.md`

Include this Notepad in every chat with `@Project Context`. This gives Cursor
persistent access to your project truth without eating prompt space on file reads.

Update the Notepad when either file changes.

### 3. Reference Skills in your rule or system prompt

Add this line to your Cursor rule so skills are applied automatically:

```
Apply all constraints from the Skills/ folder: think-first, simplicity,
surgical-changes, goal-driven. Read each file before writing code.
```

---

## Session workflow

1. Open a new Cursor chat
2. Include `@Project Context` notepad
3. Cursor reads your rule automatically - no session starter needed
4. Confirm the active task from `Rules/TASKS.md`
5. Execute the task
6. Ask Cursor to update `Rules/TASKS.md` and `Rules/DECISIONS.md` when done

---

## Task discipline

- Keep one active task at a time in `Rules/TASKS.md`
- Ask Cursor to implement only that task per session
- Close the task, then open a new chat for the next one

This keeps context tight and output predictable.

---

## Best practices

- Use `@file` references to pull in specific files rather than pasting content
- Keep tasks small - large refactors should be split into focused sessions
- When Cursor drifts or ignores rules, start a fresh chat (context degrades over long sessions)
- After major architectural changes, update your Notepad to reflect the new state