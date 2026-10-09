---
title: 阿里 Qwen 发布 Qwen-Image-2.1-Turbo：8 步完成 2K 图像生成与编辑，开放权重
date: 2026-10-10 08:00:00
tags:
  - AI动态
  - Qwen
  - 模型发布
  - 图像生成
categories:
  - AI动态
description: 阿里 Qwen 团队于 10 月 9 日发布 Qwen-Image-2.1-Turbo，是 Qwen-Image-2.1 的加速 checkpoint，去噪步数从 40 步降至 8 步，保持 2K 输出、多参考图编辑与透明图生成能力；权重开放但采用研究许可。
---

2026 年 10 月 9 日，阿里 Qwen 团队发布 Qwen-Image-2.1-Turbo。这是开源权重图像模型 Qwen-Image-2.1 的加速版本，将默认去噪步数从 40 步压缩到 8 步，生成与编辑能力与基础版本保持一致。

<!-- more -->

## 架构与参数

Turbo 版本延续 Qwen-Image-2.1 的整体架构：视觉生成器为 70 亿参数的单流 DiT，共 32 层，采用块因果注意力（block-causal attention）设计。文本编码器为 80 亿参数的 Qwen3-VL，负责理解指令与条件图像。

模型使用 64 通道 RGBA VAE，自带 16 倍空间压缩，因此支持透明图像的直接生成与编辑。输出分辨率为 2K（2048×2048）。

## 加速方式

Turbo 将默认的 40 步去噪流程蒸馏为 8 步。默认生成使用 CFG=1，推荐的 8 步采样 schedule 已内置在 checkpoint 中。

模型引入了前缀 KV 缓存机制：输入图像与文本在第一步完成计算，后续去噪步骤复用缓存。在仅有 8 步的流程下，条件计算成本大部分被缓存覆盖。

## 生成与编辑能力

Qwen 团队介绍，该 checkpoint 单一权重同时支持文生图与图像编辑。模型卡示例覆盖 8 类任务，包括人像、人物姿态、透明图像、排版与海报、UI 布局等。编辑方面支持单图变换、多参考图组合，以及 4 张图的室内场景合成；基础版本支持最多 10 张参考图，并支持通过圆形、画笔或蒙版进行局部编辑。

## 运行与 API

本地运行通过 Diffusers 的 `QwenImage21Pipeline` 直接加载，需从源码安装 Diffusers 并满足 transformers>=5.17.0。Qwen 未公布 Turbo 的显存下限；第三方估计基础模型以 GGUF 量化需 11 GB 显存、INT8/FP8 需 24 GB。

托管 API 方面，阿里云百炼 Model Studio 同步上架了 Turbo 与 Pro 两个版本：qwen-image-2.1-turbo 定价每张图 0.1 元人民币，速率上限 120 RPM；qwen-image-2.1-pro 定价每张图 0.25 元人民币，速率上限 20 RPM。Turbo 单价为 Pro 的 2.5 分之一，请求速率上限是 6 倍。

## 许可

Turbo 权重采用 Qwen 研究许可（Qwen Research License），仅授予非商业用途权利，商业自部署需另行申请许可。此前 Qwen-Image 系列曾采用 Apache 2.0，此次许可与此前版本不同。

Qwen 官方称，基础版本 Qwen-Image-2.1 在 Qwen-Image-Bench 上得分为 60.28，是厂商报告的开源权重模型最高分；Turbo 版本暂未公布独立评测分数。

## 来源

- MarkTechPost：[Alibaba Qwen Releases Qwen-Image-2.1-Turbo, an 8-Step 7B Image Model](https://www.marktechpost.com/2026/10/09/alibaba-qwen-releases-qwen-image-2-1-turbo-an-8-step-7b-image-model/)（2026-10-09）
- thehype：[AI Model Releases (October 2026) — Latest LLM, Image & Video](https://thehype.news/calendar/releases/)
