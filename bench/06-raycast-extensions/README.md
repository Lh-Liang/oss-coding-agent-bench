# Raycast Extensions

目标仓库：https://github.com/raycast/extensions

## 1. 任务要求、问题来源和建议方向

你要在 Raycast Extensions 中寻找一个真实、体验完整的扩展贡献点。Raycast 是 macOS 上的快捷启动器和生产力命令中心，扩展仓库通过 PR 接收社区扩展和已有扩展修复，审核后进入 Raycast Store。扩展通常由 TypeScript、React、Raycast API、metadata、图标和 README 组成。

你可以优先参考这些问题来源：

- 已有扩展 issue、PR review 或用户反馈中的 API 变更、空状态、错误状态、token 处理或 UI 问题。
- 某个已有扩展缺少 retry action、pagination、preferences、onboarding、截图或 README。
- 某个开发者工具或 SaaS 有稳定 API，但 Raycast Store 中缺少明确不重复的工作流。
- 本地 `npm run build`、`npm run lint`、Raycast validator 或手动运行命令暴露的问题。

建议修改方向：

- 优先修复已有扩展的小问题，补错误处理、加载状态、空结果、偏好设置或 API 字段更新。
- 新扩展要选择范围小、用户价值明确、非重复、可由 reviewer 测试的服务。
- 对 agent 系统，可以做任务队列管理、PR 打开、计划审批、CI 状态查询或代码审查摘要扩展。
- Raycast 是用户入口工具，命令名、描述、图标、ActionPanel 和空状态都要精致。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、扩展复现、API 文档、Store 缺口或同类扩展对比。
- 方案设计和影响范围，说明命令、认证、用户操作路径、数据读写和隐私影响。
- 代码或文档改动，包括扩展实现、metadata、图标、README、截图说明或测试。
- 测试和验证结果，例如 build、lint、validator、本地 Raycast 运行和截图。
- PR 标题和 PR 描述，说明扩展价值、测试账号需求、验证方式和权限。

最终目标：向 `raycast/extensions` 提交一个可运行、体验完整、能被 Store review 接受的 PR。
