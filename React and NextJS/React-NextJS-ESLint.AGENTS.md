## React + Next.js + ESLint Rules

- Follow App Router conventions.
- Use Next.js file conventions before inventing custom structure.

- Default to Server Components.
- Add `"use client"` only when a component needs state, effects, event handlers, refs, or browser APIs.

- Keep secrets, direct data access, and server-only logic out of Client Components.

- Fetch data on the server by default.
- Do not move server-owned fetching into client code without a clear need.

- Use Server Actions for internal form and UI mutations when appropriate.
- Use Route Handlers for public APIs, webhooks, and custom request handling.

- Follow the existing caching and revalidation pattern in the project.
- Do not invent or change caching behavior without updating the relevant `/spec` docs.

- Keep components and hooks pure.
- Do not cause side effects during render.
- Only call hooks at the top level.

- Do not use `useEffect` for derived state, render-time calculations, or event-driven logic.
- Use effects only to synchronize with external systems.

- Do not disable React Hooks lint rules globally.
- Fix the code instead of bypassing `rules-of-hooks` or `exhaustive-deps`.

- Use Next.js metadata APIs for page metadata.
- Do not manage `<head>` manually when Next provides a built-in pattern.

- Prefer `next/image` for standard application images.
- Do not use raw `<img>` unless there is a clear reason.

- Use the existing ESLint setup if the project already defines one.
- For new Next.js projects, use the Next.js ESLint baseline with `core-web-vitals`.
- Use flat ESLint config.

- Prefer typed linting for long-lived TypeScript projects when the repo already uses it or the project warrants it.
- Do not add heavy lint layers without clear value.

- Keep client state local and narrow.
- Do not turn full pages into Client Components when only a small interactive leaf needs it.