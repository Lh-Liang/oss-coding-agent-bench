# typescript-eslint

目标仓库：https://github.com/typescript-eslint/typescript-eslint

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录该项目近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 typescript-eslint 中寻找一个真实 TypeScript lint 贡献点。typescript-eslint 提供 parser、scope manager、AST utilities、ESLint plugin 和大量 TypeScript-aware rules。

你可以优先参考这些问题来源：

- issue、真实代码样例或 rule tests 显示某规则有误报、漏报或 autofix 问题。
- TypeScript 新语法、compiler 行为或 ESLint 变化导致 parser/rule 不兼容。
- rule docs、playground examples、migration note 或 option 说明不足。
- type-aware rule 性能或边界行为存在可复现问题。

建议修改方向：

- 优先修复已有 rule 的 false positive/false negative，并添加 valid/invalid tests。
- Autofix/suggestion 必须安全，不改变语义，注意注释和格式保留。
- 新 rule 需要充分需求，避免与已有规则重叠或引发风格争议。
- Type-aware 逻辑要控制性能成本，并说明需要 type information 的原因。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、代码样例、当前 diagnostic/autofix 和期望行为。
- 方案设计和影响范围，说明 rule、parser service、TypeScript 版本和配置。
- 代码或文档改动，包括 rule implementation、tests、docs 和 examples。
- 验证结果，例如 package tests、lint、typecheck 或 rule tester output。
- PR 标题和 PR 描述，说明行为变化、autofix 安全性和兼容风险。

最终目标：提交一个提升 TypeScript lint 准确性、文档或 parser 兼容性的 PR。
