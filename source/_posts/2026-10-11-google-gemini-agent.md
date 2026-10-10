---
title: Google Cloud 发布 Gemini Agent：面向办公场景的统一工作 Agent，可调用 Claude 模型
date: 2026-10-11 08:00:00
tags:
  - AI动态
  - Agent
  - Google
categories:
  - AI动态
description: Google Cloud 于 10 月 8 日在 Gemini at Work 2026 上发布 Gemini Agent，一个面向办公场景的统一工作 Agent：用户给出目标即可完成多步骤任务，按任务自动选择 Gemini 或 Anthropic Claude 模型，并支持子 Agent 协作与企业系统接入。
---

2026 年 10 月 8 日，Google Cloud 在 Gemini at Work 2026 大会上发布了 Gemini Agent。这是一个面向办公场景的统一工作 Agent，用户给出目标而非逐条指令，由 Agent 自行规划步骤、调用工具、连接企业系统，最终交付文档、代码或报告等完成的工作成果。

<!-- more -->

## 功能

据 Google Cloud 介绍，Gemini Agent 可以回答问题、处理知识型工作、生成图像与媒体、编写并执行代码。它支持通过一次输入完成多步骤任务：选择合适的工具、跨应用协调工作流，并将结果直接呈现在文档、收件箱或开发环境中。

Agent 运行在云端，在所有设备与通道间保持同一套记忆与上下文。耗时数小时乃至数天的长任务可以在用户关闭电脑后继续运行；对于长任务，它还可以拆分为多个临时子 Agent，分别并行或按顺序处理任务的不同阶段。

## 模型选择

Gemini Agent 会根据每个任务自动选择模型。目前可选范围包括 Google 自家的 Gemini 系列，以及 Anthropic 的 Claude 系列。Google 表示后续还会支持更多私有模型和开源模型。

## 协作模式

Google 还推出了两种 Agent 组织方式：一是多 Agent 编排，由 Gemini Agent 生成并协调专用于任务不同阶段的 AI Agent；二是"协作者 Agent"（coworker agents），可拥有独立的 Workspace 账号、邮箱地址、日历与访问权限，像团队成员一样被分配职责，通过员工熟悉的协作工具承接任务。

报道称 Agent 内置了四类记忆：会话记忆（针对特定任务）、语义记忆（执行多步骤任务中积累的知识库）、程序记忆（记录任务执行过程）以及综合的情节记忆（记录历史任务）。

## 企业接入

Gemini Agent 可运行在 Gmail、Drive、Docs、Slides、Sheets、Chat、Calendar 等 Workspace 应用中，也可从 Slack、Microsoft 365、命令行以及 Android、iOS、Web、Windows、Mac 等终端访问。在企业系统方面，它支持连接 Salesforce、ServiceNow、Snowflake、Jira 等第三方平台，并可嵌入第三方应用。

## 发布与推广

据报道，该 Agent 目前处于私有预览阶段，计划向选定 Workspace Business 与 Enterprise 计划客户扩大开放。Google 尚未公布定价与正式发布时间。Google Cloud 首席执行官 Thomas Kurian 在配套的博客文章中写道，用户给它的是"目标而非指令"，委托一个结果后，回来时即可拿到完成的工作。

此次发布被 CBS News、Bloomberg、Reuters、TechCrunch 等多家媒体在数小时内跟进报道，各方均将其解读为 Google 把聊天机器人转向"数字员工"的关键一步。同一时期，Microsoft、OpenAI 与 Anthropic 也都在推进类似的目标导向 Agent 方向。

## 来源

- Tech Insider：[Google Launches Gemini Agent to Rival OpenAI, Microsoft](https://tech-insider.org/google-gemini-agent-launch-workplace-ai-2026/)（2026-10-10）
- Digit.in：[Google introduces Gemini agent that can serve as your AI coworker: Here is what it can do](https://www.digit.in/news/general/google-introduces-gemini-agent-that-can-serve-as-your-ai-coworker-here-is-what-it-can-do.html/amp/)（2026-10-10）
- MartechAI：[Google Cloud Introduces Gemini Agent to Automate Workplace Tasks](https://www.martechai.com/ai-news/google-cloud-introduces-gemini-agent-to-automate-workplace-tasks-3470.html)（2026-10-10）
