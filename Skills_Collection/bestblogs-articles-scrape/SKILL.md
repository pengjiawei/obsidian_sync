---
name: bestblogs-articles-scrape
description: 从 bestblogs.dev 网站批量抓取优质文章列表并保存为Markdown文件。当用户想要抓取bestblogs.dev的文章列表、获取过去一周优质文章、批量保存多篇文章时使用此skill。
---

# Bestblogs.dev 文章批量抓取

这个 skill 帮助你从 bestblogs.dev 网站批量抓取优质文章，并生成格式良好的 Markdown 文件。

## 触发条件

当用户说：
- "抓取这个链接的所有文章"
- "帮我把bestblogs的文章都保存下来"
- "批量抓取bestblogs.dev的文章"
- 给了一个 bestblogs.dev 的文章列表 URL 并要求保存

## 工作流程

### 1. 获取文章列表页面

使用 Firecrawl Python SDK 抓取页面：
```python
from firecrawl import FirecrawlApp
app = FirecrawlApp(api_key='fc-365c821388cc4e039d4801d5996ecc04')
result = app.scrape('https://www.bestblogs.dev/articles?time=1w&qualified=true', wait_for=5000)
```

### 2. 分析页面结构

识别并提取：
- 文章标题
- 文章链接
- 来源网站
- 发布日期
- AI 评分
- 文章摘要

### 3. 批量抓取每篇文章

对于列表中的每篇文章，使用 Firecrawl 抓取完整内容：
```python
result = app.scrape(f'https://www.bestblogs.dev/article/{article_id}', wait_for=8000)
```

### 4. 生成 Markdown 文件

为每篇文章生成独立的 Markdown 文件，格式如下：
```markdown
---
title: [文章标题]
source: [来源]
date: [日期]
ai_score: [评分]
---

# [文章标题]

[文章内容...]
```

### 5. 生成汇总索引

创建 README.md 文件作为索引，包含：
- 所有文章的列表
- 核心主题分类
- 关键趋势洞察

**文件夹命名规范**：使用 `scraped/articles-YYYY-MM-DD-HH-MM/` 格式，如 `scraped/articles-2026-04-01-09-30/`

## 输出要求

1. **文件夹命名**：使用当前日期和时间，格式为 `scraped/articles-YYYY-MM-DD-HH-MM/`，如 `scraped/articles-2026-04-01-09-30/`
2. **文件位置**：保存在上述文件夹中的 `articles/` 子目录
3. **文件名**：使用编号+标题 slug 格式，如 `01-article-title.md`
4. **汇总文件**：创建 README.md 作为索引入口

## 错误处理

- 如果页面无法访问：明确告知用户错误信息
- 如果部分文章抓取失败：记录失败的文章，继续处理其他文章
- 完成后报告成功和失败的数量

## 注意事项

- 遵守网站的使用条款
- 合理控制请求频率
- 批量抓取后可以询问用户是否需要进一步处理

---

## 可选功能：生成文章深度解读

用户可能要求对抓取的文章进行深度分析，包括：
- 每篇文章的章节结构
- 一句话摘要
- 核心观点 (3-5条)
- 主题聚类
- 核心趋势总结

### 工作流程

1. **读取所有文章内容**：遍历 `articles/` 目录下的所有 Markdown 文件
2. **提取章节标题**：使用正则匹配 `^#{1,3}\s+` 提取各级标题
3. **提取文章正文**：跳过头部的导航和登录提示，获取正文内容
4. **使用 AI Agent 分析**：将文章内容发送给 Explore Agent 生成结构化摘要
5. **生成汇总文件**：创建 `articles-summary.md` 文件，包含：
   - 文章总览表格
   - 每篇文章的深度解读
   - 主题聚类
   - 核心趋势总结

### 输出格式

```markdown
# Bestblogs.dev 文章汇总 - 深度解读

## 📖 深度解读

### 01 | 文章标题

#### 章节结构
- 章节1
- 章节2

#### 一句话摘要
...

#### 核心观点
1. ...
2. ...

## 🔍 主题聚类

- AI Agent 工程
- 数据库与基础设施
- 大模型发布
- 开发者工具

## 💡 核心趋势总结
...
```

### 注意事项
- 批量分析时每批处理5篇文章，避免超时
- 保留所有原始 Markdown 文件
- 汇总文件命名：`articles-summary.md`