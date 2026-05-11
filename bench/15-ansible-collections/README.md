# Ansible Collections

目标仓库：https://github.com/ansible-collections/community.general

## 1. 任务要求、问题来源和建议方向

你要在 Ansible Collections 中寻找一个真实贡献点。Ansible 用 YAML playbook 做配置管理、自动化运维和资源管理。Collection 可以包含 module、plugin、role、playbook、文档和测试。`community.general` 是大型社区 collection，适合寻找模块修复、文档补全、幂等性改进和测试缺口。

你可以优先参考这些问题来源：

- collection issue、PR review、ansible-test 输出或用户报告中的模块 bug、参数错误、幂等性问题。
- 某个模块缺少 check mode、diff mode、DOCUMENTATION、EXAMPLES、RETURN 或 changelog fragment。
- 外部 API 变化导致已有模块认证、状态判断、分页或错误处理失效。
- 本地 ansible-test sanity、unit、integration 或幂等性测试暴露的问题。

建议修改方向：

- 优先给已有 module 补幂等性、check mode、diff mode、文档、返回值和测试。
- 新 module 要找到合适 collection，并证明它不是简单的一次性 API wrapper。
- 对 agent 系统，可以做管理 agent 任务配置、查询运行日志、触发分析或应用结果的 module。
- 敏感参数必须用 `no_log`，重复执行必须安全，返回值要稳定。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、ansible-test 失败、API 文档、幂等性复现或用户场景。
- 方案设计和影响范围，说明 module/plugin、参数、状态模型、check mode 和 diff mode。
- 代码或文档改动，包括 Python module、docs block、examples、RETURN、tests 和 changelog fragment。
- 测试和验证结果，例如 ansible-test sanity/unit/integration、幂等性测试和 secret 检查。
- PR 标题和 PR 描述，说明问题、方案、验证、兼容性和外部服务要求。

最终目标：提交一个符合 Ansible collection 质量要求、可被维护者 review 接受的 PR。
