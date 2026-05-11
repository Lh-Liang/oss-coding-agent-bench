# Apache Camel Components

目标仓库：https://github.com/apache/camel

## 1. 任务要求、问题来源和建议方向

你要在 Apache Camel Components 中寻找一个真实贡献点。Camel 是企业集成框架，提供 Enterprise Integration Patterns，用路由把消息从一个系统读取、转换、过滤、聚合后发送到另一个系统。components 是连接器生态，封装 endpoint、producer、consumer、配置项、metadata、测试和文档。

你可以优先参考这些问题来源：

- Camel issue、PR review、组件文档生成、测试失败或 mailing list 中确认的 bug 和缺口。
- 某个已有 component 缺少 endpoint option 文档、错误处理、测试、示例、Spring Boot/Quarkus metadata。
- 某个开发工具、SaaS、LLM 平台或内部 API 有明确企业集成需求，但 Camel 缺少 component 或 route template。
- 本地 Maven test、license check、文档生成、dependency 分析或 integration test 暴露的问题。

建议修改方向：

- 优先给已有 component 补测试、option 文档、错误处理、metadata、examples 或兼容性修复。
- 新 component 最好先有 issue 或社区讨论，避免重复已有组件。
- 对 agent 系统，可以做 `agent:review`、`agent:summarize` 等 endpoint，或 route template 封装常见自动化流程。
- 企业集成场景重视稳定性、错误语义、依赖许可证和长期维护。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、文档缺口、测试失败、API 文档或用户集成场景。
- 方案设计和影响范围，说明 component、endpoint options、producer/consumer、依赖和兼容性。
- 代码或文档改动，包括 Java 模块、tests、docs、examples、metadata 或 route templates。
- 测试和验证结果，例如 Maven test、license check、文档生成、integration test 和依赖分析。
- PR 标题和 PR 描述，符合 Apache Camel 风格，说明问题、方案、验证和维护风险。

最终目标：提交一个结构化、可测试、能被 Camel 维护者认可的组件或文档改进 PR。
