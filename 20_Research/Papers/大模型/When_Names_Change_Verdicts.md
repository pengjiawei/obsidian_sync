---
date: "2026-03-19"
paper_id: "2603.18530"
title: "When Names Change Verdicts: Intervention Consistency Reveals Systematic Bias in LLM Decision-Making"
authors: "Abhinaba Basu, Pavan Chakraborty"
domain: "大模型"
tags:
  - 论文笔记
  - 大模型
  - LLM
  - 偏见检测
  - AI安全
quality_score: "[待评估]/10"
related_papers: []
created: "2026-03-20"
updated: "2026-03-20"
status: analyzed
---

# When Names Change Verdicts: Intervention Consistency Reveals Systematic Bias in LLM Decision-Making

## 核心信息
- **论文ID**：2603.18530
- **作者**：Abhinaba Basu, Pavan Chakraborty
- **机构**：印度统计研究所
- **发布时间**：2026-03-19
- **链接**：[arXiv](https://arxiv.org/abs/2603.18530) | [PDF](https://arxiv.org/pdf/2603.18530)

## 研究问题

LLM在高风险决策中的表现如何？它们是否受到虚假特征（如人口统计特征、权威特征、框架特征）的影响？

## 方法概述

### ICE-Guard 框架

提出ICE-Guard框架，应用干预一致性测试来检测三类虚假特征依赖：

1. **人口统计特征**（Demographic）：姓名/种族交换
2. **权威特征**（Authority）：资质/声望交换
3. **框架特征**（Framing）：正面/负面重述

### 实验设置

- 3000个场景，涵盖10个高风险领域
- 评估11个LLM，来自8个模型家族

### 结构化分解

![结构化分解对比|600](images/fig_structured_comparison_page1.png)

当LLM提取特征而确定性规则决定结果时，可以显著减少翻转率。

## 实验结果

### 主要发现

1. **权威偏见**（平均5.8%）和**框架偏见**（5.0%）显著超过**人口统计偏见**（2.2%）
2. 偏见集中在特定领域：
   - 金融领域显示22.6%权威偏见
   - 犯罪司法领域仅2.8%

![领域偏见分布|600](images/fig_domain_bias_page1.png)

### 偏见减少效果

- 结构化分解可将翻转率降低最多100%（9个模型的中位数49%）
- ICE引导的"检测-诊断-缓解-验证"循环通过迭代提示修补实现累计78%的偏见减少

### 真实数据验证

在真实COMPAS累犯数据上的验证显示，COMPAS导出的翻转率超过综合合成率，说明该基准提供了对现实世界偏见的保守估计。

## 关键结果

- 权威偏见和框架偏见是LLM决策中的主要问题
- 金融领域是偏见最严重的领域
- 结构化分解是减少偏见的有力方法

## 相关工作

- 干预一致性测试 (Intervention Consistency Testing)
- LLM偏见检测
- 提示工程 (Prompt Engineering)

## 代码

代码和数据已公开可用。
