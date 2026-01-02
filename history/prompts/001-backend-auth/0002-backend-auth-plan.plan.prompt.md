---
id: "0002"
title: backend-auth-plan
stage: plan
date: 2025-12-28
surface: spec-driven-development
model: claude-sonnet-4-5-20250929
feature: 001-backend-auth
branch: 001-backend-auth
user: Icon
command: /sp.plan
labels: [backend, auth, jwt, fastapi, sqlmodel]
links:
  spec: specs/001-backend-auth/spec.md
  ticket: N/A
  adr: N/A
  pr: N/A
files:
  - path: specs/001-backend-auth/plan.md
    action: created
tests:
  - N/A (plan stage)
---

## Prompt
Generate a step-by-step **implementation plan** for the **Backend Auth (JWT)** feature for my **hackathon-todo** backend.

### Inputs to base plan on
- `specs/001-backend-auth/spec.md` (must follow this spec 1:1)
- Repo reality: FastAPI + SQLModel + Neon Postgres
- JWT HS256 with `JWT_SECRET` from env + bcrypt hashing/verification

### Plan constraints
- Do not output code
- Do not introduce new technologies
- Keep steps concrete, sequenced, and file-path oriented
- Focus only on auth scope (signup/login/logout/me + protected routes)

### Must include in the plan
- Environment + configuration handling for `JWT_SECRET`
- Password hashing + verification with bcrypt
- JWT creation with required claims (`sub/exp/iat/jti`)
- JWT validation/decoding rules (expired/invalid token handling)
- Auth routes:
  - `POST /auth/signup`
  - `POST /auth/login`
  - `POST /auth/logout`
  - `GET /auth/me` (preferred)
- Route protection approach via dependency injection (e.g., `get_current_user`)
- A testing strategy and smoke verification flow:
  - signup → login → access protected route → logout/discard token

### Deliverable
Produce `specs/001-backend-auth/plan.md` with these sections:
1) Goal  
2) Scope  
3) Non-Goals  
4) Assumptions  
5) Implementation Steps (sequenced)  
6) Testing Strategy  
7) Risks & Edge Cases

## Response snapshot
Generated a backend auth plan that sequences config setup, bcrypt password handling, JWT creation/validation rules, and FastAPI dependency-based route protection. The plan includes endpoint-by-endpoint steps (signup/login/logout/me), defines expected failure behaviors (duplicate email, invalid credentials, invalid/expired token, missing env secret), and includes a simple smoke verification flow for end-to-end validation.

## Outcome
- ✅ Impact: Plan is ready to convert into small, testable tasks
- 🧪 Tests: Defined as plan-level smoke + negative cases
- 📁 Files: `specs/001-backend-auth/plan.md`
- 🔁 Next prompts: `/sp.tasks`
- 🧠 Reflection: Steps stay implementation-ready while avoiding code output
