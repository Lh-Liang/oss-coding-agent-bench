# LlamaIndex Integrations

目标仓库：https://github.com/run-llama/llama_index

## 1. 任务要求、问题来源和建议方向

你要在 LlamaIndex 中寻找一个真实 integration 贡献点。LlamaIndex 是面向 LLM 应用、RAG、agent 和数据连接的开源框架，提供 readers、tools、retrievers、vector stores、LLM providers、embedding models、packs、observability 和 workflows。很多 integration 位于主仓库相关包目录中。

你可以优先参考这些问题来源：

- issue、discussion、PR review 或 docs 中提到的 integration bug、API 变化、metadata 缺失、async/streaming 问题。
- 某个开发工具、数据源、vector store 或 LLM provider API 稳定，但 LlamaIndex integration 缺少。
- 已有 integration 缺少 README、examples、tests、metadata、typing、mock 或错误处理。
- 本地 pytest、README 示例、mock 外部服务或依赖检查暴露的问题。

建议修改方向：

- 优先修复已有 integration 的认证、分页、metadata、async、error handling、docs 或 tests。
- 新 integration 要选择用户需求明确、API 文档清楚、依赖轻量的 reader、tool 或 retriever。
- 对 agent 系统，可以贡献 GitHub/Linear/Sentry/CI 数据 reader，或创建 issue、总结 PR、解释 CI 的 tool。
- 写操作 tool 要默认保守，README 中说明副作用、认证和确认机制。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、API 文档、docs 缺口、同类 integration 对比或测试失败。
- 方案设计和影响范围，说明 integration 类型、输入输出、依赖、认证、错误处理和副作用。
- 代码或文档改动，包括 package 代码、README、examples、metadata 和 tests。
- 测试和验证结果，例如 pytest、typing/lint、README 示例运行或 mock API 测试。
- PR 标题和 PR 描述，说明 integration 名、使用场景、验证方式和维护风险。

最终目标：提交一个符合 LlamaIndex integration 规范、能被维护者接受的 PR。
