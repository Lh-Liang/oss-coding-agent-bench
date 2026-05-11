# Elastic Integrations

目标仓库：https://github.com/elastic/integrations

## 1. 任务要求、问题来源和建议方向

你要在 Elastic Integrations 中寻找一个真实贡献点。Elastic Integrations 是 Elastic Agent / Fleet 的 package 生态，帮助用户把云服务、Kubernetes、数据库、应用日志、安全产品或自定义系统的数据采集进 Elasticsearch。一个 package 通常包含 manifest、data streams、fields、ingest pipeline、sample events、tests、dashboard 和文档。

你可以优先参考这些问题来源：

- integrations 仓库 issue、PR review、CI 失败中的 package-spec、ECS 字段、pipeline、sample event 或 dashboard 问题。
- 某个已有 package 对新版日志格式解析失败、字段映射不完整、expected output 过期。
- 某个开源服务、开发工具、CI 或 agent 系统缺少日志/指标 integration。
- 本地 `elastic-package test`、pipeline test、static check 或 sample 数据脱敏检查暴露的问题。

建议修改方向：

- 优先给已有 integration 补 sample event、pipeline test、fields、dashboard、README 或解析 bugfix。
- 新 package 要有稳定数据来源、清晰字段含义和可脱敏的样例数据。
- 对 agent 系统，可以采集工具调用、模型延迟、任务失败、代码修改、审查结果和安全审计事件。
- ECS 建模要谨慎，字段命名、类型、单位和高基数风险都要说明。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、日志样例、pipeline 失败、字段缺口或观测场景。
- 方案设计和影响范围，说明 package、data stream、fields、pipeline、dashboard 和兼容版本。
- 代码或文档改动，包括 manifest、fields、ingest pipeline、sample events、expected output、docs 或 dashboard。
- 测试和验证结果，例如 `elastic-package test`、pipeline test、static checks、ECS 映射和脱敏检查。
- PR 标题和 PR 描述，说明数据来源、解析逻辑、验证方式和隐私风险。

最终目标：提交一个能通过 Elastic package review、让用户可靠采集和分析数据的 PR。
