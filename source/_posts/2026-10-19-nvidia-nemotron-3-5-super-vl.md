---
title: NVIDIA 发布 Nemotron 3.5 Super VL：1200 亿参数开放权重模型，面向常开企业 Agent
date: 2026-10-19 08:00:00
tags:
  - AI动态
  - NVIDIA
  - 模型发布
  - 开放权重
categories:
  - AI动态
description: NVIDIA 于 10 月 15 日发布 Nemotron 3.5 系列开放权重模型：120B 参数的多模态 Super VL（每 token 激活约 12B）与 74B 参数的 Bolt，均提供权重、训练配方与数据集，定位"常开"的企业级 Agent 场景。
---

2026 年 10 月 15 日，NVIDIA 发布 Nemotron 3.5 系列开放权重模型，主打一款 1200 亿参数的多模态大模型 Nemotron 3.5 Super VL，以及面向边缘与桌面部署的 Nemotron 3.5 Bolt 74B-A9B。两款模型的权重当天同步上架 Hugging Face，第三款小型模型 Bolt E4B 4GB 计划 10 月 23 日推出。

<!-- more -->

## 模型规格

Super VL 是一款视觉-语言混合模型，总参数 120B，采用混合专家（MoE）架构，每 token 仅激活约 12B 参数。它的输入覆盖文本、图像、文档与 PDF、界面截图以及短视频片段，最大上下文为 100 万 token。NVIDIA 定位它是为"常开"（always-on）企业 Agent 设计的：多步任务、工具调用、视觉文档理解与表格推理是它的主要工作场景。

Bolt 74B-A9B 则是轻量版本：总参数 74B，每 token 激活约 9B 参数，大部分参数压缩至约 2 比特精度，使整个模型可以装进 24GB 显存，单机即可运行。NVIDIA 公示的测试硬件包括搭载 GeForce RTX 5090 的 PC 与 DGX Spark，其最大上下文为 256K token。

## 性能宣称

据 VentureBeat 报道，NVIDIA 称经过后训练的 Super VL 在部分专门任务基准上超过了 Claude Opus 5.5 和 GPT-6.1 Sol。这是公司发布的自测结果，针对的是特定任务而非通用推理榜单。

早期企业用户的实测数据也被一并公布：Scale AI 用该模型为 Skydance 做自动化财务供应商处理，推理成本降低 40 倍、延迟降至 1/5；Ramp 将其用于票据与财务发票解析，吞吐提升最高 50%、延迟降低 10 倍。

## 开放与获取

系列模型采用 NVIDIA 的 OpenMDW-1.1 许可证，允许商业使用、微调和权重再分发。NVIDIA 还发布了训练配方与数据集，并通过 NeMo 平台提供定制资源。

获取途径包括：Hugging Face 上的开放权重、OpenRouter 与 ModelScope、NVIDIA NIM 微服务。开发者可以免费使用 NVIDIA 托管的限流 API 做开发；生产部署则通过 NGC 目录获取 NIM 微服务，NVIDIA AI Enterprise 的生产许可报价为每 GPU 每年 4500 美元。

## 背景

此次发布正值 NVIDIA 宣布收购 Hugging Face 之后。据报道，该交易金额约 129.3 亿美元，尚未完成交割，NVIDIA 预计于 2027 年上半年完成，并承诺 Hugging Face 将继续向其他模型厂商和芯片厂商开放。

## 来源

- VentureBeat：[NVIDIA's new, open Nemotron 3.5 Super VL with post-training beats Claude Opus 5, GPT-6.1 Sol on specialized task benchmarks](https://venturebeat.com/technology/nvidias-new-open-nemotron-3-5-super-vl-with-post-training-beats-claude-opus-5-gpt-6-1-sol-on-specialized-task-benchmarks)（2026-10-15）
- TechTarget：[Open source and on device: the strategy behind Nvidia's new AI models](https://www.techtarget.com/ai/news/366652514/Open-source-and-on-device-the-strategy-behind-Nvidias-new-AI-models)（2026-10-16）
- MACCUS：[NVIDIA squeezes a 74B-parameter open model into 24 GB and releases a 120B agent model that reads PDFs](https://maccus.fr/en/nvidia-nemotron-3-5-open-models/)（2026-10-18）
