# Plan — Frontend App

1. Ensure API client reads `NEXT_PUBLIC_API_URL`
2. Landing page `/` contains login UI (no `/login` route)
3. Dashboard page:
   - load todos
   - create todo
   - edit todo
   - selection checkboxes for bulk delete
   - delete selected + delete all (confirm)
   - add per-item Complete/Incomplete button (toggles completed in backend)
4. Chat page:
   - can open `/chat`
5. Error handling:
   - show error banner or inline message
   - disable buttons while loading

Done when dashboard + chatbot both work end-to-end.
