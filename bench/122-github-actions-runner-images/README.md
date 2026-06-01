# GitHub Actions Runner Images

目标仓库：https://github.com/actions/runner-images

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录该项目近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 GitHub Actions Runner Images 中寻找一个真实 CI 环境贡献点。该仓库维护 GitHub-hosted runners 的 Ubuntu、Windows 和 macOS 镜像定义、预装工具、版本清单、安装脚本和验证逻辑。

你可以优先参考这些问题来源：

- issue、镜像构建日志或用户 CI 失败显示某工具安装、版本、路径或验证脚本有问题。
- software inventory、README 或生成文档中的版本/链接与实际镜像不一致。
- 某预装工具的下载 URL、checksum、安装方式或 validation test 过期。
- 运行环境差异导致 workflow 兼容性问题。

建议修改方向：

- 优先修复已有工具的安装脚本、版本文档、验证测试或下载源问题。
- 新增大型软件门槛高，不建议作为起步任务。
- 安装脚本要可靠、可缓存、可重复，避免不稳定源。
- 完整镜像构建成本高，至少验证脚本片段和 version command。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 runner OS、工具名、错误日志或文档不一致。
- 方案设计和影响范围，说明 image、install script、tool version 和 validation。
- 代码或文档改动，包括 PowerShell/Bash/Packer、tests、software inventory 或 README。
- 验证结果，例如脚本片段运行、version command、Pester/Bash validation 或 CI。
- PR 标题和 PR 描述，说明目标镜像、兼容性和风险。

最终目标：提交一个提升 GitHub-hosted runner 镜像可靠性或文档准确性的 PR。
