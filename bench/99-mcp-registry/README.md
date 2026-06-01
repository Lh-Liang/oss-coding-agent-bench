# Model Context Protocol Registry

目标仓库：https://github.com/modelcontextprotocol/registry

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录该项目近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 MCP Registry 中寻找一个真实、范围清楚、维护者可能接受的贡献点。MCP Registry 是 Model Context Protocol 生态的官方 registry，用于发现、校验和发布 MCP server package。

你可以优先参考这些问题来源：

- issue、discussion、PR review 或 registry 文档中提到的 metadata、发布流程、API 或验证问题。
- package metadata validation 错误信息不清楚、边界输入未覆盖或 schema 行为和文档不一致。
- registry API 的分页、搜索、错误处理、namespace 或 package 状态边界。
- publisher tooling、示例 package、README 或客户端消费 registry 的文档缺口。

建议修改方向：

- 优先修复 registry service、metadata validation、API contract、publisher 流程或文档中的小问题。
- 对 validation 改动要补充失败样例和回归测试，并保持对已有 package 的兼容。
- 不要把 MCP 规范变更混入 registry 小 PR；规范问题应先找到对应 upstream 讨论。
- 不要只添加推广性质的 server 链接，除非项目明确接受此类 registry metadata PR。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、API 文档、复现请求、metadata 示例或测试失败。
- 方案设计和影响范围，说明涉及 API、schema、publisher、storage 或文档的边界。
- 代码或文档改动，包括 Go 代码、测试、schema/fixture、README 或示例。
- 验证结果，例如 Go tests、metadata validation、API contract test 或手动请求输出。
- PR 标题和 PR 描述，说明问题、方案、兼容性和风险。

最终目标：提交一个改进 MCP Registry 可靠性、发布体验或文档清晰度，并能被维护者接受的 PR。
