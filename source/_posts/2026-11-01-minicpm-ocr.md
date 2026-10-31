---
title: ModelBest 与 OpenBMB 开源 MiniCPM-OCR 系列：1.3B 解析模型与 2B 质检模型
date: 2026-11-01 08:00:00
tags:
  - AI动态
  - ModelBest
  - OpenBMB
  - 模型发布
categories:
  - AI动态
description: ModelBest 与 OpenBMB 于 10 月 31 日联合发布并开源 MiniCPM-OCR 系列，包括 1.3B 参数的文档解析模型 MiniCPM-OCR 1.0 与 2B 参数的解析结果质检模型 MiniCPM-OCR Jev，覆盖文档解析与解析质量评估两个环节。
---

2026 年 10 月 31 日，ModelBest 与 OpenBMB 联合发布并开源 MiniCPM-OCR 系列，这是一组面向文档解析与解析质量评估的模型，包括 MiniCPM-OCR 1.0（1.3B 参数）与 MiniCPM-OCR Jev（2B 参数）。这是 MiniCPM 家族中首个面向 OCR 的模型系列，定位是在紧凑参数规模下提供高解析精度，并面向边缘部署优化。

<!-- more -->

## MiniCPM-OCR 1.0：文档解析

MiniCPM-OCR 1.0 是一款 13 亿参数的文档解析模型，面向扫描件、手机拍摄、弯曲、倾斜与截屏文档等真实场景，无需繁琐的图像预校正即可解析。模型支持中英双语密集内容、复杂数学公式、多级或无边框表格，以及全页重建之外的关键信息抽取（KIE），可按业务指令从发票、证件与财务报表中抽取指定字段。

在解码加速方面，模型采用 DSpark 解码加速，官方表示其显著提升了端到端吞吐并降低了单页延迟。对于金融合同档案、学术图书馆与政府记录等需要处理数百万页文档的场景，官方称在相同的硬件与时间预算下可处理更多文档，计算成本相应降低。

## MiniCPM-OCR Jev：解析结果质检

MiniCPM-OCR Jev 是一款解析结果判定模型，官方将其描述为"AI 质检员"。它本身不执行 OCR，而是将源图像与 OCR 输出进行对照，对文本、LaTeX 公式与表格快速给出置信度评分，检测缺字、错误与格式错位。

Jev 支持跨模型部署，可接入现有 OCR 工作流而无需替换原有解析引擎。它可以自动识别可直接处理的可信结果、标记需人工复核的存疑输出，并从多个 OCR 系统的结果中挑选最佳结果。官方表示，这使企业能够从逐页人工检查转向基于风险的自动化质量控制。

## 性能数据

以下数据来自官方公布的评测结果与第三方报道。MiniCPM-OCR 1.0 在 Real5-OmniDocBench 上得分为 93.68，在 OCRBench v2 上的得分区间为 47.4 至 54.7。在吞吐方面，官方公布的数据约为 PaddleOCR-VL-1.6 的 1.49 倍、MinerU2.5 Pro 的 3.62 倍。

MiniCPM-OCR Jev 在 JevOCRBench 上得分为 93.6，高于 JEV-35B-A3B 的 90.1，接近 Qwen3.5-397B-A17B 的 93.8。Jev 给出的是可靠性评分，不对错误进行修正。

## 获取与部署

MiniCPM-OCR 系列已在 GitHub、Hugging Face 与 ModelScope 上线，支持 vLLM、SGLang、llama.cpp 与 Ollama，并提供 SDK、API、Agent Skill 插件与开源微调代码。首日硬件适配覆盖 AMD、Arm、Houmo AI、Intel 与 NVIDIA；通过 FlagOS 软件栈，首日还支持 CIX Technology、华为昇腾、寒武纪、燧原、昆仑芯、MetaX、摩尔线程、沐曦、天数智芯等厂商的 AI 与边缘芯片，以及 Apple Mac（Arm）。

## 来源

- PR Newswire：[ModelBest and OpenBMB Open-Source MiniCPM-OCR Series, Delivering High-Performance Document Parsing and AI-Powered Quality Control](https://www.prnewswire.com/news-releases/modelbest-and-openbmb-open-source-minicpm-ocr-series-delivering-high-performance-document-parsing-and-ai-powered-quality-control-302925594.html)
- daily.dev：[MiniCPM-OCR 1.0: a 1.3B open OCR model from OpenBMB](https://daily.dev/posts/minicpm-ocr-1-0-a-1-3b-open-ocr-model-from-openbmb-sybdydvah)
