---
status: pending
title: Personal Todo App with Due Dates
---

1. Add shared types in `src/types/todo.ts`: a todo has an id, title, completed flag, optional due date, and created time. Outcome: one typed shape used everywhere.

2. Create `src/hooks/useTodos.ts`: keeps the todo list in state and saves/loads it from the browser's local storage. Provides add, toggle, edit, delete, and clear-completed actions. Outcome: tasks persist across page reloads, no login needed.

3. Create `src/lib/dates.ts`: helpers to format due dates ("Today", "Tomorrow", "Mar 5") and detect overdue or due-today tasks. Outcome: friendly date labels and status colors.

4. Create components in `src/components/`:
   - `TodoForm.tsx`: text input, optional date picker, and an Add button; blank titles are rejected.
   - `TodoItem.tsx`: checkbox, title (struck through when done), due-date badge (red if overdue, amber if today), inline edit, and delete button.
   - `TodoList.tsx`: renders items, sorted with incomplete first and by earliest due date; shows a friendly empty state.
   - `TodoFilters.tsx`: All / Active / Completed tabs, an "items left" count, and a "Clear completed" button.

5. Replace the placeholder in `src/routes/index.tsx` with the todo page: centered card with a heading, the form, filters, and list, composed using `useTodos`. Outcome: the home page is the working app.

6. Update `src/routes/__root.tsx` so the shell has a soft background and consistent page padding; keep the not-found page. Style everything with Tailwind, responsive for mobile and desktop.

7. Verify: add, complete, edit, delete, filter, due-date labels, and persistence after refresh all work, with no type errors.
