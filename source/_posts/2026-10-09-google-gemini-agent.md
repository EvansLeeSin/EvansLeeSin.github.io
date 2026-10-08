---
title: Google Cloud 推出 Gemini Agent：统一工作入口，按任务自动选择 Gemini 与 Claude 模型
date: 2026-10-09 08:00:00
tags:
  - AI动态
  - Google
  - AI Agent
categories:
  - AI动态
description: Google Cloud 于 10 月 8 日在 Gemini at Work 2026 大会上发布 Gemini Agent，定位为面向工作的统一 Agent：一个输入框内完成知识工作、问答、内容创作与编码，按任务自动选择最合适的模型，初期支持 Gemini 与 Claude 系列模型。
---

2026 年 10 月 8 日，Google Cloud 在 Gemini at Work 2026 大会上发布 Gemini Agent，将其定位为面向工作的统一 Agent（universal agent for work）。Google 表示，用户可以在一个输入框内完成知识工作、问答、内容创作与编码等各类任务。

<!-- more -->

## 工作方式

Gemini Agent 具备组织的业务上下文，可以规划任务、调用技能和工具、连接企业的业务系统，并把成品交付回用户已经使用的文档、收件箱和开发环境中。

它可直接在 Google Workspace 应用内使用，包括 Gmail、Drive、Docs、Slides、Sheets、Chat 和 Calendar，也可通过 Microsoft 365 和 Slack 使用，并能连接到 Teams 等协作工具以及 Git、Jira 等开发工具。

## 模型调度与成本

Google 表示，Gemini Agent 会为每个任务选择最合适的模型，初期运行在 Google 自家 Gemini 系列模型与 Anthropic Claude 系列模型上，后续将加入更多模型。同时，Agent 内置成本控制，并具备企业客户所需的安全、管理和治理能力。

Google CEO Sundar Pichai 在会上表示，Gemini Agent 先从企业客户切入，再扩展到消费者场景，原因是企业场景对安全、规模和性能的要求更高。

## Coworker Agent 与行业版本

用户可以创建 "coworker agent"，让其作为团队成员行事：拥有独立的邮箱地址，且只能访问被授予的信息。此外，Google 还推出了面向金融服务和法律行业的专用版本（已进入预览），面向政府、医疗和零售行业的版本将随后推出。

## 规模数据

据 Google Cloud CEO Thomas Kurian 在主题演讲中的介绍，过去一年，近 500 家 Google Cloud 客户各自处理了超过一万亿 token；目前近 80% 的 Google Cloud 客户在使用其 AI 产品，近 90% 的财富 100 强企业在使用 Gemini Enterprise。

## 背景

此次发布正值各大科技公司竞相推出自主工作 AI 之际：OpenAI 于 9 月推出了常驻型 Agent 产品 dots，Meta 也在上月发布了个人 AI Agent Muse。Gemini Agent 的推出，使 Google 在企业 Agent 市场正式加入这场竞争。

## 相关更新

10 月 7 日，Google 还扩展了 Developer Knowledge API 生态：新增 gcloud CLI 接口、官方 agent skill、API Explorer 和客户端库，让 AI 编程助手可以直接拉取最新的官方文档，而不是依赖模型训练时学到的数据。

例如，开发者可以用以下命令基于官方文档生成问答：

```
gcloud developer-knowledge answer-query \
--query="How do I create a BigQuery dataset?"
```

官方 agent skill 的安装命令为：

```
npx skills add google/skills --skill retrieving-developer-knowledge
```

该 skill 可配合 Developer Knowledge MCP server 使用，也可以在必要时回退到 REST API。它教导 AI 助手在回答技术问题前先检索相关文档，而不是把预训练知识当作权威依据。

## 来源

- Google 官方博客：[Google Cloud launches Gemini agent](https://blog.google/innovation-and-ai/infrastructure-and-cloud/google-cloud/gemini-at-work/)（2026-10-08）
- Unite.AI：[Google Cloud Unveils Gemini, Its Universal Agent for Work](https://www.unite.ai/google-cloud-unveils-gemini-its-universal-agent-for-work/)（2026-10-08）
- Reuters（经 LA Post）：[Google Cloud introduces Gemini agent for work as AI race heats up](https://www.lapost.com/content/google-cloud-introduces-gemini-agent-for-work-as-ai-race-heats-up)（2026-10-08）
- BitcoinVersus.Tech：[Google Lets AI Coding Assistants Read Live Official Docs](https://bitcoinversus.tech/2026/10/07/coding-google-ai-assistants-live-official-docs-developer-knowledge-api-mcp/)（2026-10-07）
- Undercode News：[Google Launches Developer Knowledge API to Give AI Agents Fresh, Grounded Access to Official Documentation](https://undercodenews.com/google-launches-developer-knowledge-api-to-give-ai-agents-fresh-grounded-access-to-official-documentation-video/)
