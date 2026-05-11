# Grafana Plugins

目标仓库：https://github.com/grafana/grafana

## 1. 任务要求、问题来源和建议方向

你要围绕 Grafana 或 Grafana 插件生态寻找一个真实贡献点。Grafana 是可观测性和数据可视化平台，用于展示 metrics、logs、traces、alerts 和业务数据。插件生态包括 data source、panel 和 app plugin，可以把外部系统接入 Grafana 或提供新的可视化方式。这个 benchmark 更关注能通过 GitHub PR 被维护者认可的改动，例如核心仓库 issue、插件工具、示例仓库或已有插件修复。

你可以优先参考这些问题来源：

- Grafana 仓库 issue、插件工具 issue、示例插件问题或近期 PR review 中的 bug 和文档缺口。
- 已有 data source 或示例缺少认证、分页、health check、错误状态、测试或 README 说明。
- 同类可观测性工具已有某个数据接入或面板能力，而 Grafana 示例或插件缺少自然补齐。
- 本地运行插件 build、typecheck、test 或 validator 时暴露的问题。

建议修改方向：

- 优先修复 Grafana 主仓库、plugin tools 或 examples 中的小型 bug、测试缺口和文档缺口。
- 如果开发独立插件，要选择 API 稳定、用户价值明确、范围小的数据源或面板。
- 对 agent 系统，可以做 agent run log、token usage、eval result、CI 状态或任务队列的数据源插件。
- 注意凭据安全，secret 不应暴露到前端，后端代理要处理超时、TLS、日志和健康检查。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、插件验证失败、用户场景或同类功能对比。
- 方案设计和影响范围，说明插件类型、查询模型、配置、认证和 UI 行为。
- 代码或文档改动，包括 TypeScript/React、Go 后端、README、示例或测试。
- 测试和验证结果，例如 build、lint、test、plugin validator 或本地 Grafana 运行结果。
- PR 标题和 PR 描述，说明用户价值、验证方式、截图需求和安全影响。

最终目标：提交一个能提升 Grafana 插件生态质量或核心项目体验的 PR，并让维护者认为它值得接收。
