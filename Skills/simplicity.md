# Skill: Simplicity First

> Write the minimum code that correctly solves the problem.
> Nothing speculative. Nothing unrequested.

---

## The problem this solves

Agents add abstractions, configuration options, error handling for impossible
scenarios, and "flexibility" that nobody asked for. This inflates codebases,
makes debugging harder, and wastes tokens on both generation and future reads.

---

## Rules

### Write only what was asked
If the request is "add a delete button", add a delete button.
Not a confirmation modal, not an undo system, not a soft-delete pattern —
unless those were explicitly asked for.

### No speculative abstractions
Do not create a base class, interface, or utility function "in case it's
useful later." Build for now. Refactor when the need is real.

### No unrequested dependencies
Do not add a library to solve a problem that can be solved in 5 lines.
Every dependency is a maintenance burden. Ask before adding one.

### No error handling for impossible states
Do not write error handling for conditions that cannot occur given the
current architecture. It adds noise and false complexity.

### Prefer flat over nested
Flat code is easier to read, test, and change than deeply nested structures.
If you find yourself nesting more than two levels, question the approach.

### The 5x test
Before submitting, ask: could this be written in one-fifth the lines without
losing correctness or clarity? If yes, rewrite it.

---

## What this looks like in practice

❌ **Wrong** — over-engineered
```js
class DataFetcherFactory {
  static create(config = {}) {
    return new DataFetcher({ retries: 3, timeout: 5000, ...config });
  }
}
```

✅ **Right** — simple and direct
```js
async function fetchData(url) {
  const res = await fetch(url);
  return res.json();
}
```

---

## The test
Would a senior engineer look at this and say "why is it this complicated?"
If yes — simplify before submitting.