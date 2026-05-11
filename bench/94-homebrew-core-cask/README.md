# Homebrew Core / Cask

目标仓库：https://github.com/Homebrew/homebrew-core 和 https://github.com/Homebrew/homebrew-cask

## 1. 任务要求、问题来源和建议方向

你要在 Homebrew Core 或 Homebrew Cask 中寻找一个真实软件分发贡献点。Homebrew 是 macOS 和 Linux 上常用的软件包管理器，Core 维护 CLI、库和开发工具 formula，Cask 维护 macOS GUI 应用和二进制应用。用户通过 `brew install` 安装软件。

你可以优先参考这些问题来源：

- issue、PR review、BrewTestBot、audit 输出或用户报告中的构建失败、测试失败、依赖错误或版本更新失败。
- 某个成熟开源开发工具已发布稳定版本，但 formula/cask 缺失或 metadata 过旧。
- 已有 formula test block 不能验证功能，或 cask 的 url、sha256、livecheck、zap 配置不完整。
- 本地 `brew audit`、`brew test`、安装、版本 bump 或 CI 结果暴露的问题。

建议修改方向：

- 优先修复已有 formula/cask 的 audit、test、依赖、patch、livecheck 或 version bump 问题。
- 新 formula 要满足 Acceptable Formulae，包括稳定 tag、license、notability、源码构建和平台支持。
- GUI 应用优先走 cask，CLI 或库优先走 formula。
- 对 agent 系统，只有成熟 CLI、daemon 或桌面工具适合投 core/cask；早期项目可先考虑自己的 tap。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、release 页面、audit/test 失败、版本差异或用户安装失败。
- 方案设计和影响范围，说明选择 core 还是 cask、依赖、构建方式、测试方式和平台影响。
- 配置改动，包括 formula/cask、test block、livecheck、patch、resource 或 metadata。
- 测试和验证结果，例如 `brew audit`、`brew test`、本地安装、版本 bump 或 CI 说明。
- PR 标题和 PR 描述，包含软件名、版本/修复点、验证命令和风险。

最终目标：提交一个符合 Homebrew 接受标准、能被维护者 review 接受的 PR。
