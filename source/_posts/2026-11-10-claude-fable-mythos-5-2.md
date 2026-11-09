---
title: Anthropic 发布 Claude Fable 5.2 与 Mythos 5.2：同一模型两种访问路径，API 价格下调 20%
date: 2026-11-10 08:00:00
tags:
  - AI动态
  - Anthropic
  - 模型发布
categories:
  - AI动态
description: Anthropic 于 11 月 9 日发布 Claude Fable 5.2 与 Mythos 5.2，两者为同一底层模型，Fable 面向所有用户、Mythos 仅限通过验证的网络安全与生命科学机构。标准 API 价格降至每百万 token 输入 8 美元、输出 40 美元，输出速度较 5.1 代最高提升 30%。
---

2026 年 11 月 9 日，Anthropic 发布 Claude Fable 5.2 与 Claude Mythos 5.2。两款模型共享同一底层模型，区别在于安全防护与访问路径：Fable 5.2 是 Anthropic 面向所有用户提供的能力最强的通用模型，Mythos 5.2 则面向通过验证的网络安全与生命科学机构开放。

<!-- more -->

## 同一模型，两种访问路径

Anthropic 表示，Fable 5.2 与 Mythos 5.2 是同一底层模型的不同版本。Fable 5.2 内置了针对网络安全与生物学领域的安全防护，会拦截大多数高风险网络安全请求和多数研究类生物学请求；被拦截的请求会转由 Opus 4.8 或 Opus 5 回答。Mythos 5.2 移除了这些限制，仅限通过 Anthropic 网络安全验证计划（Cyber Verification Program）或生命科学验证计划（Life Sciences Verification Program）审核的机构使用。

Anthropic 称，Fable 5.2 的安全分类器较 5.1 代减少了约 55% 的不必要拦截，其中网络安全类减少约 60%，生物学类减少约 40%。

Fable 5.2 即日起通过 Claude 付费订阅计划、Claude Code、Claude Platform（模型 ID 为 `claude-fable-5-2`）以及 Amazon Web Services、Google Cloud 和 Microsoft Azure 提供。Mythos 5.2 通过上述验证计划开放，Claude Enterprise 客户也可通过 Claude Security 访问。编码 Agent 工具 Devin 在发布当日同步上线了 Fable 5.2，覆盖 Devin Desktop 与 Devin CLI。

## 定价与速度

标准 API 价格为每百万 token 输入 8 美元、输出 40 美元，较 5.1 代的 10 美元与 50 美元下调 20%。缓存读取价格为每百万 token 0.20 美元，5 分钟缓存写入为 10 美元、1 小时缓存写入为 16 美元；Batch API 价格为输入 4 美元、输出 20 美元。

Anthropic 同时新增可选的快速模式（fast mode），生成速度最高为标准模式的 2.5 倍，价格为每百万 token 输入 16 美元、输出 80 美元。快速模式适用于 Claude Code 与 Claude Platform，Mythos 5.2 的快速模式仅限验证计划内的机构使用。

两款模型的输出速度较 5.1 代最高提升 30%。上下文窗口为 100 万 token，最大输出为 128K token。

## 基准成绩

Anthropic 在发布中公布了两款模型的基准测试成绩，均为 Anthropic 自行公布的数据。Fable 5.2 在智能体编码基准 FrontierCode 2.0 上得分为 49.1%，高于 Fable 5.1 的 32.4%、Opus 5.5 的 45.5%、GPT-6 Astra 的 42.8% 与 Gemini 4 Carbon 的 41.1%；在 FrontierSWE v2 上得分为 69.9%，高于 Fable 5.1 的 56.3%。

Mythos 5.2 在网络安全基准 CyScenarioBench 上得分为 76.3%，高于 Mythos 5.1 的 61.7%；在 CVE Rediscovery 上得分为 89.6%，高于 Mythos 5.1 的 78.3%。在 Anthropic 公布的 15 项成绩中，两款新模型在 13 项上领先，Gemini 4 Carbon 在 AutomationBench 上领先 Fable 5.2。

## 定位

Anthropic 表示，Fable 5.2 定位于最具挑战性、开放性最强的技术工作，Mythos 5.2 则面向经审核的网络安全与生命科学工作。Anthropic 仍建议大多数用户以 Claude Opus 5.5 作为日常编码与知识工作的起点，在更具挑战性的项目中使用 Fable 或 Mythos。

## 来源

- VentureBeat：[Anthropic releases Claude Fable 5.2 and Mythos 5.2, pairing new, record-high benchmarks with 20% API cost reduction](https://venturebeat.com/technology/anthropic-releases-claude-fable-5-2-and-mythos-5-2-pairing-new-record-high-benchmarks-with-20-api-cost-reduction)（2026-11-09）
- AWS：[Introducing Claude Fable 5.2 on AWS](https://aws.amazon.com/blogs/machine-learning/introducing-claude-fable-5-2-on-aws/)（2026-11-09）
