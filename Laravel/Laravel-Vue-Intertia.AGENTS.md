# AGENTS.md

## Repo Scope

This repository uses Laravel, Vue, Inertia, and Vite.
Follow the existing project structure and patterns before introducing new ones.

## Laravel + Vue + Inertia Rules

- Follow Laravel, Inertia, Vue, and shadcn-vue conventions before inventing custom structure.

- Keep Laravel as the source of truth.
- Keep routing, middleware, authorization, validation, persistence, and business logic in Laravel.

- Authorize actions in Laravel.
- Do not rely on Vue-only permission checks for real access control.

- Use Inertia for normal server-driven page flows.
- Do not introduce separate API patterns for standard page behavior unless clearly required.

- Keep Vue components thin.
- Use Vue for presentation, local interaction, and page state, not core business rules.
- Prefer existing shadcn-vue UI primitives for standard front-end architecture.

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

## shadcn-vue Rules

- This repo uses shadcn-vue components as the default UI building blocks.

- Before building a new UI component, check whether an equivalent shadcn-vue component already exists in the repo.
- Check existing `@/components/ui` files and current usage before creating custom UI primitives.

- If a needed shadcn-vue component already exists in the repo, use it.
- Do not rebuild, restyle from scratch, or replace an existing shadcn-vue component with a custom version unless explicitly required.

- If the needed shadcn-vue component does not exist yet, add it with the shadcn-vue CLI before building custom UI for that pattern.
- Use the repo's package manager command for shadcn-vue CLI installs.
- For npm-based repos, run `npx shadcn-vue@latest add {component}`.

- Prefer shadcn-vue components by default for buttons, inputs, dialogs, dropdowns, sheets, tabs, tables, form controls, and other standard UI patterns.
- Do not hand-roll standard UI primitives when shadcn-vue already provides them.

- Reuse the generated shadcn-vue component files and their established import paths.
- Follow the repo’s existing shadcn-vue patterns for composition, styling, and file placement.

- Treat shadcn-vue components as project-owned code.
- Modify them carefully and keep changes consistent with the existing shadcn-vue structure in the repo.