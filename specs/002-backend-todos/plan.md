# Plan — Backend Todos

## Outline
1. Ensure Todo model exists with user_id, title, description, completed
2. Ensure routes exist under `/todos`
3. Ensure endpoints require current user
4. Enforce ownership checks
5. Return consistent JSON responses
6. Smoke test with:
   - create todo
   - list todos
   - update title/description
   - toggle completed
   - delete

## Done When
- Dashboard can fully use these endpoints without hacks.
