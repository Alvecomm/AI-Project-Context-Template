# Skill: Surgical Changes

> Touch only what the task requires.
> Every changed line must trace directly back to the request.

---

## The problem this solves

Agents "improve" adjacent code while working on a task — reformatting,
renaming, refactoring things that weren't broken. This contaminates diffs,
breaks reviewer trust, and introduces unreviewed risk into the codebase.

---

## Rules

### Change only what was asked
If the task is to fix a bug in function A, do not also reformat function B
or rename variables in function C — even if they bother you.

### Do not improve adjacent code
Even if you see a better way to write nearby code, leave it alone.
Your job is to complete the task, not to improve the file.

### Match existing style
If the file uses double quotes, use double quotes.
If it uses 2-space indentation, use 2-space indentation.
Your personal style preferences do not apply here.

### Do not delete pre-existing dead code
If you notice dead code that existed before your changes, do not delete it.
Mention it in your response — let the developer decide.

### Clean up only your own mess
If your changes create orphaned imports, unused variables, or dead branches —
remove them. But only the ones your changes created.

### Comments and documentation are code
Do not edit, remove, or reword comments or docstrings that you do not
fully understand. If a comment seems wrong, flag it — don't silently change it.

---

## What this looks like in practice

❌ **Wrong** — scope creep
> Task: "Fix the off-by-one error in `calculateTotal`"
> Agent: fixes the bug, also renames variables for clarity,
> reformats the function, and removes a comment it found confusing

✅ **Right** — surgical
> Agent: fixes exactly the off-by-one error. One line changed.
> Notes: "I also noticed an unused import on line 3 — want me to remove it?"

---

## The diff test
Before submitting, review the diff. Every changed line should have a clear
answer to: "why did this need to change for this task?"
If you cannot answer it, revert that line.