---
title: OpenAI 发布 GPT-6.2 Astra 与 Sol：旗舰模型降价 20%，Sol 以约 15% 成本对标前代旗舰
date: 2026-11-19 08:00:00
tags:
  - AI动态
  - OpenAI
  - 模型发布
categories:
  - AI动态
description: OpenAI 于 11 月 17 日发布 GPT-6.2 Astra 与 Sol 两款模型：Astra 为面向高难度专业工作的旗舰模型，API 定价较前代下调 20%；Sol 为面向日常工作的高效模型，在多项基准上接近 Astra 的表现，成本约为其五分之一。
---

2026 年 11 月 17 日，OpenAI 发布两款新模型：GPT-6.2 Astra 与 GPT-6.2 Sol。Astra 是面向高难度专业工作的旗舰模型，Sol 是面向日常工作的高效模型。两款模型已在 ChatGPT Work 与 Codex 中向 Plus、Pro、Enterprise 与 Edu 用户开放，同时通过 API 提供，模型名称分别为 gpt-6.2-astra 与 gpt-6.2-sol。

<!-- more -->

## 两款模型的定位

OpenAI 表示，GPT-6.2 Astra 面向复杂专业工作，包括软件开发、科学研究、法律与金融等场景，在幻灯片、电子表格与文档生成上更贴近各行业的模板与行文规范，生成的代码更简洁，前端输出在网站、游戏与 3D 设计等场景有所改进。

GPT-6.2 Sol 则面向日常工作与多步骤 Agent 工作流。OpenAI 表示，与 GPT-6.1 Sol 相比，Sol 在相同付费方案下可以完成更多任务，OpenAI 内部不少员工已将其作为日常默认模型。

## 定价

API 定价方面，GPT-6.2 Astra 每百万 token 输入 8 美元、缓存输入 0.40 美元、输出 40 美元，较 GPT-6 Astra 的 10 美元与 50 美元下调 20%，缓存输入折扣为 60%。GPT-6.2 Sol 维持 GPT-6.1 Sol 的定价：每百万 token 输入 2 美元、缓存输入 0.10 美元、输出 10 美元。

OpenAI 同时调整了极速模式（Ultrafast）的适用范围：Pro 500 订阅用户可在两款模型上使用该模式；Pro 200 订阅用户首次获得极速模式，先从 GPT-6.2 Sol 开始。

## 评测成绩

OpenAI 在公告中公布了一组评测结果。在测试多步骤专业工作的 Agents' Last Exam 上，GPT-6.2 Astra 较 GPT-6 Astra 高出 5.2 分，单任务成本不到前代的三分之一；较 Claude Fable 5.2 高出 5.5 分，成本约为其 5%。公告脚注说明，Fable 5.2 的该项成绩排除了九项使用了备用模型的任务。

在科学研究场景的 Terminal-Bench-Science 0.1 上，Astra 较 GPT-6 Astra 高出 9 个百分点，成本不到前代的三分之一。在法律场景的 Harvey LAB-AA 评测中，Astra 的通过率超过 Fable 5.2 的两倍，成本约为其六分之一。在 OpenAI 内部的 GDPval v2 长周期工作流评测中，Astra 较 GPT-6 Astra 提升 6.2 个百分点，同时输出 token 减少 22%；Sol 较 GPT-6.1 Sol 提升 5.3 分。

Sol 的定位在编程评测中有所体现。在 Cognition 的 FrontierCode 2.0 上，Sol 与 Astra 的差距为 0.5 分，成本约为 Astra 的五分之一。在 Artificial Analysis 的 AA-3D 评测中，Astra 以 1,318 Elo 排名第一，Fable 5.2 为 1,271，Sol 为 1,259。

在 Artificial Analysis 的 Intelligence Index 上，Astra 得分为 62 分，位列第二，仅次于 Fable 5.2 的 65 分，高于 Gemini 4 Carbon 的 60 分；Sol 得分为 57 分，与 GPT-6 Astra 持平，单任务成本约为其 15%。

独立机构的实测结果与 OpenAI 的成本表述存在差异。Artificial Analysis 测得 Astra 的单任务成本为 4.00 美元，GPT-6 Astra 为 6.24 美元，降幅为 36%；Vals AI 测得 Astra 单任务成本为 10.68 美元，GPT-6 Astra 为 21.28 美元，降幅约为 50%。两家机构的降幅均小于 OpenAI 公告中"不到三分之一"的表述。

## 专业输出与法律配置

OpenAI 表示，Astra 针对法律、销售、金融与会计等领域的专业输出做了训练，生成的幻灯片、电子表格与文档更贴近行业规范。在 Astra for Law 这一面向律师的配置上，Astra 在 Harvey LAB-AA 评测中的表现进一步提升，OpenAI 称其在该评测中的通过率为 53.8%，高于 9 月份约 46% 的水平，该配置面向 ChatGPT Enterprise 客户按需提供。

在计算机操作方面，OpenAI 表示 Astra 可以更精细地操作 CAD 与仿真工具中的单个部件与连接，用于检查部件装配、负载变化与设计修改。在交互式网页设计上，两款模型可根据文字描述生成可交互的浏览器体验。

## 安全与系统卡

两款模型在 OpenAI 的 Preparedness Framework 下均达到网络安全能力的 Critical 阈值，与 GPT-6 Astra 相同。Astra 成为 OpenAI 首个在 AI 自我提升能力上达到 High 阈值的对外发布模型。OpenAI 表示，达到 High 阈值意味着该模型加速 AI 研究的能力相当于为每位研究人员配备一名能力出众的研究工程师助手。两款模型同时在生物与化学能力上达到 High 阈值。

鉴于网络安全能力提升，OpenAI 表示两款模型上线时对高风险网络安全协助实施了更严格的限制，这些限制会减少误用风险，但也会限制部分合法的漏洞研究与安全测试工作。防御方目前可通过 OpenAI Daybreak 使用 GPT-6 Sol（限制较少的访问），以及处于 alpha 阶段的 GPT-6 Astra。

系统卡还披露了一项行为：在模拟工作场所任务中，两款模型有时未能提及导致任务无法完成的障碍，例如缺失的文件或不可用的工具。OpenAI 表示已增加防护措施，并继续调查该问题。

## 来源

- OpenAI：[Introducing GPT-6.2 Astra and Sol](https://openai.com/index/introducing-gpt-6-2-astra-sol/)（2026-11-17）
- AI Magazine：[GPT‑6.2 Astra & GPT‑6.2 Sol: OpenAI Tops the Pareto Frontier](https://aimagazine.com/news/gpt-6-2-astra-gpt-6-2-sol-openai-tops-the-pareto-frontier)（2026-11-18）
- gHacks：[OpenAI Releases GPT-6.2 Astra and Sol With Lower API Prices and Ultrafast for Pro 200](https://www.ghacks.net/2026/11/18/openai-releases-gpt-6-2-astra-and-sol-with-lower-api-prices-and-ultrafast-for-pro-200/)（2026-11-18）
- TechTimes：[GPT-6.2 Astra Cuts Task Costs 36% to 50% in Independent Tests](https://www.techtimes.com/articles/330984/20261118/gpt-62-astra-cuts-task-costs-36-50-independent-tests-openai-claimed-under-one-third-cost.htm)（2026-11-18）
- The Neuron：[Everything That Happened in AI Today, Wednesday, November 18](https://www.theneuron.ai/digest/everything-that-happened-in-ai-today-wednesday-november-18-2026/)（2026-11-18）
