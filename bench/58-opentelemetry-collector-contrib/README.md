# OpenTelemetry Collector Contrib

目标仓库：https://github.com/open-telemetry/opentelemetry-collector-contrib

## 1. 任务要求、问题来源和建议方向

你要在 OpenTelemetry Collector Contrib 中寻找一个真实贡献点。OpenTelemetry 是云原生可观测性标准，Collector Contrib 收录大量 receiver、processor、exporter、connector 和 extension。组件负责接收、处理、转换和转发 traces、metrics、logs，是很多平台集成的基础。

你可以优先参考这些问题来源：

- contrib issue、component owner review、CI 失败、mdatagen、配置验证或文档缺口。
- 某个已有 receiver/exporter/processor 缺少 logs 支持、配置校验、错误处理、测试或 README 示例。
- 某个开发平台、SaaS 或 agent 系统的遥测事件可以转成标准 OTLP，但缺少组件。
- 本地 Go test、lint、config validation、race 风险或 benchmark 暴露的问题。

建议修改方向：

- 优先给已有组件补文档、测试、配置验证、错误处理、metadata 或小功能。
- 新组件要先确认适合进入 contrib，并说明维护者、用户需求和稳定性计划。
- 对 agent 系统，可以做 telemetry receiver/exporter，或 processor 用于敏感字段脱敏、LLM 成本聚合、错误分类。
- 注意性能、内存、backpressure、并发安全和敏感数据处理。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、测试失败、配置缺口、遥测场景或维护者讨论。
- 方案设计和影响范围，说明 component 类型、配置、lifecycle、数据模型和性能影响。
- 代码或文档改动，包括 Go 代码、metadata、tests、README、examples、changelog 或 docs。
- 测试和验证结果，例如 Go test、lint、mdatagen、config validation、benchmark 或 race 风险检查。
- PR 标题和 PR 描述，说明组件价值、验证方式、稳定性和维护边界。

最终目标：提交一个符合 Collector Contrib 规范、能通过 component owner review 的 PR。
