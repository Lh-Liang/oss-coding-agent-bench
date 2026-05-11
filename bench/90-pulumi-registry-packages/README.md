# Pulumi Registry Packages

目标仓库：https://github.com/pulumi/registry

## 1. 任务要求、问题来源和建议方向

你要在 Pulumi Registry 或 Pulumi package 相关工作中寻找一个真实贡献点。Pulumi 是基础设施即代码平台，用户用 TypeScript、Python、Go、C#、Java 等语言定义云资源和平台组件。Registry 收录 provider、component、template 和 package 文档，很多 API docs 由 schema 生成。

你可以优先参考这些问题来源：

- registry issue、PR review、页面错误、schema docs、安装说明、示例代码或链接失效。
- 某个已有 provider/component 已发布新能力，但 registry docs、examples 或 metadata 未更新。
- 同类 IaC provider 有清楚的 resource example、import 说明和配置文档，而目标 package 缺少。
- 本地 docs generation、schema validation、示例运行或多语言安装暴露的问题。

建议修改方向：

- 优先给已有 package 补文档、examples、schema descriptions、版本 metadata 或生成修复。
- 新 package 要确认 provider/component 已稳定发布，有 license、SDK artifacts、下载 URL 和长期维护者。
- 对 agent 系统，可以做部署 agent worker、queue、database、secrets、observability 的 Pulumi component。
- 不要轻易改变资源生命周期语义，除非有明确 issue、测试和兼容性说明。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、registry 页面、schema/docs 差异、示例失败或同类 provider 对比。
- 方案设计和影响范围，说明 package、schema、docs、examples、metadata 和发布影响。
- 代码或文档改动，包括 registry 条目、docs、examples、schema 描述或生成配置。
- 测试和验证结果，例如 docs generation、schema validation、示例运行、多语言安装或链接检查。
- PR 标题和 PR 描述，说明 package 名、用户影响、验证方式和兼容性风险。

最终目标：提交一个能帮助 Pulumi 用户正确安装、理解或使用 package 的 PR。
