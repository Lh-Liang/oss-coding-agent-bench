# MELPA Emacs Packages

目标仓库：https://github.com/melpa/melpa

## 1. 任务要求、问题来源和建议方向

你要在 MELPA 中寻找一个真实 Emacs package 收录或 recipe 贡献点。MELPA 是 Emacs 重要第三方包仓库，它通常不保存包源码，而是保存 recipe，告诉构建系统从上游 Git 仓库拉取哪些文件、如何构建并发布给 `package.el` 用户。

你可以优先参考这些问题来源：

- issue、PR review、MELPA build log 或包作者反馈中的 recipe 失效、repo 迁移、文件包含错误、autoload 问题。
- 某个成熟 Emacs 开发工具包已有稳定仓库、README、license、package headers，但尚未进入 MELPA。
- 已有 recipe 的 fetcher、repo、files、branch、version 规则不再匹配上游结构。
- 本地 recipe build、byte-compile、package-lint 或安装测试暴露的问题。

建议修改方向：

- 优先修复已有 recipe 的上游迁移、文件列表、依赖、autoloads、license 或构建问题。
- 新 recipe 前要确认上游包质量足够，包括 headers、README、license、autoloads、tag 和依赖。
- 对 agent 系统，可以做 Emacs 内 diff 总结、测试失败解释、commit message、PR review 或 issue workflow package。
- 不要提交只是 shell wrapper、没有 Emacs 生态约定或不可维护的随机包。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 build log、issue、上游 repo 变化、缺失包需求或 recipe 对比。
- 方案设计和影响范围，说明 recipe、files、dependencies、autoloads、license 和上游维护状态。
- 代码或配置改动，包括 MELPA recipe、必要的上游包修复说明、README 或 metadata。
- 测试和验证结果，例如 recipe build、byte-compile、package-lint、安装测试或限制说明。
- PR 标题和 PR 描述，包含包名、recipe 变化、验证方式和维护信息。

最终目标：提交一个可构建、可维护、符合 MELPA 收录习惯的 PR。
