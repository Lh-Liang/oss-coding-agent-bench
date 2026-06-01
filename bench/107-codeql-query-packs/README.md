# CodeQL Query Packs

目标仓库：https://github.com/github/codeql

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录该项目近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 CodeQL query packs 中寻找一个真实语义代码分析贡献点。CodeQL 将代码库解析成可查询数据库，并通过 queries/model packs 发现安全漏洞、代码质量问题和 API 使用风险。

你可以优先参考这些问题来源：

- issue、安全研究、真实误报/漏报或 framework API 行为显示某 query/model 不准确。
- source、sink、sanitizer、summary model 或 dataflow/type tracking 边界缺失。
- query help、metadata、severity 或 remediation 文档不足。
- 测试 fixture 未覆盖某语言特性、框架版本或漏洞模式。

建议修改方向：

- 优先修复已有 query/model 的 false positive 或 false negative。
- 新 query 要小而明确，附 query help、metadata 和充分 fixture。
- 注意查询性能，避免对 code scanning 用户造成明显成本。
- 涉及未公开漏洞时必须遵守负责任披露边界。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括真实代码样例、issue、安全文档或当前 alert。
- 方案设计和影响范围，说明语言、query pack、dataflow/model 和误报边界。
- 代码或文档改动，包括 QL query/model、fixtures、expected alerts 和 query help。
- 验证结果，例如 CodeQL targeted tests、metadata validation 或 alert diff。
- PR 标题和 PR 描述，说明安全风险、修复建议和性能考虑。

最终目标：提交一个提高 CodeQL 规则准确性、覆盖率或文档质量的 PR。
