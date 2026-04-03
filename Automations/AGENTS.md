# AGENTS.md

## Tech Stack

This repository is for automation development using Make.com.

The main artifact is a Make.com scenario blueprint exported as a `.json` file. Blueprints are edited in code, stored in this repo, and re-imported into Make for validation, testing, and deployment.

Make is the orchestration layer and execution environment. The connected apps and services vary by client and project, so this repo should standardize how Make scenarios are developed, edited, reused, and reviewed without assuming one fixed service stack.

Typical connected systems may include CRMs, forms, webhooks, HTTP APIs, spreadsheets, messaging tools, or client-specific platforms, but those integrations are not the defining architecture of the repo. Make is.

## Workflow Model

This repo is not a traditional software application codebase.

It is a blueprint development workspace built around this workflow:

1. Build or update a scenario in Make.
2. Export the scenario as a blueprint `.json`.
3. Store the blueprint in this repo.
4. Edit the blueprint in code for logic, mappings, structure, portability, reuse, and cleanup.
5. Re-import the blueprint into Make.
6. Reconnect services, validate mappings, test behavior, and deploy inside the client’s Make environment.

The repo exists to make Make scenarios easier to:
- version
- review
- reuse
- adapt across clients
- maintain as structured artifacts instead of opaque visual-only flows

## Purpose

Use this repo to manage Make blueprint development in a way that is portable, reusable, and easy to reason about.

This repo should capture:
- scenario blueprints
- reusable Make patterns
- sample payloads and reference data
- lightweight notes when needed
- project rules and constraints in `/spec`

This repo should not assume:
- imported connections survive
- client environments match each other
- standard software test workflows apply
- one client’s integrations define rules for all other projects

## Repo Structure

### `/blueprints`
Stores exported Make scenario blueprint JSON files.

Use this folder for:
- source scenario blueprints
- in-progress blueprint revisions
- finalized blueprints ready for re-import
- project or client-specific scenario variants

Blueprint JSON is the primary artifact in this repo.

### `/patterns`
Stores reusable Make patterns and reference implementations.

Use this folder for:
- routers
- filters
- webhook patterns
- HTTP module patterns
- mapping structures
- reusable logic arrangements
- repeatable scenario design patterns

Check here before building a new structure from scratch.

### `/samples`
Stores sample payloads, request bodies, response bodies, field references, and example data used to design or debug mappings and logic.

Use samples to understand expected data shape before changing scenario behavior.

### `/docs`
Stores lightweight documentation when needed.

Use this folder for:
- project notes
- client setup notes
- mapping notes
- deployment notes
- manual follow-up steps
- known quirks or constraints

Do not add documentation unless it preserves useful working context.

### `/spec`
Stores project instructions, workflow constraints, and implementation rules. This is where client context and scope-specific stacks, workflows, and goals will be defined.

Use `/spec` for:
- project conventions
- scenario requirements
- integration constraints
- scope-specific instructions
- folder-specific rules
- architecture or workflow notes that should govern future work

If a relevant spec exists, follow it.

## Working Rules

- Treat blueprint JSON as the canonical working artifact.
- Edit blueprint JSON intentionally and conservatively.
- Read the surrounding structure before changing modules, mappings, routers, filters, or settings.
- Keep changes minimal and focused.
- Preserve unrelated structure unless the task requires change.
- Reuse existing patterns before creating new scenario structures.
- Prefer portable Make logic over client-bound logic.
- Do not hard-code client-specific IDs, connections, or assumptions unless the project explicitly requires them.
- Keep repeated logic consistent across scenarios when practical.

## Make Workflow Rules

- Assume imported connections do not survive.
- Build scenarios so connections, bindings, and environment-specific settings can be remapped after import.
- Treat Make as the execution environment and this repo as the editable source workspace.
- Prefer Make-native structures before inventing custom workarounds.
- Use webhooks, routers, filters, variables, HTTP modules, error handlers, and data stores intentionally. They must have a reason for existing.

## JSON Editing Rules

- Do not reformat unrelated JSON.
- Do not rename or remove unrelated modules, mappings, or keys without clear reason.
- Keep blueprint files uploadable and Make-compatible.
- Preserve stable structure where possible so diffs remain readable.
- Keep notes outside blueprint JSON unless the format explicitly supports them.

## Portability Rules

- Design every blueprint for re-import into Make.
- Do not assume workspace structure, connection IDs, or account bindings will match across clients.
- Separate reusable Make logic from client-specific implementation details whenever possible.

## Verification Rules

Standard code tests do not apply to this repo.

Verify changes by checking:
- blueprint JSON structure
- module order
- router and filter intent
- mapping intent
- webhook behavior where relevant
- external write behavior where relevant
- retry and duplicate-run safety where relevant
- import readiness for Make

Live verification is assumed to not be possible.

## Documentation Expectations

Do not require a full setup document for every scenario by default.

Document only when needed to preserve:
- important setup context
- non-obvious mapping logic
- deployment constraints
- client-specific remapping steps
- known limitations
- scope changes

## Preferred Outcome

The goal of this repo is not just to store Make exports.

The goal is to maintain a reusable blueprint workflow where Make scenarios can be exported, understood, edited safely, reused across projects, and re-imported into client environments with minimal confusion.