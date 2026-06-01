# markdownlint

目标仓库：https://github.com/DavidAnson/markdownlint  
辅助仓库：https://github.com/DavidAnson/markdownlint-cli2

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录该项目近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 markdownlint 或 markdownlint-cli2 中寻找一个真实 Markdown 文档质量贡献点。markdownlint 提供规则检查标题、列表、代码块、链接、空行、表格和格式一致性，CLI 用于 CI 和本地检查。

你可以优先参考这些问题来源：

- issue、真实 Markdown 文档或 rule fixture 显示某规则有误报、漏报或 fixer 问题。
- GitHub Flavored Markdown 表格、HTML、代码块、链接、front matter 或 MDX 边界未正确处理。
- CLI 配置、ignore pattern、glob、退出码或文档示例不清楚。
- Rule docs 缺少 valid/invalid 示例或配置说明。

建议修改方向：

- 优先修复已有 rule 或 CLI 行为的小边界，并补 fixture。
- Fixer 必须保留内容，特别是代码块、表格、HTML 和缩进。
- 注意 Markdown 方言差异，避免把偏好当成通用错误。
- CLI 行为要考虑 Windows/macOS/Linux shell 和 glob 差异。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 Markdown 样例、当前 warning/fix、期望行为或 issue。
- 方案设计和影响范围，说明 rule、parser、fixer、CLI 或 docs 变化。
- 代码或文档改动，包括 JavaScript 逻辑、fixtures、rule docs 和 CLI docs。
- 验证结果，例如 npm test、fixture warning diff 或 fixer output diff。
- PR 标题和 PR 描述，说明 Markdown 方言、兼容性和风险。

最终目标：提交一个提升 markdownlint 规则准确性、fixer 安全性或 CLI 易用性的 PR。
