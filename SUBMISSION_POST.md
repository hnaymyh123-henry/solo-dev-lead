# 【Skill 创作】SOLO Dev Lead：让 TRAE SOLO 像技术负责人一样拆解、实现和 Review 软件需求

## 1、Skill 简介

SOLO Dev Lead 是一个面向软件开发场景的 TRAE SOLO Skill。它会让 SOLO 不再只是“收到需求就立刻写代码”，而是先扮演一个有工程纪律的 Tech Lead：识别需求类型、确认产品范围、做架构决策、拆解任务卡、组织实现、验证测试、Review diff，最后输出 Retro。

它适合经常用 AI 写代码的人，尤其适合产品经理、独立开发者、AI 编程学习者，以及想让 SOLO 更稳定地处理新功能、Bug 修复、重构和项目初始化的用户。

## 2、使用场景

我做这个 Skill 的原因很直接：AI 写代码很快，但如果没有流程约束，常见问题也很明显：

- 一上来就改代码，需求边界还没确认清楚；
- 没有把任务拆成可验证的 acceptance criteria；
- 大改动和小改动混在一起，后续很难 Review；
- 测试只写“已通过”，但看不出验证了哪些路径；
- 做完功能没有复盘，下一轮接着改时上下文又散掉了。

SOLO Dev Lead 试图解决的是“AI 编程里的工程管理缺口”。它把一次开发请求拆成 5 个阶段：

1. Phase 0：判断这是新项目、小改动、新功能、Bug、重构还是架构变更；
2. Phase 1：只问会影响实现的关键产品问题；
3. Phase 2：锁定技术决策，并拆成可执行任务卡；
4. Phase 3：按任务卡执行，保留范围边界；
5. Phase 4/5：Review、验证、Retro 和下一步建议。

这样做之后，SOLO 更像一个能带节奏的技术负责人，而不是一个只会补代码的助手。

## 3、创作过程

这个 Skill 的前身是我为 Claude Code 设计的 `/dev` 多 Agent 软件开发 SOP。原始版本强依赖 Claude Code 的 slash command、`.claude/commands` 目录、Worker Agent、GitHub Issue、PR 和 worktree。

为了适配 TRAE SOLO，我没有做简单的“替换品牌名”，而是重新按 SOLO Skill 的结构做了改造：

- 入口改成 TRAE Skill 标准的 `SKILL.md`；
- 把详细阶段流程拆到 `references/`，让主文件保持轻量；
- 把 Claude Code 专属的命令路径移除；
- 把 GitHub Issue / PR / worktree 从硬依赖改为可选增强；
- 增加本地 fallback：没有 GitHub 时使用本地任务卡、分支、diff review；
- 明确 TRAE SOLO 中的执行方式：有多任务能力就并行拆分，没有就按任务卡顺序执行；
- 保留最有价值的工程约束：需求确认、架构检查点、验收标准、反例自检、Review 清单、Retro。

改造后的目录结构是：

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

我在 TRAE SOLO 中做了实际测试：导入 Skill 后，可以正常触发，并且 SOLO 会按照 Skill 里的 Tech Lead 流程执行，不会直接跳到写代码。测试中它能先分类需求，再生成任务拆解和验证步骤，符合预期。

【截图 1：Skill 在 TRAE SOLO 中成功导入】

【截图 2：输入开发需求后，SOLO Dev Lead 先进行需求分类和范围确认】

【截图 3：Skill 输出任务卡 / 架构决策 / 验证清单】

## 4、使用步骤

推荐方式：

1. 下载或复制 `solo-dev-lead` 文件夹；
2. 在 TRAE SOLO 中打开 Skills 管理入口；
3. 导入 `SKILL.md`，或把整个 `solo-dev-lead` 文件夹放入项目 Skill 目录；
4. 在 SOLO 对话中输入：

```text
/dev 我想做一个带登录和任务管理的 Todo 应用
```

或者：

```text
使用 solo-dev-lead，帮我把这个 Bug 修复流程跑一遍
```

触发后，它会先判断任务类型，再根据需要进入产品对齐、架构决策、任务拆解、实现、验证和 Review。

## 5、效果展示

使用前，我通常需要在对话里反复提醒 AI：

- 先别急着写代码；
- 先拆任务；
- 验收标准写清楚；
- 改完后跑测试；
- Review 一下有没有越界改动。

使用 SOLO Dev Lead 后，这些约束都被沉淀在 Skill 里。只要任务和软件开发有关，SOLO 就会自动进入更结构化的工程流程。

一个典型输出会包含：

- 需求类型判断；
- MVP 范围和不做事项；
- 架构决策；
- 任务卡和依赖关系；
- 每张任务卡的验收标准；
- 实现后的验证清单；
- Review 和 Retro。

对我来说，最大的变化是：AI 不再只是“帮我写”，而是在帮我“把开发过程管住”。

## 6、Skill 链接

Skill 分享链接 / GitHub：

https://github.com/hnaymyh123-henry/solo-dev-lead

## 7、总结与思考

我目前最满意的是，这个 Skill 把一个原本偏 Claude Code 的多 Agent `/dev` 工作流，改造成了更适合 TRAE SOLO 的工程 Skill。它没有强迫用户必须使用 GitHub、PR 或复杂工具，而是把核心价值保留下来：让 AI 写代码之前先想清楚，写完以后能验证和 Review。

后续我还想继续优化三件事：

- 增加更多真实项目测试样例；
- 针对前端、后端、脚本、数据分析等不同项目类型，补充更细的任务卡模板；
- 把 Review 清单和测试输出做得更适合新手阅读。

我希望体验这个 Skill 的同学重点反馈两点：第一，它有没有真的让 SOLO 更稳；第二，它的问题和追问是不是足够少、足够关键。

这个作品不是为了让流程变复杂，而是为了让 AI 编程更可控。
