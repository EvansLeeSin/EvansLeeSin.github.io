---
title: Meta 发布 Muse Ember：最小最便宜的 Muse 模型，瞄准 Agent 高频重复任务
date: 2026-11-11 08:00:00
tags:
  - AI动态
  - Meta
  - 模型发布
categories:
  - AI动态
description: Meta 于 11 月 9 日发布 Muse Ember，Muse 系列中最小、最便宜的模型，定位 Agent 每天重复执行的工具调用、编码子任务、路由与长文档解析等工作。输入每百万 token 0.10 美元，上下文窗口 100 万 token，已在 Meta Model API 与 Muse Code 上线。
---

2026 年 11 月 9 日，Meta 发布 Muse Ember，这是 Muse 系列中最小、最便宜的模型。Meta 表示，该模型面向 Agent 每天重复执行的工作：工具调用、编码子任务、路由、信息抽取和长文档解析。

Muse Ember 即日起在 Meta Model API 与 Muse Code 上线，模型 ID 为 `muse-ember-1.0`，同时登陆 Google Cloud 与 Oracle Cloud，并支持 Responses API。

<!-- more -->

## 定价

输入每百万 token 0.10 美元，缓存输入每百万 token 0.004 美元，输出每百万 token 0.50 美元。输入超过 20 万 token 的请求按长上下文定价，费率升至输入每百万 token 0.30 美元、缓存输入 0.012 美元、输出 1.50 美元。

上下文窗口为 100 万 token，单次输出上限 51.2 万 token。Meta 表示，模型可以一次读入完整代码库或文档集。

## 性能

Meta 引用 Artificial Analysis 2026 年 11 月 9 日的数据称，Muse Ember 在最高推理档位下 Intelligence Index 得分为 36，与 Claude Haiku 5.5 的最高分持平，单个任务成本约为 Haiku 的三分之一，每任务 0.14 美元；同一指标下 Muse Spark 1.3 得分为 37，每任务成本 2.39 美元。

在 Meta 公布的评测表中，Muse Ember 在 AutomationBench 端到端业务工作流上得 37.8 分，在 Agents' Last Exam 端到端 Agent 任务上得 61.6 分，在 Terminal-Bench 4.0 上得 40.9 分，在 Coding Agent Index 上得 46 分。Meta 同时表示，面对最难的问题，可由 Muse Wonder 负责规划、Muse Ember 承担执行量。

## 多模态

Muse Ember 原生支持文本、图像、音频与视频输入。Meta 表示，Agent 可以用它读取截图、图表与扫描文档，或处理语音备忘、会议录音与视频；也可以直接根据截图操作电脑。

## 安全

发布前，Meta 按其 Superintelligence Scaling Framework 对 Muse Ember 进行了评估，覆盖化学与生物、网络安全与失控风险，评估结果显示模型在各类别中均低于框架的高风险阈值。Meta 表示，尽管是小模型，Muse Ember 接受了与系列其他模型相同的核心安全训练与测试，还评估了它代表用户行动时的表现，包括是否遵循用户意图、妥善处理敏感信息、抵御藏在网页、文档或工具输出中的指令，以及在高影响操作前寻求人工确认。

## 背景

Muse Ember 是首个使用 Muse Wonder Full 训练的模型。至此 Muse 系列形成三档分工：Muse Wonder 面向最难的问题，Muse Spark 面向编码与 Agent 工作流，Muse Ember 面向可大规模重复的编码与 Agent 任务。Meta 表示，目标是个人超级智能，让前沿能力以可扩展的价格提供给所有人，并称还有更高效的模型在训练中。

## 来源

- Meta：[Introducing Our Smallest, Most Efficient Model: Muse Ember](https://research.meta.ai/blog/muse-ember)（2026-11-09）
- eesel AI：[Meta Muse Ember explained: specs, uses, and how to call it (2026)](https://www.eesel.ai/blog/meta-muse-ember)
- madrobot：[Meta Muse Ember: Haiku-level AI at a third of the cost per task](https://madrobot.blog/2026/11/09/meta-muse-ember-small-model-ai-agents/)
