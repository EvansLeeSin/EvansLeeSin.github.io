---
title: Earendil 发布开源编程 Agent Pi 1.0：Codemode 工具调用机制号称削减约 40% 提示词 token
date: 2026-10-15 08:00:00
tags:
  - AI动态
  - Agent
  - 开源工具
categories:
  - AI动态
description: Earendil 于 10 月 1 日发布 Pi 1.0，开源终端编程 Agent，采用 MIT 许可证。新版引入名为 Codemode 的工具调用系统，据称可将提示词 token 量削减约 40%；同时内置 MCP 支持，并发布了面向长任务的实验性组件 Pi Durable。
---

2026 年 10 月 1 日，小型团队 Earendil（Earendil Works）发布 Pi 1.0。这是 Pi 终端编程 Agent 的首个稳定版本，采用 MIT 许可证开源，安装方式为一键脚本（macOS/Linux）或 PowerShell 命令（Windows）。

Pi 自称为一个"极简、可扩展的 Agent 脚手架"（agent harness）：它本身不是模型，而是运行在开发者指向的任意大语言模型之上，负责调度编排——读取文件、运行命令、调用工具、管理会话上下文。Earendil 称每周有数十万人使用 Pi。

<!-- more -->

## Codemode

1.0 的核心新功能是 Codemode，一套新的工具调用系统。多数 MCP 兼容的 Agent 习惯把每个工具的完整描述都放进系统提示词，而 Codemode 让模型改为编写简短的 JavaScript 代码片段来按需调用工具，不再在每次轮次前阅读一长串工具菜单。

据 Earendil 发布的材料，切换到 Codemode 后提示词体积缩小约 40%。其引用的一个示例中，一次 GPT-5.6 的编程请求从约 5,300 token 降到约 3,300 token。Codemode 配合延迟工具加载一同工作：会话开始时不再预载全部工具，而是等到具体工具被实际调用时再加载。

## MCP 与 Pi Durable

1.0 把 MCP 支持直接内置进 Codemode，扭转了团队此前的公开立场——他们此前认为开发者可通过扩展系统实现同等功能，无需原生 MCP 支持。

同日发布的 Pi Durable 是面向长时间运行 Agent 应用的实验性组件，与主程序分开打包。它的目标是解决长任务因进程崩溃、网络中断或机器休眠导致进度丢失的问题，提供可断点恢复的运行基座，目前仍标为实验性质。

## 模型与接入方式

Pi 本身不收取订阅费，运行成本完全取决于开发者指向的模型提供方。新版支持 15 家以上提供方，包括 Anthropic、OpenAI、Google、Amazon Bedrock、Mistral、xAI、Hugging Face、OpenRouter 和 Ollama，并支持对话中切换模型；也可以通过 Ollama 的 OpenAI 兼容端点接入本地模型。

新版还引入虚拟模型（virtual models），允许把多个底层模型组合成一个逻辑模型，例如把需要推理的步骤路由到一个提供方，把快速便宜的补全交给另一个提供方。

## 背景

Pi 1.0 发布正值编程 Agent 工具密集更新的窗口：Anthropic 于 10 月 9 日发布 Claude Code 2.1.296，为子 Agent 引入独立的压缩调度；SST 在 10 月 11 日至 13 日连续推送 OpenCode v1.19.0 与 v2.0.28；GitHub Copilot 于 10 月 13 日确认 Gemini 4 Argon 已在 Copilot 中全面可用；OpenAI 则在 10 月的研究更新中推出面向编程与计算机使用场景的 GPT-6.1 Sol。

## 来源

- Tech Insider：[Pi 1.0 Coding Agent: Open-Source Release Cuts Tokens 40%](https://tech-insider.org/pi-1-0-coding-agent-tokens-cut-2026/)（2026-10-14）
- PithWire：[Earendil ships Pi 1.0 agent harness plus Pi Durable](https://pithwire.com/en/articles/pi-10-3r7927/)（2026-10-02）
- SitePoint：[Pi 1.0 Coding Agent Setup: Installation and MCP Guide](https://www.sitepoint.com/pi-1-0-coding-agent-setup-mcp/)（2026-10-04）
- AI Book News：[Pi Hits 1.0: Codemode Ships, and a Durable Substrate for Long-Running Agents](https://getaibook.com/news/pi-1-0-ships-codemode-and-durable-agent-substrate/)（2026-10-03）
