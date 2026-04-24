# Skill: Goal-Driven Execution

> Define what success looks like before you start.
> Execute in verifiable steps. Loop until verified.

---

## The problem this solves

Imperative instructions ("add validation", "fix the bug") leave the agent
guessing what "done" means. This leads to incomplete implementations, missed
edge cases, and back-and-forth that wastes tokens and time.

---

## Rules

### Transform tasks into verifiable goals
Before executing, reframe the task as a success criterion.

| Instead of | Use |
|---|---|
| "Add validation" | "All required fields reject empty input and show an error message" |
| "Fix the bug" | "The crash no longer occurs when the list is empty" |
| "Refactor X" | "Logic is extracted, all existing tests still pass, no new tests needed" |

### State a plan for multi-step tasks
For any task with more than one meaningful step, write the plan first:

```
Plan:
1. [Step] → verified by: [check]
2. [Step] → verified by: [check]
3. [Step] → verified by: [check]
```

Get confirmation before executing if the plan involves significant changes.

### Use tests as success criteria whenever possible
If a test framework exists in the project:
- Write the test that defines success first
- Then write the code that makes it pass
- This gives the agent a loop to run independently

### Loop until verified
Do not submit until you have confirmed the success criteria are met.
If you cannot verify automatically, state what the developer needs to check.

### Surface blockers immediately
If you reach a step where you cannot proceed without information or a
decision, stop. Name the blocker. Do not skip it or make it up.

---

## What this looks like in practice

❌ **Wrong** — vague execution
> "I've added validation to the form."

✅ **Right** — goal-driven
> "Goal: all required fields reject submission when empty and display an
> inline error. I've implemented this. To verify: submit the form with each
> required field left blank — each should show '[field] is required' beneath
> it without the form submitting."

---

## The leverage insight
An agent given clear success criteria can loop independently until the goal
is met. An agent given vague instructions will stop and ask repeatedly —
or worse, deliver something wrong with confidence.

Strong success criteria are the highest-leverage thing you can give an agent.