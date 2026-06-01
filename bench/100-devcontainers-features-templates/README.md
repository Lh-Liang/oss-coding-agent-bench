# Dev Container Features and Templates

目标仓库：https://github.com/devcontainers/features  
辅助仓库：https://github.com/devcontainers/templates

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录该项目近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 Dev Container Features 或 Templates 中寻找一个真实贡献点。Dev Containers 用 `.devcontainer/devcontainer.json` 描述可复现开发环境，Features 和 Templates 是复用工具链安装与项目起步配置的官方入口。

你可以优先参考这些问题来源：

- issue、CI 失败、用户复现日志或 README 中提到的 feature/template 兼容问题。
- feature install script 在某个 Linux 发行版、CPU 架构、shell 选项或工具版本上失败。
- metadata、options、documentationURL、README 示例或 test scenario 缺失。
- template 中基础镜像、工具版本、端口、features 或验证命令过期。

建议修改方向：

- 优先修复已有 feature/template 的兼容性、幂等性、错误信息、metadata 或测试。
- 新 feature 要谨慎；官方仓库不一定接受 niche 工具，必要时先做独立 feature repo。
- 安装第三方二进制要注意来源、checksum、license、版本策略和多架构。
- 对脚本改动要补充 devcontainer CLI test 或最小 smoke test。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、构建日志、目标平台和失败命令。
- 方案设计和影响范围，说明 feature/template、发行版、架构和工具版本。
- 代码或文档改动，包括 install script、metadata、README、test scenario 或 template 文件。
- 验证结果，例如 devcontainer CLI test、container build、shellcheck 或工具 smoke test。
- PR 标题和 PR 描述，说明兼容性、验证范围和未覆盖平台。

最终目标：提交一个提升 Dev Container feature/template 可复现性和可维护性的 PR。
