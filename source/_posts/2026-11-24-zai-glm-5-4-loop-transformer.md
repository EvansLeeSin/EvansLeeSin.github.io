---
title: Z.ai 发布 GLM-5.4：首款 Loop Transformer 旗舰模型，28 层循环两次对标 2T–3T 参数模型
date: 2026-11-24 08:00:00
tags:
  - AI动态
  - Z.ai
  - 模型发布
categories:
  - AI动态
description: Z.ai 于 11 月 23 日发布 GLM-5.4，首款基于 Loop Transformer 架构的旗舰模型。模型将 GLM-5 约 7500 亿参数基座中的 28 层循环执行两次，Z.ai 称其智能水平可与 2T–3T 参数模型相当，现已面向全部 GLM Coding Plan 订阅用户开放。
---

2026 年 11 月 23 日，Z.ai 发布 GLM-5.4，这是其首款基于 Loop Transformer 架构的旗舰模型。模型将 GLM-5 基座中约 7500 亿参数规模的 28 层循环执行两次，Z.ai 称其智能水平可与 2T–3T 参数规模的模型相当。模型已面向全部 GLM Coding Plan 订阅用户开放，同时可在 ZCode 与 Z.ai Chat 中使用。

<!-- more -->

## Loop Transformer 架构

在标准 Transformer 中，每一层在一次前向传播中只执行一次。GLM-5.4 则让一组共享权重的 28 层循环执行两次，在不增加参数量的情况下加深网络，让第二次迭代在第一次的基础上继续精炼隐状态。Z.ai 表示，这一思路并不新颖，2018 年的 Universal Transformer 已提出权重共享的深度概念，近期关于循环深度与循环语言模型的研究也在小规模上取得了进展。

Z.ai 没有从零开始预训练循环模型，而是通过继续训练将已预训练好的 GLM-5 基座改造为 Loop Transformer。Z.ai 在技术博客中表示，在相同预训练算力预算下，从零训练的循环模型仍落后于非共享权重的模型，改造已有基座则能以相对较小的算力开销抬高智能上限。

为让循环在 7500 亿参数规模下实际可行，Z.ai 做了三处工程改动：每轮迭代引入独立的逐 token 门控，按比例将候选更新写回残差流，避免直接覆盖隐状态导致激活范数膨胀；第二轮循环复用第一轮选出的稀疏 KV，只在局部滑动窗口内保留新生成的 KV，使额外一轮循环的代价仅为一个滑动窗口的 KV 缓存，而非完整上下文缓存，在 100 万 token 上下文下仍可控制部署成本增幅；第二轮循环直接复用第一轮注意力索引器的索引，不产生额外的索引开销。

## 性能

Z.ai 尚未公布 7500 亿参数旗舰模型本身的基准分数。博客中给出的证据来自一台与 7500 亿基座架构相同的 300 亿参数模型上的等参数对照实验：在参数量相同、总训练算力仅增加约 10% 的条件下，循环版本取得明显提升，AIME25 从 19.17 升至 30.42，GPQA-Diamond 从 47.58 升至 56.26，MMLU-Pro 从 71.65 升至 75.05。Z.ai 表示，数学、科学推理与长上下文任务的提升最大，而在多数基准上平均输出长度下降 10%–14%，部分推理从显式的输出 token 转入循环的隐式深度。

Z.ai 也在博客中提到模型的局限：模型有时会陷入过长的"马拉松式思考"循环，不过这种 prolonged 的反思与自我纠正会持续提升超出其参数规模的准确率。

## 泛化编码

GLM-5.4 标志着 Z.ai 所称的"泛化编码"（Generalized Coding）的开始，即以代码为基础处理更广泛的任务。Z.ai 自 2025 年初全面转向编码以来，已解锁 Agent 工程、长时任务与网络安全等方向，此次将能力进一步扩展到传统软件开发之外。

博客展示了四项演示：用代码生成并剪辑自述音乐视频《Hello World》；通过 FreeCAD 中的工程级 CAD 建模搭建六轴机械臂；直接生成一款包含角色移动、物理、地图、战斗系统与美术资源的完整游戏；用纯数学几何与自定义 GLSL 着色器从零生成交互式 3D 观鸟场景。GLM-5.4 还新增了视觉能力，前代旗舰 GLM-5.3 的主线版本仅支持文本输入，新模型可直接接受图像输入。

## 速度与获取方式

Z.ai 称，GLM-5.4 在非高峰时段可达每秒 200 token，高峰负载下维持在每秒 70–80 token。模型现已面向全部 GLM Coding Plan 订阅用户开放，周配额比 GLM-5.3 增加 50%，同时可在 ZCode 桌面应用与 Z.ai Chat 中使用。公开 API 将在安全评估完成后开放，模型权重计划在完成必要的安全加固后开源。

Z.ai 表示，GLM-5.4 只是循环架构的第一步，下一步将探索自适应算力，让更难的 token 动态获得更多迭代次数，同时研究循环次数与模型规模继续增长时的收益变化。更大规模的下一代模型将沿用此次的经验。

## 来源

- Z.ai 官方博客：[Toward Generalized Coding with Our First Loop Transformer](https://z.ai/blog/glm-5.4)
- MarkTechPost：[Z AI Releases GLM-5.4: A 750B Loop Transformer That Runs 28 Layers Twice](https://www.marktechpost.com/2026/11/23/zai-glm-5-4-loop-transformer/)（2026-11-23）
- Wccftech：[Z.ai Debuts GLM-5.4 With a Novel Looped Transformer Architecture, Skipping AI Benchmarks Entirely](https://wccftech.com/z-ai-debuts-glm-5-4-with-a-novel-looped-transformer-architecture-skipping-ai-benchmarks-entirely/)（2026-11-23）
