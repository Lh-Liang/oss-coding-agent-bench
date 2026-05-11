# Zed Extensions

目标仓库：https://github.com/zed-industries/extensions

## 1. 任务要求、问题来源和建议方向

你要在 Zed Extensions 中寻找一个真实编辑器扩展贡献点。Zed 是现代开源代码编辑器，扩展仓库收录语言支持、主题、语法高亮、LSP 配置、debugger、MCP 或 context server 相关能力。贡献通常是让 Zed 更好支持某种语言、工具链或开发者工作流。

你可以优先参考这些问题来源：

- extensions 仓库 issue、PR review 或用户反馈中的 language server、grammar、file type、formatter 或主题问题。
- 某个已有语言扩展缺少 file associations、outline、diagnostics、formatter、injection 或平台支持说明。
- 某种小众语言或工具已有 Tree-sitter grammar / LSP，但 Zed 尚未支持或支持不完整。
- 本地安装扩展、打开样例文件、启动 LSP 或运行下载脚本时暴露的问题。

建议修改方向：

- 优先修复已有扩展的配置、语法高亮、LSP 启动、版本下载、README 或平台兼容。
- 新扩展要先确认不重复，并提供可信来源、样例文件和本地测试说明。
- 对 agent 系统，可以探索 MCP/context server、代码解释、测试失败分析或 PR 摘要相关扩展。
- 如果涉及二进制下载或外部 server，要说明版本、平台、安全来源和失败处理。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、样例文件、LSP 日志、语法缺口或同类编辑器对比。
- 方案设计和影响范围，说明 extension manifest、grammar、LSP、平台和用户体验。
- 代码或配置改动，包括 `extension.toml`、grammar 配置、语言配置、主题或 README。
- 测试和验证结果，例如本地安装、打开样例文件、LSP 启动、语法高亮截图或限制说明。
- PR 标题和 PR 描述，说明扩展能力、验证方式、平台支持和风险。

最终目标：提交一个能提升 Zed 语言或工具支持质量的 PR，并通过扩展仓库 review。
