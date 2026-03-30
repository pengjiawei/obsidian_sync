---
date: "2026-03-25"
paper_id: "2603.23405"
title: "Planning over MAPF Agent Dependencies via Multi-Dependency PIBT"
authors: "Zixiang Jiang, Yulun Zhang, Rishi Veerapaneni, Jiaoyang Li"
domain: "智能体"
tags:
  - 论文笔记
  - 智能体
  - 多智能体路径规划
  - MAPF
  - 规划算法
quality_score: "[待评估]/10"
related_papers: []
created: "2026-03-26"
updated: "2026-03-26"
status: analyzed
---

# Planning over MAPF Agent Dependencies via Multi-Dependency PIBT

## 核心信息
- **论文ID**：2603.23405
- **作者**：Zixiang Jiang, Yulun Zhang, Rishi Veerapaneni, Jiaoyang Li
- **机构**：待确认
- **发布时间**：2026-03-25
- **链接**：[arXiv](https://arxiv.org/abs/2603.23405) | [PDF](https://arxiv.org/pdf/2603.23405)

## 研究问题

现代多智能体路径规划（MAPF）算法需要在拥挤环境中为数百到数千个智能体在1秒内进行规划，如何提高效率？

## 方法概述

### Multi-Dependency PIBT

提出Multi-Dependency Priority Inheritance with Backtracking (MD-PIBT)算法。

![MAPF大规模问题|600](images/mapf-large_page1.png)

### 核心贡献

- 处理多个智能体依赖关系
- 扩展Priority Inheritance with Backtracking (PIBT)
- 高效处理拥挤环境中的大规模智能体

## 实验结果

### 性能评估

在多种场景（random, room, warehouse, Paris）上评估：
- 运行时间
- 吞吐量
- 成功率

![运行时性能|600](images/runtime_agent_num_w_random-32-32-20_page1.png)

## 关键结果

- 在大规模MAPF问题上展示高效性
- 能够有效规划数百到数千个智能体

## 相关工作

- Multi-Agent Path Finding (MAPF)
- Priority Inheritance with Backtracking (PIBT)
- Multi-Agent Planning

## 代码

代码和数据待公开。