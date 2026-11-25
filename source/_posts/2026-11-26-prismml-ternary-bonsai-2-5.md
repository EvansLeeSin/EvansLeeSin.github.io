---
title: PrismML 发布 Ternary Bonsai 2.5 27B：5.9GB 本地模型，Agent 编程基准平均分 54.2
date: 2026-11-26 08:00:00
tags:
  - AI动态
  - PrismML
  - 开源模型
categories:
  - AI动态
description: PrismML 于 11 月 24 日发布 Ternary Bonsai 2.5 27B，基于 Qwen3.8 27B 的三值量化模型，体积 5.9GB。Agent 编程基准平均分从前代的 37.9 提升至 54.2，工具调用基准平均分从 60.2 提升至 82.2，Apache 2.0 协议免费提供下载。
---

2026 年 11 月 24 日，PrismML 发布 Ternary Bonsai 2.5 27B，这是 Ternary Bonsai 2 27B 的升级版本，面向 Agent 编程与多轮工具调用场景。模型基于 Qwen3.8 27B，采用三值权重（每个权重取值为 -1、0 或 +1），将 270 亿参数的模型压缩到 5.9GB 的体积，可在个人设备上运行。

<!-- more -->

## 性能

在 Agent 编程基准测试（SWE-bench Verified、DeepSWE v1.1、Terminal-Bench 2.1）上，Ternary Bonsai 2.5 27B 的平均分为 54.2，前代 Ternary Bonsai 2 27B 为 37.9。其中 SWE-bench Verified 单项得分为 75.6，前代为 60.8，全精度基底模型为 80.6。

在 Agent 工具调用基准测试（AppWorld、τ³-Bench）上，新模型平均分为 82.2，前代为 60.2。完整结果与评估设置见 PrismML 随附的白皮书。以上均为 PrismML 公布的数据。

## 长任务能力

PrismML 表示，压缩模型在 Agent 工作负载上面临的挑战在于，小误差会在连续工具调用中累积，导致 Agent 偏离目标或重复无效尝试。Bonsai 2.5 的开发重点放在任务执行过程中的表现上，包括结合工具反馈、从失败操作中恢复，以及避免不必要的推理和无效重复，目标是让 Agent 更可靠地完成工作，减少浪费的步骤、token 用量和执行时间。

在应用场景上，PrismML 提到，本地编程助手可以在开发者本地环境中检查私有代码库、修改代码、运行相关测试并根据结果修正；知识工作助手可以将一个文件夹的文档整理为结构化分析、核对不一致的记录，或为定期报告准备可重复的工作流程。产品团队也可以将模型直接嵌入应用中，在用户设备上完成推理，敏感信息无需离开本地。

## 运行方式与获取

Ternary Bonsai 2.5 27B 通过 llama.cpp 支持 NVIDIA 与 Intel GPU，通过 MLX 支持苹果设备，包括 Mac、iPhone 和 iPad。模型自 2026 年 11 月 24 日起按 Apache 2.0 协议免费提供下载，权重发布在 Hugging Face。

## 背景

PrismML 是一家美国人工智能公司，团队源自加州理工学院的研究人员，获得 Khosla Ventures、Cerberus、Google 与 Samsung 的支持，公司专注于让 AI 更高效、更易用。Bonsai 系列此前已发布两代：首代 Bonsai 27B 于 2026 年 7 月发布，Bonsai 2 于同年 9 月发布，Bonsai 2.5 与前代相隔约十周。

## 来源

- PrismML：[PrismML Launches Ternary Bonsai 2.5 27B for Agentic Coding and Private Knowledge Work](https://prismml.com/news/prismml-launches-ternary-bonsai-2-5-27b)（2026-11-24）
- PR Newswire：[PrismML Launches Ternary Bonsai 2.5 27B for Agentic Coding and Private Knowledge Work](https://www.prnewswire.com/news-releases/prismml-launches-ternary-bonsai-2-5-27b-for-agentic-coding-and-private-knowledge-work-302949886.html)（2026-11-24）
- Hugging Face：[prism-ml/Ternary-Bonsai-2.5-27B-GGUF](https://huggingface.co/prism-ml/Ternary-Bonsai-2.5-27B-GGUF)
