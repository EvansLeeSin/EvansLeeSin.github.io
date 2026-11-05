---
title: 百度发布 ERNIE 5.5 Flash Base：2800 亿参数 MoE 基础模型，开放权重供微调与训练研究
date: 2026-11-06 08:00:00
tags:
  - AI动态
  - 百度
  - 模型发布
categories:
  - AI动态
description: 百度于 11 月 5 日发布 ERNIE-5.5-Flash-Base，总参数 2800 亿、每 token 激活 140 亿，预训练使用 33.5 万亿 token，权重以 FP8 与 BF16 格式开放下载，定位为供开发者微调与训练方法研究的预训练检查点。
---

2026 年 11 月 5 日，百度 ERNIE 团队发布 ERNIE-5.5-Flash-Base，并开放模型权重下载。这是一个纯文本混合专家（MoE）模型，总参数 2800 亿，每 token 激活 140 亿参数。该检查点止于预训练阶段，未经过中期训练与后训练，百度表示，后训练完成的 ERNIE 5.5 Flash 将随后发布。

<!-- more -->

## 模型规模与架构

模型共 43 层，隐藏层维度 4096，注意力头 64 个。除第一层外，每层均使用 MoE 模块，包含 512 个路由专家，每 token 激活其中 10 个，另有 1 个共享专家。专家运行在 2048 维的隐空间中，而非模型完整的隐藏宽度，百度表示，这使专家分发与合并的流量和计算量约为全宽专家的一半。

注意力方面，37 层使用重度压缩注意力（Heavily Compressed Attention），其缓存为每 128 个 token 的块保存一个条目，另保留一小段未压缩的近期 token；其余 6 层使用多头隐注意力（Multi-head Latent Attention），保留对完整上下文的 token 级访问，并用索引器选择得分最高的先前位置。百度表示，这种稀疏选择使每次查询的核心注意力成本在上下文增长时保持恒定。

模型还包含四条并行残差流（通过流形约束超连接）与一个带可学习分段温度的 MultiMax 输出头。

## 预训练与长上下文

预训练从零开始，使用 33.5 万亿 token、Muon 优化器与 FP8 混合精度。训练上下文逐步扩展至 128K token，微调与推理支持 100 万 token。

训练语料除多语言网页数据外，还包括代码与软件开发记录，如提交、issue、Pull Request、评审、生成的测试与经 CI 验证的修复。精选的长文档、含语义相似干扰项的序列，以及合成的检索与问答数据用于长上下文训练。百度表示，这些选择使该基础模型适用于仓库级推理、Agent 式软件工程与长输入场景。

配套的 FlashMask 仓库提供了面向 Hopper 与 Blackwell GPU 的注意力核，Blackwell 配置支持 query 与 key 最高 576 维、value 最高 512 维的头维度。百度报告，在 SM100 硬件上，前向速度较 FlashAttention-4 MaskMod 最高提升 175%，后向最高提升 74%。

## 基准表现

百度使用同一评估框架、提示词、少样本示例与自由问答的同一 LLM 评判器，将 ERNIE 与已公开的 DeepSeek-V4-Flash-Base、Hy3-preview-Base、MiMo-V2.5-Base 三个检查点进行了对比。百度公布的部分结果如下：

| 基准 | ERNIE 5.5 Flash | DeepSeek V4 Flash | Hy3 preview | MiMo V2.5 |
| --- | --- | --- | --- | --- |
| MMLU，五样本 | 93.3 | 89.4 | 87.5 | 87.6 |
| HumanEval+，单样本 Pass@1 | 82.3 | 69.5 | 78.0 | 74.4 |
| FullStackBench，单样本 Pass@1 | 54.6 | 43.3 | 56.7 | 54.1 |
| InfiniteBench，零样本平均 | 46.5 | 48.0 | 33.0 | 46.7 |

对比结果因任务而异：ERNIE 在 MMLU 与 HumanEval+ 上领先，Hy3 在 FullStackBench 上领先，DeepSeek 在 InfiniteBench 上领先。

## 部署与生态

权重以 FP8 与 BF16 safetensors 格式提供，可在 Hugging Face 下载。模型卡记录了通过 SGLang 与 vLLM 进行生产部署的方式，两者均通过 completions API 提供服务，与其基础模型的定位一致。vLLM 路径需要 0.32.0 版本及 vLLM-ERNIE 插件，SGLang 示例使用 4 路张量并行。

NVIDIA 的 Megatron Bridge 方案提供了有监督微调工作流，覆盖数据准备、训练与导回 Hugging Face 格式，完整模型方案使用 16 个节点、每节点 4 块 GB300 GPU，并在 Blackwell GB200 与 GB300 系统上验证。

## 许可条件

该模型使用自定义的 ERNIE 5.5 Flash Base 模型许可协议 1.0 版。许可地域不包括欧盟、英国与韩国，在该地域之外使用、修改与分发未获授权。非商业使用免收模型许可费用；相关产品或服务的年收入在 5000 万美元及以下的商业使用，需一次性通知并显著标注"Powered by ERNIE"；超过该阈值需获得百度的事先书面授权。协议还禁止使用许可材料、衍生模型或其输出改进无关的 AI 或机器学习系统。

## 来源

- Unite.AI：[Baidu Releases ERNIE 5.5 Flash Base for Further Training](https://www.unite.ai/baidu-releases-ernie-5-5-flash-base-for-further-training/)
- MarkTechPost：[Baidu Releases ERNIE 5.5 Flash Base: A 280B MoE Base Model With 14B Active Parameters](https://www.marktechpost.com/2026/11/05/baidu-ernie-5-5-flash-base-280b-moe/)
- The Decoder：[Baidu releases ERNIE 5.5 Flash Base with 280 billion parameters as an open-source foundation model](https://the-decoder.com/baidu-releases-ernie-5-5-flash-base-with-280-billion-parameters-as-an-open-source-foundation-model/)
- Artiverse：[Baidu's ERNIE 5.5 Base Targets Serious Model Research](https://www.artiverse.ca/baidus-ernie-55-base-targets-serious-model-research/)
