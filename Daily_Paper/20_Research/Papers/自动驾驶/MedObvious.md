---
date: "2026-03-25"
paper_id: "2603.23501"
title: "MedObvious: Exposing the Medical Moravec's Paradox in VLMs via Clinical Triage"
authors: "Ufaq Khan, Umair Nawaz, L D M S S Teja, Numaan Saeed, Muhammad Bilal, Yutong Xie, Mohammad Yaqub, Muhammad Haris Khan"
domain: "自动驾驶"
tags:
  - 论文笔记
  - 自动驾驶
  - VLM
  - 医疗AI
  - 医学影像
quality_score: "[待评估]/10"
related_papers: []
created: "2026-03-26"
updated: "2026-03-26"
status: analyzed
---

# MedObvious: Exposing the Medical Moravec's Paradox in VLMs via Clinical Triage

## 核心信息
- **论文ID**：2603.23501
- **作者**：Ufaq Khan, Umair Nawaz, L D M S S Teja, Numaan Saeed, Muhammad Bilal, Yutong Xie, Mohammad Yaqub, Muhammad Haris Khan
- **机构**：待确认
- **发布时间**：2026-03-25
- **链接**：[arXiv](https://arxiv.org/abs/2603.23501) | [PDF](https://arxiv.org/pdf/2603.23501)

## 研究问题

视觉语言模型（VLM）在医学报告生成和视觉问答等任务上表现流畅，但这是否意味着安全的视觉理解？在临床实践中，解释始于预诊断的合理性检查：验证图像是否与报告的解剖结构匹配。

## 方法概述

### MedObvious 基准

提出MedObvious，通过临床分诊揭示VLM中的医学Moravec悖论。

![主要方法|600](images/MedObvious-Main-Final.jpg)

### 核心发现

- 流利的诊断文本并不保证安全的视觉理解
- VLM在简单视觉理解任务上失败，但能生成复杂的医学报告
- 存在"聪明但愚笨"的问题

![医学影像对比|600](images/v4_chest_ct_vs_xray_6_grid.png)

## 实验结果

### 评估结果

- 测试多种VLM的视觉理解能力
- 发现VLM在医学影像理解上的显著差距

## 关键结果

- 揭示VLM中的医学Moravec悖论
- 呼吁在临床部署前进行严格的安全检查

## 相关工作

- Vision Language Models (VLM)
- Medical AI
- Moravec's Paradox

## 代码

代码和数据待公开。