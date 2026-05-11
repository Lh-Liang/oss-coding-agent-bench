# Airbyte Connectors

目标仓库：https://github.com/airbytehq/airbyte

## 1. 任务要求、问题来源和建议方向

你要在 Airbyte 中寻找一个真实 connector 贡献点。Airbyte 是开源数据集成平台，用 source 和 destination connectors 把 API、数据库、文件、SaaS、消息队列等数据同步到数据仓库、数据湖或其他系统。connector 需要处理认证、schema discovery、分页、增量同步、状态管理和错误恢复。

你可以优先参考这些问题来源：

- issue、connector catalog、PR review 或用户报告中的 sync failure、schema mismatch、pagination、rate limit 或 incremental sync 问题。
- 目标 SaaS API 新增 region、endpoint、字段或认证方式，但 connector 尚未支持。
- 某个 connector 缺少 acceptance tests、metadata、sample config、README、changelog 或错误处理。
- 本地 connector acceptance tests、unit tests、manifest 校验或 CDK 代码阅读暴露的问题。

建议修改方向：

- 优先修复已有 connector 的 API 变更、分页、增量状态、schema、错误处理或文档。
- 为低覆盖 connector 补 acceptance tests、unit tests、sample config 和 README。
- 新 connector 要选择 API 文档清楚、认证可测试、数据模型稳定的服务。
- 对 agent 系统，可以做 GitHub、CI、issue、incident、客服反馈或 agent telemetry source connector。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、API 文档、失败日志、connector 对比或可复现测试。
- 方案设计和影响范围，说明 connector、stream、schema、state、auth、分页和兼容性。
- 代码或配置改动，包括 manifest/CDK 代码、schemas、metadata、README、changelog 和 tests。
- 测试和验证结果，例如 connector acceptance tests、unit tests、format/lint 或手动 sync。
- PR 标题和 PR 描述，包含 connector 名、问题、方案、验证和数据安全说明。

最终目标：提交一个能通过 Airbyte connector review 和 CI 的 PR。
