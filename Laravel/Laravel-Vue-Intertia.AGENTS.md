## Laravel + Vue + Inertia Rules

- Follow Laravel, Inertia, and Vue conventions before inventing custom structure.

- Keep Laravel as the source of truth.
- Keep routing, controllers, middleware, authorization, validation, persistence, and core business rules in Laravel.

- Use Inertia for server-driven pages.
- Do not introduce a separate API pattern for normal page flows unless the interaction clearly requires it.

- Keep Vue components thin.
- Use Vue for presentation, local interaction, and page state, not core business logic.

- Validate all request data in Laravel.
- Prefer Form Requests for non-trivial validation and authorization.
- Do not duplicate validation rules in Vue when the server already owns them.

- Pass only the data the page actually needs.
- Do not send full models, oversized collections, or unnecessary props to Inertia pages.

- Use shared props only for data that must be available across many pages.
- Keep shared props minimal.

- Use partial reloads, deferred props, lazy props, or similar built-in Inertia patterns when refreshing only part of a page.
- Do not solve partial data updates with oversized full-page reloads unless necessary.

- Follow the existing project pattern for forms.
- Prefer Inertia form patterns for Inertia-driven pages.
- Do not replace normal Inertia form flows with ad hoc client request handling without a clear need.

- Keep client state small and local.
- Do not duplicate server-owned state in Vue without a clear reason.

- Use separate endpoints only when the interaction clearly does not fit the normal Inertia page model.

- Use multi-word Vue component names.
- Use detailed prop definitions.
- Always key `v-for`.
- Never use `v-if` on the same element as `v-for`.

- Use Laravel config files for configuration.
- Do not scatter environment reads across application code.

- Follow the existing Vite, app boot, and entrypoint structure in the repo.
- Do not change build structure or asset entrypoints without updating `/spec`.

- Handle production errors intentionally.
- Do not rely on development-only Inertia error behavior as the production pattern.

- When changing routes, validation, shared props, page props, forms, config, or build behavior, update the relevant `/spec` docs in the same task.