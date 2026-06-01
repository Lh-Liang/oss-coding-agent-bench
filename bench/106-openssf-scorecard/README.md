# OpenSSF Scorecard

目标仓库：https://github.com/ossf/scorecard

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录该项目近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 OpenSSF Scorecard 中寻找一个真实开源安全检查贡献点。Scorecard 会检查仓库安全健康度，例如分支保护、安全策略、依赖更新、token permissions、CI 安全和维护状态。

你可以优先参考这些问题来源：

- issue、真实仓库样本或当前输出显示某 check 有误报、漏报或建议不清楚。
- GitHub API 行为、权限、分页、rate limit 或组织策略导致检查不准确。
- check 文档、remediation steps 或输出解释与实际行为不一致。
- 新安全 best practice 有明确来源，并适合做小而稳定的 check。

建议修改方向：

- 优先修复已有 check 的误报/漏报，并补 mock GitHub API tests。
- 新 check 要谨慎，必须有可靠安全依据和清楚的分数语义。
- 输出建议要可执行，避免给用户制造无意义告警。
- 对 archived、fork、template、private-like 权限边界要特别注意。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括真实仓库样本、当前输出、期望输出或安全文档。
- 方案设计和影响范围，说明目标 check、分数变化、误报/漏报边界。
- 代码或文档改动，包括 Go checker、mock tests、docs 和 remediation。
- 验证结果，例如 Go tests、targeted check run 或 sample repo comparison。
- PR 标题和 PR 描述，说明安全语义、兼容性和风险。

最终目标：提交一个提升 Scorecard 安全判断准确性或可操作性的 PR。
