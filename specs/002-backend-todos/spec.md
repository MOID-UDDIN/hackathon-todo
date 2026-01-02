# Feature Spec — Backend Todos (CRUD + Completion)

## Summary
Implement todo CRUD endpoints for authenticated users with optional description and completion status.

## Goals
- Users can create a todo with:
  - required title
  - optional description
- Users can list their todos
- Users can update title and/or description
- Users can delete a todo
- Users can toggle completion complete/incomplete

## Non-Goals
- Sharing todos with other users
- Labels/categories/priority (unless already in your DB)
- Full-text search

## API Requirements (Expected)
- `GET /todos` — list user todos
- `POST /todos` — create todo
- `PATCH /todos/{id}` — update fields (title/description/completed)
- `DELETE /todos/{id}` — delete

## Data Requirements
- Todo belongs to user_id
- Fields:
  - id
  - user_id
  - title
  - description (nullable)
  - completed (bool, default false)

## Acceptance Criteria
- Unauthorized requests return 401
- User cannot edit/delete another user’s todos
- Title validation rejects empty title
- PATCH can:
  - update title
  - update description
  - toggle completed true/false

## Edge Cases
- Delete non-existing id returns 404
- Update with empty title returns 400
- Large description allowed within limits (frontend may restrict)
