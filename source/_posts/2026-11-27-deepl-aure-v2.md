---
title: DeepL 发布 Aure v2：语音翻译延迟降低 50%，端到端语音直译
date: 2026-11-27 08:00:00
tags:
  - AI动态
  - DeepL
  - 语音翻译
categories:
  - AI动态
description: DeepL 于 11 月 26 日发布语音翻译模型 Aure v2，采用端到端语音直译架构，翻译延迟较前代降低 50%，首批支持英、德、法、西、日、韩六种语言。
---

2026 年 11 月 26 日，DeepL 在东京举办的首届 Unmute Summit 上发布语音翻译模型 Aure v2。Aure v2 现已面向 DeepL Voice 客户提供，较前代 Aure 翻译延迟降低 50%，同时进一步提升了翻译准确性与表现力。

<!-- more -->

## 性能

在 DeepL 的内部基准测试中，Aure v2 的表现包括：翻译延迟中位数较前代 Aure 降低 50%；在全部测试语言对中，翻译质量高于参与对比的六个竞品系统；英日这一实时语音翻译难度较高的语言对，翻译错误比 Google Gemini 3.5 Live Translate 少 32%。

上述基准来自 DeepL 2026 年 11 月的内部研究，基于 10 个语言对的 1 分钟真实语音录音，配以人工验证的转录文本；各模型均通过公开 API 测试，不含应用层开销。

## 技术

Aure v2 采用全新的端到端模型架构，直接将语音翻译为语音，省去了以往转录、翻译、语音合成三个独立步骤。传统实时语音翻译先把语音转成文字，再翻译文字，最后把译文合成为语音，每一步都依赖前一步的结果，逐级累积处理时间。Aure v2 把三个步骤合并为一步，大幅缩短了延迟。

新架构之外，DeepL 还用强化学习解决了实时翻译的另一个难题：判断何时开始输出译文。开始太早可能丢失重要上下文，导致翻译不准确；等太久则翻译准确，但对话节奏被拖慢。德语、日语等语言的关键信息往往出现在句尾，这个问题尤为突出。训练中，Aure v2 会因既准确又快速开始的翻译而获得奖励，逐渐学会在听到足够上下文时开始翻译。

Aure v2 的前代 Aure 于 11 月 11 日发布，特点是在对话过程中持续适应说话人的声音、语调与语气，使译文更贴近说话人的表达方式。

## 增长与应用

DeepL Voice 的使用量持续增长。2026 年第三季度，DeepL Voice 总语音分钟数同比增长 8 倍以上，翻译会议分钟数增长约 7 倍。按会议分钟数计，日本的 DeepL Voice 会议使用量同比增长 7 倍以上，韩国增长 5 倍，美国和德国均增长 6 倍以上。截至 2026 年 10 月，带有会议使用量的 DeepL Voice 活跃订阅数在日本和韩国合计同比增长约 12 倍，在美国增长 8 倍，在德国增长 9 倍。

DeepL 表示，面向企业客户时，音频、转录文本和翻译内容不会用于训练其 AI 模型，会议数据在通话结束后删除，具体保留规则由客户控制。DeepL 持有 ISO 27001 与 SOC 2 Type II 认证，并支持 GDPR 合规。

## 可用性

Aure v2 首批支持六种语言：英语、德语、法语、西班牙语、日语和韩语，更多语言即将推出。该模型现已覆盖 DeepL Voice for Online Meetings、DeepL Voice for In-Person Conversations 以及 DeepL API for Voice，支持的语言无需额外设置即可自动启用。

同日，DeepL 还在日本启动了灾害多语言沟通支援计划，向地方政府、支援机构与受灾民众免费提供 DeepL Voice for In-Person Conversations，用于一对一实时翻译对话。

## 来源

- DeepL：[DeepL introduces Aure v2, its fastest Voice AI translation model](https://www.deepl.com/en/press-release/aure-v2)（2026-11-26）
- PR Newswire：[DeepL introduces Aure v2, its fastest Voice AI translation model](https://www.prnewswire.com/apac/news-releases/deepl-introduces-aure-v2-its-fastest-voice-ai-translation-model-302950696.html)（2026-11-26）
