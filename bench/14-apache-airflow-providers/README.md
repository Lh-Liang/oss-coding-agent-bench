# Apache Airflow Providers

目标仓库：https://github.com/apache/airflow

## 1. 任务要求、问题来源和建议方向

你要在 Apache Airflow Providers 中寻找一个真实贡献点。Airflow 用 Python DAG 编排数据管道、定时任务、批处理、训练、报表和外部 API 调用。Providers 是 Airflow 的扩展包体系，包含 Hook、Operator、Sensor、Transfer、Connection UI 和文档，用来接入云平台、数据库、SaaS、消息队列和数据工具。

你可以优先参考这些问题来源：

- Airflow issue、provider issue、PR review 或系统测试中确认的 provider bug、分页、认证、异步、deferrable operator 问题。
- 某个 Hook/Operator/Sensor 的文档、示例 DAG、连接字段、template fields 或错误处理不完整。
- 外部服务 API 发生变化，而已有 provider 未支持新字段、endpoint 或兼容逻辑。
- 本地 pytest、provider docs build、import check 或示例 DAG 校验暴露的问题。

建议修改方向：

- 优先给已有 provider 补小 Operator、分页修复、类型标注、deferrable sensor、测试或示例 DAG。
- 新 provider 要先做 custom provider 原型，并确认社区愿意维护。
- 对 agent 系统，可以做提交任务、等待完成、下载结果、生成报告的 Hook/Operator/Sensor。
- 注意 Airflow 调度语义，Operator 不应随意长时间阻塞，连接和 secret 处理要规范。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、API 文档、测试失败、文档缺口或可复现 DAG。
- 方案设计和影响范围，说明 Hook、Operator、Sensor、Connection、依赖和兼容性。
- 代码或文档改动，包括 provider 代码、tests、system tests、example DAG、docs 或 metadata。
- 测试和验证结果，例如 pytest、provider docs build、import check 或手动 DAG 验证。
- PR 标题和 PR 描述，符合 Apache Airflow 贡献风格，说明验证和风险。

最终目标：提交一个结构清楚、测试充分、能被 Airflow provider 维护者接受的 PR。
