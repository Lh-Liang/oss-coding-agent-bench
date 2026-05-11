# Falco Plugins

目标仓库：https://github.com/falcosecurity/plugins

## 1. 任务要求、问题来源和建议方向

你要在 Falco Plugins 中寻找一个真实运行时安全或审计事件集成贡献点。Falco 是 CNCF 运行时安全项目，用规则引擎检测 Kubernetes、容器、主机和云环境中的异常行为。Plugins 扩展 Falco 的事件来源、字段提取和事件解析能力。

你可以优先参考这些问题来源：

- issue、PR review、registry、rules 或用户报告中的 plugin 解析错误、字段缺失、文档不清、示例不可运行。
- 某个安全事件源有稳定审计日志，但 Falco 缺少 event source plugin 或 rules。
- 已有 plugin 缺少 fields、README、sample events、rules、tests 或 registry metadata。
- 本地 build、sample event parsing、rules validation 或性能检查暴露的问题。

建议修改方向：

- 优先给已有 plugin 补 fields、rules、example events、README、registry metadata 或解析 bugfix。
- 新 plugin 要选择事件格式稳定、用户价值明确、敏感数据边界清楚的来源。
- 对 agent 系统，可以设计 agent activity event source，记录工具调用、文件写入、PR 创建和高风险命令。
- 安全规则要减少误报，event schema 和 fields 要考虑长期兼容。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、样例日志、解析失败、规则缺口、同类 plugin 对比或安全场景。
- 方案设计和影响范围，说明 event source、fields、rules、配置、registry metadata 和性能影响。
- 代码或配置改动，包括 plugin 代码、registry entry、rules、README、sample events 和 tests。
- 测试和验证结果，例如 build、sample parsing、rules validation、测试结果和敏感数据脱敏。
- PR 标题和 PR 描述，说明 plugin/规则名、安全价值、验证方式和数据边界。

最终目标：提交一个能提升 Falco 事件覆盖或插件质量的 PR。
