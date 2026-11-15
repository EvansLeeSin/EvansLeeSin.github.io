---
title: OpenAI 推出 ChatGPT Wallet：dots 智能体可代用户完成支付
date: 2026-11-16 08:00:00
tags:
  - AI动态
  - OpenAI
  - Agent
categories:
  - AI动态
description: OpenAI 于 11 月 13 日推出 ChatGPT Wallet，与美国运通、万事达卡和 Visa 合作，让 dots 智能体使用令牌化支付凭证代用户完成购买，每笔交易需用户通过设备安全验证批准，初期仅面向美国 ChatGPT Pro 订阅用户。
---

2026 年 11 月 13 日，OpenAI 推出 ChatGPT Wallet，一项让其 dots 智能体代用户完成购买的支付功能。该功能与美国运通（American Express）、万事达卡（Mastercard）和 Visa 合作开发，是 OpenAI 首次接入美国运通 Agentic Commerce Experiences 的集成。

ChatGPT Wallet 让 dots 从"帮用户找到商品"延伸到"替用户结账"。用户可以请 dots 帮忙挑选一件毛衣或预订酒店房间，结账时使用 Wallet 完成支付。

<!-- more -->

## 工作方式

用户在 Wallet 中添加一次银行卡后，即可让 dots 在对话中发起购买。支付时，支付网络提供一个替代凭证——包含卡号、安全码和有效期的令牌，实际卡号不提供给智能体，也不提供给商家。OpenAI 表示，智能体和商家都不会看到用户的真实卡号。

每笔购买都需要用户明确批准，批准时须通过设备安全验证，例如 Face ID 或指纹。批准本身并不等于订单成立，用户仍需查看商家的订单确认。

## 上线范围

ChatGPT Wallet 初期仅在 dots 对话中使用，不适用于普通 ChatGPT 对话、ChatGPT Work 或 Codex 工作区。首批面向年满 18 周岁的美国 ChatGPT Pro 订阅用户，需持有符合条件的美国发行的银行卡和美国账单地址。

借记卡和虚拟卡在上线初期不在支持范围内；Chase 发行的卡须由主卡持卡人添加，附属卡持卡人无法添加。OpenAI 表示，将根据初期推广的反馈改进兼容性和可靠性，之后再扩大覆盖范围。

## 后续计划

OpenAI 表示，未来用户将能够通过设定支出上限、商品类别和时间范围等条件，把购买完全委托给智能体，并辅以额外的保障措施。目前尚未公布具体时间。

## 商家侧

OpenAI 同步发布了面向商家的《Commerce Partner Playbook》，提示商家配置 CDN 或防火墙以识别 Web Bot Auth，避免拦截合法的智能体结账流量。OpenAI 同时表示，部分网站可能尚不支持智能体购买，商家的反欺诈系统也可能将合法的智能体购买误判为异常，导致交易被拒绝或取消。

## 来源

- The Hindu BusinessLine：[OpenAI expands into payments with ChatGPT Wallet, allowing AI agents to make purchases using users' cards](https://www.thehindubusinessline.com/info-tech/openai-expands-into-payments-with-chatgpt-wallet-allowing-ai-agents-to-make-purchases-using-users-cards/article71700851.ece)（2026-11-14）
- Zot News（转引 CNBC）：[OpenAI launches ChatGPT Wallet, letting AI agents shop with credit cards](https://zot.news/article/openai-launches-ai-agent-payments-chatgpt-visa-mastercard-z29se)（2026-11-14）
- Infohandle：[OpenAI Partners With Card Networks on ChatGPT Wallet That Completes Checkouts Inside the Bot](https://infohandle.net/2026/11/14/openai-chatgpt-wallet-card-networks/)（2026-11-14）
- Releasebot（转引 OpenAI 发布说明）：[ChatGPT Updates by OpenAI - November 2026](https://releasebot.io/updates/openai/chatgpt)
