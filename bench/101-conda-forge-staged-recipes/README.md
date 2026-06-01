# conda-forge Staged Recipes

目标仓库：https://github.com/conda-forge/staged-recipes

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录该项目近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 conda-forge staged-recipes 中寻找一个真实 packaging 贡献点。staged-recipes 是新增 conda-forge package 的入口，合并后会生成独立 feedstock 并进入 conda-forge 分发体系。

你可以优先参考这些问题来源：

- 一个成熟开源工具已有稳定 release、license 和源码归档，但尚未进入 conda-forge。
- staged recipe 或 feedstock PR 中暴露的依赖、license、source hash、平台构建或测试问题。
- 用户 issue、项目文档或同类 package 显示某工具适合 conda-forge 分发。
- 已有 recipe 缺少 import/CLI test、run dependency 或 metadata。

建议修改方向：

- 优先新增或修复范围小、构建方式清楚、license 明确的软件包。
- Recipe 必须声明准确的 source hash、license、host/run dependencies、tests 和 maintainers。
- 二进制包和复杂 C/C++/Rust 依赖要谨慎，避免无法在 CI matrix 中稳定构建。
- 记录你愿意承担 feedstock 后续维护责任的边界。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括上游 release、license、用户需求或构建失败。
- 方案设计和影响范围，说明 package name、版本、构建系统、依赖和平台。
- Recipe 或修复改动，包括 `recipe.yaml`/`meta.yaml`、build script、tests 和 metadata。
- 验证结果，例如 conda build/rattler-build、import test、CLI smoke test 或 CI 结果。
- PR 标题和 PR 描述，说明 package 用途、验证方式和维护风险。

最终目标：提交一个符合 conda-forge 规范、能通过 CI 和 review 的 recipe/feedstock PR。
