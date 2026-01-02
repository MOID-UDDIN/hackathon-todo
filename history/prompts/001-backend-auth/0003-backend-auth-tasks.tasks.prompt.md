---
id: "0003"
title: backend-auth-tasks
stage: tasks
date: 2025-12-28
surface: claude-code
model: claude-sonnet-4-5-20250929
feature: 001-backend-auth
branch: 001-backend-auth
user: Icon
command: /sp.tasks
labels: [tasks, auth, jwt]
links:
  spec: specs/001-backend-auth/spec.md
  ticket: N/A
  adr: N/A
  pr: N/A
files:
  - path: specs/001-backend-auth/tasks.md
    action: created
tests:
  - N/A (tasks stage)
---

## Prompt
Generate a **tasks breakdown** for implementing **Backend Auth (JWT)** for my **hackathon-todo** backend.

### Inputs (must follow)
- `specs/001-backend-auth/spec.md`
- `specs/001-backend-auth/plan.md`

### Task rules
- Keep tasks small, testable, and ordered
- Each task should mention the likely file targets (config/security/routes/deps/models/schemas/tests/docs)
- Tasks must align with spec acceptance criteria and plan steps
- Include at least one end-to-end smoke verification task:
  - signup → login → protected route → logout/discard token
- Include negative cases (expired token, invalid token, missing secret, duplicate email, wrong password)

### Constraints
- Do not introduce OAuth providers
- Do not introduce refresh tokens
- Do not introduce RBAC/roles
- Keep implementation minimal and repo-aligned

### Deliverable
Produce `specs/001-backend-auth/tasks.md` as a checklist grouped by category (Config, Models, Security, Routes, Dependencies, Tests, Docs).

## Response snapshot
Generated a tasks checklist that converts the auth plan into discrete implementation items: env/config validation for `JWT_SECRET`, bcrypt hashing/verification utilities, JWT creation with `sub/exp/iat/jti`, token validation rules, auth routes for signup/login/logout (plus /me), dependency-based protection via `get_current_user`, and an end-to-end smoke verification flow with key negative cases.

## Outcome
- ✅ Impact: Tasks are ready to drive implementation prompt/code generation
- 🧪 Tests: Smoke flow + negative cases included as tasks
- 📁 Files: `specs/001-backend-auth/tasks.md`
- 🔁 Next prompts: implementation prompt that maps tasks → code changes
- 🧠 Reflection: Task granularity stays small enough to implement and verify quickly