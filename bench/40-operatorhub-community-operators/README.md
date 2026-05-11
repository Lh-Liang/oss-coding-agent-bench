# OperatorHub / Community Operators

目标仓库：https://github.com/k8s-operatorhub/community-operators

## 1. 任务要求、问题来源和建议方向

你要在 Community Operators 中寻找一个真实 Kubernetes Operator 贡献点。OperatorHub 是 Kubernetes Operator 的发现入口，Community Operators 仓库通过 bundle、CSV、CRD、annotations、CI 测试和维护者 review，把社区 Operator 收录到可安装目录中。贡献通常集中在某个 Operator 目录。

你可以优先参考这些问题来源：

- PR、issue、CI 失败或维护者评论中的 bundle validation、CSV、CRD、annotations、升级路径问题。
- 某个已有 Operator 的图标、描述、links、maintainers、examples、installModes 或 capabilities 不完整。
- 上游软件有新版本，但 Operator bundle、channels、defaultChannel 或升级图没有更新。
- 本地 `operator-sdk bundle validate`、YAML schema、deprecated API 扫描或安装测试暴露的问题。

建议修改方向：

- 优先修复已有 Operator 的元数据、bundle 校验、示例 CR、升级路径和 CI 失败。
- 新 Operator 要选择有明确维护者、稳定镜像、清楚部署文档和真实 Kubernetes 用户需求的项目。
- 对 agent 系统，可以做部署 agent worker、queue、RBAC、secrets 和 observability 的 Operator 原型。
- 注意 OpenShift 和上游 Kubernetes 目录差异，选择正确目录和测试目标。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 CI 日志、bundle 校验失败、OperatorHub 页面缺口或版本差异。
- 方案设计和影响范围，说明 bundle、CSV、CRD、channels、升级路径和安装环境。
- 代码或配置改动，包括 CSV、CRD、annotations、metadata、README、示例 CR 或 bundle。
- 测试和验证结果，例如 bundle validate、deprecated API 扫描、YAML 校验、安装测试和升级检查。
- PR 标题和 PR 描述，说明 Operator、版本、验证方式、目录选择和维护信息。

最终目标：提交一个能通过 Community Operators CI 和维护者 review 的 Operator PR。
