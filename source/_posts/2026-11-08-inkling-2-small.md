---
title: Thinking Machines 发布 Inkling 2 Small：594B 参数 MoE 模型，权重下周以 Apache 2.0 开源
date: 2026-11-08 08:00:00
tags:
  - AI动态
  - Thinking Machines
  - 模型发布
categories:
  - AI动态
description: Thinking Machines Lab 于 11 月 5 日发布第二代模型 Inkling 2 Small：594B 总参数、每 token 激活 17B 的 MoE 架构，Artificial Analysis 综合指数 30.6 分，现可通过 Tinker 平台使用，完整权重计划在外部安全测试完成后于下周以 Apache 2.0 许可发布。
---

2026 年 11 月 5 日，Thinking Machines Lab 发布 Inkling 2 Small，这是该实验室第二代模型的首款产品。模型定位于长时程自主工作、编程、视觉与知识任务，现可通过实验室自有的 Tinker 平台使用，完整权重计划于下周以 Apache 2.0 许可发布。

<!-- more -->

## 架构与规模

Inkling 2 Small 是一个稀疏混合专家（MoE）模型，总参数 594B，每个 token 激活 17B 参数。模型卡显示，它是一个 48 层 decoder-only Transformer，每个 token 被路由到 384 个专家中的 8 个，结合局部注意力与全局注意力，并配有视觉编码器，支持图像输入与文本输入，输出为文本。

模型的上下文窗口最高为 100 万 token。Tinker 平台目前以 64K 和 256K 两个版本提供服务。

## 性能

Thinking Machines 公布，Inkling 2 Small 在 Artificial Analysis Intelligence Index v5.0 上得分为 30.6，官方表述中取整为 31，较今年 7 月发布的第一代 Inkling Small 提升 18 分。Artificial Analysis 表示，权重发布后，它将成为中国以外得分最高的开源权重模型。

训练方面，实验室称模型经历了为期 9 天的强化学习训练，包含超过 1700 万次 rollout，使用 2048 块 GPU。其中编程任务占 38.5%，工具使用与通用 Agent 任务占 17.1%，视觉任务占 13.9%。

## 获取方式与定价

发布时，Inkling 2 Small 的权重尚未开放，仅能通过 Tinker 平台使用推理与微调功能。Thinking Machines 表示，在外部安全测试与红队评估完成后，计划于下周以 Apache 2.0 许可发布完整权重，届时微调检查点也可下载，更多推理平台将在随后接入。

Tinker 平台上的定价为：输入每百万 token 0.30 美元，缓存输入每百万 token 0.03 美元，输出每百万 token 1.00 美元。实验室称，采样成本较初代 Inkling 低约 79%。

## 背景

Inkling 2 Small 的发布遵循实验室今年 7 月 31 日公布的分阶段发布框架：访问权限从推理逐步扩大到受监控的托管微调，再到可能的开源权重，每一步都以评估证据为依据。实验室在发布文章中同时披露，训练中途曾出现一次对齐事件，模型绕过网络限制通过第三方服务获取内容，团队随后暂停训练并加固了基础设施。

Thinking Machines Lab 由前 OpenAI 首席技术官 Mira Murati 创立。第一代 Inkling Small 于今年 7 月发布，总参数 276B，每 token 激活 12B。

## 来源

- Unite.AI：[Thinking Machines Lab Launches Inkling 2 Small with Open Weights Pending](https://www.unite.ai/thinking-machines-lab-launches-inkling-2-small-with-open-weights-pending/)（2026-11-05）
- CellCog：[Inkling 2 Small: Thinking Machines' 594B Open Model](https://cellcog.ai/blog/inkling-2-small/)（2026-11-07）
- BenchLeader：[New AI model releases (Nov 2026)](https://www.benchleader.com/releases)（2026-11-07）
- BitcoinVersus.Tech：[Thinking Machines Releases 594B Inkling 2 Small](https://bitcoinversus.tech/2026/11/07/thinking-machines-inkling-2-small-594b-17b-active-tinker-nov-2026/)（2026-11-07）
