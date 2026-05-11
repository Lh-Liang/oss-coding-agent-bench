# Home Assistant Core / Integrations

目标仓库：https://github.com/home-assistant/core

## 1. 任务要求、问题来源和建议方向

你要在 Home Assistant Core 中寻找一个真实、范围清楚、维护者可能接受的贡献点。Home Assistant 是本地优先的智能家居自动化平台，核心仓库维护大量官方集成，用来接入设备品牌、协议、云服务、能源平台、传感器和自动化能力。你的任务不是随意生成一个新集成，而是基于代码、issue、文档、质量等级和近期 PR 风格，找到一个值得提交 PR 的问题。

你可以优先参考这些问题来源：

- 已有 issue、integration 维护者评论或用户日志中确认的 bug、API 兼容问题、配置流问题、实体状态错误。
- Integration Quality Scale 中缺失的测试、diagnostics、repairs、translations、config flow 或实体命名规范。
- 某个第三方设备或云 API 已变化，而现有集成没有同步支持。
- 本地 pytest、fixture、边界输入或错误分支暴露出的回归风险。

建议修改方向：

- 优先修复已有集成的小问题，例如 API 字段变化、错误处理、唯一 ID、配置流提示、状态映射或文档示例。
- 为已有集成补测试 fixture、错误分支测试、诊断数据脱敏或质量等级缺口。
- 全新官方集成门槛较高，除非有稳定 API、真实设备或样例响应、维护意愿和充分测试。
- 涉及门锁、安防、电器等真实家庭设备时，写操作必须保守，并说明风险边界。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 issue、日志、API 文档、质量等级缺口或可复现测试。
- 方案设计和影响范围，说明涉及的 integration、平台、实体、配置和兼容性。
- 代码或文档改动，包括 Python 代码、fixture、测试、翻译、manifest 或文档。
- 测试和验证结果，至少记录运行过的 pytest、lint 或手动复现步骤。
- PR 标题和 PR 描述，清楚说明问题、方案、验证方式和风险。

最终目标：提交一个符合 Home Assistant 规范、能通过 review 和 CI、并尽可能被维护者接受或合并的 PR。
