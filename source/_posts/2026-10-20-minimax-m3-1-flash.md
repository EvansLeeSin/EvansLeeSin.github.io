---
title: MiniMax 发布 M3.1 Flash：低成本 Agent 模型，开放权重 10 月 23 日上线
date: 2026-10-20 08:00:00
tags:
  - AI动态
  - MiniMax
  - 模型发布
  - Agent
categories:
  - AI动态
description: MiniMax 于 10 月 19 日发布 M3.1 Flash 模型，输入定价每百万 token 0.15 美元，约为上一代 M3 标准价格的一半。模型将于 10 月 23 日开放权重。
---

2026 年 10 月 19 日，MiniMax 发布 M3.1 Flash，一个面向 Agent 场景、主打高效低成本的新模型。Flash 定位该产品线的高速低价层级，与同日正式版 M3 构成高低搭配。

M3.1 Flash 是一个 MoE 架构模型。MiniMax 公布的参数规模为 428B，总参数量下每次推理激活约 23B。模型支持最长 100 万 token 上下文，输入类型包括文本、图像和视频。

<!-- more -->

## 定价

M3.1 Flash 采用固定费率定价：输入每百万 token 0.15 美元，输出每百万 token 0.60 美元，缓存输入每百万 token 0.015 美元，无长上下文附加费。

与上一代 M3 的标准定价（输入 0.30 美元、输出 1.20 美元）相比，新模型在每 token 价格上约为其一半。MiniMax 称，在 Agent 任务上的整体使用成本比 M3 低约 70%，并且推理速度达到 M3 的约 3 倍，产品页面标注的输出速度约为每秒 150 token。

## 性能

据 MiniMax 公布的数据，M3.1 Flash 在 Artificial Analysis Intelligence Index 上得 42 分，比 M3 高 13 分。

在公司发布的对比表中，M3.1 Flash 在 Automation-Bench 上得 62.2 分、DeepSWE 得 73.7 分、Terminal Bench 4.0 得 38.1 分；CyberGym 网络安全测试中得 82 分。官方称这些结果在 Automation-Bench 与 HLE 等基准上领先 DeepSeek V4.1 Flash。

## 接入方式与开放权重

M3.1 Flash 已在 MiniMax 官方 API 平台上线，同时提供 Anthropic 兼容与 OpenAI 兼容的接口、M Plan 订阅，以及桌面应用 MiniMax Code。

MiniMax 表示模型的权重将于 10 月 23 日开放，具体许可协议尚未公布。此外公司还宣布将推出定位更高的 Pro 版本，但未给出发布时间。

## 背景

M3.1 Flash 此前曾以"Space Bunny"的代号出现在第三方基准榜单上，此次发布同时确认了该模型的身份。从 9 月底的预览版到此次正式发布，MiniMax 将 M3.1 Flash 的 pay-as-you-go 价格补齐，也标志着其 M 系列产品线补全了低价位层级。

## 来源

- Unite.AI：[MiniMax Launches M3.1 Flash, Revealing Space Bunny Stealth Model](https://www.unite.ai/minimax-launches-m3-1-flash-revealing-space-bunny-stealth-model/)
- MarkTechPost：[MiniMax Just Launched M3.1 Flash: 428B MoE Agentic Model at $0.15/M Input](https://www.marktechpost.com/2026/10/19/minimax-m3-1-flash-release/)
- Oossa：[MiniMax releases M3.1 Flash model at about $0.22 per task](https://oossa.com/en/minimax-releases-m3-1-flash-model-at-about-0-22-per-task)
