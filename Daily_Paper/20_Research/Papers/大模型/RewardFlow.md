---
date: "2026-03-19"
paper_id: "2603.18859"
title: "RewardFlow: Topology-Aware Reward Propagation on State Graphs for Agentic RL with Large Language Models"
authors: "Xiao Feng, Bo Han, Zhanke Zhou, Jiaqi Fan, Jiangchao Yao, Ka Ho Li, Dahai Yu, Michael Kwok-Po Ng"
domain: "大模型"
tags:
  - 论文笔记
  - 大模型
  - LLM
  - Agentic RL
  - 强化学习
  - 奖励模型
quality_score: "[待评估]/10"
related_papers: []
created: "2026-03-20"
updated: "2026-03-20"
status: analyzed
---

# RewardFlow: Topology-Aware Reward Propagation on State Graphs for Agentic RL with Large Language Models

## 核心信息
- **论文ID**：2603.18859
- **作者**：Xiao Feng, Bo Han, Zhanke Zhou, Jiaqi Fan, Jiangchao Yao, Ka Ho Li, Dahai Yu, Michael Kwok-Po Ng
- **机构**：上海交通大学、复旦大学、香港中文大学等
- **发布时间**：2026-03-19
- **链接**：[arXiv](https://arxiv.org/abs/2603.18859) | [PDF](https://arxiv.org/pdf/2603.18859)

## 研究问题

如何解决LLM智能体强化学习中稀疏终端奖励和过程奖励建模成本高的问题？

## 方法概述

### 核心方法

RewardFlow是一种轻量级的状态级奖励估计方法，专门针对智能体推理任务设计。该方法的核心思想是利用推理轨迹中状态的内在拓扑结构，通过构建状态图来：

1. **构建状态图**：将推理轨迹中的状态表示为图中的节点
2. **分析状态贡献**：分析每个状态对最终成功的贡献程度
3. **拓扑感知传播**：利用图的拓扑结构进行奖励传播，产生客观的状态级奖励

### 方法架构

![RewardFlow架构图|600](images/rewardflow_overview.pdf)

![动机图|600](images/motivation.pdf)

### 关键创新

1. **轻量级奖励估计**：无需训练专门的奖励模型，降低计算成本
2. **拓扑感知传播**：利用状态图的拓扑结构进行奖励分配
3. **状态级密集奖励**：为每个状态提供细粒度的奖励信号

## 实验结果

### 数据集
- ALFWorld：智能体感官任务
- WebShop：网页交互任务
- Sokoban：推箱任务
- 其它智能体推理基准

### 主要结果

![结果对比|600](images/result_overview.pdf)

![训练曲线|600](images/reward_flow_train_val_curve.pdf)

RewardFlow在四个智能体推理基准上显著优于之前的RL基线，展现出：
- 更好的性能
- 更好的鲁棒性
- 更高的训练效率

![效率对比|600](images/efficiency.pdf)

## 关键结果

RewardFlow作为密集奖励用于RL优化后，在四个智能体推理基准上显著优于之前的RL基线。

## 相关工作

- GRPO (Group Relative Policy Optimization)
- PPO (Proximal Policy Optimization)
- Process Reward Modeling

## 代码

实现代码已公开：https://github.com/tmlr-group/RewardFlow
