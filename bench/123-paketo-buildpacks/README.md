# Paketo Buildpacks

目标组织：https://github.com/paketo-buildpacks

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录 Paketo Buildpacks 组织近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 Paketo Buildpacks 组织中的具体 buildpack 仓库寻找一个真实容器构建贡献点。Paketo Buildpacks 基于 Cloud Native Buildpacks，把应用源码自动构建成 OCI image，覆盖多种语言和运行时。

你可以优先参考这些问题来源：

- issue、pack build 日志或 sample app 显示 detect/build 逻辑、依赖安装或 runtime version 处理错误。
- lockfile、package manager、runtime version、environment variables 或 dependency metadata 边界缺失。
- Buildpack 文档、配置说明、错误信息或 integration tests 不完整。
- 上游 runtime 或 dependency 版本更新导致构建失败。

建议修改方向：

- 优先选择一个具体 buildpack 仓库，修复小范围 detect/build/config/docs 问题。
- 用最小 sample app 或 integration fixture 证明构建行为。
- 注意 Cloud Native Buildpacks layer/cache/env 语义，避免破坏现有构建。
- Dependency update 要可追溯，并说明安全和兼容性。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 build log、sample app、issue 或 runtime 文档。
- 方案设计和影响范围，说明目标 buildpack、detect/build 阶段、依赖和环境变量。
- 代码或文档改动，包括 Go 代码、dependency metadata、integration tests、sample app 或 docs。
- 验证结果，例如 pack build、container smoke test、Go tests 或 integration tests。
- PR 标题和 PR 描述，说明构建前后差异、验证范围和风险。

最终目标：提交一个让 Paketo buildpack 在真实应用构建中更可靠或更清晰的 PR。
