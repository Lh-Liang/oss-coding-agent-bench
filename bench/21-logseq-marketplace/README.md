# Logseq Marketplace / Plugins

目标仓库：https://github.com/logseq/marketplace

## 1. 任务要求、问题来源和建议方向

你要在 Logseq Marketplace 或插件生态中寻找一个真实贡献点。Logseq 是本地优先、双链大纲式知识管理工具，以 block、页面、查询、日记和白板组织个人知识、任务和项目记录。Marketplace 仓库用于收录社区插件和主题。

你可以优先参考这些问题来源：

- Marketplace issue、PR review、插件作者反馈中的 metadata、release、图标、README 或 API 兼容问题。
- 某个已有插件在新版 Logseq 中 block/page 操作、设置项、命令或 UI 行为出错。
- 用户知识管理工作流中明确缺失的只读统计、任务同步、block 整理或开发记录插件。
- 本地测试 graph 中运行插件、读写 block、安装 release 或校验 metadata 时发现的问题。

建议修改方向：

- 优先修复已有 Marketplace 条目、插件 metadata、README、图标、release 或 API 兼容问题。
- 新插件要选择数据安全风险低、操作可理解、最好可撤销的知识工作流。
- 对 agent 系统，可以做任务运行记录写入 daily journal、PR/issue 同步、block 摘要或项目知识库整理。
- 用户 graph 是私有资产，批量写入必须有确认、范围限制和隐私说明。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、Marketplace 缺口、插件复现、API 文档或用户工作流。
- 方案设计和影响范围，说明 block/page 操作、设置项、联网行为、撤销策略和隐私影响。
- 代码或配置改动，包括插件源码、README、icon、release metadata 或 Marketplace entry。
- 测试和验证结果，例如本地加载、测试 graph 操作、metadata 校验和批量写入检查。
- PR 标题和 PR 描述，说明插件价值、数据访问范围、验证方式和限制。

最终目标：提交一个能被 Logseq Marketplace 或插件维护者接受、并安全服务用户知识库的 PR。
