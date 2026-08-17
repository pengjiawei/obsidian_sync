---
type: source
title: book1-claude-code
created: 2026-07-13
updated: 2026-07-13
tags: [ai-agent, system-prompt, claude-code, software-engineering, prompt-engineering]
related: [claude-code, control-plane, context-governance, skill-as-institutional-slice, ai-agent-error-handling]
authors: []
year: 2026
url: "https://weread.qq.com/web/reader/4a742f33643425f47347a345558345658415254373274373146365a4a385250716"
venue: "微信读书"
sources: ["book1-claude-code.md"]
---
# book1-claude-code

本文档是对Claude Code系统架构和设计哲学的深度剖析笔记。其核心论点是：对于具备复杂执行能力的AI代理系统，其System Prompt的根本作用是定义系统的“控制平面”（即行为规则、协议和责任边界），而非塑造“人格”。

文档通过分析Claude Code的源码实现（如`compact.ts`、`claudemd.ts`、`SkillTool`等），提炼出多个关键设计理念和工程实践，包括：

1.  **Prompt作为宪法**：将Prompt视为规定系统权力边界、责任关系和异常处理的“运行时协议”，而非角色扮演的台词。
2.  **控制平面的分层构建**：CLAUDE.md、memory、MCP instructions等组件共同构成完整的行为控制层。
3.  **上下文治理**：在上下文压缩时，优先保留维持“工作语义”（当前任务、计划、关键约束）的信息，而非信息量最大的内容。
4.  **Skill作为可复用的制度切片**：将任务知识、工具边界、工作流和验证要求封装成可稳定调用的自动化单元，是团队知识制度化的关键。
5.  **错误处理的工程原则**：旨在维护“执行叙事的一致性”，包括分层恢复、防止自我回环、熔断机制、续写而非总结等。
6.  **团队落地的关键**：在于将个人经验硬化为分层规则、可执行Skill、审批边界和可复盘的生命周期轨迹。

这些发现共同指向一个核心实践：如何通过制度化的设计，构建可靠、可管理、可团队协作的AI代理系统。