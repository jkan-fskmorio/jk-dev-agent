---
name: super-prd
description: Generate technical Product Requirements Documents (PRDs) for software systems. Supports dual-mode: quick synthesis from conversation context, or deep discovery through structured interview. Use when user wants to create a PRD, document requirements, plan a feature, or turn conversation context into a specification.
---

# Super PRD

## Mode Selection

Assess the conversation context before starting:

| Mode | Trigger | Behavior |
|------|---------|-----------|
| **Quick** | Context already rich with requirements, user stories, and technical decisions | Synthesize directly from context, no additional interview |
| **Deep** | Requirements are vague, missing key dimensions | Initiate structured discovery interview (1-3 rounds) |

Announce which mode you're using and why.

## Deep Mode: Discovery Interview

Ask across these dimensions, one round at a time. Stop when all dimensions are sufficiently clear (max 3 rounds).

1. **项目背景** — 核心问题？目标用户？使用场景？现有替代方案和痛点？
2. **功能范围** — Must-have 核心功能？Nice-to-have 辅助功能？明确的 Non-goals？
3. **技术约束** — 指定技术栈？现有系统集成？性能/安全/合规要求？
4. **成功指标** — 可量化的 KPI 或 OKR？

## PRD Template

Generate the PRD using the structure below. For detailed guidance on each section, tech stack recommendations, and examples, refer to `prd-expert-prompts.md`.

1. **背景** — 问题陈述、项目目标、成功指标（3-5 个可量化 KPI）、术语表
2. **用户故事** — 用户画像、故事列表（P0/P1/P2 优先级）、Gherkin 验收标准（含异常流和边界条件）、Non-Goals
3. **功能模块设计** — 模块划分、依赖关系、交互接口、可复用模块
4. **流程设计** — 业务流程图、数据流程图、核心功能流程图（Mermaid 或文字描述）
5. **技术选型** — 前端/后端/数据库/部署方案，每个选型附理由
6. **架构设计** — 系统架构图、组件交互、部署架构
7. **数据库设计** — 表结构（字段、类型、约束、关系）、索引策略、迁移方案
8. **API 设计** — 规范（RESTful/GraphQL）、端点清单（方法、路径、请求/响应）、认证授权
9. **前端和 UI 设计** — UI 风格、组件库规范、状态管理、响应式策略
10. **项目规范** — 代码规范、注释规范、Git 工作流、目录结构
11. **开发边界** — 禁止触碰的文件/模块、技术债务、未来扩展点
12. **参考技术文档** — 官方文档、最佳实践、相关 ADR

## Quality Standards

- 所有指标具体可量化，避免"快""好用""直观"等模糊词
- 用户故事遵循 INVEST 原则，验收标准使用 Gherkin 语法
- 技术选型有对比和理由，数据库设计含完整字段定义
- API 设计符合规范，架构图清晰展示交互和数据流

## Boundary Limits

- 不讨论商业化方向（定价、市场策略、盈利模式）
- 不直接修改代码文件，仅生成规范和示例
- 不访问生产环境或敏感配置
- 不生成具体业务逻辑代码，仅定义接口和规范

## Reference

完整技术栈推荐、5 阶段工作流详解、示例输出片段，参见配套 Prompt：`prd-expert-prompts.md`。