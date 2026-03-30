---
date: "2026-03-20"
paper_id: "2603.19852"
title: "Failure Modes for Deep Learning-Based Online Mapping: How to Measure and Address Them"
authors: "Michael Hubbertz, Qi Han, Tobias Meisen"
domain: "自动驾驶"
tags:
  - 论文笔记
  - 自动驾驶
  - 在线地图
  - 深度学习
  - 泛化
quality_score: "[待评估]/10"
related_papers: []
created: "2026-03-23"
updated: "2026-03-23"
status: analyzed
---

# Failure Modes for Deep Learning-Based Online Mapping: How to Measure and Address Them

## 核心信息
- **论文ID**：2603.19852
- **作者**：Michael Hubbertz, Qi Han, Tobias Meisen
- **机构**：待确认
- **发布时间**：2026-03-20
- **链接**：[arXiv](https://arxiv.org/abs/2603.19852) | [PDF](https://arxiv.org/pdf/2603.19852)

## 研究问题

基于深度学习的在线映射已成为自动驾驶的基石，但这些模型经常无法在熟悉的环境之外进行泛化。如何识别和测量潜在的失败模式？

## 方法概述

### 失败模式框架

提出一个框架，通过解耦两种效应来识别和测量潜在的失败模式：
1. 输入特征的记忆
2. 对已知地图几何的过拟合

### 评估子集

提出基于评估子集的措施，控制训练和验证场景之间的地理接近度和几何相似性。

![动机条形图|600](images/Motivation_bar_chart_v5_cropped.png)

### 指标

- 引入基于Fréchet距离的重建统计，捕获每个元素的形状保真度，无需阈值调优
- 定义互补的失败模式分数：
  - 定位过拟合分数：当地理线索消失时量化性能下降
  - 地图几何过拟合分数：当场景几何上新时测量退化

### 数据集贡献

除了模型，还分析数据集偏见，并贡献地图几何感知诊断：
- 训练集的最小生成树（MST）多样性度量
- 对称覆盖度量，量化分割之间的几何相似性

![拓扑可视化|600](images/sim_topo_vis_v2.png)

## 实验结果

### 基准

在nuScenes和Argoverse 2上评估多种最先进模型。

### 主要发现

- 更值得信赖的泛化评估
- 地图几何多样且平衡的训练集带来更好的性能

## 关键结果

- 揭示深度学习在线映射的失败模式
- 地图几何感知的数据集设计对可部署在线映射至关重要
- MST-based稀疏化策略减少冗余同时改善平衡和性能

## 相关工作

- Deep Learning
- Online Mapping
- Autonomous Driving
- Generalization

## 代码

代码和数据待公开。
