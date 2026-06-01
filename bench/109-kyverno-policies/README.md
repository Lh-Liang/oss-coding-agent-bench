# Kyverno Policies

目标仓库：https://github.com/kyverno/policies

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录该项目近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 Kyverno Policies 中寻找一个真实 Kubernetes policy 贡献点。Kyverno 是 Kubernetes 原生 policy engine，policy library 提供安全、最佳实践、供应链和多租户治理策略。

你可以优先参考这些问题来源：

- issue、policy library 文档、Kubernetes API 变化或安全基线显示某 policy 缺失/过期。
- 现有 policy 对 containers、initContainers、ephemeralContainers、CRD 或新 API version 漏检。
- policy 缺少 pass/fail resource fixtures、annotation、category、severity 或 README。
- 用户部署场景显示某规则误报过多或错误信息不清楚。

建议修改方向：

- 优先修复已有 policy 的兼容性、漏检、误报或测试覆盖。
- 新 policy 必须有明确安全/治理目标和可靠来源。
- Mutate/generate policy 要谨慎，避免意外改变生产资源。
- 用 pass/fail fixtures 清楚证明行为。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括安全基线、issue、违规样例或当前测试缺口。
- 方案设计和影响范围，说明 resource、API version、policy 类型和例外边界。
- Policy 或文档改动，包括 YAML、test resources、metadata 和 README。
- 验证结果，例如 kyverno test/apply、Chainsaw tests 或 YAML validation。
- PR 标题和 PR 描述，说明治理价值、误报风险和验证范围。

最终目标：提交一个能被 Kyverno policy library 接受、可测试且有实际治理价值的 PR。
