---
title: IBM 发布模块化语言模型 Granite Switch 4.1：聊天、决策与语音转写合于一个端点
date: 2026-10-16 08:00:00
tags:
  - AI动态
  - 大模型
  - 开源模型
categories:
  - AI动态
description: IBM 于 10 月 15 日发布 Granite Switch 4.1，包含 8B 与 30B 两个规格。将基础模型与决策、安全、语音转写三种适配器组合进同一个端点，Apache 2.0 许可证开源，显存占用与基础模型单独部署大致相同。
---

2026 年 10 月 15 日，IBM 发布 Granite Switch 4.1 系列模型，包含 Granite-Switch-4.1-8B 与 Granite-Switch-4.1-30B 两个规格。该系列基于 granite-4.1-8b 与 granite-4.1-30b 基础模型，上下文窗口为 128K，采用 Apache 2.0 许可证，在 Hugging Face 提供 Transformers 与 vLLM 两种后端支持。

Switch 是 IBM 在 2026 年春季推出的模块化模型开发思路：不再为每种能力单独部署一个模型副本，而是把独立训练的 Activated LoRA（aLoRA）适配器嵌入同一个检查点，在推理时通过控制 token 动态选用。

<!-- more -->

## 一个端点上的三种能力

每个 Switch 4.1 检查点在基础模型之外组合了三个组件：

- **通用决策 aLoRA**：面向通用决策场景，官方文档称可用于 15 种以上的通用决策标记检测；
- **安全 aLoRA（guardian-core）**：来自 IBM Guardian 库，覆盖有害内容、越狱攻击、粗俗用语、暴力、性内容、社会偏见与不道德行为等安全风险检测。官方材料称其在安全相关决策任务上的平均表现优于 Jev 1.13、Microsoft-Decision-1、GPT-Luna-Decisions 与 Clef-Flash；
- **语音转写编码器（Granite Speech 5.0 TurboCTC）**：一个 4.7 亿参数的英文非自回归 conformer CTC 编码器，嵌入模型中承担语音转写任务。IBM 称它是 OpenASR 榜单上速度最快的自动语音识别模型。

三项组件与基础模型共同封装为一个可部署的端点，同一端点可实时完成音频转写、文本摘要、有害内容筛查等多种任务，无需在不同模型之间切换。

## 显存与推理效率

IBM 表示，这三项技术与基础模型组合在一起，部署所需的 GPU 显存与单独部署基础模型大致相同。Switch 适配器采用缓存友好的 Activated LoRA 形式：基础模型生成产生的 KV 缓存可被后续的适配器决策复用；配合官方近期为 vLLM 低秩适配器推理所做的性能优化，模型可在聊天请求、决策请求与语音请求之间快速切换。

适配器之间通过 KV 缓存归一化保持隔离：每个适配器只能看到基础模型的表示，而看不到其他适配器的缓存激活值，因此适配器可以独立开发、组合部署而不损失精度。

## 预览版与 Granite Libraries

随同发布的还有不含音频组件的预览版变体（granite-switch-4.1-8b-preview、granite-switch-4.1-30b-preview 与 granite-switch-4.1-3b-preview），打包了完整的 Granite Libraries 适配器集合，支持通过 chat template 中的控制 token 按需激活 RAG、安全、可解释性等专用能力。Granite Libraries 是 IBM 此前发布的专用决策与任务适配器仓库，供开发者组合出自定义的 Switch 模型。

## 来源

- Hugging Face：[Granite Switch 4.1: Chat, Decisions, and Speech from One Endpoint](https://huggingface.co/blog/ibm-granite/granite-switch-4-1)（2026-10-15）
- Unite.AI：[IBM Releases Modular Granite Switch 4.1 Models in 8B and 30B Sizes](https://www.unite.ai/ibm-releases-modular-granite-switch-4-1-models-in-8b-and-30b-sizes/)（2026-10-15）
- Hugging Face 模型卡：[ibm-granite/granite-switch-4.1-8b-preview](https://huggingface.co/ibm-granite/granite-switch-4.1-8b-preview)
