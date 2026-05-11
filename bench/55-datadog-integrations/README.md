# Datadog Integrations / Marketplace

目标仓库：https://github.com/DataDog/integrations-extras

## 1. 任务要求、问题来源和建议方向

你要在 Datadog community integrations 中寻找一个真实贡献点。Datadog 用于收集 metrics、logs、traces、events、安全信号和用户体验数据。`integrations-extras` 接收社区集成，通常包含 Agent check、manifest、metadata、dashboard、monitor、README、测试和示例环境。

你可以优先参考这些问题来源：

- integrations-extras issue、PR review、CI 失败中的 manifest、metric metadata、测试、README 或 dashboard 问题。
- 某个 community integration 缺少 monitor templates、sample data、错误处理、认证失败处理或文档示例。
- 开源服务、开发工具、队列、API 网关或 agent 系统缺少 Datadog 可观测性集成。
- 本地测试、manifest 校验、metric metadata 校验或 docker compose 模拟环境暴露的问题。

建议修改方向：

- 优先给已有集成补测试、dashboard、monitor、README、指标 metadata 或错误处理。
- 新集成要设计克制的指标和 tags，避免高基数、成本不可控或过重的 Agent check。
- 对 agent 系统，可以暴露任务队列、运行耗时、失败原因、模型调用量、PR 成功率和审查反馈。
- Agent check 运行在客户环境，必须轻量、稳定、可诊断，并安全处理凭据。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、CI 失败、监控缺口、目标服务 API 或用户场景。
- 方案设计和影响范围，说明指标、tags、service checks、dashboard、认证和运行环境。
- 代码或文档改动，包括 check、manifest、metadata、dashboard、monitor、README 和 tests。
- 测试和验证结果，例如 manifest 校验、unit tests、sample data、docker 环境和 tag 高基数检查。
- PR 标题和 PR 描述，说明集成价值、验证方式、数据流和凭据安全。

最终目标：提交一个能通过 Datadog community integration review、真正提升观测能力的 PR。
