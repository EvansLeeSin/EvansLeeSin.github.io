---
title: Mistral 发布 Large 4 开源权重：万亿参数旗舰面向 Agent 编程与网络安全防御
date: 2026-10-30 08:00:00
tags:
  - AI动态
  - Mistral
  - 开源模型
categories:
  - AI动态
description: Mistral 于 10 月 29 日发布旗舰模型 Large 4 的开源权重，该模型总参数约 1 万亿，面向 Agent 编程与防御性网络安全，权重已在 Hugging Face 上线，并可通过 API 与多个合作平台使用。
---

2026 年 10 月 29 日，Mistral 发布旗舰模型 Large 4（ML4）的开源权重，代号“Le Chonk”。该模型于 10 月 6 日以公开预览形式上线，此次发布将其权重开放下载，企业与政府机构可以在自有基础设施上部署和使用。

<!-- more -->

## 从预览到开源权重

Mistral 表示，公开预览之后的约三周里，公司在客户反馈的基础上继续进行强化学习，模型在编程、防御性网络安全与推理效率方面均有提升，且提升趋势尚未出现放缓迹象。权重发布后，开发者可以下载、微调并在自有环境中运行该模型，部署方式不再依赖单一服务商的托管接口。

Mistral 科学副总裁 Pierre Stock 表示，开放权重意味着企业与政府机构可以获得前沿智能来防御网络攻击，并且这种获取方式不会因服务中断而被切断，模型也可以部署在机构自身的生态系统内。

## 编程能力

在编程相关基准上，Mistral 公布的数据显示，Large 4 在 Cognition 的 FrontierCode 2.0 上取得 19.7%，为开源权重模型中的最高成绩；在 Artificial Analysis 的 Coding Agent Index 上取得 48%，与 GLM-5.3 相当，同时每个任务平均使用的 token 数量少 47%。

在 Terminal-Bench 4.0 上，该模型的成绩从预览时的 28% 提升至 41%，提升 13 个百分点。Mistral 还表示，该模型新增低、中、高三种推理模式，开发者可以在成本与性能之间进行选择，其中高推理模式默认开启，效率较此前提升 50%。

## 网络安全防御

网络安全是此次发布的另一重点。Mistral 表示，Large 4 在 Artificial Analysis 的 Cyber Index 上取得 51%，该基准覆盖漏洞的发现、复现、验证与修复，同时要求不破坏现有功能。

在防御性任务之外，Mistral 公布的数据显示，该模型对恶意网络请求的平均拒绝率为 96.6%，覆盖 JailbreakBench、StrongREJECT 与 AgentHarm 三项测试，为 Mistral 在开源模型中测得的最高值。Mistral 同时表示，正在调整防护机制，并与经过审核的企业伙伴测试面向自有或已授权系统的专用网络安全版本。

## 模型规格与获取方式

Large 4 为原生多模态混合专家架构，总参数约 1.05 万亿，每个任务约激活 520 亿参数，上下文长度为 100 万 token，输入覆盖文本与图像，支持 160 多种语言。Mistral 表示，该模型在欧洲数据中心使用 3,800 块 NVIDIA Grace Blackwell GPU 从零训练完成。

权重已在 Hugging Face 上线，同时提供量化版本，Mistral 表示该版本可在 4 块 NVIDIA B200 或 B300 GPU 上运行。API 方面，模型以 mistral-large-4 的名称通过 Mistral API 与 Mistral Studio 提供，也可通过 OpenRouter、NVIDIA NIM 容器与 Microsoft Foundry 使用，Microsoft 为首个提供该模型的云厂商。模型还支持 vLLM 与 SGLang 等推理框架。

## 许可与定价

Large 4 的权重采用 Mistral Ecosystem Open-Weight 许可，这是一种经修改的 MIT 许可，允许免费使用、修改、微调与商业化，但以模型即服务形式对外提供该模型的企业需要另行获得 Mistral 的商业许可。

API 定价为每百万输入 token 0.70 美元、每百万缓存输入 token 0.07 美元、每百万输出 token 2.10 美元，较预览时期的价格有所下调。

## 背景

此次发布正值开源权重模型竞争加剧之时：Mistral 将 Large 4 定位为面向 Agent 编程与网络安全防御的旗舰模型，并强调企业与公共部门可以在自有基础设施上下载、部署并拥有前沿模型，用于检测、分析与响应代码与 IT 基础设施中的威胁。

## 来源

- TechCrunch：[Mistral releases weights for its trillion-parameter AI model, targeting cybersecurity](https://techcrunch.com/2026/10/29/mistral-releases-weights-for-its-trillion-parameter-ai-model-targeting-cybersecurity/)
- Unite.AI：[Mistral's 1-Trillion-Parameter Le Chonk Checkpoint Lands on Hugging Face](https://www.unite.ai/mistrals-1-trillion-parameter-le-chonk-checkpoint-lands-on-hugging-face/)
- DEV Community：[AI Daily Digest October 30, 2026: Mistral Opens a Trillion Parameters, Cloud Giants Report, OpenAI Rewrites the Spec](https://dev.to/hiroki-ii-ai/ai-daily-digest-october-30-2026-mistral-opens-a-trillion-parameters-cloud-giants-report-openai-1gk7)
