# Renovate

目标仓库：https://github.com/renovatebot/renovate

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录该项目近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 Renovate 中寻找一个真实依赖自动化贡献点。Renovate 会扫描仓库中的依赖文件，查询新版本，生成更新 PR，并按配置执行分组、排期和自动合并。

你可以优先参考这些问题来源：

- issue、discussion 或真实项目文件显示某 manager、datasource、versioning 或 preset 行为错误。
- package file 未被识别、dependency extraction 误报/漏报、版本比较错误或 registry API 行为变化。
- 文档中 custom manager、配置选项、troubleshooting 或 datasource 行为说明不足。
- fixture 或 dry-run 结果和真实生态版本语义不一致。

建议修改方向：

- 优先修复已有 manager/datasource/versioning 的小 bug，并补 fixtures 和 Jest tests。
- 新 manager 或 datasource 要有明确用户需求和稳定 registry/API。
- Extraction 逻辑要避免过宽匹配，防止为用户生成错误 PR。
- 外部 API 查询要考虑缓存、分页、404、限流和认证边界。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、真实文件样例、registry 响应或 dry-run 输出。
- 方案设计和影响范围，说明 manager、datasource、versioning、preset 或 docs 变化。
- 代码或文档改动，包括 TypeScript 逻辑、fixtures、tests 和配置文档。
- 验证结果，例如 targeted Jest tests、lint/typecheck、fixture snapshot 或 dry-run。
- PR 标题和 PR 描述，说明依赖类型、兼容性和误报风险。

最终目标：提交一个能提高 Renovate 依赖识别、版本查询或用户配置可靠性的 PR。
