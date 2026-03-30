---
date: "2026-03-20"
paper_id: "2603.19987"
title: "Breaking the Capability Ceiling of LLM Post-Training by Reintroducing Markov States"
authors: "Yurun Yuan, Tengyang Xie"
domain: "大模型"
tags:
  - 论文笔记
  - 大模型
  - LLM
  - 强化学习
  - 后训练
quality_score: "[待评估]/10"
related_papers: []
created: "2026-03-23"
updated: "2026-03-23"
status: analyzed
---

# Breaking the Capability Ceiling of LLM Post-Training by Reintroducing Markov States

## 核心信息
- **论文ID**：2603.19987
- **作者**：Yurun Yuan, Tengyang Xie
- **机构**：待确认
- **发布时间**：2026-03-20
- **链接**：[arXiv](https://arxiv.org/abs/2603.19987) | [PDF](https://arxiv.org/pdf/2603.19987)

## 研究问题

强化学习已成为LLM后训练和对齐的标准范式，但最近证据表明它面临一个持续的"能力天花板"：与发现新策略的经典RL系统不同，LLM的RL通常只是对预训练权重中已有模式的精炼。

## 方法概述

### 识别结构性瓶颈

本文识别了一个根本性的结构性瓶颈：经典RL依赖于紧凑、信息丰富的马尔可夫状态，而当前LLM后训练形式依赖于不断扩展的动作历史。

### 马尔可夫状态

重新审视一个在RL中长期以来核心但在LLM后训练中缺失的原则：显式马尔可夫状态。

![组合锁游戏|600](images/combination-lock-game.drawio_page1.png)

### 理论保证

理论上，提供了严格的保证，证明利用估计的马尔可夫状态可以显著降低样本复杂度。

![训练奖励对比|600](images/train_reward_comparison_page1.png)

## 实验结果

### 复杂逻辑谜题

在复杂的逻辑谜题套件上，表明引入马尔可夫状态持续打破标准RL后训练的性能边界。

![Pass@k结果|600](images/pass_at_k_subplot_page1.png)

## 关键结果

- 引入马尔可夫状态持续打破标准RL后训练的性能边界
- 超越"历史即状态"建模，转向结构化马尔可夫表示，对于解锁开放性发现和生成AI中真正的新推理能力至关重要

## 相关工作

- Reinforcement Learning (RL)
- LLM Post-Training
- Markov Decision Processes

## 代码

代码和数据待公开。
