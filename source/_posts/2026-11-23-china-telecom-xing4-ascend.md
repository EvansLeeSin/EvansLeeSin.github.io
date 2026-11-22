---
title: 中国电信发布星辰 Xing4：285B 模型在 8192 张昇腾 910C 上完成训练
date: 2026-11-23 08:00:00
tags:
  - AI动态
  - 中国电信
  - 开源模型
categories:
  - AI动态
description: 中国电信星辰 AGI 实验室于 11 月 17 日发布 TeleChat 星辰 Xing4 系列技术报告，旗舰 285B 模型全程在 8192 张昇腾 910C 上完成预训练，同时以 Apache 2.0 协议开源 29B 参数的 Xing4.0-29B-A4B 模型。
---

2026 年 11 月 17 日，中国电信星辰 AGI 实验室发布 TeleChat 星辰 Xing4 系列技术报告。这是一组面向智能体任务的大语言模型，延续 TeleChat 系列，旗舰模型全程在 8192 张华为昇腾 910C 神经网络处理器上完成预训练，未使用 GPU 或 CUDA。

<!-- more -->

## 旗舰模型

Xing4 系列的旗舰模型为 285B-A17B，采用混合专家（MoE）架构，总参数 2850 亿，每 token 激活约 170 亿参数，支持最长 100 万 token 的上下文。报告称，该模型在星辰 AGI 实验室从大规模生产集群中调配的 8192 张昇腾 910C 卡上完成预训练，训练软件栈为 MindSpore HyperParallel。

报告还提到，系列后续将向万亿参数规模扩展，万亿参数模型的训练正在进行中。

## 开源模型

与技术报告同步发布的还有开源模型 Xing4.0-29B-A4B，总参数 290 亿，每 token 激活 40 亿参数，原生支持 25.6 万 token 上下文，可扩展至 51.2 万 token。模型以 Apache 2.0 协议开源，提供 BF16、FP8、GGUF 与 W8A8 等权重格式。

根据模型卡，Xing4.0-29B-A4B 完全基于昇腾 NPU 与 MindSpore 框架训练，训练语料为 1.5 万亿中英双语 token。GGUF 量化版本文件大小在 11 至 34 GB 之间，4-bit 量化版本约需 15GB 显存，可在消费级显卡上通过 llama.cpp 本地运行，llama.cpp 主线已于 11 月 5 日合并对该模型的原生支持。微调支持 ms-swift 与 LLaMA-Factory，推理部署支持 vLLM 与 SGLang。

## 架构

Xing4 在架构上结合了多头潜在注意力（MLA）、稀疏注意力（DSA）与跨层 IndexShare，并引入流形约束超连接（mHC）与多 token 预测（MTP），面向长上下文规划、工具调用与多步骤推理。报告给出的一组系统测量数据称，相比纯 MLA 基线，预填充吞吐提升最高 4.68 倍；DSpark 投机解码带来 2.67 至 3.77 倍的解码吞吐提升；取消流水线并行后，训练吞吐提升 16.1%。报告同时说明，预填充数据来自研究团队自己的模拟器。

在整体训练效率上，报告称通过细粒度 MoE 通信优化、选择性重计算、图算子融合与 Ascend C 手写融合算子等手段，训练吞吐较开箱即用的基线提升约 96%。

## 后训练：TeleGym

后训练阶段，报告引入了 TeleGym，一个统一的智能体执行平台，将执行、评估与轨迹构建连接到策略优化流程，覆盖数学推理、代码生成与多轮智能体任务。报告称，TeleGym 通过解耦的异步执行、有界过采样与部分展开（partial rollout）处理工具调用与评分耗时差异较大的问题。

## 基准成绩

根据 Hugging Face 模型卡公布的基准数据，Xing4.0-29B-A4B（BF16）在 SWE-bench Verified 上得分 75.00，在 Terminal-Bench 2.1 上得分 57.50，在 AIME2026 上得分 90.00，在 IFBench 上得分 69.67，在 Claw-Eval 上得分 76.55，在中文综合评测 SuperCLUE 上得分 93.52。同一张对照表还列出 Gemma4-26B-A4B 与 Qwen3.6-35B-A3B 的成绩作为同级别开源模型的对比。

## 来源

- arXiv：[TeleChat to Xing4: Advancing Frontier Agentic Models on Domestic Chips and Frameworks](https://arxiv.org/html/2611.22115v1)（arXiv:2611.22115，2026-11-17）
- Hugging Face：[XingChen-AGI/Xing4.0-29B-A4B](https://huggingface.co/XingChen-AGI/Xing4.0-29B-A4B)
- Hugging Face：[XingChen-AGI/Xing4.0-29B-A4B-GGUF](https://huggingface.co/XingChen-AGI/Xing4.0-29B-A4B-GGUF)
- AI Weekly：[TeleChat Xing4 Trains 285B-Param Agentic MoE Entirely on 8,192 Ascend 910C NPUs With MindSpore](https://aiweekly.co/alerts/telechat-xing4-trains-285b-param-agentic-moe-entirely-on-8192-ascend-910c-npus)
