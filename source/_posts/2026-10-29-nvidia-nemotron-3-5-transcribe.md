---
title: 英伟达发布 Nemotron 3.5 Transcribe：开源权重语音模型支持 40 种语言转录
date: 2026-10-29 08:00:00
tags:
  - AI动态
  - NVIDIA
  - 语音模型
categories:
  - AI动态
description: 英伟达于 10 月 28 日发布开源权重语音模型 Nemotron 3.5 Transcribe，支持 40 种语言转录、31 种语言与英语互译、13 种语言的说话人区分，并同步推出覆盖 48 种语言的开源语音数据集 Granary v2。
---

2026 年 10 月 28 日，英伟达发布开源权重语音模型 Nemotron 3.5 Transcribe，并同步推出开源语音数据集 Granary v2。该模型将转录、说话人区分、翻译与音频问答整合进同一个检查点，可免费下载，权重采用 OpenMDW-1.1 许可，允许商业用途。

<!-- more -->

## 一次处理多项语音任务

Nemotron 3.5 Transcribe 支持 40 种语言的转录、31 种语言与英语之间的互译，以及 13 种语言的说话人区分，单段录音最长可处理 1 小时，最多区分 8 位说话人，并返回词级时间戳。

该模型可通过自然语言指令引导输出形式：同一段录音可以根据指令生成逐字转录、整理后的文本、翻译结果，或回答关于录音内容的问题。指令中还可以加入产品术语与格式约定，用于处理医疗、金融等领域的专业词汇。

英伟达表示，该模型面向会议记录与医疗转录等场景的开发者，开发者可以结合模型、Granary v2 数据集以及 NeMo Speech 等工具，针对特定行业的术语定制应用。该模型面向录制好的音频，不适用于直播流转录。

## 模型架构与部署

Nemotron 3.5 Transcribe 为混合专家架构，总参数 300 亿，每个 token 约激活 40 亿参数，由语音编码器与混合 Mamba-Transformer 语言模型组成。稀疏架构使其可以在单块英伟达芯片上运行，覆盖 Jetson AGX Thor 边缘芯片、DGX Spark 桌面系统以及 Blackwell 数据中心芯片。

英伟达公布的公司测试数据显示，在 NVFP4 精度下，单块 RTX PRO 6000 Blackwell Server Edition GPU 可以在不到 3 分钟内处理 100 小时音频，该数据基于 30 秒音频片段在高并发条件下测得。量化版本计划随后推出，可在 RTX Spark、DGX Spark 或 Jetson AGX Thor 上本地运行。

在定制演示中，英伟达使用印度医生的医疗语音对模型进行训练，在单块 GPU 上训练约 14 小时后，保留测试片段的错误率降低 45.8%。

## Granary v2 数据集

与模型一同发布的 Granary v2 是开源语音数据集与数据整理流程，其公开清单覆盖 48 种语言、463,062 小时语音，语言覆盖范围较上一代的 25 种有所扩大。开发者可从原始来源获取音频，各来源的许可协议分别适用。

## 基准表现

在基准测试方面，英伟达表示，Nemotron 3.5 Transcribe 在 Hugging Face Open ASR Leaderboard 的英语榜单上位列开源权重模型第一，平均词错误率为 5.33%。Artificial Analysis 的数据显示，该模型以 2.8% 的 AA-WER 与 Mistral 的 Voxtral Small 并列开源权重模型第一，激活参数约为 40 亿，而后者为 240 亿。

在说话人区分方面，该模型在 David AI 的 21 种语言说话人区分榜单上取得最低错误率，并在 VoiceArena 的 14 个系统对比中排名第一。

该模型已在 Hugging Face、ModelScope、NGC 与 Build.nvidia.com 上线，Baseten、DeepInfra 与 Simplismart 提供托管端点，Hugging Face Spaces 与 ModelScope Studios 提供交互演示。

## 背景

此次发布正值语音模型密集发布期：Mistral 在本月早些时候推出 Voxtral 3，ElevenLabs 推出面向语音 Agent 的实时语音服务，Salesforce 推出语音模型 Launa-Omni。英伟达此前已推出开源权重语音模型 Parakeet，参数为 11 亿。

## 来源

- TechCrunch：[Voice AI in vogue: Nvidia releases new open transcription model](https://techcrunch.com/2026/10/28/voice-ai-in-vogue-nvidia-releases-new-open-transcription-model/)
- Hugging Face（NVIDIA 官方博客）：[NVIDIA Nemotron 3.5 Transcribe and Granary v2: Intelligent Multilingual Transcription You Can Prompt and Adapt](https://huggingface.co/blog/nvidia/nemotron-transcribe-granary)
- Silicon Report：[Nvidia releases Nemotron 3.5 Transcribe for speech in 40 languages](https://www.siliconreport.com/nvidia-releases-nemotron-3-5-transcribe-for-speech-in-40-languages)
- Unite.AI：[NVIDIA Launches Open-Weight Speech Model and 463,062-Hour Audio Dataset](https://www.unite.ai/nvidia-launches-open-weight-speech-model-and-463-062-hour-audio-dataset/)
