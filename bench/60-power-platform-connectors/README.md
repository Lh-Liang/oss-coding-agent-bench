# Microsoft Power Platform Connectors

目标仓库：https://github.com/microsoft/PowerPlatformConnectors

## 1. 任务要求、问题来源和建议方向

你要在 Power Platform Connectors 中寻找一个真实 connector 贡献点。这个仓库维护 Power Automate、Power Apps 和 Azure Logic Apps 使用的 connector definitions，包括 OpenAPI、apiProperties、icons、policies 和认证配置。用户会在低代码流程中直接使用这些 action 和 trigger。

你可以优先参考这些问题来源：

- 仓库 issue、PR review、connector validation 或用户反馈中的 OpenAPI、认证、pagination、trigger/action、schema 问题。
- 某个已有 connector 的 operation 描述、参数、响应 schema、示例、icon、policy 或 docs 不完整。
- 目标 API 已有新 endpoint、字段或分页方式，但 connector 尚未支持。
- 本地 paconn/validation、Power Platform 自定义 connector 测试或 OpenAPI lint 暴露的问题。

建议修改方向：

- 优先修复已有 connector 的 schema、参数描述、响应、pagination、错误说明或 docs。
- 新 connector 前要确认 API 稳定、公开文档明确、认证方式可支持，并选择 certified 或 independent publisher 路径。
- 对 agent 系统，可以做摘要、分类、代码审查、任务生成、PR 状态查询等低风险 actions。
- 权限 scope 要最小化，写操作和企业数据出境要说明清楚。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、API 文档、connector bug、validation 失败或同类 connector 对比。
- 方案设计和影响范围，说明 connector、operation、auth、policy、schema 和权限影响。
- 配置或文档改动，包括 OpenAPI、apiProperties、icon、policy、README 或示例。
- 测试和验证结果，例如 connector validation、OpenAPI lint、自定义 connector 运行或手动验证说明。
- PR 标题和 PR 描述，包含 connector 名、操作、验证方式、权限和数据风险。

最终目标：向 `microsoft/PowerPlatformConnectors` 提交一个可通过 review 的 connector PR。
