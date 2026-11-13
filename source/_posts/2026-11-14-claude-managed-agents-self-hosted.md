---
title: Anthropic 推出自托管 Claude Managed Agents 私有测试版：Agent 控制平面可部署在企业自己的环境中
date: 2026-11-14 08:00:00
tags:
  - AI动态
  - Anthropic
  - Agent
categories:
  - AI动态
description: Anthropic 于 11 月 12 日宣布自托管 Claude Managed Agents 进入私有测试版，企业可在自己的云或本地环境中运行完整的 Agent 服务，包括编排器、沙箱、凭据与会话历史，模型请求则按企业选择发送至 Anthropic 或其他云厂商。
---

2026 年 11 月 12 日，Anthropic 宣布自托管 Claude Managed Agents 进入私有测试版。企业可以在自己的云环境或本地基础设施中运行完整的 Managed Agents 服务，包括 Agent 编排器、沙箱、凭据与会话历史。

Managed Agents 是 Anthropic 提供的一组可组合 API，用于构建和部署自主 Agent，面向长时间运行的 Agent 任务，例如修复构建、测试版本、处理告警和清理缺陷积压。此前该服务以托管形式提供，Anthropic 负责运行基础设施；之后 Anthropic 增加了自托管沙箱选项。此次推出的自托管版本则将整个服务移入企业自己的环境。

<!-- more -->

## 部署方式

自托管部署中，企业自行运行 Managed Agents 服务器（cma-server）、数据库和工作节点。cma-server 提供与托管服务相同的 API，并运行 Agent 循环；会话历史存储在企业自己的 PostgreSQL 16 或更高版本数据库中；工作节点在企业自己的沙箱内运行 Agent 的 shell 与文件工具，服务器本身不运行这些工具。

模型本身并不随服务一起移入企业环境。每次模型请求仍需发送到企业选择的提供方：直接发送给 Anthropic，或经由 Amazon Bedrock、Google Agent Platform、Microsoft Foundry，或企业自己的网关。开发者仍使用与托管服务相同的核心 API 构建 Agent。

Anthropic 表示，对自托管服务器及其日志没有远程访问权限。已与 Anthropic 配置零数据保留（ZDR）的组织，该约定同样适用于发送给 Claude 的请求。

## 安全设计

Anthropic 在公告中列出了 Managed Agents 的四项安全原则，这些原则适用于托管、自托管沙箱与全自托管三种部署方式。

第一，大脑与手分离。编排器负责调用 Claude，沙箱负责运行 Agent 的代码，两者按设计分离。Agent 循环、会话历史和 vault 凭据保存在沙箱之外；会话历史以事件日志形式存储在沙箱外，沙箱只在工具需要时启动。

第二，凭据不出沙箱。Vault 的设计使凭据不进入沙箱：对于 MCP 工具和受支持的 API 调用，沙箱外的代理会在请求中附加凭据。自托管部署中，企业也可以将凭据存放在自己的 secrets manager 中。

第三，网络访问可以限制。每个环境可以限定为一份允许访问的主机列表，对其他主机的请求会被阻止。自行托管沙箱时，企业可以在自己的防火墙中设置同样的限制。

第四，每次会话留下完整记录。Managed Agents 会记录 Agent 每一步的操作，包括调用的工具及其返回结果，记录可经由 OpenTelemetry 导出，接入企业已有的监控工具。

## 接入与限制

自托管 Claude Managed Agents 目前处于私有测试版，面向符合条件的组织，需联系 Anthropic 客户团队申请接入，下载文件也由客户团队提供。Anthropic 未公布服务器软件的价格，也未给出全面开放的时间。

据文档相关报道，自托管版本暂未提供部分托管功能，包括云环境、Files API、webhooks 与定时部署等。从托管服务迁移时，Agent、技能、vault 凭据、记忆库与会话历史不会自动迁移，需要重新建立。

## 背景

Managed Agents 最初于 2026 年 4 月以托管测试版形式推出，随后增加了自托管沙箱。此次自托管版本是该服务的进一步延伸，面向希望 Agent 控制平面完全留在自己安全边界内的团队。同在 11 月，Mistral 也将其 Mistral Studio 推向客户 VPC 与本地部署。

## 来源

- Anthropic：[Operate Claude Managed Agents inside your security perimeter](https://claude.com/resources/articles/self-hosted-claude-managed-agents)（2026-11-12）
- Geekbyte：[Anthropic opens a private beta for self-hosting the whole Claude Managed Agents service](https://www.geekbyte.com/post/claude-managed-agents-self-hosted/)（2026-11-12）
- CellCog：[Self-Hosted Claude Managed Agents: Beta, Limits, License](https://cellcog.ai/blog/claude-managed-agents-self-hosted/)
- Dirty Static：[Anthropic Opens Self-Hosted Claude Managed Agents Beta](https://dirtystatic.com/articles/anthropic-opens-self-hosted-claude-managed-agents-beta/)
