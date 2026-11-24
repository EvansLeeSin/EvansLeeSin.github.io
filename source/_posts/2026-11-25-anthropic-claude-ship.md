---
title: Anthropic 推出 Claude Ship：AI Agent 审阅、修复并批准 Pull Request
date: 2026-11-25 08:00:00
tags:
  - AI动态
  - Anthropic
  - Agent
categories:
  - AI动态
description: Anthropic 于 11 月 23 日推出 Claude Ship（beta），由 Code Review、PR Steward 与 Claude Approvals 三个 Agent 组成，覆盖 GitHub Pull Request 的审阅、修复与审批环节，面向 Claude Team 与 Enterprise 计划开放。
---

2026 年 11 月 23 日，Anthropic 推出 Claude Ship（beta），一套面向 GitHub Pull Request 的 AI Agent 组合。Claude Ship 由 Code Review、PR Steward 与 Claude Approvals 三个 Agent 组成，分别负责审阅代码变更、修复评审与持续集成中发现的问题，以及按团队制定的审批策略决定变更是否可以合并。Claude Ship 面向 Claude Team 与 Enterprise 计划开放，适用于托管在 GitHub 上的仓库。

<!-- more -->

## 三个 Agent 的分工

Code Review 是三者中唯一已正式可用的组件。它结合代码变更与周边代码库进行审阅，核查发现的问题后以行内评论的形式发布，按严重程度排序。Code Review 此前已作为独立功能提供，Claude Ship 将其纳入完整的 PR 处理流程。

PR Steward 处于 beta 阶段，负责让 PR 保持可合并状态。它处理持续集成检查失败、合并冲突，以及来自 Code Review、其他审阅工具或团队成员的反馈，并在每次推送后评论说明自己改了什么、如何回滚。Anthropic 表示，PR Steward 的设计目标是不批准或合并 Pull Request，审批仍由 Claude Approvals 或人工完成。

Claude Approvals 同样处于 beta 阶段，负责执行团队写在仓库中的审批策略。团队将策略写为仓库默认分支下的 `.claude/approvals.yml` 文件，Claude Approvals 据此评估变更，报告哪些审批仍然缺失，并在策略允许时给出批准评审。Anthropic 建议团队先以仅观察模式运行审批功能，在建立信任后再开启自动批准。

## 两种使用方式

个人开发者可以通过 Claude Code 与桌面应用中的新命令 `/ship` 使用 Claude Ship。运行该命令后，Claude 会提交并推送变更、打开 Pull Request、审阅变更，并持续跟进反馈与失败的检查。`/ship` 命令自 11 月 23 日起在 Claude Code 与桌面应用中陆续推出。

管理员也可以为整个仓库开启 Claude Ship，之后它会自动处理该仓库团队的全部 Pull Request，无需逐个调用命令。Anthropic 建议从一个仓库开始，选定审阅级别与运行计划，设置月度支出上限，并先以仅观察模式运行审批策略。

## Anthropic 内部的使用数据

Anthropic 援引了自身 Claude Code 团队的使用情况作为参考：在 Claude 的审阅作为更广泛流程其中一环的前提下，该团队合并的 PR 数量从 6 月到 9 月增长了一倍以上，同时被回滚的 PR 占比下降超过 40%。Anthropic 举例称，Claude Code 团队的一名产品经理现在可以就一条客户反馈与 Claude 讨论想法与取舍，由 Claude 打开 PR，随后由 Claude Ship 完成审阅、修复与审批决策。

## 计费与适用范围

Claude Ship 按 token 计费，开启后会增加组织的用量成本。Claude Approvals 本身没有基础费用，但策略中的分类器按其使用的 token 计费；如果策略触发了 Claude 的审阅，即使在仅观察模式下也会产生 Code Review 的费用。

符合条件的 Claude Enterprise 组织可以申请最低 1 万美元的 Claude Ship 用量额度，申请截止日期为 2027 年 1 月 15 日。

Claude Ship 不适用于采用零数据保留、HIPAA 配置或客户自管加密密钥的组织。Anthropic 在文档中说明，这些 Agent 不能保证完全准确，可能遗漏缺陷、安全漏洞或其他问题，关键代码仍需常规的静态分析与人工评估。

## 来源

- TechCrunch：[Anthropic launches Claude Ship, letting AI agents review, fix, and approve code changes](https://techcrunch.com/2026/11/23/anthropic-launches-claude-ship-letting-ai-agents-review-fix-and-approve-code-changes/)（2026-11-23）
- Neowin：[Anthropic's new Claude Ship agents automatically fix and approve GitHub pull requests](https://www.neowin.net/news/anthropics-new-claude-ship-agents-automatically-fix-and-approve-github-pull-requests/)（2026-11-24）
- 9to5Mac：[Anthropic launches new Claude Ship feature for builders](https://9to5mac.com/2026/11/23/anthropic-launches-new-claude-ship-feature-for-builders/)（2026-11-23）
