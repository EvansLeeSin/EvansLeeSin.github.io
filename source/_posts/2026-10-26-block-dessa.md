---
title: Block 发布 Dessa：仅用人类语音训练的全双工语音模型，可本地运行于 MacBook Pro M4 Max
date: 2026-10-26 08:00:00
tags:
  - AI动态
  - Block
  - 语音模型
categories:
  - AI动态
description: Block 于 10 月 23 日发布全双工语音模型 Dessa，该模型从零开始仅用人类对话语音训练，不含文本与预训练模型，推理速度快于实时，可本地运行于 MacBook Pro M4 Max 及以上机型。
---

2026 年 10 月 23 日，Block 发布全双工语音模型 Dessa。Block 将其称为迄今最真实的全双工语音模型，称与之对话如同与人交谈，带有情绪、细微差别、停顿与自然的语调。Dessa 由 Block 内部的小型 AI 研究实验室开发，该实验室由多伦多深度学习初创公司 Dessa 的前成员创立，负责人为 Ragavan Thurairatnam，直接向 Block 联合创始人 Jack Dorsey 汇报。

<!-- more -->

## 语音到语音，不经过文本

Dessa 是一个真正的语音到语音模型：音频输入、音频输出。Block 表示，Dessa 从零开始仅用人类对话训练，不含文本、不使用预训练模型，其所知的一切均来自人类语音。

与常见的语音助手不同，Dessa 不经过语音转文本、再由文本模型生成答案、最后转回语音的流水线。Block 表示，现有的语音 AI 把语音转成文本，丢弃了文本本身无法承载的大量信息，听不到说话者的情绪；Dessa 则原生地听见并表达情绪、讽刺、笑声、沮丧的叹息与哽咽的声音。

## 全双工对话

Dessa 是全双工模型，即边听边说，与人交谈的方式相同。Block 表示，Dessa 从真实对话中学到了何时打断、何时以"yeah""got it"之类的回应表示自己在跟进。Block 发布的演示录音中，Dessa 在对话里表现出不同的声音、语调与情绪，例如在谈到工作疲惫时声音听起来同样疲惫；其中一段演示为 Dessa 与 OpenAI 的 GPT-Live-1 之间的对话，Block 表示与该模型的开发者并无关联。

Block 表示，Dessa 的推理速度快于实时，因此回复之间没有令人尴尬的等待；同时该模型可本地运行于 MacBook Pro M4 Max 或更高配置的机型。

## 训练规模

Block 表示，Dessa 学习语言所用的词量比大语言模型少数百倍，训练仅使用了一台 NVIDIA GB200 NVL72 系统。Block 同时表示，该实验室从事生成式语音模型已有八年以上。

## 获取方式与未公布的信息

目前 Dessa 处于研究预览阶段，暂无公开访问渠道。Block 已开放公开候补名单，并向一小部分 AI 安全研究人员提供早期访问，用于测试语音助手可能误导对话另一方等情形。

Block 尚未公布 Dessa 的参数量、API、定价、权重与基准测试结果，现有证据均为 Block 自身发布的演示录音。

## 背景

Block 是 Square 与 Cash App 背后的公司。Square 已在使用语音 AI 处理点单等业务。Block 表示，拥有一个可在设备端运行的自有语音模型后，可以更低的成本支撑更多面向商家与消费者的体验。

## 来源

- Block：[Dessa](https://block.xyz/dessa)
- TechCrunch：[Block's new voice model sounds eerily human](https://techcrunch.com/2026/10/24/blocks-new-voice-model-sounds-eerily-human/)
- Unite.AI：[Block Unveils Dessa, a Full-Duplex Speech Model Trained on Conversation](https://www.unite.ai/block-unveils-dessa-a-full-duplex-speech-model-trained-on-conversation/)
