# Phase 1 - Product Alignment

Goal: remove only the ambiguities that would change implementation.

## If the user provides a PRD or detailed request

Treat it as the source of truth when it includes:
- core capability
- target user or usage scenario
- technical or non-functional constraints

Do not rewrite the PRD unless asked. Ask only questions whose answers affect:
- database schema
- API shape
- UI flow
- module boundaries
- runtime or framework choice
- permissions, auth, or data ownership

Ask at most five questions, ordered by implementation impact.

## If the user does not provide a PRD

Ask at most two rounds.

Round 1, up to three questions:
- What is the core capability?
- Who uses it and in what scenario?
- What form should it take: web app, CLI, API, desktop app, script, library, or local tool?

Round 2, only if still needed:
- What is in the MVP?
- What is explicitly out of scope?
- What success signal proves the first version works?

## Confirmation Summary

Before Phase 2, output:

```markdown
I will proceed with this understanding:
- Core capability:
- MVP scope:
- Explicitly out of scope:
- Technical constraints:
- Success signal:
```

Continue only after the user confirms or the request is already specific enough that implementation risk is low.
