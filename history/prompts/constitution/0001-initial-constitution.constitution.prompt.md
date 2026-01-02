---
id: "0001"
title: initial-constitution
stage: constitution
date: 2025-12-28
surface: claude-code
model: claude-sonnet-4-5-20250929
feature: constitution
branch: main
user: Icon
command: /sp.constitution
labels: [sdd, constitution, hackathon, todo, phase2, phase3]
links:
  spec: N/A
  ticket: N/A
  adr: N/A
  pr: N/A
files:
  - .specify/memory/constitution.md
tests:
  - N/A (constitution stage)
---
## Prompt
Create the project constitution for my repo `hackathon-todo`.

Reality constraints you MUST follow:
- Backend is FastAPI + SQLModel and already contains JWT auth setup (not separate auth service).
- Frontend is Next.js and login page is the landing route `/`.
- Phase II + Phase III are in scope: full-stack todos + chatbot that edits todos and stores chat history.
- Model must be `claude-sonnet-4-5-20250929`.
- Make principles testable and aligned with what exists.

Write the constitution at: `.specify/memory/constitution.md`

## Response snapshot
Generated a repo-aligned constitution focusing on:
- Non-negotiable SDD workflow
- Repo reality alignment (no fake features)
- Phase II-III scope only
- JWT + password hashing correctness
- Chatbot must change todos + persist chat history
- Success criteria that are verifiable

## Outcome
- ✅ Impact: Foundation rules established for all features
- 🧪 Tests: N/A
- 📁 Files: 1 file created: `.specify/memory/constitution.md`
- 🔁 Next prompts: `/sp.specify` for Feature 001 (backend-auth)
- 🧠 Reflection: Constitution explicitly prevents scope drift and “fictional docs” problem.

## Evaluation notes (flywheel)
- Failure modes observed: None
- Graders run and results (PASS/FAIL): N/A
- Prompt variant (if applicable): Standard Spec-Kit Plus constitution workflow
- Next experiment (smallest change to try): None
