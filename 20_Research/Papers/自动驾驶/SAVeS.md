---
date: "2026-03-19"
paper_id: "2603.19092"
title: "SAVeS: Steering Safety Judgments in Vision-Language Models via Semantic Cues"
authors: "Carlos Hinojosa, Clemens Grange, Bernard Ghanem"
domain: "自动驾驶"
tags:
  - 论文笔记
  - 自动驾驶
  - VLM
  - 安全
  - 多模态
quality_score: "[待评估]/10"
related_papers: []
created: "2026-03-20"
updated: "2026-03-20"
status: analyzed
---

# SAVeS: Steering Safety Judgments in Vision-Language Models via Semantic Cues

## 核心信息
- **论文ID**：2603.19092
- **作者**：Carlos Hinojosa, Clemens Grange, Bernard Ghanem
- **机构**：KAUST（阿卜杜拉国王科技大学）
- **发布时间**：2026-03-19
- **链接**：[arXiv](https://arxiv.org/abs/2603.19092) | [PDF](https://arxiv.org/pdf/2603.19092)

## 研究问题

视觉语言模型（VLM）在现实和具身环境中的安全决策如何受到视觉上下文的影响？哪些视觉证据驱动了这些判断？

## 方法概述

### 语义引导框架

提出语义引导框架，应用受控的文本、视觉和认知干预，而不改变底层场景内容。

### SAVeS 基准

提出SAVeS，一个在语义线索下的情境安全基准 together with an evaluation protocol that separates behavioral refusal, grounded safety reasoning, and false refusals.

![数据集流程|600](images/dataset_pipeline_compressed_page1.png)

### 主要发现

实验跨越多个VLM和额外的最先进基准，表明：
- 安全决策对语义线索高度敏感
- 依赖于学习的视觉-语言关联而非基于视觉的理解
- 自动引导管道可以利用这些机制，揭示多模态安全系统的潜在漏洞

![定性示例|600](images/qualitative_page1.png)

## 实验结果

### VLM安全行为

在MSSBench上的评估显示：
- VLM的安全判断容易被语义线索操纵
- 表明模型依赖学习的关联而非真正的视觉理解

## 关键结果

- 安全决策高度依赖语义线索
- 揭示了多模态安全系统的潜在漏洞
- 需要更基于视觉理解的安全机制

## 相关工作

- Vision-Language Models (VLM)
- Multimodal Safety
- Semantic Steering

## 代码

代码和数据待公开。
