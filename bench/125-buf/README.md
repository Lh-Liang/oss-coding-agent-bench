# Buf

目标仓库：https://github.com/bufbuild/buf

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录该项目近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 Buf 中寻找一个真实 Protobuf schema 工具链贡献点。Buf 提供 lint、breaking change detection、format、generate、module registry 和 plugin workflow，帮助团队治理 Protobuf API schema。

你可以优先参考这些问题来源：

- issue、真实 `.proto` 文件或 CLI 输出显示 lint/breaking/format/generate 行为错误。
- nested messages、reserved fields、oneof、editions、comments、config v2 或 plugin generation 边界未覆盖。
- Breaking change detection 有误报/漏报，或错误信息未指出具体字段路径。
- CLI docs、config 示例、registry workflow 或 plugin 文档不足。

建议修改方向：

- 优先修复已有 lint/breaking/format/CLI 行为的小边界，并补 proto fixture。
- Breaking change 判断要保守且准确，说明兼容性影响。
- Formatter 输出稳定性敏感，避免无关格式变化。
- Registry/remote module 行为需要明确是否能本地或集成测试验证。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 proto 样例、buf.yaml、当前 CLI 输出或 issue。
- 方案设计和影响范围，说明 lint/breaking/format/generate 或 docs 变化。
- 代码或文档改动，包括 Go 实现、fixtures、expected output、docs 或 examples。
- 验证结果，例如 go test、buf lint/breaking/generate 或 fixture output diff。
- PR 标题和 PR 描述，说明 schema 语义、兼容性和风险。

最终目标：提交一个提升 Buf schema 检查、兼容性判断、生成流程或文档质量的 PR。
