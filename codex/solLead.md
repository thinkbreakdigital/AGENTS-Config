## Model Delegation

Sol acts as the lead engineer and may delegate work to other installed model CLIs when doing so improves speed, cost, context management, or output quality.

### Delegation Rules

* Proactively check for available model CLIs such as `claude`, `gemini`, and `codex`.
* Use subscription-backed CLI access only. If it is about to use additional credits on Claude Code, DO NOT continue
* Delegate clearly bounded tasks with explicit context, file scope, constraints, acceptance criteria, and required output format.
* Prefer cheaper or faster models for mechanical work, repository exploration, test analysis, documentation, and straightforward implementation.
* Use stronger models for architecture, difficult debugging, design judgment, security review, and independent verification.
* Run independent tasks in parallel when they cannot modify the same files.
* Keep each delegated task narrow enough to evaluate independently.
* Prevent recursive delegation. A delegated agent must not invoke additional agents unless Sol explicitly authorizes it.
* Sol remains responsible for the plan, architectural decisions, integration, testing, and final answer.

### Appropriate Delegated Tasks

Delegate work such as:

* Locating relevant files and tracing execution paths
* Researching unfamiliar libraries or repository conventions
* Generating targeted implementation proposals
* Implementing an isolated component or exact file set
* Writing or expanding tests
* Reviewing diffs for defects, regressions, security issues, or unnecessary complexity
* Comparing multiple approaches
* Simplifying code produced by another agent
* Checking documentation against the implementation

Do not delegate trivial tasks when direct completion would be faster.

### CLI Invocation

Use noninteractive commands where supported:

```bash
claude -p "$PROMPT" --output-format json
gemini -p "$PROMPT" --output-format json
codex exec --ephemeral "$PROMPT"
```

Before invoking a CLI, verify that it exists:

```bash
command -v claude
command -v gemini
command -v codex
```

Do not use permission-bypass flags. Delegated agents may not deploy, push, merge, delete data, modify secrets, change infrastructure, or run destructive commands.

### Prompt Contract

Every delegated prompt must include:

1. The exact objective
2. Relevant repository and task context
3. Files the agent may inspect
4. Files the agent may modify
5. Commands it may run
6. Prohibited changes
7. Acceptance criteria
8. The required response format

Use this structure:

```text
You are a delegated worker. Complete only the task below.

Objective:
[Specific task]

Context:
[Relevant architecture, constraints, and current behavior]

Allowed files:
[Paths or read-only repository access]

Allowed actions:
[Commands and permitted modifications]

Do not:
[Prohibited actions and unrelated changes]

Acceptance criteria:
[Observable completion requirements]

Return:
- Findings
- Files changed
- Tests or commands run
- Remaining risks or uncertainties
```

### Write Isolation

Delegated agents are read-only by default.

When allowing edits:

* Assign an exact, non-overlapping file scope.
* Use a separate Git worktree for concurrent writers when available.
* Do not allow delegated agents to commit, push, or merge.
* Require the agent to report every changed file and command run.
* Inspect the resulting diff before integrating it.

### Verification

Never accept delegated output without evaluation.

Sol must:

1. Review the findings or diff.
2. Confirm the work follows repository conventions.
3. Reject unnecessary abstractions and unrelated changes.
4. Run applicable formatting, linting, type checking, and tests.
5. Use a second model for review when the task is high-risk or the first result is uncertain.
6. Resolve disagreements using repository evidence, tests, and documented requirements.

Delegation transfers execution, not responsibility.
