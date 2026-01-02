# Architecture Overview (hackathon-todo)

## Monorepo Layout
- `frontend/` — Next.js app (landing page is login at `/`, dashboard, chat)
- `backend/` — FastAPI app (JWT auth, todos, chatbot routes)
- `specs/` — specifications, plans, tasks, checklists
- `history/prompts/` — prompt history records (PHR)

## Core Flows

### Authentication
- Frontend calls backend auth endpoints.
- Backend issues JWT access token signed with `JWT_SECRET`.
- Frontend stores token (localStorage or equivalent via your `auth` utilities) and sends `Authorization: Bearer <token>`.

### Todos
- All todo operations are user-scoped.
- Fields:
  - `title` (required)
  - `description` (optional)
  - `completed` (boolean)

### Chatbot
- Frontend chat page sends natural language messages.
- Backend parses intent:
  - quick deterministic parser first (add/list/update/delete/complete)
  - fallback to Gemini (if configured) to produce JSON action
- Backend then performs todo actions and returns assistant reply.
- Chat history is stored per user.
- Chat history delete option exists.

## Deployment Notes (Vercel)
- Frontend and backend deployed separately.
- Frontend environment variable points to backend base URL.
- Backend environment variables include DB, JWT secret, Gemini key, etc.
