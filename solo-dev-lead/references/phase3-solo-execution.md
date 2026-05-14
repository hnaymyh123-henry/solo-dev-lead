# Phase 3 - SOLO Execution

Goal: implement task cards while preserving scope and verification.

## Before Editing

For each task card:
- restate the task in one or two sentences
- list intended changed files
- read the nearest existing implementation patterns
- check for overlapping active task cards
- identify checks to run after implementation

If a task changes shared contracts, complete that foundation card before dependent cards.

## Execution Modes

### Multiple SOLO tasks or agents available

Assign independent cards to separate sessions. Give each session:
- one task card
- expected files or modules
- acceptance criteria
- constraints from architecture decisions
- required validation command or manual check

### Single SOLO session

Run cards sequentially. After each card:
- review changed files
- run targeted checks
- note any integration risk before starting the next card

## Implementation Discipline

- Keep unrelated refactors out of feature cards.
- Prefer existing project patterns over new abstractions.
- Add abstractions only when they remove real duplication or isolate shared policy.
- For bug fixes, reproduce or localize the failure before patching when feasible.
- For refactors, preserve behavior and run regression checks.

## Counterexample Self-Check

For each core path, check:

```markdown
- Null or missing input:
- Empty input:
- Boundary values:
- External dependency failure:
- Concurrent or repeated calls:
- Malicious or malformed input:
```

Fix discovered issues before moving to review.
