# Sublime Text Package Control

目标仓库：https://github.com/sublimehq/package_control_channel

## 1. 任务要求、问题来源和建议方向

你要在 Sublime Text Package Control 生态中寻找一个真实贡献点。Sublime Text 是轻量快速的代码编辑器，Package Control 是事实标准包管理器。`package_control_channel` 维护可安装包索引，用户通过它安装语法包、主题、命令、lint/build 集成和编辑器工具。

你可以优先参考这些问题来源：

- Package Control channel PR、issue 或包作者反馈中的索引格式、仓库迁移、版本 tag、许可证或安装问题。
- 某个已有 Sublime package 的语法规则、命令、菜单、README、Python runtime 兼容或测试样例缺失。
- 小众语言、配置格式、agent report 格式或开发工具缺少 Sublime 语法/命令支持。
- 本地安装包、运行命令、校验 channel JSON 或跨平台路径时暴露的问题。

建议修改方向：

- 优先修复已有 package entry 的仓库地址、metadata、版本和安装问题。
- 新包要有公开仓库、license、README、版本 tag，并能在 Sublime 中实际安装运行。
- 对 agent 系统，可以做选区解释、diff 总结、测试失败说明、任务状态查询或轻量命令包。
- 避免危险文件操作和不透明网络请求，外部 agent 调用要有配置和隐私说明。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、安装失败、索引差异、包缺口或可复现行为。
- 方案设计和影响范围，说明 package、命令、语法、配置、平台和用户操作路径。
- 代码或配置改动，包括 package 源码、syntax、menus/keymaps、README 或 channel entry。
- 测试和验证结果，例如本地加载、命令执行、Package Control JSON 校验和跨平台检查。
- PR 标题和 PR 描述，说明包名、变更原因、验证方式和安全边界。

最终目标：提交一个让 Sublime 用户能可靠安装或使用插件/语法包的 PR。
