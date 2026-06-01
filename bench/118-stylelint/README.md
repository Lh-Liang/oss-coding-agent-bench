# Stylelint

目标仓库：https://github.com/stylelint/stylelint

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录该项目近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 Stylelint 中寻找一个真实 CSS lint 贡献点。Stylelint 检查 CSS、SCSS、Less 和 CSS-in-JS 中的错误、兼容性问题和规则约束。

你可以优先参考这些问题来源：

- issue、CSS 规范变化或真实样式代码显示某 rule 有误报、漏报或 autofix 问题。
- CSS nesting、container queries、custom properties、cascade layers、SCSS/Less 或 CSS-in-JS 边界未覆盖。
- Rule docs 缺少 valid/invalid examples、option 说明或迁移提示。
- Syntax parser、message 或 fixer 行为和实际 CSS 语义不一致。

建议修改方向：

- 优先修复已有 rule 的小边界，并添加 accept/reject tests。
- Autofix 必须保留语义、注释和格式，不要和 formatter 职责混淆。
- 新 rule 或 option 要有明确需求，避免纯风格争议。
- 预处理器和 CSS-in-JS 行为要用对应 fixture 验证。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、CSS 样例、当前 warnings 和期望行为。
- 方案设计和影响范围，说明 rule、syntax、option、fixer 和兼容性。
- 代码或文档改动，包括 rule logic、fixtures、docs 和 examples。
- 验证结果，例如 targeted Jest tests、fixture warning diff 或 fixer output diff。
- PR 标题和 PR 描述，说明 CSS 语义、误报边界和验证方式。

最终目标：提交一个提升 Stylelint 规则准确性、CSS 新语法兼容或文档质量的 PR。
