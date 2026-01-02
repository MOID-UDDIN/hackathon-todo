# Feature Spec — Frontend App (Auth + Dashboard)

## Summary
Build the Next.js UI that connects to backend:
- Landing page `/` is login page
- Dashboard supports todo CRUD, optional description, bulk delete, delete all, and completion toggle button
- Navigation to chatbot page

## Goals
- User can login at `/`
- After login, user lands on `/dashboard`
- Dashboard supports:
  - add todo title + description
  - edit title + description
  - delete one
  - select checkboxes and delete selected
  - delete all with confirmation
  - per-todo complete/incomplete toggle button (not selection checkbox)
- Logout button works
- API errors show clearly

## Non-Goals
- Complex UI frameworks; keep it clean
- Multi-tenant theming

## API Integration
- Use `NEXT_PUBLIC_API_URL` to call backend.
- Always send token for protected endpoints.

## Acceptance Criteria
- All operations work against backend deployed URL
- No hardcoded localhost in production
- Confirmations for destructive actions
