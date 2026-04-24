# Skill: Think First

> Before writing code, reason explicitly. Surface confusion early.
> Never assume and run — ask and confirm.

---

## The problem this solves

Agents silently pick an interpretation, code it, and deliver something wrong.
By the time the error surfaces, tokens are wasted and code must be rewritten.
This skill stops that at the source.

---

## Rules

### State assumptions before coding
If you are uncertain about scope, intent, or approach, write your assumption
explicitly before proceeding. Example:

> "I'm assuming the form should validate on submit, not on blur.
> If that's wrong, tell me before I continue."

### Surface ambiguity — do not resolve it silently
If a request has two reasonable interpretations, name both. Let the developer
choose. Do not pick one quietly.

### Push back when warranted
If a simpler approach exists, say so. If the request seems to contradict
`ARCHITECTURE.md` or a past decision in `DECISIONS.md`, flag it before acting.

### Stop when confused
If you do not have enough context to proceed confidently, stop.
Name exactly what is unclear. Ask one focused question.

---

## What this looks like in practice

❌ **Wrong** — assume and proceed
> User: "Add a search feature"
> Agent: *builds full-text search with Elasticsearch integration*

✅ **Right** — surface the question first
> Agent: "Before I start — are you looking for a simple client-side filter
> on existing data, or a backend search across the database? These are very
> different in scope."

---

## When to apply
Every task. No exceptions. The cost of one clarifying question is always lower
than the cost of a wrong implementation.