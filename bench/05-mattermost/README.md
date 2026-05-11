# Mattermost Plugins

目标仓库：https://github.com/mattermost/mattermost

## 1. 任务要求、问题来源和建议方向

你要在 Mattermost 主仓库或插件生态中寻找一个真实贡献点。Mattermost 是开源团队协作和 ChatOps 平台，常用于企业自托管聊天、告警协作、发布审批和开发流程集成。插件可以扩展 Go 后端、React Web App、slash command、bot、webhook、配置页和交互按钮。

你可以优先参考这些问题来源：

- Mattermost 仓库 issue、插件 API issue、已有插件 PR 中的 bug、兼容性问题、配置或文档缺口。
- 某个插件的 `plugin.json`、权限、生命周期 hook、slash command、前端 UI 或配置页行为不完整。
- 团队协作和 ChatOps 场景中已有用户需求，例如 CI 失败总结、PR 状态通知、incident 流程。
- 本地 build、lint、manifest 校验、插件安装或命令调用暴露出的错误。

建议修改方向：

- 优先给已有插件或主仓库插件 API 相关问题做小修复、测试和文档改进。
- 新插件应围绕明确工作流，例如 `/agent` 命令、PR/CI 状态摘要、告警解释或审批流程。
- 对 agent 系统，要清楚区分只读查询和写操作，避免在频道中泄露 token、日志或敏感代码。
- 注意集群部署、高可用和权限模型，不要依赖单机本地状态。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、复现步骤、插件 API 文档或用户工作流证据。
- 方案设计和影响范围，说明 server、webapp、manifest、权限、配置和兼容版本。
- 代码或文档改动，包括 Go、TypeScript/React、plugin manifest、README、测试或示例。
- 测试和验证结果，例如 build、lint、单元测试、插件本地安装和 slash command 验证。
- PR 标题和 PR 描述，说明工作流价值、验证方式、安全影响和回滚风险。

最终目标：提交一个能改善 Mattermost 协作或插件生态的 PR，并让维护者愿意接受。
