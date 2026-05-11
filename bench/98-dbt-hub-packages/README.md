# dbt Hub Packages

目标仓库：https://github.com/dbt-labs/hub.getdbt.com

## 1. 任务要求、问题来源和建议方向

你要在 dbt Hub Packages 中寻找一个真实 package 收录或 metadata 贡献点。dbt 是数据转换和 analytics engineering 工具，用户用 models、macros、tests、seeds 和 docs 把数据仓库中的原始数据建模成可测试、可复用的数据资产。dbt Hub 是社区 package 的发现入口。

你可以优先参考这些问题来源：

- issue、PR review、Hub 页面或 package 作者反馈中的 metadata 错误、版本缺失、README 渲染问题、链接失效。
- 某个成熟 dbt package 已有稳定 repo、license、tag、README 和测试，但尚未进入 Hub。
- 已有 package 的 compatibility、latest version、repository URL 或 docs 与上游不一致。
- 本地 `dbt deps`、`dbt compile`、`dbt test` 或 Hub index 格式检查暴露的问题。

建议修改方向：

- 优先修复已有 package 的索引 metadata、版本、链接、文档渲染或 dev/docker 环境问题。
- 新 package 前要确认上游有 `dbt_project.yml`、README、license、版本 tag 和可运行测试。
- 对 agent 系统，可以做 engineering analytics package，建模 PR、issue、CI、incident 或 agent task 数据。
- 不要把 Hub 收录描述成安全认证，PR 中要准确说明它是官方索引接收。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 Hub 页面差异、issue、上游 package 信息、版本 tag、运行失败或同类 package 对比。
- 方案设计和影响范围，说明 package、metadata、版本、兼容 dbt 版本、warehouse 支持和用户影响。
- 代码或配置改动，包括 Hub index 条目、metadata、README/docs、dev/docker 配置或 package 修复说明。
- 测试和验证结果，例如 index 格式检查、`dbt deps/compile/test`、链接检查或无法完整验证的原因。
- PR 标题和 PR 描述，包含 package 名、metadata 变化、验证方式和 Hub 收录边界。

最终目标：提交一个能让 dbt 用户更可靠发现、安装或理解 package 的 PR。
