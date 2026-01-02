# Feature Spec — Chatbot (Todo Assistant + History)

## Summary
Provide a chat UI and backend route that can:
- store chat history (user + assistant)
- interpret user message into todo actions
- apply todo changes
- return assistant reply
- allow user to delete chat history with confirmation

## Goals
- Chat page shows history
- Send message stores user message
- Assistant reply is returned and stored
- Assistant can:
  - list todos
  - add todo (title + optional description)
  - update todo title/description
  - complete/incomplete todo
  - delete todo
- Add “Delete History” option

## Non-Goals
- Multi-conversation threads
- Sharing history across users

## Acceptance Criteria
- Chat history is user-scoped
- Deleting history deletes only that user’s messages
- Chatbot actually changes todos (not just saves messages)
