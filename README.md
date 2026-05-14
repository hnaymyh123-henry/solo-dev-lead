# SOLO Dev Lead

SOLO Dev Lead is a TRAE SOLO Skill that turns SOLO into a software-development Tech Lead.

It guides SOLO through a disciplined delivery loop:

- classify the request
- align product scope
- make architecture decisions
- split work into task cards
- implement with scope control
- verify behavior
- review changes
- close with a retro

## Why

AI coding often jumps into implementation too early. This Skill keeps the process grounded in clear requirements, testable acceptance criteria, validation, review, and follow-up.

## Structure

```text
solo-dev-lead/
  SKILL.md
  references/
    phase1-product-alignment.md
    phase2-architecture-and-tasking.md
    phase3-solo-execution.md
    phase4-review-and-verification.md
    phase5-retro.md
    task-card-template.md
    project-context-template.md
```

## Install

Recommended:

1. Copy the `solo-dev-lead` folder into your TRAE SOLO project skills directory.
2. Or open TRAE SOLO Skills settings and import `solo-dev-lead/SKILL.md`.
3. Start a SOLO conversation and say:

```text
/dev I want to build a Todo app with login and task management.
```

Chinese example:

```text
使用 solo-dev-lead，帮我把这个新功能按技术负责人流程拆解并实现。
```

## Skill Link

https://github.com/hnaymyh123-henry/solo-dev-lead

## Notes

This Skill was adapted from an earlier Claude Code `/dev` workflow. The TRAE version removes Claude-specific command paths and treats GitHub Issues, PRs, and worktrees as optional accelerators rather than hard requirements.

## License

MIT
