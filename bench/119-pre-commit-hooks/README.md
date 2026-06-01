# pre-commit Hooks

目标仓库：https://github.com/pre-commit/pre-commit-hooks

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录该项目近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 pre-commit Hooks 中寻找一个真实提交前质量门禁贡献点。pre-commit-hooks 维护官方常用 hooks，例如检查 YAML/JSON/TOML、尾随空格、合并冲突、大文件和权限问题。

你可以优先参考这些问题来源：

- issue、真实仓库失败日志或 hook 输出显示某 hook 对文件名、编码、路径、权限或 symlink 处理错误。
- Windows/macOS/Linux 换行、路径、可执行位或 shell 行为差异导致 hook 不稳定。
- 某 hook 缺少配置选项、错误信息不清楚或 docs 示例不足。
- YAML/JSON/TOML 等文件检查在边界内容上误报/漏报。

建议修改方向：

- 优先修复已有 hook 的小 bug，并添加 pytest fixture。
- 保持 hooks 简单通用，不把业务逻辑放入官方 hooks。
- 新 option 要谨慎，避免让 hook 行为过于复杂。
- 文件匹配要准确，避免扫描过多文件或误伤二进制文件。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括失败文件、当前输出、操作系统和期望行为。
- 方案设计和影响范围，说明 hook、参数、文件类型和平台边界。
- 代码或文档改动，包括 Python hook、metadata、tests 和 README。
- 验证结果，例如 pytest、pre-commit run 或跨平台路径样例。
- PR 标题和 PR 描述，说明复现步骤、修复方式和兼容性。

最终目标：提交一个让 pre-commit 官方 hook 更稳定、更清晰或更可配置的 PR。
