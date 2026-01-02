# Plan — Chatbot

1. Backend:
   - `/chat/history` returns chat messages for user
   - `/chat/message` stores user msg, computes action, edits todos, stores assistant msg, returns reply
   - `/chat/history` DELETE endpoint to delete user history
2. Frontend:
   - chat page loads history
   - send message -> appends local user message -> calls backend -> appends assistant reply
   - add “Delete History” button with confirmation
3. Ensure todo changes are real:
   - add/update/delete/complete must call Todo table operations

Done when chat can add/update/complete/delete todos and history delete works.
