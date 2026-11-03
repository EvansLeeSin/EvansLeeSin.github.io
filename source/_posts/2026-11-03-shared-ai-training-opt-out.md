---
title: 谷歌、微软、OpenAI 与 Anthropic 共推共享 robots.txt 信号：一行规则退出 AI 训练
date: 2026-11-03 08:00:00
tags:
  - AI动态
  - Google
  - Microsoft
  - OpenAI
  - Anthropic
categories:
  - AI动态
description: 2026 年 10 月 30 日，谷歌、微软、OpenAI 与 Anthropic 宣布支持一个共享的 robots.txt 训练偏好信号，网站可通过一行规则向参与的 AI 提供方表达不用于 AI 训练的偏好，各家的落地时间从 2027 年 2 月起陆续展开。
---

2026 年 10 月 30 日，谷歌、微软、OpenAI 与 Anthropic 宣布支持一个共享的 robots.txt 信号，用于表达网站内容不用于生成式 AI 训练的偏好。此前，网站需要针对每家公司的爬虫分别配置规则，例如 Google-Extended、GPTBot 与 ClaudeBot；新的共享信号将这一表达合并为一条规则，由参与的提供方共同读取。相关机制来自互联网工程任务组（IETF）AI Preferences 工作组的一份 Internet-Draft，标题为《Machine-Readable Training Preference Signal》，由 Anthropic 的 Kevin Kelley 于同日提交。

<!-- more -->

## 共享信号的写法

该机制引入一个共享策略令牌 `__usage_ai-training`，写在 robots.txt 普通规则组的 User-Agent 行中，配合已有的 Allow 与 Disallow 规则使用，不引入新的指令名称与新的语法。表达全站不用于 AI 训练的规则组写法如下：

```
User-Agent: __usage_ai-training
Disallow: /
```

规则组也可以只针对部分路径生效，例如 Disallow 全站、同时 Allow 特定目录。草案规定，通配符规则组（User-Agent: *）不得被解释为匹配该策略令牌； robots.txt 中没有 `__usage_ai-training` 规则组的，视为未表达训练偏好。未实现该信号的提供方会忽略这一规则组，已有的各家专用规则继续有效。

## 各家的落地时间

四家公司的落地时间并不一致。Anthropic 已经开始着手实现该信号；OpenAI 表示将在未来几个月内支持；谷歌表示目标是在 2027 年支持该控制，其爬虫文档中写明的目标为 2027 年初；微软给出了最具体的时间表，自 2027 年 2 月 1 日起在抓取时开始执行新的偏好。

谷歌在 Search Central 博客的文章中表示，该控制将帮助网站跨多个 AI 提供方一步表达训练偏好。谷歌同时说明，如果网站使用共享令牌退出训练、且未明确提及 Google-Extended，谷歌将把这一表达视为等同于禁止 Google-Extended。Google-Extended 是谷歌自 2023 年起提供的训练控制，覆盖未来 Gemini 模型的训练以及 Gemini 应用中的 grounding，该控制继续有效。

## 微软：训练与 grounding 分开处理

微软在同一天由 Bing 首席产品经理 Krishna Madhavan 发布的文章中宣布采用共享训练偏好，并在此基础上增加了一个独立的 AI Grounding 偏好。Grounding 是指 AI 助手在回答问题时实时检索并引用网页内容的过程，与用于构建模型的训练有所区分。微软的 Grounding 偏好在页面级别设置，可通过元标签或 HTTP 响应头表达，选项包括 Allow、Disallow，以及 DisallowExtended：后者将 grounding 使用限定于微软自营的 AI 体验，例如 Copilot 与 Microsoft 365，不包括微软提供给第三方的 grounding 服务。

微软还宣布了旧有标记的替换时间表。NoArchive 与 NoCache 标记自 2027 年 3 月 1 日起不再被读取为训练或 grounding 偏好，网站需要在该日期前发布新的偏好。面向仍在使用旧标记的网站，Bing Webmaster Tools 中的临时 grounding 设置将于 2026 年 12 月 15 日开放。微软表示，这些偏好不改变网站在传统 Bing 搜索结果中的收录资格。

## 现状与范围

该信号目前仍处于草案阶段。IETF 文档追踪系统将其列为个人提交的草案，不代表 IETF 的正式标准化活动，草案的有效期至 2027 年 5 月 3 日。信号本身是自愿性的行业机制，并非法律要求，覆盖范围仅限于训练，不阻止爬虫抓取页面，也不影响搜索收录与排名。Meta 对这一方向表示支持，但未作出实施承诺。

## 来源

- Search Engine Journal：[Google, Microsoft & OpenAI Plan To Honor Shared AI Training Opt-Out](https://www.searchenginejournal.com/google-microsoft-openai-shared-ai-training-opt-out/595387/)
- PPC Land：[Google and Bing back one robots.txt rule to opt out of AI training](https://ppc.land/google-and-bing-back-one-robots-txt-rule-to-opt-out-of-ai-training/)
- Coywolf：[Google, OpenAI, Microsoft, and Anthropic back a shared robots.txt AI training signal](https://coywolf.com/news/seo/google-openai-microsoft-and-anthropic-back-a-shared-robotstxt-ai-training-signal/)
- Unite.ai：[Google Plans Support for Shared Robots.txt AI Training Control](https://www.unite.ai/google-plans-support-for-shared-robots-txt-ai-training-control/)
- Skimwire：[One robots.txt rule to opt out of AI training: how it works](https://www.skimwire.com/ai-training-opt-out-robots-txt-openai-google-microsoft-anthropic/)
