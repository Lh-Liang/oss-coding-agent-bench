# OpenAPI Generator

目标仓库：https://github.com/OpenAPITools/openapi-generator

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录该项目近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 OpenAPI Generator 中寻找一个真实代码生成贡献点。OpenAPI Generator 根据 OpenAPI specification 生成 API clients、server stubs、文档和配置，支持大量语言和框架。

你可以优先参考这些问题来源：

- issue、真实 OpenAPI spec 或生成结果显示某 generator/template 输出错误。
- nullable、oneOf/anyOf、enum、reserved words、date/time、auth 或 serialization 边界处理不正确。
- 某 generator 配置项缺少测试、示例、文档或 sample。
- schema handling 与 OpenAPI/JSON Schema 语义不一致。

建议修改方向：

- 优先修复已有 generator 的 template 或 Java 逻辑，并添加最小 spec fixture。
- 控制 sample 更新范围，避免把大量无关 generated noise 混进 PR。
- 行为变化可能影响用户 SDK，必要时通过配置开关或兼容方案实现。
- 新 generator 维护成本高，除非有明确需求和维护意愿。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、OpenAPI spec、错误生成片段或编译失败。
- 方案设计和影响范围，说明目标 generator、template、schema 语义和兼容性。
- 代码或文档改动，包括 Java 代码、Mustache template、fixture、sample 和 docs。
- 验证结果，例如 targeted Maven tests、sample generation、generated code compile 或 diff review。
- PR 标题和 PR 描述，说明输入 spec、生成前后差异和风险。

最终目标：提交一个让 OpenAPI Generator 生成结果更正确、更可维护的 PR。
