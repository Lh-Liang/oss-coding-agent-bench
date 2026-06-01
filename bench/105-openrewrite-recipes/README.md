# OpenRewrite Recipes

目标仓库：https://github.com/openrewrite/rewrite

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录该项目近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 OpenRewrite 中寻找一个真实自动化代码迁移贡献点。OpenRewrite 通过 AST-aware recipes 修改 Java、Kotlin、XML、YAML、properties、Gradle/Maven 等文件，用于依赖升级、框架迁移和安全修复。

你可以优先参考这些问题来源：

- 官方迁移文档、issue、真实项目代码或已有 recipe 测试显示某迁移步骤缺失。
- 已有 recipe 对泛型、static import、注解、配置文件、build 文件或边界代码误改/漏改。
- 某库 API 变更、dependency coordinate 变更或框架升级有明确迁移规则。
- Recipe catalog 文档、metadata 或示例不足。

建议修改方向：

- 优先修复已有 recipe 的误改/漏改，并添加 before/after tests。
- 新 recipe 要选择范围小、来源清楚、可通过 fixture 精确验证的迁移场景。
- 避免文本替换式重构，优先使用 OpenRewrite AST 和 type attribution 能力。
- 必须包含不应修改场景，降低误改风险。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括迁移文档、issue、旧/新代码样例或真实失败案例。
- 方案设计和影响范围，说明 recipe 适用版本、前置条件和限制。
- 代码或文档改动，包括 recipe、visitor、metadata、before/after tests 和 docs。
- 验证结果，例如 JUnit recipe tests、Gradle/Maven test 或 sample dry run。
- PR 标题和 PR 描述，说明迁移价值、验证覆盖和误改风险。

最终目标：提交一个可复用、可验证、能帮助真实项目迁移的 OpenRewrite PR。
