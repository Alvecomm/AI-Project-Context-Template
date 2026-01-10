# Decisions (ADR-lite)

This log captures decisions made during development so humans and AI don’t re-debate them.
Keep entries short. One decision per section.

---

## 2026-01-10 — Repository is the source of truth for AI context
**Decision:** Store system context and AI rules in versioned markdown files (`AI_RULES.md`, `AI_CONTEXT.md`, `ARCHITECTURE.md`).

**Why:** Models are stateless; this reduces repetition and architectural drift.

**Notes:** Pin these files in the IDE and reference them at the start of each new AI session.
