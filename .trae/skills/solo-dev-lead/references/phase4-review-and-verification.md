# Phase 4 - Review and Verification

Goal: decide whether the work is ready to hand back.

## Scope Review

Compare changes with task cards:
- unrelated files changed -> revert or explain before proceeding
- acceptance criteria missing -> continue implementation
- hidden behavior change -> document and verify

## Verification Ladder

Run checks in this order when available:

1. Format or syntax checks.
2. Unit tests for touched modules.
3. Integration tests for changed flows.
4. Full test suite when shared contracts, auth, schema, build, or dependencies changed.
5. Manual UI or CLI smoke test for user-visible workflows.

If a check cannot run, explain why and provide the closest executed substitute.

## Review Checklist

```markdown
Critical:
- Scope drift:
- Data loss or migration risk:
- Auth or permission boundary:
- Injection or unsafe command construction:
- Missing error handling for external calls:
- Broken public API or CLI compatibility:

Quality:
- Edge-case coverage:
- Test coverage:
- Duplicated logic:
- Hardcoded values:
- Dead code or unused imports:
- User-facing copy and error clarity:
```

Critical issues block completion. Quality issues can ship only if they are minor and documented.

## Completion Report

When done, output:

```markdown
Done:
- ...

Verified:
- ...

Notes:
- ...
```
