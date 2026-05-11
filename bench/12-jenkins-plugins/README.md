# Jenkins Plugins

目标仓库：https://github.com/jenkinsci/jenkins

## 1. 任务要求、问题来源和建议方向

你要围绕 Jenkins 主仓库或插件生态寻找一个真实贡献点。Jenkins 是开源 CI/CD 自动化服务器，插件生态负责接入 SCM、云平台、凭据、通知、测试报告、制品库和各种流水线能力。虽然插件分散在 `jenkinsci` 组织下多个仓库，这个 benchmark 以 Jenkins 代表仓库和插件开发流程为入口。

你可以优先参考这些问题来源：

- Jenkins core、插件开发文档或已有插件 issue 中的 bug、Pipeline 兼容、Java 版本、依赖升级或测试缺口。
- 某个插件缺少 Pipeline step 示例、JenkinsRule 测试、表单校验、权限检查或凭据处理。
- 构建失败、测试报告、ChatOps、部署审批等 CI/CD 场景中已有明确用户需求。
- 本地 Maven test、JenkinsRule、SpotBugs、Checkstyle 或插件安装验证暴露的问题。

建议修改方向：

- 优先给已有插件或 core 中插件 API 相关问题做小修复、测试和文档。
- 新插件要先确认没有重复，并说明长期维护计划；更稳的做法是先在个人仓库验证。
- 对 agent 系统，可以做 build failure 分析 Pipeline step、PR 修复触发器、测试报告摘要或 ChatOps 通知插件。
- Jenkins 安全敏感，credentials API、权限模型、日志脱敏和重启恢复都要谨慎。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、测试失败、插件行为复现或用户工作流证据。
- 方案设计和影响范围，说明插件/core 模块、Pipeline 行为、权限、凭据和兼容版本。
- 代码或文档改动，包括 Java、Jelly/Stapler、Pipeline step、README、测试或示例。
- 测试和验证结果，例如 Maven test、JenkinsRule、lint、插件本地安装或 Pipeline 运行。
- PR 标题和 PR 描述，说明问题、方案、验证、安全影响和兼容性风险。

最终目标：提交一个能改善 Jenkins 插件或 CI/CD 工作流的 PR，并让维护者认可其价值。
