# Tekton Catalog / Hub

目标仓库：https://github.com/tektoncd/catalog

## 1. 任务要求、问题来源和建议方向

你要在 Tekton Catalog 中寻找一个真实 CI/CD 资源贡献点。Tekton 是 Kubernetes 原生 CI/CD 框架，用 Task、Pipeline、PipelineRun 和 TaskRun 定义构建、测试、部署和自动化流程。Catalog 收录可复用 Tasks、Pipelines 和相关资源，Tekton Hub 是发现入口。

你可以优先参考这些问题来源：

- Catalog issue、PR review、CI 失败中的 Task 参数、results、workspaces、README、samples 或 tests 问题。
- 某个已有 Task 使用旧 API、示例不可运行、权限过宽、secret 暴露或镜像版本不合理。
- 常见开发工作流已有其他 CI/CD 实现，但 Tekton Catalog 缺少自然的、范围小的 Task。
- 本地 YAML/schema 检查、sample run 或 Tekton 测试暴露的问题。

建议修改方向：

- 优先修复已有 Task 的参数、results、examples、README、tests 或新版 API 兼容。
- 新 Task 要选择通用且边界小的能力，例如测试失败摘要、release notes、manifest review。
- 对 agent 系统，可以封装代码审查、PR 描述生成、测试日志总结、Kubernetes manifest 风险检查。
- 最小化权限和凭证访问，输出通过 results 或清晰日志表达，避免打印 secrets。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、sample 失败、schema 检查、CI 日志或同类工具对比。
- 方案设计和影响范围，说明 Task/Pipeline、params、workspaces、results、镜像和副作用。
- 资源或文档改动，包括 YAML、README、samples、tests、version metadata 或脚本。
- 测试和验证结果，例如 YAML/schema 检查、sample run、Tekton 测试或本地模拟。
- PR 标题和 PR 描述，说明资源名、使用场景、验证方式和安全边界。

最终目标：提交一个能通过 Tekton Catalog CI 和维护者 review 的 PR。
