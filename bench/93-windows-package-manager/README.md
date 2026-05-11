# Windows Package Manager / winget-pkgs

目标仓库：https://github.com/microsoft/winget-pkgs

## 1. 任务要求、问题来源和建议方向

你要在 Windows Package Manager Community Repository 中寻找一个真实 package manifest 贡献点。`winget-pkgs` 保存 Windows 应用的安装包 URL、版本、hash、installer type、locale metadata、silent install 参数和验证规则。用户通过 `winget install` 和 `winget upgrade` 安装软件。

你可以优先参考这些问题来源：

- issue、PR review、bot validation、dynamic scan 或用户报告中的 hash、URL、installer type、silent switch 问题。
- 某个开源开发者工具已有稳定 Windows release，但 winget 缺少 manifest。
- 软件已有新版本发布，但 manifest 未更新、metadata 不完整或 locale 信息错误。
- 本地 `winget validate`、hash 校验、安装/卸载测试或 URL 可达性检查暴露的问题。

建议修改方向：

- 优先修复已有 package 的版本、URL、hash、locale metadata、installer switches 或 validation 错误。
- 新 manifest 前要确认软件有稳定公开下载地址、明确 license、publisher 和可验证 installer。
- 对 agent 系统，可以为成熟 Windows CLI、桌面端或后台服务准备 manifest。
- 不要使用临时链接、不可验证 installer 或没有静默安装能力的早期实验版本。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 release 页面、installer URL、旧 manifest 差异、validation 失败或用户报告。
- 方案设计和影响范围，说明 package identifier、版本、installer、locale metadata 和安装/卸载影响。
- 配置改动，包括 YAML manifests、hash、installer switches、locale 文件或 version metadata。
- 测试和验证结果，例如 `winget validate`、hash 校验、安装/卸载测试或无法本地验证的原因。
- PR 标题和 PR 描述，包含 package id、版本、验证结果和 validation 风险。

最终目标：提交一个能通过自动验证和维护者审查的 winget manifest PR。
