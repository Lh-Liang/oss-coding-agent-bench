# HACS Default Repositories

目标仓库：https://github.com/hacs/default

## 1. 任务要求、问题来源和建议方向

你要在 HACS default repositories 或 Home Assistant 社区集成生态中寻找一个真实贡献点。HACS 是 Home Assistant Community Store，用于安装社区自定义集成、前端插件、主题和模板。`hacs/default` 维护默认可搜索安装的社区仓库列表，是官方 Core 之前更现实的社区分发路径。

你可以优先参考这些问题来源：

- `hacs/default` PR、issue 或 HACS 发布要求中的仓库结构、manifest、release、README、hacs.json 问题。
- 某个社区集成或 Lovelace card 缺少配置流、文档、安装说明、license、release 或维护信息。
- Home Assistant 社区已有设备/API 需求，但尚未有质量足够的 HACS 集成。
- 本地 HACS validation、Home Assistant 加载、manifest 校验或文档链接检查发现的问题。

建议修改方向：

- 优先修复已有 HACS 项目的文档、manifest、release、hacs.json、配置流或加载问题。
- 新增 default repository 前，确保项目已公开、可安装、有 release、README、license 和活跃维护。
- 对 agent 系统，可以做只读传感器、自定义卡片、任务状态 Lovelace card 或设备诊断集成。
- HACS 不是官方质量背书，但用户会在真实家庭环境安装，所以安全和维护说明要清楚。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括 HACS 要求、issue、加载失败、用户需求或仓库缺口。
- 方案设计和影响范围，说明集成类型、实体、前端卡片、发布材料和维护边界。
- 代码或配置改动，包括 custom integration/card、README、release、hacs.json 或 default entry。
- 测试和验证结果，例如 HACS validation、Home Assistant 本地加载、manifest 校验和链接检查。
- PR 标题和 PR 描述，说明仓库价值、验证方式、安装路径和安全限制。

最终目标：提交一个符合 HACS default 要求、能让用户可靠安装社区项目的 PR。
