# Ruff

目标仓库：https://github.com/astral-sh/ruff

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录该项目近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 Ruff 中寻找一个真实 Python lint/formatter 贡献点。Ruff 是用 Rust 编写的 Python linter 和 formatter，覆盖大量规则、parser、formatter、diagnostics 和 autofix 行为。

你可以优先参考这些问题来源：

- issue、真实 Python 代码或规则 fixture 显示某 rule 有误报、漏报或 autofix 问题。
- Formatter 对 Python 新语法、typing、f-string、pattern matching、注释或括号边界处理不稳定。
- Rule docs、safe/unsafe fix 说明、diagnostic message 或 preview/stable 行为说明不足。
- Python 版本兼容、AST 解析或 import 排序边界存在可复现问题。

建议修改方向：

- 优先修复已有 rule/formatter 的小边界，并补 fixture 或 snapshot。
- Autofix 必须保持语义，正确标记 safe/unsafe，并保留注释。
- Formatter 改动影响面大，必须控制范围并说明输出变化。
- 注意性能，避免在常用规则中引入昂贵遍历。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、代码样例、当前输出和期望输出。
- 方案设计和影响范围，说明 rule、formatter、parser、Python 版本和 autofix 安全性。
- 代码或文档改动，包括 Rust 实现、fixtures/snapshots、rule docs 和 diagnostics。
- 验证结果，例如 targeted cargo tests、snapshot review 或 fixture diff。
- PR 标题和 PR 描述，说明行为变化、性能和兼容性。

最终目标：提交一个提升 Ruff 规则准确性、formatter 稳定性或文档质量的 PR。
