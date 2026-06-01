# Rust Clippy

目标仓库：https://github.com/rust-lang/rust-clippy

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录该项目近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 Rust Clippy 中寻找一个真实 Rust lint 贡献点。Clippy 是 Rust 官方 lint 工具，提供额外 lint 来发现 bug、性能问题、复杂代码、风格问题和惯用法改进。

你可以优先参考这些问题来源：

- issue、真实 Rust 代码或 UI tests 显示某 lint 有误报、漏报或 suggestion 错误。
- Rust 新语法、edition、macro、async、const、generic、trait 或 lifetime 边界未覆盖。
- lint 文档、diagnostic message 或 applicability 标记不清楚。
- rustc 内部表示变化导致 lint 行为变化。

建议修改方向：

- 优先修复已有 lint 的 false positive/false negative，并补 UI test。
- Suggestion 必须机器可应用且不改变语义，保留注释和格式。
- 新 lint 要非常明确、低争议，优先 correctness/perf 类。
- 注意 macro-generated code、edition 和 MSRV 边界。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、触发代码、当前/期望 diagnostic。
- 方案设计和影响范围，说明 lint、Rust edition、macro/generic 边界和 applicability。
- 代码或文档改动，包括 Rust lint logic、UI tests、diagnostics 和 docs。
- 验证结果，例如 targeted Clippy tests、UI test diff 或 cargo test。
- PR 标题和 PR 描述，说明语义、安全性和误报边界。

最终目标：提交一个提高 Clippy lint 准确性或建议质量的 PR。
