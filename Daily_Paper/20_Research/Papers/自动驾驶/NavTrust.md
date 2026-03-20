---
date: "2026-03-19"
paper_id: "2603.19229"
title: "NavTrust: Benchmarking Trustworthiness for Embodied Navigation"
authors: "Huaide Jiang, Yash Chaudhary, Yuping Wang, Zehao Wang, Raghav Sharma, Manan Mehta, Yang Zhou, Lichao Sun, Zhiwen Fan, Zhengzhong Tu, Jiachen Li"
domain: "自动驾驶"
tags:
  - 论文笔记
  - 自动驾驶
  - 具身智能
  - 导航
  - 基准测试
quality_score: "[待评估]/10"
related_papers: []
created: "2026-03-20"
updated: "2026-03-20"
status: analyzed
---

# NavTrust: Benchmarking Trustworthiness for Embodied Navigation

## 核心信息
- **论文ID**：2603.19229
- **作者**：Huaide Jiang, Yash Chaudhary, Yuping Wang, Zehao Wang, Raghav Sharma, Manan Mehta, Yang Zhou, Lichao Sun, Zhiwen Fan, Zhengzhong Tu, Jiachen Li
- **机构**：卡内基梅隆大学、字节跳动等
- **发布时间**：2026-03-19
- **链接**：[arXiv](https://arxiv.org/abs/2603.19229) | [PDF](https://arxiv.org/pdf/2603.19229)

## 研究问题

现有工作主要在名义条件下评估模型性能，忽略了现实世界中可能出现的腐败问题。如何系统地评估具身导航代理在真实场景下的鲁棒性？

## 方法概述

### NavTrust 基准

提出NavTrust，一个统一基准，系统性地腐蚀输入模态（包括RGB、深度和指令），在现实场景中评估其对导航性能的影响。

![NavTrust概览|600](images/NavTrust_fig1_page1.png)

### 腐蚀类型

- **RGB-Depth腐蚀**：多种真实世界的图像/深度退化
- **指令变化**：自然语言指令的变异

### 评估方法

评估7种最先进方法，揭示：
- 在现实腐蚀下显著的性能下降
- 关键鲁棒性差距

### 缓解策略

系统评估四种不同的缓解策略，以增强对RGB-Depth和指令腐蚀的鲁棒性。

![缓解方法|600](images/NavTrust_mitigation_method_page1.png)

## 实验结果

### 基准模型

- Uni-NaVid
- ETPNav

### 关键发现

- 在真实腐败下性能显著下降
- 揭示关键鲁棒性差距
- 真实机器人部署显示改善的鲁棒性

## 关键结果

- NavTrust是首个在统一框架中暴露具身导航代理于多样化RGB-Depth腐蚀和指令变化的基准
- 为更可信的具身导航系统提供路线图

## 相关工作

- Vision-Language Navigation (VLN)
- Object-Goal Navigation (OGN)
- Robustness Benchmarking

## 代码

项目网站：https://navtrust.github.io
