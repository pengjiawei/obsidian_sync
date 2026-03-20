---
date: "2026-03-19"
paper_id: "2603.19008"
title: "Hypothesis-Conditioned Query Rewriting for Decision-Useful Retrieval"
authors: "Hangeol Chang, Changsun Lee, Seungjoon Rho, Junho Yeo, Jong Chul Ye"
domain: "大模型"
tags:
  - 论文笔记
  - 大模型
  - LLM
  - RAG
  - 信息检索
quality_score: "[待评估]/10"
related_papers: []
created: "2026-03-20"
updated: "2026-03-20"
status: analyzed
---

# Hypothesis-Conditioned Query Rewriting for Decision-Useful Retrieval

## 核心信息
- **论文ID**：2603.19008
- **作者**：Hangeol Chang, Changsun Lee, Seungjoon Rho, Junho Yeo, Jong Chul Ye
- **机构**：韩国科学技术院（KAIST）
- **发布时间**：2026-03-19
- **链接**：[arXiv](https://arxiv.org/abs/2603.19008) | [PDF](https://arxiv.org/pdf/2603.19008)

## 研究问题

当任务需要在竞争选项中进行选择时，简单地将生成接地到广泛相关的上下文通常不足以驱动最终决策。现有RAG方法通常依赖单一初始查询，这往往偏向主题相关性而非决策相关证据。

## 方法概述

### HCQR 框架

提出Hypothesis-Conditioned Query Rewriting (HCQR)，一个无需训练的预检索框架，将RAG从主题导向检索重新定向为证据导向检索。

![HCQR框架|600](images/main_figure_page1.png)

### 工作原理

1. **假设推导**：从输入问题和候选选项中推导轻量级工作假设
2. **查询重写**：将检索重写为三个针对性查询，寻求证据来：
   - (1) 支持假设
   - (2) 从竞争替代方案中区分
   - (3) 验证问题中的显著线索

### 优势

- 使上下文检索与答案选择更直接对齐
- 允许生成器根据检索到的证据确认或推翻初始假设

## 实验结果

### 数据集

- MedQA
- MMLU-Med

### 主要结果

HCQR始终优于单查询RAG和重新排序/过滤基线：
- MedQA：比Simple RAG平均准确率提高5.9分
- MMLU-Med：比Simple RAG平均准确率提高3.6分

## 关键结果

- 为需要决策的RAG任务提供了新的检索范式
- 证据导向检索比主题导向检索更有效

## 相关工作

- Retrieval-Augmented Generation (RAG)
- Query Rewriting
- Decision-Making in NLP

## 代码

代码可用：https://anonymous.4open.science/r/HCQR-1C2E
