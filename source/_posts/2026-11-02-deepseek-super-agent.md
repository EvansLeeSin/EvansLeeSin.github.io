---
title: DeepSeek Harness 团队开源 Super-agent 原型：面向单个 GitHub 仓库的主动式编码 Agent
date: 2026-11-02 08:00:00
tags:
  - AI动态
  - DeepSeek
  - Agent
  - 开源
categories:
  - AI动态
description: DeepSeek Harness 团队于 10 月 31 日发布并以 MIT 协议开源 Super-agent 研究原型 dsh-superagent-prototype，该原型面向单个 GitHub 仓库，以常驻 Router 与并行 Worker 会话的架构处理团队提出的编码任务。
---

2026 年 10 月 31 日，DeepSeek Harness 团队发布并开源 Super-agent 研究原型，代码仓库为 dsh-superagent-prototype，采用 MIT 协议。该原型面向单个 GitHub 仓库，定位为主动式编码 Agent，可监听仓库与团队对话中的请求，并以代码变更的形式返回处理结果。团队同时发布了设计文章《Exploring Super-agent Design：Towards a More Autonomous Agent System》，介绍 Super-agent 的设计思路。

<!-- more -->

## 发布内容

Super-agent 以 DeepSeek Harness 的 bundle 形式打包。DeepSeek Harness 是 DeepSeek 的 Agent 运行框架，原型运行于其上。原型监听一个 GitHub 仓库，并可选择接入飞书作为额外的对话渠道。当获得授权的人员提出工作请求时，原型会创建一项工作任务，在独立的会话与工作目录中执行，并回到原始对话中返回结果，结果形式可能包括提交代码变更的拉取请求。

团队在仓库说明中将这一原型的核心原则表述为：占用尽可能少的人工注意力，提供尽可能多的价值。原型仅在被请求，或团队预先设定的规则允许时采取行动；仅在需要有人采取行动，或有人能够使用其结果时才发言。

## Router 与 Worker 架构

Super-agent 将职责分为两层。常驻的 Router 负责与人对话并维护共享上下文，接收来自仓库与对话渠道的事件，并将工作分配给 Worker。每个 Worker 会话独立运行一项任务，处理各自的工作项，并可接收与其处理线程相关的后续事件。多个 Worker 会话可以并行运行，从而同时处理多项任务。

这一架构针对的是多人协作场景中常见的会话管理问题。团队在设计文章中指出，一个人通常只能同时有效监管三到五个 Agent 会话。Super-agent 的思路是将会话管理交由 Router 承担，Worker 在各自独立的会话中执行具体任务，任务完成后结果回到原始对话。

## 实验数据

团队在模拟环境中对 Super-agent 进行了初步实验。实验使用约 300 条模拟消息，其中约 20 条为真实工作请求，并与单会话 Agent 基线进行了对比。团队公布的数据显示，Super-agent 完成一半任务的中位时间为 12.4 分钟，95% 任务的完成时间为 15.7 分钟；单会话基线的 95% 完成时间为 29.5 分钟。团队同时指出，实验仅基于模拟消息与模拟工具，未对真实编码质量进行衡量，相关数据为团队自报结果。

## 定位与限制

仓库说明明确指出，该发布为研究原型，仅供参考，并非 DeepSeek 的正式产品。公开版本与团队内部运行的版本并不相同，设计文章中讨论的部分设计属于未来发展方向，尚未在原型中实现。仓库说明还指出，原型的部分工程工作由编码 Agent 完成，代码可能仍包含缺陷，尚未达到可用于生产的状态。

团队列出的未完成事项包括 Router 的扩展性、长期记忆、Agent 实例之间的通信，以及云端 Agent 可访问本地设备凭据时带来的提示注入风险。原型运行需要专用的 GitHub 用户账号，支持 github.com，暂不支持 GitHub Enterprise Server。运行环境要求包括 Node.js 22.19 或更高版本、GitHub CLI 2.48 或更高版本，以及在 DeepSeek Harness 中配置模型服务。Agent 会话以操作系统的用户身份运行，团队建议使用独立的操作系统账号进行隔离。

## 来源

- GitHub：[deepseek-ai/dsh-superagent-prototype](https://github.com/deepseek-ai/dsh-superagent-prototype)
- MarkTechPost：[DeepSeek Open-Sources dsh-superagent, a Router-Worker Coding Agent](https://www.marktechpost.com/2026/11/01/deepseek-dsh-superagent-router-worker-coding-agent/?amp=1)
- AI Affairs：[DeepSeek Harness team releases coding agent prototype for GitHub](https://www.aiaffairs.com/technology/deepseek-harness-super-agent-coding-prototype/)
- Madrobot：[DeepSeek Super-agent: free coding agent that fixes bugs unasked](https://madrobot.blog/2026/11/01/deepseek-super-agent-open-source-proactive-coding-agent/)
