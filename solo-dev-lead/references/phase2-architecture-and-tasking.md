# Phase 2 - Architecture and Tasking

Goal: turn the confirmed scope into implementation decisions and task cards.

## Architecture Checkpoint

For non-small changes, decide these before implementation:

```markdown
Architecture decisions:
- Runtime and framework:
- Data storage:
- Authentication and authorization:
- API or command interface:
- Error format:
- Testing approach:
- Project structure:
- Deployment or local-only assumption:
```

If the user has no preference, choose the smallest conventional option that matches the existing codebase and explain the reason briefly.

For existing projects, inspect:
- README and setup docs
- package or dependency files
- existing test framework
- routing, service, and data access patterns
- project-specific rules, including `.trae/rules`, `AGENTS.md`, `CLAUDE.md`, or `PROJECT_CONTEXT.md` if present

## Task Card Rules

Each task card must:
- be independently understandable
- name expected changed files or modules when known
- include testable acceptance criteria
- state dependencies
- state what is explicitly not included

Use `task-card-template.md`.

## Dependency Shape

Group cards as:

```markdown
Foundation:
- CARD-1 ...

Parallelizable:
- CARD-2 ...
- CARD-3 ...

Integration:
- CARD-4 ...
```

If no true parallelism exists, say so and run cards sequentially.

## Tooling Choice

Use GitHub Issues and PRs only if the repository already uses them and authentication is available. Otherwise, keep the board local:

```markdown
docs/solo-dev/tasks.md
docs/solo-dev/decisions.md
docs/solo-dev/retro.md
```

Do not block delivery on remote project-management setup.
