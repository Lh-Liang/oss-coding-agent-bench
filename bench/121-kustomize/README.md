# Kustomize

目标仓库：https://github.com/kubernetes-sigs/kustomize

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录该项目近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 Kustomize 中寻找一个真实 Kubernetes 配置定制贡献点。Kustomize 通过 overlays、patches、transformers 和 generators 组合 Kubernetes YAML，并集成在 `kubectl apply -k` 工作流中。

你可以优先参考这些问题来源：

- issue、真实 kustomization 或 golden output 显示 patch、transformer、generator 或 replacements 行为错误。
- Kubernetes API 变化、CRD 字段路径、resource identity 或 YAML merge 边界未正确处理。
- 文档示例、错误信息、validation 或 target matching 说明不足。
- kyaml/KRM function 行为和当前 docs 不一致。

建议修改方向：

- 优先修复已有 transformer/generator/patch 行为的小边界，并补最小 input/output fixture。
- 保持向后兼容，避免破坏大量用户 overlay。
- 用 golden tests 明确证明输出变化，避免无关 YAML 重排。
- 区分 Kustomize 行为问题和 Kubernetes API 本身问题。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 kustomization 目录、当前输出、期望输出或 issue。
- 方案设计和影响范围，说明 transformer、generator、patch、field path 或 docs 变化。
- 代码或文档改动，包括 Go 逻辑、golden fixtures、examples 和 docs。
- 验证结果，例如 go test、kustomize build output diff 或 kubectl kustomize smoke test。
- PR 标题和 PR 描述，说明兼容性、输出变化和风险。

最终目标：提交一个提升 Kustomize 行为正确性、错误提示或文档清晰度的 PR。
