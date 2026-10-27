---
title: Akamai 推出推理服务与 Agent 沙箱：12 款开源权重模型走 OpenAI 兼容 API，Agent 代码以 WebAssembly 隔离运行
date: 2026-10-28 08:00:00
tags:
  - AI动态
  - Akamai
  - Agent
categories:
  - AI动态
description: Akamai 于 10 月 27 日在 Akamai Cloud 上推出 Akamai Inference 与 Akamai Agent Sandbox，两项服务均处于 Beta 阶段，前者提供 12 款开源权重模型的托管推理，后者为 Agent 及其编写的代码提供隔离的执行环境。
---

2026 年 10 月 27 日，Akamai 在 Akamai Cloud 上推出两项服务：Akamai Inference 与 Akamai Agent Sandbox，两项服务均处于 Beta 阶段。Akamai 表示，两项服务连同其安全产品组合，补齐了其 AI 云平台的推理与执行层。

<!-- more -->

## 推理服务

Akamai Inference 提供开源权重模型与自定义模型的托管访问，首批目录包含 12 款开源权重模型，参数规模从 80 亿到 2.8 万亿不等，包括 NVIDIA Nemotron 3 Ultra、OpenAI gpt-oss-120b 与 Google Gemma 4，此外还提供用于检索增强生成（RAG）场景的 embedding 模型。

该服务通过 OpenAI 兼容的 API 提供访问，现有应用无需重写即可迁移。客户可以在无服务器按量付费推理与专属部署两种方式中选择。Akamai Inference 负责编排、模型执行与身份验证，Akamai Cloud 提供的托管数据库与对象存储可为模型提供企业数据来源，请求在 Akamai 全球网络上运行。

Akamai 云业务首席运营官兼总经理 Adam Karon 表示，推理将成为绝大多数企业后续关注的重点，客户希望在同一平台上构建、运行并保护 AI 应用。

## Agent 沙箱

Akamai Agent Sandbox 为 Agent 及其编写并运行的代码提供隔离的执行环境。Agent 运行在 Akamai Functions 上，其编写的代码则在与 Agent 运行时隔离的独立环境中运行。

该沙箱是 Spin 框架的开源组件，采用 WebAssembly 隔离，对计算、内存、出站连接与系统能力设定限制。Akamai 表示，Agent 隔离正收敛为几种形态，包括具备快照与分叉能力的微虚拟机、策略强制的容器，以及 WebAssembly 隔离的函数，开发者可以根据工作负载选择合适的架构，基础设施选项包括 NVIDIA 加速与专属 CPU 基础设施、托管 Kubernetes，以及用于无服务器执行的 Akamai Functions。Akamai 还计划增加用于管理 Agent 可访问对象与可被哪些对象访问的能力。

Akamai 云技术高级副总裁 Jon Alexander 表示，每个运行 Agent 的团队都需要在 Agent 编写的代码周围设定边界。

## 背景

Akamai Agent Sandbox 所基于的 WebAssembly 技术来自 Akamai 收购 Fermyon 获得的框架，Spin 框架目前在云原生计算基金会（CNCF）下推进。推理服务则与 Akamai 已有的托管数据库与存储服务互补，Akamai 在全球部署了 4350 多个部署点，其集群混合使用传统 CPU 与 NVIDIA GPU，以降低网络延迟。

Akamai 表示，Akamai Inference 与 Akamai Agent Sandbox 增加了推理与执行层，使其 AI 基础设施成为完整的 AI 栈，其安全产品组合则保护其中的每一层。

## GPU 与部署选择

Akamai 同时扩展了 Akamai AI Cloud 的 GPU 平台 fleet，提供 NVIDIA Blackwell Ultra 集群，具体为 RTX PRO 6000 Blackwell Server Edition GPU，每个 8 卡 Blackwell Ultra 节点提供最高 2.3TB 的 HBM3e 显存，用于支持长上下文推理。Akamai 还表示，计划于 2027 年增加对 NVIDIA Vera Rubin 处理器的支持。

本次发布未公布定价信息。

## 来源

- SiliconANGLE：[Akamai expands its AI Cloud platform with dedicated inference and agent execution environments](https://siliconangle.com/2026/10/27/akamai-expands-its-ai-cloud-platform-with-dedicated-inference-and-agent-execution-environments/)
- GlobeNewswire（经 Morningstar 转载）：[Akamai Launches AI Inference Service and Agent Execution Environment](https://www.morningstar.com/news/globe-newswire/9853536/akamai-launches-ai-inference-service-and-agent-execution-environment)
- Techstrong.ai：[Akamai Adds Pair of Managed AI Services to Securely Access Custom Models](https://techstrong.ai/features/akamai-adds-pair-of-managed-ai-services-to-securely-access-custom-models/)
- LetsDataScience：[Akamai Launches Agent Sandbox and Inference Service in Beta](https://letsdatascience.com/news/akamai-launches-agent-sandbox-and-inference-service-in-beta-5a536583)
