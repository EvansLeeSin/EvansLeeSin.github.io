---
title: ElevenLabs 发布 Eleven Realtime v1：两款端到端语音到语音模型，v1 Max 在 Big Bench Audio 上拿下 98.8% 准确率
date: 2026-10-21 08:00:00
tags:
  - AI动态
  - ElevenLabs
  - 语音模型
  - 模型发布
categories:
  - AI动态
description: ElevenLabs 于 10 月 20 日发布 Eleven Realtime 语音到语音模型家族，包含 v1 Mini 和 v1 Max 两个版本。v1 Max 在 Artificial Analysis 的 Big Bench Audio 基准上取得 98.8% 准确率，响应延迟 470 毫秒；两个模型通过 ElevenAgents 平台和兼容 OpenAI 的 Realtime API 提供。
---

2026 年 10 月 20 日，ElevenLabs 发布语音到语音（speech-to-speech）模型家族 Eleven Realtime，一次推出 v1 Mini 和 v1 Max 两个版本。

以往基于 ElevenLabs 的语音助手需要把语音识别、语言模型和语音合成等多个组件串联起来。Eleven Realtime 把这些环节收进一个端到端模型：语音识别、轮次切换、语言模型和发音在一个系统内联合调优，开发者无需逐个挑选和调参各个组件。

<!-- more -->

## 两个版本

**Eleven Realtime v1 Max** 面向对推理和准确率要求最高的任务，如客服、工具调用型 Agent 工作流。**Eleven Realtime v1 Mini** 面向自然的日常对话，把延迟和成本放在首位，ElevenLabs 表示它足以覆盖大多数用例。

模型支持最多 90 种语言，可调用 ElevenLabs 语音库中的 17,000 个声音。Mini 版专门训练了对真实对话节奏的感知，能分辨说话人是讲完了，还是只是随口"嗯嗯"一声。

## 基准表现

在 Artificial Analysis 的 Big Bench Audio（语音推理）基准上，v1 Max 取得 98.8% 的准确率，高于 Grok Voice 3.0 的 98.5% 和 Gemini 3.8 Live Extended Thinking 的 97.7%；Mini 版为 75.9%。

在对话自然度（Conversational Dynamics）维度，Mini 版得 95.8%，略高于 Max 的 94.1%，与 OpenAI 的 GPT-Realtime 2.1 持平。需要调用工具的任务中差距拉大：Max 成功率 87.1%，Mini 为 60.3%。在用户盲测的 Speech Agent Arena 上，Max 得 998 分，Mini 得 988 分。

延迟方面，v1 Max 响应时间 470 毫秒，Mini 为 500 毫秒。对比之下，Grok Voice 3.0 为 810 毫秒，GPT-Realtime-2（High）为 1.14 秒。在 Artificial Analysis 的准确率-延迟坐标上，目前没有模型同时比 Max 更快且更准确。

## 接入与定价

两个模型通过 ElevenAgents 平台和兼容 OpenAI 格式的 Realtime API 提供。计费按音频分钟数加 token 用量，v1 Max 价格高于 v1 Mini，完整价格见 ElevenLabs 官网的定价页面。

## 来源

- The Decoder：[Elevenlabs releases two new speech-to-speech models designed for real-time AI conversations](https://the-decoder.com/elevenlabs-releases-two-new-speech-to-speech-models-designed-for-real-time-ai-conversations/)（2026-10-20）
- Journal du Net：[ElevenLabs Unveils Faster, More Accurate Speech-to-Speech Models](https://www.journaldunet.com/en/1556895-elevenlabs-unveils-faster-more-accurate-speech-to-speech-models/)（2026-10-20）
- AI Parabellum：[ElevenLabs Eleven Realtime: New Voice Agent Models](https://aiparabellum.com/elevenlabs-eleven-realtime-voice-models/)
