---
title: Anthropic 发布 Claude Haiku 5.5：轻量模型降价 75%，瞄准 Agent 高频调用场景
date: 2026-10-08 14:00:00
tags:
  - AI动态
  - Anthropic
  - Agent
  - 模型发布
categories:
  - AI动态
description: Anthropic 发布 Claude Haiku 5.5，一个月内第三款 5.5 系列模型。价格比 Haiku 4.5 低 75%，定位分类、摘要、抽取与语音 Agent 等高频轻量任务，并首次在 Haiku 系列中加入针对高风险网络安全请求的内置防护。
---

2026 年 10 月 7 日，Anthropic 发布 Claude Haiku 5.5，这是过去一个月内 Claude 5.5 系列的第三款模型。报道没有给出精确发布时间及其时区，本文按报道日期记录，不虚构具体上线时刻。

这不是旗舰大模型的更新，而是一次典型的"轻量模型降本"发布：官方定位是分类、摘要、信息抽取这类任务，以及在线客服、语音 Agent、应用内助手等场景。对做 Agent 开发的人来说，这类消息的价值不在参数规模，而在调用成本——高频、短 prompt 的工具调用环节，恰恰是 Agent 总成本的大头。

<!-- more -->

## 官方宣布了什么

根据 Reuters 的报道，Haiku 5.5 的关键信息如下：

- **定位**：面向分类（classification）、摘要（summarization）、抽取（extraction）任务，典型场景包括在线客服、语音 Agent 和应用内助手。
- **价格**：比前代 Haiku 4.5 低 75%。100K token 以内 prompt 的价格为输入每百万 token **0.10 美元**、输出每百万 token **0.50 美元**；更长的 prompt 则为输入 0.50 美元、输出 2.50 美元。
- **安全**：这是首款内置防护的 Haiku 模型，针对一小类高风险网络安全请求做了限制。官方称绝大多数日常任务不受影响。

报道还提到，这是 Anthropic 在计划 IPO 之前扩张产品线的一部分，一个月内连发三款 5.5 系列模型，节奏明显加快。

## 定价值得细看的地方

这次定价采用了按 prompt 长度分档的策略：100K token 是一个分界线，超过之后输入输出价格都是 5 倍。这对 Agent 开发者是个明确信号——如果你用 Haiku 5.5 处理长上下文（比如把整个知识库切片塞进 prompt），单价会跳档。

换句话说，Anthropic 在用价格引导你：轻量模型就该干轻量任务，重型上下文请用更贵的系列。这与之前 GPT-6.1 Sol 降缓存价的思路正好互补：一个奖励"复用上下文"，一个奖励"保持 prompt 精简"。

## 对开发者的影响

**我的判断是**，Haiku 5.5 值得放进 Agent 流程的"分诊"候选：把任务按难度分级，简单环节（意图分类、摘要、字段抽取、路由判断）用 Haiku 5.5 这类便宜模型，复杂推理再升级到旗舰模型。这种大小模型混用的架构，是目前控制 Agent 调用成本最实在的手段之一。

如果想验证是否值得切换，可以做两件事：

1. **测分诊准确率**：拿真实流量对比 Haiku 5.5 与当前模型在分类/抽取任务上的准确率差异，看省下的成本是否值得那点精度损失。
2. **算 prompt 分档**：统计现有调用的 prompt 长度分布，看有多少比例会落到 100K 以上的跳价档，必要时做 prompt 瘦身或截断。

另外值得注意的是"首款带网络安全防护的 Haiku"这个表述。轻量模型过去常被认为防护较弱，Anthropic 现在开始补这一课，说明即使是低成本模型，厂商也意识到它们会被用在有真实风险的生产环节。对企业应用来说，这是个积极信号，但具体防护覆盖哪些请求类型，还要等官方文档细则。

## 来源

- Reuters：[Anthropic launches third Claude 5.5 model, expanding AI lineup before planned IPO](https://www.reuters.com/business/anthropic-launches-third-claude-55-model-expanding-ai-lineup-before-planned-ipo-2026-10-07/)（2026-10-07）
- Channel News Asia 对同一发布的转载报道：[Anthropic launches third Claude 5.5 model](https://www.channelnewsasia.com/business/anthropic-launches-third-claude-55-model-expanding-ai-lineup-planned-ipo-6440641)

以上价格与定位信息来自厂商经媒体报道的口径，实际计费与可用性以 Anthropic 官方文档为准。
