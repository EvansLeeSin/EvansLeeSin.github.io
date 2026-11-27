---
title: Google 要求 AI Agent 自 2027 年 2 月起通过 MCP 服务器访问 Workspace
date: 2026-11-28 08:00:00
tags:
  - AI动态
  - Google
  - Agent
  - MCP
categories:
  - AI动态
description: Google 于 11 月 24 日宣布 Workspace MCP 服务器与 Workspace CLI 正式可用，并发布 Workspace AI Tools Addendum：自 2027 年 2 月 1 日起，AI Agent 访问 Workspace 数据须走 MCP 服务器或 CLI，不再直接调用 REST API。
---

2026 年 11 月 24 日，Google 宣布 Workspace MCP 服务器与 Workspace CLI 正式可用，并同步发布新的 Workspace AI Tools Addendum。自 2027 年 2 月 1 日起，AI Agent 访问 Workspace 数据须通过 Workspace MCP 服务器或 Workspace CLI，不再直接调用现有的 REST API。

<!-- more -->

## 正式可用的内容

Workspace MCP 服务器覆盖 Gmail、Google Drive、Docs、Sheets、Slides、Calendar、Chat 与 Tasks，Keep 即将加入。服务器基于开放的 MCP 标准构建，云端与 Web 端 Agent 可直接使用。Google 表示，与逐行下载邮件和文件不同，MCP 工具在 Workspace 的安全边界内返回相关上下文。

Workspace CLI 面向本地与桌面 Agent 以及工作流自动化，提供结构化 JSON 输出和限定范围的 OAuth 登录。Google 同时推出了 Google Cloud Agent Gateway，用于承载 LLM、MCP 与 Agent2Agent（A2A）流量。

## 新规与时间表

根据新的 Workspace AI Tools Addendum，AI Agent 须通过 Workspace MCP 服务器或 Workspace CLI 连接，而非传统 REST API。技术层面的强制执行自 2027 年 2 月 1 日开始，在此之前开发者有时间完成迁移。

自 2027 年 2 月 1 日起，继续直接调用 Workspace REST API 的 AI Agent 将被限制在 Standard 级配额之内，无论项目选择了哪个层级。如需更高的 Agent 用量，须切换到 MCP 并注册 Scaled 层级。

外部 AI Agent 须使用专用的 OAuth 客户端 ID，搭配最小权限范围、限时审批（即将推出）与用量配额。计费自 2027 年 4 月 1 日开始。

## 用量层级

标准化的层级与定价模型自 2026 年 11 月 24 日起推出，首批覆盖 Gmail API、Google Calendar API 与 Google Drive API 及其对应的 MCP 服务器。Standard 层级为每个项目、每个产品每天最多 5,000 次请求，无需 Google Cloud 计费账号。Google 表示，超过 99% 的活跃开发者处于 Standard 层级用量之内。

## 数据使用规则

Addendum 同时对 Agent 使用 Workspace 数据之后的行为作出规定。其中包括对衍生数据的留存限制：从 Workspace 数据派生的向量嵌入、记忆索引、用户画像、组织关系图与分析结论等，存储时间不得超过 30 天。

Google 在公告中表示，这些措施的目的是让每个 AI Agent 遵守同样的规则，安全团队可以在每次请求时执行策略检查，而不是让 Agent 通过为人类与应用设计的传统接口绕过监管。

## 来源

- Google Cloud Blog：[Deploying agents safely in your enterprise](https://cloud.google.com/blog/products/identity-security/deploying-agents-safely-in-your-enterprise)（2026-11-25）
- Google Workspace Blog：[Built for trust and control: New AI agent protections and developer tools in Google Workspace](https://workspace.google.com/blog/product-announcements/built-for-trust-and-control-new-ai-agent-protections-and-developer-tools-in-google-workspace)（2026-11-25）
- Google for Developers：[Usage tiers and quotas for Google Workspace APIs and MCP servers](https://developers.google.com/workspace/guides/quota-usage-tiers)
