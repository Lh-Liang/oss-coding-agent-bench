# Biome

目标仓库：https://github.com/biomejs/biome

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录该项目近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 Biome 中寻找一个真实前端工具链贡献点。Biome 提供 formatter、linter、parser、import sorting 和 assist，覆盖 JavaScript、TypeScript、JSX、JSON、CSS 等文件类型。

你可以优先参考这些问题来源：

- issue、真实前端代码或 snapshot 显示 formatter、parser、rule 或 assist 行为错误。
- TypeScript/JSX/CSS/JSON 新语法、注释、换行、泛型或配置边界未正确处理。
- Linter rule 有误报/漏报、diagnostic 不清楚或 docs 示例不足。
- Assist/autofix 在边界代码上改变语义或输出不可应用。

建议修改方向：

- 优先修复已有 rule、formatter、parser 或 assist 的小边界。
- 用 fixtures/snapshots 证明输入输出变化，避免无关格式化噪音。
- Formatter 和 assist 变更要特别说明稳定性和语义安全性。
- 新 rule 要有明确用户价值，避免与已有规则重叠。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、代码样例、当前 Biome 输出和期望输出。
- 方案设计和影响范围，说明语言、模块、diagnostic、formatter 或 assist 行为。
- 代码或文档改动，包括 Rust 实现、fixtures、snapshots、rule docs 或 examples。
- 验证结果，例如 targeted cargo tests、snapshot review 或 fixture output diff。
- PR 标题和 PR 描述，说明兼容性、语义安全和风险。

最终目标：提交一个让 Biome 在真实前端代码中更准确、更稳定或更易用的 PR。
