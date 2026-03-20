---
date: "2026-03-19"
paper_id: "2603.18756"
title: "Are complicated loss functions necessary for teaching LLMs to reason?"
authors: "Gabriele Carrino, Andrea Sassella, Nicolo Brunello, Federico Toschi, Mark James Carman"
domain: "大模型"
tags:
  - 论文笔记
  - 大模型
  - LLM
  - 强化学习
  - 推理优化
quality_score: "[待评估]/10"
related_papers: []
created: "2026-03-20"
updated: "2026-03-20"
status: analyzed
---

# Are complicated loss functions necessary for teaching LLMs to reason?

## 核心信息
- **论文ID**：2603.18756
- **作者**：Gabriele Carrino, Andrea Sassella, Nicolo Brunello, Federico Toschi, Mark James Carman
- **机构**：意大利帕多瓦大学
- **发布时间**：2026-03-19
- **链接**：[arXiv](https://arxiv.org/abs/2603.18756) | [PDF](https://arxiv.org/pdf/2603.18756)

## 研究问题

复杂的损失函数（如GRPO）对于提升LLM的推理和数学能力是否真的必要？

## 方法概述

### GRPO 系统分析

Group Relative Policy Optimization (GRPO) 是一种用于提升LLM推理能力的训练方法，它结合了：
- 群体相对优势估计
- PPO风格裁剪
- KL正则化

### 关键发现

研究进行了系统的GRPO分析，识别出两个关键发现：

1. **负反馈的必要性**：仅在基线以上的动作上进行训练会限制学习，纳入负反馈是必要的
2. **PPO风格约束的非必要性**：策略比率裁剪等PPO风格约束对提升数学推理或性能并非必需

### RGRA 方法

基于这些发现，提出RGRA（REINFORCE with Group Relative Advantage）：
- 保留群体相对优势估计
- 移除PPO风格裁剪
- 移除策略比率项

## 实验结果

### 基准测试

在标准数学基准上进行实验，包括：
- MATH
- GSM8K
- 其他数学推理数据集

### 主要结果

实验表明RGRA有可能比GRPO取得更强性能，表明：
- 更简单的基于REINFORCE的方法可以有效增强LLM的推理能力
- 提供更透明和高效的GRPO替代方案

## 关键结果

- 负反馈对于有效的推理训练是必要的
- PPO风格的复杂约束可以移除而不损失性能
- 简化的RGRA方法可以优于复杂的GRPO

## 相关工作

- GRPO (Group Relative Policy Optimization)
- PPO (Proximal Policy Optimization)
- REINFORCE
- 数学推理训练

## 代码

代码和实验细节待公开。
