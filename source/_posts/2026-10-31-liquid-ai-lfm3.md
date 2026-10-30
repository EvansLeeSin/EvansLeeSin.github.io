---
title: Liquid AI 发布 LFM3：六款约 2B 参数的开源权重模型，主打端侧部署
date: 2026-10-31 08:00:00
tags:
  - AI动态
  - Liquid AI
  - 模型发布
categories:
  - AI动态
description: Liquid AI 于 10 月 27 日发布 LFM3 系列，六款约 2B 参数的开源权重模型共享同一基座，覆盖文本、视觉、音频、全模态与决策场景，定位在手机、笔记本等本地设备上运行。
---

2026 年 10 月 27 日，Liquid AI 发布 LFM3（Liquid Foundation Models 第三代），首批共六款约 2B 参数的开源权重模型，覆盖文本、视觉、音频、全模态与决策场景，定位在手机、笔记本等本地设备上运行。

六款模型均由同一基座 LFM3-1.7B-Base 衍生而来，该基座参数量为 17.3 亿，预训练数据量为 22 万亿 token。Liquid AI 表示，六款模型均可下载、微调与部署，权重已在 Hugging Face 上线，并提供适用于 GPU 服务器、llama.cpp、Apple MLX 与 ONNX 的格式。

<!-- more -->

## 模型一览

- LFM3-1.7B：文本模型，支持工具调用与本地 Agent 任务，上下文窗口为 256K token。
- LFM3-VL-2B：视觉语言模型，支持图像与视频输入，输出文本，上下文窗口为 128K token。这是 Liquid AI 首款支持视频输入的视觉模型。
- LFM3-Audio-2B：音频模型，支持语音与文本输入，输出文本或语音，支持 18 种语言，上下文窗口为 32K token。
- LFM3-Omni-2B：全模态模型，同时处理文本、图像、视频与音频，输出文本或语音，上下文窗口为 32K token。
- d1-2B 与 d1-Omni-2B：决策模型，分别由视觉模型与全模态模型特化而来，返回经过校准的答案而非生成式文本，适用于分类、路由与信息抽取类任务。

## 架构与体积

LFM3 采用 Liquid AI 称为 tri-hybrid 的混合架构，共 24 层：13 层门控短卷积、5 层滑动窗口注意力与 6 层全局注意力。Liquid AI 表示，该架构通过硬件在环搜索确定，覆盖 14 种设备与后端组合。

文本模型在 4-bit 量化下约占用 1GB 内存。Liquid AI 表示，六款模型均支持单 GPU 微调，适用于在本地设备、私有服务器或云端部署。

## 性能数据

以下数据均来自 Liquid AI 官方公布的评测结果。LFM3-1.7B 在 29 项基准测试中平均分为 49.37，高于 Qwen3.5-9B 的 47.24。在 WebArena-Verified 上，LFM3-1.7B 得分为 38.42，高于 Qwen3.5-9B 的 28.94，以及上一代 LFM2.5-2.6B 的 3.02。

LFM3-VL-2B 在 62 项视觉基准测试中平均分为 71.4，高于上一代 LFM2.5-VL-3B 的 57.6。LFM3-Audio-2B 在 UTMOSv2 语音质量评测中得分为 3.83，高于上一代 LFM2.5-Audio-1.5B 的 3.22。

Liquid AI 在模型卡中说明，LFM3-1.7B 不建议用于 Agent 编程或复杂多步推理任务。

## 许可与获取

六款模型以 LFM Open License v1.0 发布，年收入低于 1000 万美元的企业可免费商用，年收入超过该门槛的企业需与 Liquid AI 另行签署协议。模型权重已在 Hugging Face 上线，也可通过 Liquid AI Playground 与 Liquid AI API 使用。首发合作伙伴包括 Ambarella、AMD、Arm、Intel（OpenVINO）、NVIDIA、OpenRouter、高通与 Vercel。

## 来源

- Liquid AI：[Introducing LFM3: Every Modality for Specialized Intelligence](https://www.liquid.ai/blog/lfm3)
- VentureBeat：[Liquid AI's new LFM3 models put browser agents, voice commands, and image recognition onto local devices](https://venturebeat.com/technology/liquid-ais-new-lfm3-models-put-browser-agents-voice-commands-and-image-recognition-onto-enterprise-controlled-devices)
- Unite.AI：[Liquid AI Launches LFM3 Family of Six Open-Weight 2B-Class Models](https://www.unite.ai/liquid-ai-launches-lfm3-family-of-six-open-weight-2b-class-models/)
