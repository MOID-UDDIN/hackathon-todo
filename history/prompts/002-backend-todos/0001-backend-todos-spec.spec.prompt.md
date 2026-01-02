---
id: "0001"
title: backend-todos-spec
stage: spec
date: 2025-12-28
surface: claude-code
model: claude-sonnet-4-5-20250929
feature: 002-backend-todos
branch: 002-backend-todos
user: Icon
command: /sp.specify
labels: [backend, todos, crud, fastapi]
links:
  spec: specs/002-backend-todos/spec.md
  ticket: N/A
  adr: N/A
  pr: N/A
files:
  - path: specs/002-backend-todos/spec.md
    action: created
  - path: specs/002-backend-todos/checklists/requirements.md
    action: created
tests:
  - N/A (spec stage)
---

## Prompt
Create a backend todos feature specification for an existing FastAPI application.

The specification must define authenticated and user-scoped CRUD behavior with the following constraints:
- Each todo contains a required title
- Description is optional
- Todos support completed and incomplete states
- All endpoints require JWT authentication
- Users can only access and modify their own todos

The output must clearly define:
- API endpoints
- Data model fields
- Validation rules
- Acceptance criteria
- Edge cases

The generated specification should act as the single source of truth for planning and task generation.

---

## Response Snapshot
Generated a complete backend todos specification defining user-scoped CRUD endpoints, todo model fields, authentication requirements, validation behavior, acceptance criteria, and edge cases aligned with dashboard usage.

---

## Outcome
- ✅ Impact: Todos specification finalized and ready for planning
- 📁 Files: spec.md and requirements checklist generated
- 🔁 Next prompts: /sp.plan followed by /sp.tasks
- 🧠 Reflection: Specification remains minimal, explicit, and implementation-focused
