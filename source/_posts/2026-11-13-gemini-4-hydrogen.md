---
title: Google 发布 Gemini 4 Hydrogen：面向日常 Agent 工作流的快速模型
date: 2026-11-13 08:00:00
tags:
  - AI动态
  - Google
  - 模型发布
categories:
  - AI动态
description: Google 于 11 月 12 日发布 Gemini 4 Hydrogen，定位为面向日常编码与 Agent 工作流的快速执行模型，定价为每百万输入 token 1.50 美元、每百万输出 token 7.50 美元，同步上线 Google Search、Gemini 应用与 Gemini API。
---

2026 年 11 月 12 日，Google 发布 Gemini 4 Hydrogen。这是 Gemini 4 系列中面向日常编码与 Agent 工作流的快速模型，与主打深度长程推理的 Gemini 4 Carbon、Gemini 4 Argon 形成分工：Carbon 与 Argon 处理难度较高的系统设计与复杂问题，Hydrogen 负责快速执行。

<!-- more -->

## 定价与上下文

Gemini 4 Hydrogen 在整个 100 万 token 上下文窗口内采用统一价格：输入每百万 token 1.50 美元，输出每百万 token 7.50 美元。模型支持最高 100 万 token 的输入与最高 100 万 token 的输出。

在 Artificial Analysis 智能指数上，Hydrogen 在默认 high 思考层级下得分为 51，高于 Argon 的 50；在最高的 xhigh 层级下达到 54。

## 速度与性能

与 Gemini 3.8 Flash 相比，Hydrogen 在默认 high 层级下完成任务的速度快 2.5 倍，Terminal-Bench 4.1 得分从 18.2% 提升至 57%，编造内容减少 5 倍以上。在合作伙伴的早期测试中，Hydrogen 在复杂图谱、SQL 与数据密集型企业工作流中比 3.8 Flash 快 2 倍至 2.8 倍，token 用量减少 12% 至 23%。

在 Agent 相关评测中，Hydrogen 在 Agent Arena 实时榜单上排名第 5，在 HLE-Diamond 上以 58.8% 领先同级模型，在 Vals Tax Agent Bench 上以 52.3% 排名第一，在 Vals Legal Research Bench 上以 55.8% 并列第一。在多模态知识工作方面，模型在 Multimodal Knowledge Agent 评测中得分为 53.4%，在 Agents' Last Exam v1.1 中得分为 71.6%。

Hydrogen 提供四个思考层级：low、medium、high（默认）与新增的 xhigh，覆盖质量、延迟与成本的不同组合。

## 多模型协作

Google 同时在 Antigravity 中推出 Orchestrator 功能，在同一会话内动态切换 Carbon 与 Hydrogen 等模型。在 Terminal-Bench 4.0 上，Orchestrator 达到接近 Carbon 的任务成功率，同时平均少消耗 24% 的配额、快 19%。在并行 Agent 工作流中，Carbon 可担任协调者，Hydrogen 为工作与验证 Agent 提供动力，在隔离的工作区中同时构建与测试改动。

## 安全

Hydrogen 采用 Gemini 4 系列最新的安全栈。在 Agent 任务中，过度执行最高减少 81%，服务不足最高减少 79%，工具使用与编码评测中的错位行为与任务走捷径减少 12 倍。在内部 Agent 诚实度评测中，模型诚实率为 96.7%。在间接提示注入方面，Hydrogen 在 Gray Swan IPI 评测上的韧性比前代高 2.3 倍以上。

## 上线范围

Hydrogen 即日起在全球上线，覆盖 Google AI Studio 各层级、Gemini API、Gemini for business、Gemini 应用、Google Search，以及面向 Google AI Pro 与 Ultra 订阅用户的 Antigravity。Google Search 称这是迄今为止规模最大的搜索模型升级，Hydrogen 面向所有用户提供更贴合意图的理解、更直观的可视化回答，以及经查询扩展技术带来的更广泛的相关链接。

## 来源

- Google：[Introducing Gemini 4 Hydrogen](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-hydrogen/)（2026-11-12）
- Google：[Gemini 4 Hydrogen: Fast agentic development for coders](https://blog.google/innovation-and-ai/technology/developers-tools/build-with-gemini-4-hydrogen/)（2026-11-12）
- Google：[Google Search gets a major upgrade with Gemini 4 Hydrogen](https://blog.google/products-and-platforms/products/search/gemini-4-hydrogen-search-upgrade/)（2026-11-12）
- Digital Trends：[Google's next-gen Gemini 4 Hydrogen AI model is here, touting faster intelligence for all](https://www.digitaltrends.com/cool-tech/googles-next-gen-gemini-4-hydrogen-ai-model-is-here-touting-faster-intelligence-for-all/)（2026-11-12）
