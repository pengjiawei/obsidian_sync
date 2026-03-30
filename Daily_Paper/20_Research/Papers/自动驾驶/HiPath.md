---
date: "2026-03-20"
paper_id: "2603.19957"
title: "HiPath: Hierarchical Vision-Language Alignment for Structured Pathology Report Prediction"
authors: "Ruicheng Yuan, Zhenxuan Zhang, Anbang Wang, Liwei Hu, Xiangqian Hua, Yaya Peng, Jiawei Luo, Guang Yang"
domain: "自动驾驶"
tags:
  - 论文笔记
  - 自动驾驶
  - VLM
  - 医疗AI
  - 病理报告
quality_score: "[待评估]/10"
related_papers: []
created: "2026-03-23"
updated: "2026-03-23"
status: analyzed
---

# HiPath: Hierarchical Vision-Language Alignment for Structured Pathology Report Prediction

## 核心信息
- **论文ID**：2603.19957
- **作者**：Ruicheng Yuan, Zhenxuan Zhang, Anbang Wang, Liwei Hu, Xiangqian Hua, Yaya Peng, Jiawei Luo, Guang Yang
- **机构**：待确认
- **发布时间**：2026-03-20
- **链接**：[arXiv](https://arxiv.org/abs/2603.19957) | [PDF](https://arxiv.org/pdf/2603.19957)

## 研究问题

病理报告是结构化的多粒度文档，编码诊断结论、组织学分级和辅助检测结果。然而，现有的病理视觉语言模型（VLM）将这些输出简化为扁平标签或自由形式文本。

## 方法概述

### HiPath 框架

提出HiPath，一个轻量级的VLM框架，基于冻结的UNI2和Qwen3主干网络，将结构化报告预测作为主要训练目标。

![HiPath架构|600](images/architecture_page1.png)

### 三个可训练模块

三个可训练模块（共15M参数）解决问题的不同方面：

1. **Hierarchical Patch Aggregator (HiPA)**：用于多图像视觉编码
2. **Hierarchical Contrastive Learning (HiCL)**：通过最优传输进行跨模态对齐
3. **Slot-based Masked Diagnosis Prediction (Slot-MDP)**：用于结构化诊断生成

### 训练数据

在来自三家医院的749K真实世界中国病理病例上训练。

## 实验结果

### 性能表现

- 严格准确率：68.9%
- 临床可接受准确率：74.7%
- 安全率：97.3%

在相同冻结主干网络下优于所有基线。

### 跨医院评估

跨医院评估确认泛化性：
- 严格准确率仅下降3.4个百分点
- 保持97.1%安全率

## 关键结果

- 首个将结构化报告预测作为主要训练目标的病理VLM
- 15M参数实现高质量结构化病理报告生成
- 在真实世界病理数据上验证有效性

## 相关工作

- Vision-Language Models (VLM)
- Medical AI
- Pathology Report Generation

## 代码

代码和数据待公开。
