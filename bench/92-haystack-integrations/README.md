# Haystack Integrations

目标仓库：https://github.com/deepset-ai/haystack-integrations

## 1. 任务要求、问题来源和建议方向

你要在 Haystack Integrations 中寻找一个真实 integration 贡献点。Haystack 是用于构建 RAG、agent、语义搜索、问答、文档处理和生产级 LLM pipeline 的开源框架。Integrations 仓库帮助用户发现可用于 Haystack Pipeline 或 Agent 的外部组件、包和服务。

你可以优先参考这些问题来源：

- issue、PR review、integration index 或 docs 中的链接失效、示例不可运行、安装说明缺失或组件列表不准确。
- 某个 Haystack component package 已存在，但还没有被 integrations index 收录。
- 已有 integration 缺少 runnable examples、pipeline 示例、license、维护者信息或 issue 链接。
- 本地 pip install、example 运行、pipeline 测试或 README 链接检查暴露的问题。

建议修改方向：

- 优先补已有 integration 的文档、可运行示例、metadata、logo、license 或兼容性说明。
- 新 integration 要先确保独立 package 能安装、示例能运行，并符合 Haystack component API。
- 对 agent 系统，可以做 GitHub/Linear/Sentry tool、开发知识库 retriever、document store 或 evaluation component。
- 涉及写操作的 tool 要说明副作用、认证、权限和人工确认边界。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、docs 缺口、安装失败、示例失败或同类 integration 对比。
- 方案设计和影响范围，说明 component 类型、安装方式、pipeline 示例、认证、license 和维护边界。
- 文档或代码改动，包括 integration 条目、README、examples、metadata、logo 或 package 修复。
- 测试和验证结果，例如 pip install、example 运行、pipeline 测试、链接检查或版本兼容说明。
- PR 标题和 PR 描述，说明 integration 名、用户价值、验证方式和维护信息。

最终目标：提交一个能让 Haystack 用户可靠发现并使用 integration 的 PR。
