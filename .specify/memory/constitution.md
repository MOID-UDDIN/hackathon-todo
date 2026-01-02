<!--
Sync Impact Report:
Version change: None -> 1.0.0
Modified principles: All (initial creation)
Added sections: Development Guidelines, Project Phases & Deliverables
Removed sections: None
Templates requiring updates:
- .specify/templates/plan-template.md ⚠ pending
- .specify/templates/spec-template.md ⚠ pending
- .specify/templates/tasks-template.md ⚠ pending
- .specify/templates/commands/*.md ⚠ pending
Follow-up TODOs: None
-->
# Hackathon Todo (Full-Stack + AI Chatbot) Constitution

## Core Principles

### I. Spec-Driven Development (NON-NEGOTIABLE)
All changes MUST be driven via specs (Constitution → Feature Spec → Plan → Tasks → Implementation prompts). Specs are the source of truth. Implementation MUST map back to requirements.

### II. Keep It Simple & Shippable
Prefer smallest working solution that is reliable. Avoid adding unused abstractions, unused folders, or “future-proof” complexity that isn’t used in this project.

### III. Monorepo Reality (This Project)
This repo is a monorepo:
- `frontend/` contains Next.js app (login page is the landing `/`)
- `backend/` contains FastAPI app (JWT auth + todos + chatbot routes)
No “extra auth folder” is created—auth lives under backend routes and frontend pages.

### IV. Security Baselines
- JWT tokens must be signed with a secret (env var).
- Passwords must be hashed (bcrypt).
- Token decode must verify algorithm.
- Never log secrets.

### V. Data Integrity
- Todos belong to a user (multi-user).
- CRUD operations must enforce ownership.
- Chat history is user-scoped.

### VI. UX Rules (Project-Specific)
- Login is the home page (`/`).
- Dashboard supports:
  - create todo with optional description
  - edit title + description
  - delete one
  - bulk delete selected
  - delete all (confirmation)
  - complete/incomplete toggle button
- Chatbot supports:
  - show todos
  - add todo (with description if provided)
  - update todo title/description
  - complete/incomplete
  - delete todo
  - chat history view
  - delete chat history (button + confirmation)

## Development Guidelines

### Folder Structure (Specs + Prompt History)
This repo uses:
- `.specify/memory/constitution.md` as the main memory constitution
- `history/prompts/...` as Prompt History Records (PHR)
- `specs/...` as feature specs + plans + tasks + checklists

### Workflow
1) Write/Update spec
2) Write plan
3) Write tasks
4) Write implementation prompt
5) Implement in code
6) Verify behavior

## Project Phases & Deliverables (Your Current Status)
- Phase 1/2: Full-stack todo app (auth + todos)
- Phase 3: Todo AI chatbot (natural language)
You’ve implemented Phase 1–3; future phases are out of scope unless explicitly requested.

## Governance
This Constitution overrides all other docs. Changes must update specs and keep repo consistent.

**Version**: 1.0.0 | **Ratified**: 2025-12-28 | **Last Amended**: 2025-12-28