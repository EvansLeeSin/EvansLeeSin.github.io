---
title: Agentic AI Foundation 新增四个项目：Agent Skills、Open Responses、OpenEnv 与 OpenSandbox
date: 2026-10-23 08:00:00
tags:
  - AI动态
  - Agent
  - 开源标准
categories:
  - AI动态
description: 10 月 22 日，Agentic AI Foundation 在 AGNTCon + MCPCon North America 大会上宣布新增四个开源项目，分别由 Anthropic、OpenAI、Hugging Face 与阿里巴巴捐赠，覆盖技能、跨厂商接口、训练环境与沙箱执行四个层面，基金会托管的项目数量在其成立一年内从 3 个增至 10 个。
---

2026 年 10 月 22 日，Agentic AI Foundation（AAIF）在加州圣何塞举行的 AGNTCon + MCPCon North America 大会上宣布，新增四个开源项目：Agent Skills、Open Responses、OpenEnv 与 OpenSandbox。这四个项目分别由 Anthropic、OpenAI、Hugging Face 和阿里巴巴捐赠给基金会管理，使 AAIF 托管的项目数量在其成立第一年内从 3 个增长到 10 个。

<!-- more -->

## 四个新项目覆盖 Agent 技术栈的四个层面

新增项目分别对应 Agent 技术栈的四个环节：如何为 Agent 增加技能、应用如何跨厂商与模型对话、Agent 如何训练与评估、以及 Agent 在哪里安全运行。它们将与 A2A 协议、Agent Router、agentgateway、AGENTS.md、goose 以及 Model Context Protocol（MCP）等既有项目一样，纳入 AAIF 的开放、中立治理体系。

### Agent Skills：可移植的技能标准

Agent Skills 由 Anthropic 捐赠，是一个为 Agent 赋予新能力与领域专业知识的开放格式。技能把指令、脚本和资源打包成可复用的单元，Agent 可以按需加载，让特定领域的专有知识能够跨 Agent 产品和平台携带。

Anthropic MCP 的联合创始人兼主要维护者 David Soria Parra 表示，Agent Skills 自推出以来一直致力于为开发者与企业提供一个开放标准，让 Agent 更有能力；将其捐赠给 AAIF 后，任何使用技能进行构建的人都可以参与其未来发展。

### Open Responses：跨厂商的统一接口规范

Open Responses 由 OpenAI 捐赠，是一个基于 OpenAI Responses API 的开放规范，用于构建多厂商互操作的大语言模型接口。它定义了统一的 schema、一致的流式事件与可扩展的工具机制，开发者可以一次描述请求与输出格式，并以最少的转换在各模型厂商之间运行。

OpenAI 技术成员 Steve Coffey 表示，Open Responses 加入 AAIF 是为了帮助开发者在当今的语言模型上通过简单、干净、统一的接口构建产品。

### OpenEnv：强化学习环境框架

OpenEnv 由 Hugging Face 捐赠，是一个创建强化学习（RL）环境的开放框架与社区中心，旨在让 RL 环境互操作、可插拔、易构建、易分享、易扩展。它通过一个简单的容器化服务实现这一点，该服务暴露了熟悉的 Agent 接口、MCP，以及训练库常用的训练协议 Gym。

Hugging Face 机器学习工程师 Ben Burtenshaw 表示，RL 环境是整个技术栈中不可或缺的一部分，因为它们教授 Agent 在现实世界中将要使用的能力。

### OpenSandbox：AI 应用的通用沙箱平台

OpenSandbox 由阿里巴巴捐赠，是一个面向 AI 应用的通用沙箱平台，提供多语言 SDK、统一的沙箱 API，以及 Docker 和 Kubernetes 运行时，适用场景包括代码 Agent、GUI Agent、Agent 评估、AI 代码执行与强化学习训练。它包含一套定义生命周期与执行 API 的沙箱协议，团队可以扩展自定义运行时。

阿里巴巴开发基础设施负责人 Xiaobin Xu 表示，虽然 OpenSandbox 创建于阿里巴巴，但不希望它的未来由单一公司定义；交由 AAIF 后，更多开发者和组织可以共同塑造 Agent 生态中沙箱环境的发展方向。

## 背景

Agentic AI Foundation 定位为 Agent 领域开放标准、协议与基础设施的中立之家，创始项目包括 MCP、goose 与 AGENTS.md。其 2025 年 12 月创立时有 3 个项目，本次新增后达到 10 个。基金会联合创始人兼 CTO Manik Surtani 表示，四个不同公司选择把各自覆盖技术栈不同环节的项目交由中立治理，正是基金会存在的意义：给社区一个构建共享标准、协议与基础设施的地方，不由单一公司主导。

此次发布恰逢 AGNTCon + MCPCon North America 大会，该会于 10 月 22 日至 23 日在圣何塞 McEnery 会议中心举行，聚焦开放的 Agent AI 社区在构建、保护与运行 AI Agent 方面的实践经验。

## 来源

- Agentic AI Foundation：[Agentic AI Foundation Announces Four New Projects: Agent Skills, Open Responses, OpenEnv, and OpenSandbox](https://aaif.io/news/agentic-ai-foundation-announces-four-new-projects)（2026-10-22）
- Morningstar / PR Newswire：[Agentic AI Foundation Announces Four New Projects: Agent Skills, Open Responses, OpenEnv, and OpenSandbox](https://www.morningstar.com/news/pr-newswire/20261022dc78734/agentic-ai-foundation-announces-four-new-projects-agent-skills-open-responses-openenv-and-opensandbox)（2026-10-22）
