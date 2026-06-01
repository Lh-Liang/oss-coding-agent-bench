# Nixpkgs

目标仓库：https://github.com/NixOS/nixpkgs

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录该项目近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 Nixpkgs 中寻找一个真实可复现 packaging 或 NixOS module 贡献点。Nixpkgs 是 Nix/NixOS 的核心 package collection 和模块仓库，包含软件包定义、构建逻辑、patch、测试和系统模块。

你可以优先参考这些问题来源：

- broken package、版本更新、缺失依赖、hash 变化、构建失败或 runtime smoke test 失败。
- 上游 release、issue、Nixpkgs review 或用户报告显示某工具适合新增/修复。
- NixOS module 缺少 option、test、文档或兼容性修复。
- package metadata、license、platforms、maintainers 或 homepage 不准确。

建议修改方向：

- 优先做小型 CLI/package 更新、构建修复、缺失 runtime dependency 或 metadata 修正。
- 新 package 要有稳定 release、清楚 license、可复现构建和维护意愿。
- 避免 vendored binary、网络访问、不可复现生成或过大依赖闭包。
- 尽量用 nixpkgs-review 和 smoke test 验证。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括上游 release、build log、issue 或 broken package 信息。
- 方案设计和影响范围，说明 derivation、dependencies、platforms、module option 或 patch。
- Nix 代码或文档改动，包括 package/module、tests、meta 和 maintainers。
- 验证结果，例如 nix-build、nixpkgs-review、package smoke test 或 NixOS VM test。
- PR 标题和 PR 描述，说明构建平台、测试结果和维护风险。

最终目标：提交一个符合 Nixpkgs 规范、可复现构建并能通过 review 的 PR。
