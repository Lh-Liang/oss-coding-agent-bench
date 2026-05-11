# openHAB Add-ons

目标仓库：https://github.com/openhab/openhab-addons

## 1. 任务要求、问题来源和建议方向

你要在 openHAB Add-ons 中寻找一个真实贡献点。openHAB 是开源智能家居自动化平台，用 Thing、Channel、Item、Rule、UI 和 Add-on 组织设备和自动化。Add-ons 仓库维护官方发行版中的 bindings 和扩展，binding 负责把设备品牌、协议、云 API 或服务接入 openHAB。

你可以优先参考这些问题来源：

- issue、forum 讨论、PR review 或用户日志中的 binding bug、认证失败、discovery 问题、状态不同步。
- 某个设备或云服务 API 变化后，handler、ThingType、Channel、配置或 README 没有同步。
- 已有 binding 缺少 i18n、README、mock 测试、ThingType 文档、错误处理或兼容新版 openHAB。
- 本地 Maven test、XML schema、mock 响应或边界配置暴露的问题。

建议修改方向：

- 优先修复已有 binding 的解析错误、状态映射、配置校验、README 示例、测试或 i18n。
- 新 binding 要选择 API 稳定、文档公开、测试条件明确的设备或服务。
- 对 agent 系统，可以做只读状态摘要、能耗分析、自动化失败解释或设备健康 add-on。
- 门锁、安防、电器等高风险控制动作必须保守，默认避免无确认写操作。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、设备/API 文档、日志、测试失败或同类 binding 对比。
- 方案设计和影响范围，说明 binding、ThingType、Channel、handler、配置和兼容性。
- 代码或文档改动，包括 Java/OSGi 代码、XML、README、i18n、tests 或 examples。
- 测试和验证结果，例如 Maven test、目标 module 测试、XML 校验或手动复现。
- PR 标题和 PR 描述，说明设备/服务、修复点、验证方式和安全边界。

最终目标：提交一个符合 openHAB add-on 规范、可测试、能被维护者接受的 PR。
