# Prometheus Community Helm Charts

目标仓库：https://github.com/prometheus-community/helm-charts

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录该项目近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 Prometheus Community Helm Charts 中寻找一个真实 Kubernetes 可观测性部署贡献点。该仓库维护 Prometheus、Alertmanager、kube-prometheus-stack、exporters 和相关组件的 Helm charts。

你可以优先参考这些问题来源：

- issue、chart-testing 失败、真实 values 或 Kubernetes API 变化导致 chart 渲染错误。
- values.schema.json、README values 文档、migration note 或 default values 不完整。
- ServiceMonitor、Ingress、RBAC、PodSecurity、affinity/tolerations、labels/annotations 等模板边界错误。
- Prometheus Operator、CRD 或 Kubernetes 版本兼容问题。

建议修改方向：

- 优先修复已有 chart template、values schema、文档或测试中的小问题。
- 控制改动范围，避免影响大量用户的现有 values。
- Chart version、appVersion、changelog 和 generated docs 要按项目规范同步。
- 对复杂 chart 要用多个 values 组合渲染验证。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、values 示例、渲染错误或 Kubernetes API 证据。
- 方案设计和影响范围，说明 chart、templates、values、CRD 和兼容版本。
- Chart 或文档改动，包括 templates、values schema、README、tests 和 changelog。
- 验证结果，例如 helm lint、helm template、ct lint/install 或 kubeconform。
- PR 标题和 PR 描述，说明部署影响、兼容性和风险。

最终目标：提交一个提升 Prometheus Helm charts 可配置性、兼容性或文档准确性的 PR。
