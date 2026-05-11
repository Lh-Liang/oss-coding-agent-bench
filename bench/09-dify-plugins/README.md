# Dify Plugins

目标仓库：https://github.com/langgenius/dify-plugins

## 1. 任务要求、问题来源和建议方向

你要在 Dify Plugins 中寻找一个真实 LLM 应用插件贡献点。Dify 是开源 LLM 应用开发平台，支持聊天应用、RAG、workflow、agent、模型管理、工具调用和部署。插件系统用于扩展 Tool、Model Provider、Agent Strategy、Extension 和外部 API 能力。

你可以优先参考这些问题来源：

- dify-plugins 仓库 issue、PR review、schema 变更或已有插件中的 bug、文档缺口、错误处理缺失。
- 某个已有插件的 manifest、YAML schema、凭证字段、输入输出 schema 或 README 与 Dify 规范不一致。
- 某个开发者工具、数据工具、模型服务或 agent 系统 API 有明确用户需求，但缺少 Dify Tool 插件。
- 本地插件调试、schema 校验、示例调用或错误分支测试暴露的问题。

建议修改方向：

- 优先从 Tool 插件开始，选择动作明确、输入输出稳定、凭证简单的 API。
- 给已有插件补错误处理、超时、速率限制、README、示例 workflow 或 schema 修复。
- 对 agent 系统，可以做创建任务、查询状态、获取 PR 摘要、触发代码分析或读取审查结果的 Tool 插件。
- 凭证和隐私要写清楚，避免把 workspace 级、用户级配置混淆。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、API 文档、schema 缺口、用户场景或可复现错误。
- 方案设计和影响范围，说明插件类型、manifest、凭证、输入输出 schema 和副作用。
- 代码或文档改动，包括 YAML schema、Python 实现、README、示例 workflow 或测试。
- 测试和验证结果，例如 schema 校验、本地调试、示例请求、错误分支和凭证字段检查。
- PR 标题和 PR 描述，说明工具价值、配置方式、验证步骤和隐私边界。

最终目标：向 `langgenius/dify-plugins` 提交一个符合 Dify 插件规范、能被维护者接受的 PR。
