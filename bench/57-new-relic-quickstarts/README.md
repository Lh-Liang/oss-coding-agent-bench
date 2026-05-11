# New Relic Quickstarts / Integrations

目标仓库：https://github.com/newrelic/newrelic-quickstarts

## 1. 任务要求、问题来源和建议方向

你要在 New Relic Quickstarts 中寻找一个真实贡献点。New Relic 是可观测性平台，Quickstarts 是 Instant Observability 目录中的可安装方案，通常为某个技术栈、服务或开源工具提供 dashboard、alerts、NRQL 查询、install plan、metadata 和文档。

你可以优先参考这些问题来源：

- quickstarts 仓库 issue、PR review、schema 校验、链接检查或 dashboard 查询失败。
- 某个已有 quickstart 的 NRQL、alert 默认阈值、截图、图标、README 或安装说明过期。
- 某个开源工具、队列、worker、CI/CD 或 agent 系统有明确可观测性需求但缺少 quickstart。
- 本地 schema 校验、链接检查、NRQL 审查或真实数据验证发现的问题。

建议修改方向：

- 优先修复已有 quickstart 的 broken link、查询错误、metadata、截图或 alert 条件。
- 新 quickstart 要围绕有真实数据模型的服务，避免只有空 dashboard。
- 对 agent 系统，可以展示任务量、失败率、延迟、模型调用成本、审查通过率和安全事件。
- 默认告警阈值要保守，避免给用户制造噪声。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、schema 失败、数据模型、监控缺口或用户场景。
- 方案设计和影响范围，说明 quickstart metadata、dashboard、alerts、NRQL 和安装方式。
- 配置或文档改动，包括 YAML/JSON、dashboard、alerts、docs、icon 或 screenshots。
- 测试和验证结果，例如 schema 校验、链接检查、NRQL 审查、真实/样例数据验证和截图检查。
- PR 标题和 PR 描述，说明 quickstart 价值、数据要求、验证方式和 alert 风险。

最终目标：提交一个能被 New Relic review 接受、帮助用户快速获得可观测性的 PR。
