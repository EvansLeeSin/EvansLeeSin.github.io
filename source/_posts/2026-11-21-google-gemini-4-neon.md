---
title: Google 发布 Gemini 4 Neon：旗舰级能力，任务完成速度更快
date: 2026-11-21 08:00:00
tags:
  - AI动态
  - Google
  - 模型发布
categories:
  - AI动态
description: Google DeepMind 于 11 月 18 日发布 Gemini 4 Neon，定位在 Carbon 与 Hydrogen 之间，以更快的速度提供接近旗舰的性能，上下文窗口 100 万 token，定价为输入每百万 token 3 美元、输出 15 美元。
---

2026 年 11 月 18 日，Google DeepMind 发布 Gemini 4 Neon。Google 表示，Neon 在软件工程、知识工作和科学工作流等复杂任务上提供旗舰级智能，同时保持更快的端到端任务完成速度。

Neon 是 Gemini 4 系列的第四款模型，定位在 Carbon 与 Hydrogen 之间：Carbon 面向最难的长周期项目与深度研究，Hydrogen 是速度最快、成本最低的日常执行模型，Neon 则在深度与效率之间取得平衡。Google 称，在早期评估中，Neon 在整体质量上达到或超过 Carbon，速度约为 Carbon 的 3 倍，成本约为 60%。

<!-- more -->

## 定价与上下文

Neon 的定价为输入每百万 token 3 美元、输出每百万 token 15 美元，缓存输入每百万 token 0.15 美元，上下文窗口为 100 万 token。模型提供低、中、高、超高四个思考级别，其中超高级别是在 Hydrogen 发布时引入 Gemini 模型的。

作为对照，Carbon 的标准定价为输入每百万 token 4 美元、输出 20 美元；促销价输入 2 美元、输出 10 美元，促销将于 11 月 30 日结束。此后 Neon 的输入与输出价格将比 Carbon 低 25%。

## 基准表现

在 Artificial Analysis 智能指数上，Neon 在超高思考级别下得分为 61，排名第三，排在 GPT-6.2 Astra 与 Claude Fable 5.2 之后，比 Carbon 高 1 分。Artificial Analysis 的测算显示，Neon 每个任务的成本约为 6.44 美元，比 Carbon 低约 17%，每个任务耗时约 21 分钟，比 Carbon 少约 40%。

在 Vals 指数上，Neon 以 70.9% 排名第二，并在法律研究基准与税务 Agent 基准上排名第一。在 Surge AI 的多项基准中，Neon 在金融、会计、电子表格建模与复杂约束遵循等类别多数排名第一；在 Chartography 上得分为 73.5%，在 Agents' Last Exam v1.1 上得分为 75.8%。

在 Agent 相关基准中，Neon 在 Zapier 的 AutomationBench 上以 56.3% 排名第一，在 Andon Labs 的 Vending-Bench 2 上以 16,843 美元排名第一，并在 Arena 新推出的 Agent Arena Index 上以 1336 分排名第二。在 Artificial Analysis 编码 Agent 指数上，Neon 以 58.6 分排名第一。

在科学与数学推理方面，Neon 在 Terminal-Bench Science 上得分为 70.5%，在 RiemannBench 上为 84.0%，在 HLE-Diamond 上为 71.3%，均为同类最佳。在代码安全方面，Neon 在 AutoBaxBench 困难级别上达到 76%，在 CWE-bench v2 上达到 70.7%，比 Carbon 高 3.4 个百分点。Google 还表示，Neon 在内部 Antigravity 测试中创下公司最低的编造率。

## 上线渠道

Gemini 4 Neon 已在 Gemini API（Google AI Studio）、Gemini for Business、Google Antigravity 以及 Gemini 应用中上线，Antigravity 与 Gemini 应用中的使用面向 Google AI Pro 与 Ultra 订阅用户。Neon 同时取代了此前的 Argon 模型。

## 来源

- Google Blog：[Introducing Gemini 4 Neon](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/)（2026-11-18）
- 9to5Google：[Gemini 4 Neon launches: Carbon quality at Flash speeds, for AI Pro](https://9to5google.com/2026/11/18/gemini-4-neon-announcement/)
- VentureBeat：[Google launches Gemini 4 Neon with Opus 5.5-level coding performance at 25% lower API token prices](https://venturebeat.com/technology/google-launches-gemini-4-neon-with-opus-5-5-level-coding-performance-at-25-lower-api-token-prices)
- Artificial Analysis：[Google continues to accelerate its release cadence with Gemini 4 Neon](https://artificialanalysis.ai/articles/gemini-4-neon-intelligence-gain)
