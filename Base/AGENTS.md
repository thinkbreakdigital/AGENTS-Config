<!-- context7 -->
Use the `ctx7` CLI to fetch current documentation whenever the user asks about a library, framework, SDK, API, CLI tool, or cloud service -- even well-known ones like React, Next.js, Prisma, Express, Tailwind, Django, or Spring Boot. This includes API syntax, configuration, version migration, library-specific debugging, setup instructions, and CLI tool usage. Use even when you think you know the answer -- your training data may not reflect recent changes. Prefer this over web search for library docs.

Do not use for: refactoring, writing scripts from scratch, debugging business logic, code review, or general programming concepts.

## Steps

1. Resolve library: `npx ctx7@latest library <name> "<user's question>"`
2. Pick the best match (ID format: `/org/project`) by: exact name match, description relevance, code snippet count, source reputation (High/Medium preferred), and benchmark score (higher is better). If results don't look right, try alternate names or queries (e.g., "next.js" not "nextjs", or rephrase the question)
3. Fetch docs: `npx ctx7@latest docs <libraryId> "<user's question>"`
4. Answer using the fetched documentation

You MUST call `library` first to get a valid ID unless the user provides one directly in `/org/project` format. Use the user's full question as the query -- specific and detailed queries return better results than vague single words. Do not run more than 3 commands per question. Do not include sensitive information (API keys, passwords, credentials) in queries.

For version-specific docs, use `/org/project/version` from the `library` output (e.g., `/vercel/next.js/v14.3.0`).

If a command fails with a quota error, inform the user and suggest `npx ctx7@latest login` or setting `CONTEXT7_API_KEY` env var for higher limits. Do not silently fall back to training data.
<!-- context7 -->

## Global Rules

- Check `/spec` before making meaningful changes.
- Treat relevant files in `/spec` as authoritative project instructions.
- If behavior, scope, architecture, routes, config, or page requirements change, update the relevant `/spec` docs in the same task.

- Read before editing.
- Inspect the target files and nearby usage before changing code.

- Check `/components` and existing shared code before creating anything new.
- Reuse or extend existing components, functions, templates, and patterns whenever possible.
- Only create new components or helpers when no existing option reasonably fits.

- Make the smallest correct change.
- Keep diffs focused on the requested task.
- Do not refactor unrelated code.

- Prefer clarity over cleverness.
- Use the simplest solution that fully solves the problem.

- Never rename, move, or delete files unless explicitly requested.

- Validate external input at the boundary.
- Handle null, empty, malformed, and unexpected values explicitly.

- Fail clearly.
- Do not swallow errors.
- Return or log actionable errors with enough context to debug.

- Never hardcode secrets, credentials, tokens, or environment-specific values.

- Prefer existing dependencies and platform-native features.
- Do not add new dependencies unless they provide clear value.

- Verify changed behavior before finishing.
- Run the narrowest useful check available.
- If verification cannot be run, state that clearly and describe what was checked.
- The exception is when doing visual styling changes that will clearly be seen while running a project. These do not need to be tested

- Update docs when behavior, configuration, setup, or usage changes.

- Preserve accessibility.
- Do not break keyboard access, labels, focus behavior, or semantic structure.

- Make external writes retry-safe whenever possible.
- Assume retries, duplicate events, rate limits, and partial failures can occur.

- Check for redundancies, logic loops, and best practices. If you see a way to make anything more efficient, suggest it to me and I will determine if it is worth it.
