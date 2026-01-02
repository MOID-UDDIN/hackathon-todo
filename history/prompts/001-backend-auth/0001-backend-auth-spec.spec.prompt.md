---
id: "0001"
title: backend-auth-spec
stage: spec
date: 2025-12-28
surface: claude-code
model: claude-sonnet-4-5-20250929
feature: 001-backend-auth
branch: 001-backend-auth
user: Icon
command: /sp.specify
labels: [backend, auth, jwt, fastapi, sqlmodel]
links:
  spec: specs/001-backend-auth/spec.md
  ticket: N/A
  adr: N/A
  pr: N/A
files:
  - path: specs/001-backend-auth/spec.md
    action: created
  - path: specs/001-backend-auth/checklists/requirements.md
    action: created
tests:
  - N/A (spec stage)
---

## Prompt
Create a **Backend Auth (JWT)** feature spec for my **hackathon-todo** backend.

### Repo reality / constraints
- Backend framework: **FastAPI**
- ORM/data layer: **SQLModel**
- Database: **PostgreSQL (Neon)**
- Auth mechanism: **JWT (HS256)**
- Secret source: `JWT_SECRET` from environment variables
- Password security: **bcrypt** hashing + verification
- Auth must be implemented inside `backend/app/` only
- Keep scope minimal and aligned to a hackathon-ready product

### Token requirements
- Use HS256 with `JWT_SECRET`
- Token claims must include: `sub`, `exp`, `iat`, `jti`
- Token decode must validate algorithm = HS256 and reject invalid/expired tokens

### API scope (must cover)
- `POST /auth/signup`  
  Create a new user with **email + password**. Enforce unique email.
- `POST /auth/login`  
  Validate credentials and return a signed JWT.
- `POST /auth/logout`  
  Support client-side discard; optionally include server-side invalidation notes if desired.
- `GET /auth/me` (preferred)  
  Return current authenticated user to validate auth flow.

### Data requirements
Define the user data model and constraints:
- `id` (primary key)
- `email` (unique, indexed)
- `hashed_password`
- `created_at`

### Security + error rules
- Always hash passwords; never store plaintext passwords
- Return safe error messages (no leakage of whether a specific email exists)
- Define error cases for:
  - duplicate email on signup
  - wrong password / invalid login
  - missing/invalid JWT
  - expired JWT
  - missing `JWT_SECRET` in environment

### Spec output format
Generate:
1) `specs/001-backend-auth/spec.md` containing:
   - Summary
   - Goals / Non-Goals
   - API requirements (high-level request/response)
   - Data requirements
   - Security requirements
   - Error handling rules
   - Acceptance criteria + edge cases
2) `specs/001-backend-auth/checklists/requirements.md` containing a compact checklist.

### Explicit non-goals
Do not include:
- OAuth providers
- Refresh tokens
- Roles/RBAC
- Any new frameworks or unrelated tech

## Response snapshot
Generated a Backend Auth (JWT) spec aligned to FastAPI + SQLModel and Neon Postgres. The spec defines signup/login/logout (plus optional /me), bcrypt password handling, JWT HS256 token structure with `sub/exp/iat/jti`, and clear security/error rules. Acceptance criteria includes duplicate-email handling, invalid credentials behavior, expired/invalid token rejection, and environment secret validation.

## Outcome
- ✅ Impact: Backend auth spec ready for plan and tasks generation
- 🧪 Tests: N/A (spec stage)
- 📁 Files: `specs/001-backend-auth/spec.md` + `specs/001-backend-auth/checklists/requirements.md`
- 🔁 Next prompts: `/sp.plan` then `/sp.tasks`
- 🧠 Reflection: Scope stays minimal, hackathon-friendly, and matches repo constraints
