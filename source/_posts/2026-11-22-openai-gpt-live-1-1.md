---
title: OpenAI 推出 GPT-Live-1.1：语音 Agent 新增待机计费，空闲成本降至每分钟 0.02 美元
date: 2026-11-22 08:00:00
tags:
  - AI动态
  - OpenAI
  - 语音模型
categories:
  - AI动态
description: OpenAI 于 11 月 20 日在 API 中推出 GPT-Live-1.1，全双工语音模型，口音更自然稳定、转录更准确，并新增待机模式：WebRTC 会话空闲时推理暂停，按每分钟 0.02 美元计费，较标准费率低 60%。
---

2026 年 11 月 20 日，OpenAI 在 API 中推出 GPT-Live-1.1。这是 OpenAI 全双工语音模型的新版本，面向构建实时语音 Agent 的开发者。新版本在多语言口音、转录准确度和任务完成可靠性上有所改进，同时引入待机模式，降低语音会话的空闲成本。

<!-- more -->

## 模型改进

GPT-Live-1.1 是全双工语音模型，支持边听边说，通话者可以在模型说话中途打断。OpenAI 表示，新版本在不同语言中的口音更自然、更稳定，转录更准确，执行任务也更可靠，在理解字母、数字等精确细节时表现更好。

与 GPT-Live-1 相同，GPT-Live-1.1 把推理和工具调用交给开发者自选的后端模型处理，语音模型本身负责实时的语音交互。模型支持音频和文本输入输出、流式传输和函数调用。

GPT-Live-1.1 此前已于 10 月 15 日起为 ChatGPT Plus 和 Pro 用户提供语音功能，此次是首次通过 API 向开发者开放。

## 待机模式

待机模式是本次更新中新增的计费配置，适用于 GPT-Live-1 和 GPT-Live-1.1。开发者在创建会话时设置空闲超时时间（`idle_timeout_s`，5 至 60 秒的整数），当会话在该时长内没有输入或输出转录时，模型暂停推理，但 WebRTC 连接保持打开；有人再次说话时，推理恢复，会话 ID 和对话历史保留。

待机模式通过 `wake_policy.type` 设为 `speech` 启用，会话等待检测到语音后再开始推理。开发者可以通过监听数据通道上的 `session.paused` 和 `session.resumed` 事件感知待机状态的切换。

## 定价

语音会话按时长计费，按秒结算。活跃会话时间每分钟 0.05 美元，与 GPT-Live-1 相同；待机状态下的 WebRTC 会话时间每分钟 0.02 美元，较标准费率低 60%。待机计费仅适用于 WebRTC 会话，WebSocket 和 SIP 会话的全部连接时间均按活跃费率计费。

后端模型和工具调用产生的费用另行计算，按所配置模型和工具的正常费率收取。待机后首次回复的延迟可能有所增加。

## 接入方式

GPT-Live-1.1 通过 `v1/live/sessions` 端点提供，支持 WebRTC、WebSocket 和 SIP 三种连接方式，模型 ID 为 `gpt-live-1.1`。OpenAI 的模型页面标注，该模型不支持 Chat Completions、Responses 和 `v1/realtime` 端点。

## 来源

- OpenAI：[GPT-Live-1.1 Model](https://developers.openai.com/api/docs/models/gpt-live-1.1)
- APIdog：[How to Use GPT-Live-1.1 API?](https://apidog.com/blog/gpt-live-1-1-api/)
- DataStudios：[OpenAI GPT-Live-1.1 API: $0.05/min active, new $0.02/min standby mode](https://www.datastudios.org/post/openai-gpt-live-1-1-api-standby-mode-0-02-per-minute)
