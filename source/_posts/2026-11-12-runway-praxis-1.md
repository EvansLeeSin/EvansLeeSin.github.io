---
title: Runway 开源 Praxis-1：27B 参数世界动作模型，登顶 NVIDIA 机器人榜单
date: 2026-11-12 08:00:00
tags:
  - AI动态
  - Runway
  - 机器人
  - 开源模型
categories:
  - AI动态
description: Runway 于 11 月 11 日开放 Praxis-1 的权重，27B 参数混合专家扩散 Transformer，同时预测视频与机器人动作，在 NVIDIA RoboLab-120 榜单上以 46.2% 的成功率位居首位，Apache 2.0 协议允许商用。
---

2026 年 11 月 11 日，Runway 开放了 Praxis-1 的权重。这是一款面向机器人控制的世界动作模型（world action model），以 Apache 2.0 协议发布，允许商用。Praxis-1 于今年 9 月首次亮相，是 Runway 推出的首个世界动作模型，建立在其通用世界模型背后的大规模视频预训练之上。

Praxis-1 是一个 270 亿参数的混合专家扩散 Transformer，同时预测视频与机器人动作。Runway 表示，该模型在 NVIDIA 的 RoboLab-120 榜单上位居世界动作模型首位，并超过所有开源视觉-语言-动作（VLA）模型。

<!-- more -->

## 基准表现

在 RoboLab-120 榜单上，Praxis-1 在 1,200 次测试中成功率为 46.2%，即完成 555 次。同一榜单上，FLUX 3 Action 为 42.9%，Cosmos 3 Nano 为 36.8%，π0.5 为 28.0%。

Runway 表示，Praxis-1 从大规模视频中学习物体的运动方式与任务的展开过程，这让它在针对新硬件微调之前就具备先发优势。据其研究，网络视频作为预训练数据，在策略性能上与遥操作机器人视频相当，模型能力的瓶颈由此转向模型能够学习多少通用视频。

在跨硬件泛化方面，Praxis-1 在从未出现在训练数据中的谷歌 RT-1 机器人上微调后，于 SimplerEnv 测试中达到 80.0% 的成功率，高于原始 RT-1 策略的 52.4%。

## 开放获取

Praxis-1 即日起可在 GitHub、Hugging Face（原生支持 LeRobot 机器人库）以及 vLLM-Omni 中获取，托管推理则由 Reactor 提供。发布内容包括权重、推理代码与微调代码，支持全参数微调与 LoRA 微调。

Hugging Face 上提供三个检查点：基础中训模型、在 DROID 数据集上微调的版本，以及针对双臂 YAM 机器人微调的版本。模型以 bfloat16 格式占用 54.4GB，支持 4 位 NVFP4 量化，量化后为 17.5GB，可在单块 80GB 显存的 GPU 上部署。

Praxis-1 可直接运行于 NVIDIA 硬件之上，覆盖数据中心 GPU（H100、B200）、工作站 GPU（RTX 5090、RTX PRO 6000）以及机器人本体搭载的 Jetson Thor。Runway 称，模型在单块 H100 上生成每段 1.6 秒的动作片段约需 0.55 至 0.6 秒。

## 合作伙伴

发布前，Praxis-1 已在三家合作伙伴的硬件上运行：Noble Machines 的双足人形机器人、Standard Bots 的六轴工业机械臂，以及 Ultra 的双臂仓储机器人。Runway 表示，单个检查点经过轻量微调即可适配多种机器人形态，LoRA 微调可进一步适配自有硬件、摄像头与任务。

## 背景

Runway 以面向影视创作者的视频生成工具为人所知，Praxis-1 是其将视频模型转向机器人控制的尝试。Runway 在发布时表示，开放权重是其在 9 月宣布 Praxis-1 时就做出的承诺。Praxis-1 建立在 Runway 作为创始成员参与的 Cosmos Coalition 之上，该联盟与 NVIDIA 合作推进面向物理 AI 的开放世界模型。

## 来源

- Runway：[Praxis-1 Is Now Available](https://runway.com/news/company-news/praxis-1-is-now-available)（2026-11-11）
- MadRobot：[Runway Praxis-1: free open-weight robot AI model released](https://madrobot.blog/2026/11/11/runway-praxis-1-open-weight-robot-model/)（2026-11-11）
- Dev.to：[Praxis-1: How Runway Turned a Video Foundation Model Into a Robot Brain](https://dev.to/prabhakar_chaudhary_7afe4/praxis-1-how-runway-turned-a-video-foundation-model-into-a-robot-brain-4m51)（2026-11-11）
- AlphaSignal：[Runway's Praxis-1 Beats Every Open Robot Model at 46% Success Rate](https://alphasignal.ai/news/runway-s-praxis-1-beats-every-open-robot-model-at-46-success-rate)（2026-11-11）
