# Backstage Community Plugins

目标仓库：https://github.com/backstage/community-plugins

## 1. 任务要求、问题来源和建议方向

你要在 Backstage 社区插件生态中寻找一个真实贡献点。Backstage 是面向工程组织的开发者门户，用软件目录、TechDocs、Scaffolder、权限和插件把服务、团队、CI/CD、监控、云资源和内部工具集中到一个入口。社区插件仓库承接大量前端插件、后端插件、Scaffolder actions 和 Entity providers。

你可以优先参考这些问题来源：

- community plugin 的 issue、PR review、迁移任务、测试失败、依赖升级或文档缺口。
- 某个插件与 Backstage 新前端系统、后端系统、权限模型或配置 schema 不兼容。
- 已有插件缺少安装说明、示例 app 配置、错误状态、测试、Storybook 或权限说明。
- 同类开发者门户能力已有，但某个社区插件缺少自然的小功能。

建议修改方向：

- 优先修复已有社区插件的 bug、测试、文档、配置 schema 或版本兼容。
- 新插件要先确认不重复，并说明维护者、用户场景和适合进入 community-plugins 的原因。
- 对 agent 系统，可以做任务状态面板、PR 分析结果页、Scaffolder action、Entity provider 或 TechDocs 质量检查。
- 注意认证、权限、后端代理和配置，不要把企业内部数据假设写死。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、插件行为复现、文档缺口或同类插件对比。
- 方案设计和影响范围，说明插件包、前后端边界、权限、配置和迁移影响。
- 代码或文档改动，包括 TypeScript/React、backend plugin、tests、README 或示例配置。
- 测试和验证结果，例如 typecheck、lint、unit test、Storybook 或 example app 验证。
- PR 标题和 PR 描述，说明用户价值、安装影响、验证方式和风险。

最终目标：向 `backstage/community-plugins` 提交一个可维护、符合 Backstage 插件规范的 PR，并争取被维护者接受。
