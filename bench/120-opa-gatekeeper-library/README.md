# OPA Gatekeeper Library

目标仓库：https://github.com/open-policy-agent/gatekeeper-library

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录该项目近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 OPA Gatekeeper Library 中寻找一个真实 Kubernetes admission policy 贡献点。Gatekeeper Library 维护可复用 ConstraintTemplate 和示例 constraints，用 Rego 表达 Kubernetes 安全与治理规则。

你可以优先参考这些问题来源：

- 安全基线、issue、真实集群策略或用户报告显示某 policy 缺失、误报或漏检。
- 现有 Rego 未覆盖 initContainers、ephemeralContainers、新 API version 或 CRD 字段。
- Policy 缺少 allowed/denied fixtures、参数说明、README 或例外边界。
- 规则性能、可读性或错误信息有明确改进空间。

建议修改方向：

- 优先修复已有 ConstraintTemplate 的漏检/误报，并补 allow/deny fixtures。
- 新 policy 必须有清楚治理目标和可靠来源，不假设所有集群都适用。
- Rego 要简单、可维护，避免昂贵或难懂的表达式。
- Admission policy 会影响部署，误报边界必须写清楚。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括安全要求、违规样例、合规样例或 issue。
- 方案设计和影响范围，说明 resource、ConstraintTemplate、parameters 和例外边界。
- Policy 或文档改动，包括 Rego、YAML constraints、fixtures 和 README。
- 验证结果，例如 OPA test、Gatekeeper policy test 或 YAML validation。
- PR 标题和 PR 描述，说明治理价值、风险和验证覆盖。

最终目标：提交一个可复用、可测试、低误报的 Gatekeeper policy library PR。
