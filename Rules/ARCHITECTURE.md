# Architecture Overview

This document defines the intended structure of the system.
AI assistants must follow it unless explicitly instructed otherwise.

---

## Principles

- Separation of concerns
- Minimal coupling between modules
- Predictable side effects
- Clear boundaries and ownership

---

## Suggested module boundaries (adjust to your stack)

- `api/` or `routes/`
  - routing, validation, auth (thin layer)
- `services/`
  - business logic (primary home of rules)
- `domain/` (optional)
  - core entities/value objects/invariants
- `db/`
  - migrations, queries, repository layer
- `integrations/` (optional)
  - third-party APIs, webhooks, external services
- `tests/`
  - unit/integration tests

---

## Request lifecycle (typical)

1. Route/controller receives request
2. Validate input and permissions
3. Call service for business logic
4. Service reads/writes via db layer
5. Return response DTO

---

## Error handling strategy

- Validation errors: return 4xx with clear message
- Auth errors: return 401/403
- Domain errors: map to appropriate 4xx
- Unexpected errors: 500 + log with request id/correlation id

---

## Security & permissions

- Authentication method:
- Authorization model (roles/scopes/tenant):
- Sensitive operations and audit requirements:

---

## Non-goals / constraints

- Performance constraints:
- Compliance requirements:
- Backward-compatibility expectations:
