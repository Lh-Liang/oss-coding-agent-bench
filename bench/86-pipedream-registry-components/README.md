# Pipedream Registry Components

目标仓库：https://github.com/PipedreamHQ/pipedream

## 1. 任务要求、问题来源和建议方向

你要在 Pipedream Registry Components 中寻找一个真实 integration 贡献点。Pipedream 是开发者自动化平台，Registry 维护各个 app 的 sources 和 actions。source 监听 webhook、轮询事件或定时触发；action 作为 workflow 步骤调用外部 API 或处理数据。

你可以优先参考这些问题来源：

- issue、PR review、component 目录或用户反馈中的 auth、pagination、dedupe、webhook lifecycle、props 文案问题。
- 某个 app API 有常用 endpoint，但 Pipedream 缺少对应 action 或 source。
- 同类 app 已有 create/update/search/list actions，而目标 app 缺少自然补齐。
- 本地组件测试、lint、sample output、props 校验或错误分支暴露的问题。

建议修改方向：

- 优先给已有 app 补高频、低风险、文档明确的 action 或 source。
- 修复已有 component 的 props、auth scope、pagination、dedupe、error message 或 sample data。
- 对 agent 系统，可以做 summarize、classify、create task、review PR、release notes 等 action。
- 默认避免删除、转账、批量通知等高风险写操作，必要时加入明确参数和说明。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 API 文档、issue、组件运行失败或同类 action/source 对比。
- 方案设计和影响范围，说明 app、component 类型、props、auth、pagination、dedupe 和副作用。
- 代码或文档改动，包括 source/action component、app metadata、sample data、tests 或 README。
- 测试和验证结果，例如本地组件测试、lint、示例调用、mock 验证和 secret 检查。
- PR 标题和 PR 描述，说明 app 名、组件能力、验证方式和权限影响。

最终目标：提交一个可被 Pipedream 团队 review 并合并的 component PR。
