# Scoop Buckets

目标仓库：https://github.com/ScoopInstaller/Main  
辅助仓库：https://github.com/ScoopInstaller/Extras

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录该项目近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 Scoop official buckets 中寻找一个真实 Windows packaging 贡献点。Scoop bucket manifest 用 JSON 描述软件下载 URL、版本、hash、bin、persist、installer、checkver 和 autoupdate 规则。

你可以优先参考这些问题来源：

- 上游 Windows CLI/工具已有稳定 release，但 bucket manifest 缺失或过期。
- manifest URL/hash、checkver、autoupdate、bin shim、persist、shortcuts 或 installer 行为失败。
- issue、CI、用户报告或 release asset 改名导致安装失败。
- Main/Extras bucket 中 manifest metadata、license 或架构支持不准确。

建议修改方向：

- 优先修复已有 manifest 的版本、hash、autoupdate、URL 或安装行为。
- 新 manifest 要选择成熟、可分发、license 清楚且适合对应 bucket 的软件。
- Windows installer 静默参数、portable 行为和架构 asset 要本地验证。
- Hash 和下载 URL 必须稳定，避免依赖不确定动态链接。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括上游 release、安装失败、issue 或 manifest 缺口。
- 方案设计和影响范围，说明 bucket、manifest、架构、installer 和 autoupdate。
- Manifest 或文档改动，包括 JSON、checkver/autoupdate、bin、persist 和 shortcuts。
- 验证结果，例如 scoop install/uninstall、hash check、CLI smoke test 或 bucket tests。
- PR 标题和 PR 描述，说明安装验证、版本来源和平台限制。

最终目标：提交一个能让 Scoop 用户可靠安装或更新目标工具的 PR。
