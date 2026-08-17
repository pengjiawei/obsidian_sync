---
type: entity
title: Claude Code
created: 2026-07-13
updated: 2026-07-13
tags: [ai-agent, tool, anthropic]
related: [control-plane, context-governance, skill-as-institutional-slice, ai-agent-error-handling]
sources: ["book1-claude-code.md"]
---
# Claude Code

Claude Code是由Anthropic开发的一个AI代理系统（AI agent system）。它超越了简单的聊天机器人，具备文件操作、工具调用、shell命令执行、权限处理和多步任务执行等复杂能力。

根据 `book1-claude-code` 的分析，其架构的核心特点是**“控制平面”的设计**：

1.  **Prompt的本质**：其System Prompt被设计为一套“运行时协议”或“宪法”，而非静态的角色设定文本。它定义了系统“能做什么、什么时候做、做错了怎么办”。
2.  **分层控制架构**：控制平面由分层拼装的Prompt区块、`CLAUDE.md`（用于注入团队规则）、memory、MCP instructions等组件共同构成。
3.  **上下文治理**：在压缩或截断上下文时，遵循“保留工作语义”的原则，优先保证当前任务执行的关键信息得以延续。
4.  **制度化执行单元（Skill）**：其`SkillTool`机制将特定任务的知识、工具边界、工作流和验证要求封装成可稳定调用的“制度切片”，用于团队知识的自动化复用。
5.  **鲁棒性设计**：错误处理机制强调维护“执行叙事的一致性”，通过分层恢复、熔断等手段确保系统可解释、可恢复。

这些设计使得Claude Code成为一个可管理、可审计、适合团队协作的复杂代理系统范例。