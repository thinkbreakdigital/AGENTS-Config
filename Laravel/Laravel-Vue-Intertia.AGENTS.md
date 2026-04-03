# AGENTS.md

## Repo Scope

This repository uses Laravel, Vue, Inertia, and Vite.
Follow the existing project structure and patterns before introducing new ones.

## Laravel + Vue + Inertia Rules

- Follow Laravel, Inertia, and Vue conventions before inventing custom structure.

- Keep Laravel as the source of truth.
- Keep routing, middleware, authorization, validation, persistence, and business logic in Laravel.

- Authorize actions in Laravel.
- Do not rely on Vue-only permission checks for real access control.

- Use Inertia for normal server-driven page flows.
- Do not introduce separate API patterns for standard page behavior unless clearly required.

- Keep Vue components thin.
- Use Vue for presentation, local interaction, and page state, not core business rules.

- Validate request data in Laravel.
- Prefer Form Requests for non-trivial validation and authorization.
- Do not duplicate server-owned validation in Vue.

- Pass only the data the page needs.
- Do not send full models, oversized collections, or unnecessary props to Inertia pages.
- For non-trivial page props, prefer explicit transformation over passing raw model structures.

- Keep shared props minimal.

- Keep reloadable Inertia props at the top level when practical.
- Use partial reloads, deferred props, lazy props, and built-in Inertia patterns before custom client-side data handling.

- Prefer the existing Inertia form pattern in the repo.
- Do not replace normal Inertia form flows with ad hoc client requests without clear need.

- Use Inertia remembered state for filters, tabs, and local form state that should survive history navigation.

- Keep client state small and local.
- Do not duplicate server-owned state in Vue without a clear reason.

- Use separate endpoints only when the interaction clearly does not fit the normal Inertia page model.

- Use multi-word Vue component names.
- Use detailed prop definitions.
- Always key `v-for`.
- Never use `v-if` on the same element as `v-for`.

- Use Laravel config files for configuration.
- Do not scatter environment reads through application code.

- Follow the repo’s existing Vite, boot, and entrypoint structure.

- Handle production errors intentionally.
- Do not rely on development-only error behavior as the production pattern.

## Verification

- When changing routes, validation, authorization, page props, shared props, partial reload behavior, redirects, forms, config, or build behavior, verify the changed behavior directly.
- Prefer targeted Laravel HTTP or feature tests for server behavior.
- Prefer targeted front-end verification for Vue and Inertia rendering changes.
- If verification cannot be run, state exactly what was checked and what remains unverified.