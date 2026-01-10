# Zed Setup

Zed is fast, minimal, and opinionated. It pairs extremely well with this template
when you treat the repository as the source of truth and keep AI sessions short-lived.

The goal is to compensate for model statelessness with **explicit, versioned context**.

---

## Recommended workflow

### 1) Keep core context files visible
Always keep these files open in tabs or easily accessible:

- `AI_RULES.md`
- `AI_CONTEXT.md`
- `ARCHITECTURE.md`
- `TASKS.md`

Avoid pasting large files into chat unless explicitly needed.

---

### 2) Start every AI session with the one-liner
At the beginning of each new AI interaction, paste:

> Read and strictly follow `AI_RULES.md`, `AI_CONTEXT.md`, and `ARCHITECTURE.md`.  
> Apply changes as unified diffs. If context is missing, ask before coding.

This establishes authority and prevents guessing.

---

### 3) Work in small, isolated tasks
Zed excels when combined with strict task discipline:

- Define one active task in `TASKS.md`
- Implement only that task in the current session
- Close the task when done
- Start a new session for the next task

Do not accumulate long chat histories.

---

## Best practices

- Prefer unified diffs over full file rewrites
- Keep prompts file- and goal-specific
- Let Zed handle navigation and edits; let AI reason and propose changes
- Record architectural or behavioral decisions in `DECISIONS.md`

---

## Mental model

- Zed = speed and focus
- Repository files = memory and authority
- AI chats = disposable workers

When used this way, Zed stays fast and AI output stays predictable.
