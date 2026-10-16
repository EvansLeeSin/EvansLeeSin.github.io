---
title: Elorian 发布首款模型 Glimpse：在推理中反复"回看"图像的视觉推理模型
date: 2026-10-17 08:00:00
tags:
  - AI动态
  - Elorian
  - 模型发布
categories:
  - AI动态
description: Elorian 于 10 月 16 日发布首款模型 Glimpse，以"研究预览版 + API"形式上线。其核心机制是"visual scratch space"：在推理过程中反复回到原始图像，裁剪区域、抽取视频帧或运行代码测量对比，而非只依赖一次性的图像转文本。
---

2026 年 10 月 16 日，Palo Alto 的 AI 初创公司 Elorian 发布了其首款模型 Glimpse，目前以研究预览版形式通过 API 提供，聊天界面仅开放候补名单。TechCrunch 对该发布做了独家报道。

Elorian 创始人兼 CEO Andrew Dai 曾是 Google DeepMind 的研究员。他的核心论点是：今天的 AI 模型在语言和代码上表现很强，但依然"看不清"。大多数多模态模型只看一次图像、将其转换为 token，然后完全在文本中推理——就像凭记忆描述一张照片。Glimpse 则在推理过程中不断回到源图像：不确定时裁剪某个区域、从视频中抽取特定帧，甚至运行代码去测量或对比所看到的内容。Elorian 把这套机制称为"visual scratch space"（视觉草稿空间）。

<!-- more -->

## 定价

Glimpse 的定价为输入每百万 token 0.60 美元、输出每百万 token 3 美元。TechCrunch 的报道将其与中量级模型（Sonnet、Sol）对比：比中量级便宜，但高于 Haiku、Luna 一类的轻量模型。

## 技术方案

Elorian 称公司用一支小团队、在几百块 GPU 上完成了 Glimpse 的训练，模型规模远小于它对标的前沿系统。报道同时提到，这条技术路线并非完全新颖——OpenAI 已在 2025 年为其 o 系列模型加入了推理过程中的裁剪与缩放；Elorian 的主张是它把整个模型都围绕这一机制构建。

## 评测表现

据 Elorian 自身的评测，Glimpse 在科学图表推理和短视频字幕任务上超过了 GPT-6 Astra，其他视觉推理任务结果接近。不过 runtimewire 指出，这些是公司自报的结果，且 Elorian 自己的评测表也显示了在部分任务上与 GPT-6 Astra 的明显差距。

## 背景与后续计划

Elorian 半年前结束隐身状态，公布的融资轮由 Striker Venture Partners、Menlo Ventures 和 Altimeter Capital 联合领投，Nvidia 和 Google 首席科学家 Jeff Dean 参与。Glimpse 的初期目标客户是手握大量视频的企业：机器人公司、科学实验室、媒体和创意公司。Dai 表示，长期目标是从"看"走向"做"：利用对场景的建模来选择动作，包括直接控制机器人；明年公司的目标是打造"世界最好的视觉推理模型"，在每一项视觉推理测试上领先。

## 来源

- TechCrunch：[Elorian's first AI model wants to reason with images, not just about them](https://techcrunch.com/2026/10/16/elorians-first-ai-model-wants-to-reason-with-images-not-just-about-them/)（2026-10-16）
- runtimewire：[Elorian launches Glimpse to give AI a second look at visual evidence](https://runtimewire.com/article/elorian-glimpse-visual-reasoning-model-launch)（2026-10-16）
