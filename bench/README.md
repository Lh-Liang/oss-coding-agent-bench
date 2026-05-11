# oss-coding-agent-bench

## 目标

这个 benchmark 用来评估软件开发 agent 在真实 GitHub 开源项目中的端到端贡献能力。

每个项目目录对应一个真实开源项目。agent 的任务不是完成玩具题，也不是维护一份完整仓库副本，而是在真实仓库中找到一个值得维护者接受的问题，完成代码、测试、文档或配置修改，生成一个可审查、可应用的 PR patch，并尽可能提交 Pull Request。

最终目标是 PR 被项目维护者接受或合并。执行过程中应尽量让每个项目沉淀约 20 个高质量 patch/PR task，但不得为了数量降低问题价值或交付质量。

## 核心原则

- 真实 PR 导向：每个 task 默认服务于一个可以提交给上游项目的 PR。
- Patch 为核心交付物：benchmark 目录只保存任务元数据、索引摘要和 `patches/*.patch`，不保存完整目标仓库。
- 可复现基线：每个 task 必须记录 `base_commit`，patch 应能从该 commit 的干净 checkout 上应用。
- 证据优先：每个 task 必须有真实问题来源和证据，不得伪造 issue、用户反馈、benchmark、测试结果或维护者意见。
- 验证清楚：每个 task 必须记录验证命令、验证结果和未覆盖风险。
- 范围克制：优先选择小而完整的改动，避免无关重构、纯格式化和没有用户价值的依赖噪音。

## 问题来源

可以从以下视角寻找任务。优先选择证据充分、范围清楚、维护者更可能接受的问题。

### 1. 已有 Issue

从仓库已有 issue、discussion、roadmap、TODO、PR review 或维护者评论中选择任务。

可接受证据包括：

- issue 明确描述 bug、缺失功能、兼容性问题或文档缺口。
- issue 带有 `good first issue`、`help wanted`、`bug`、`enhancement`、`documentation` 等标签。
- 维护者在评论中确认问题存在或欢迎贡献。
- 近期重复出现的用户报告、失败日志或使用困惑。

### 2. 有实质证据的缺失功能

如果仓库没有现成 issue，可以通过对比证明项目缺少一个合理功能。

可接受证据包括：

- 同类项目已经支持该功能，而目标项目没有。
- 目标项目文档、API、插件机制或配置结构暗示应该支持该能力。
- 用户在 issue、讨论区、论坛、文档评论或第三方使用案例中表达过需求。
- 项目已有相邻功能，但缺少一个自然补齐的场景、选项、平台、格式或集成。

这类任务必须避免凭空发明需求。PR 描述中要写清楚对比对象、用户场景和为什么该功能适合目标项目。

### 3. 项目本身的 Bug

可以通过阅读代码、运行测试、复现 issue、分析边界条件或检查近期变更发现 bug。

可接受证据包括：

- 可复现的报错、失败测试、异常输出或崩溃。
- 代码逻辑与文档、类型定义、配置说明或 API 契约不一致。
- 边界条件未处理，例如空输入、缺失配置、权限错误、网络失败、版本兼容问题。
- 近期 PR 引入的回归风险。

bug 修复应尽量包含回归测试。回归测试只能证明覆盖到的行为没有复发，不能证明所有功能都被覆盖。

### 4. 更好的算法或数据处理方案

如果项目的核心逻辑、调度策略、解析器、匹配规则、排序逻辑、缓存策略、压缩/索引方式、搜索方法或某类数据处理流程使用了一个已有算法，可以在有证据的前提下提出更好的算法或实现方案。

可接受证据包括：

- 当前算法在真实项目场景中存在可复现的性能、准确性、稳定性、内存占用或边界条件问题。
- 同类项目、标准库、论文、成熟工程实践或项目自身其他模块已经采用了更合适的算法。
- benchmark、profile、测试数据或复杂度分析表明替换方案能带来实际收益。
- 新算法能修复当前实现无法正确处理的某类输入、规模、顺序、编码、并发或异常数据。

这类任务必须避免只凭“理论上更先进”就改动核心逻辑。PR 描述中要写清楚当前算法的问题、替代方案的依据、收益、兼容性风险和验证方式。涉及行为变化时，应补充回归测试、benchmark 或对比测试。

### 5. 其他高质量视角

也可以选择其他更好的贡献切入点，但必须能说明真实价值。

例如：

- 测试覆盖缺口：为已有行为补关键测试。
- 文档缺口：补充会影响用户成功使用的说明，而不是只做措辞润色。
- CI/构建问题：修复 flaky test、依赖升级、平台兼容或发布流程问题。
- 安全和隐私问题：修复权限、凭证、日志泄露、输入校验等风险。
- 性能或可维护性问题：必须有 profile、benchmark、复杂度证据或维护者认可。

## 基本工作流程

对于每个项目中的每个 task，应按以下流程执行：

1. 调研真实项目的代码、贡献指南、PR 模板、测试说明、近期 PR 风格和维护者偏好。
2. 选择一个有证据的问题，记录 `problem_statement`、证据链接、影响范围和预期改动。
3. 确定 `base_commit`，作为 patch 应用和验证的固定基线。
4. 在临时 clone、临时 worktree 或其他外部开发目录中实现改动。
5. 补充或更新必要的测试、文档、示例、配置或 changelog。
6. 在临时仓库中使用 `git diff --binary --full-index` 生成一个完整 PR patch，并把输出保存到 benchmark 项目目录的 `patches/Txxx-short-slug.patch`。
7. 从干净 checkout 的 `base_commit` 验证 `git apply --check <patch_path>`，然后应用 patch 并运行测试、构建或 lint。
8. 更新 `tasks.jsonl`、`TASKS.md` 和 `SUMMARY.md`，记录 patch 路径、验证命令、验证结果和状态。
9. 从同一 diff 创建真实 PR，准备 PR 标题和描述，并在提交后记录 `pr_url`。

PR 提交即为该 task 在 benchmark 执行周期内的终点。不要依赖维护者反馈再修复明显问题；提交前必须完成充分测试、自查和 PR 材料准备。

## 项目目录规范

每个项目目录应作为轻量索引目录维护。目标仓库代码应放在临时 clone 或外部 worktree 中，不应复制或长期维护在 benchmark 目录内。

推荐目录结构：

```text
PROJECT/
  README.md
  TASKS.md
  tasks.jsonl
  SUMMARY.md
  patches/
    T001-short-slug.patch
```

各文件用途如下：

- `README.md`：稳定任务说明，说明该项目的目标仓库、问题来源、建议修改方向、交付要求和最终目标。不要把执行过程写入这个文件。
- `TASKS.md`：人工可读任务池，只同步高层信息，包括 task 标题、来源类型、证据摘要、patch 路径、验证状态和 PR 状态。
- `tasks.jsonl`：机器可读主记录，每行一个 task，用于统计、评估、自动化筛选和复现。
- `SUMMARY.md`：项目级执行汇总，记录候选数、已产出 patch 数、验证通过数、已开 PR 数、accepted/merged 数、主要失败原因和后续高价值方向。
- `patches/`：保存该项目所有 task 的完整 PR patch。每个 task 对应一个 `Txxx-short-slug.patch`。


## Patch 规范

每个 `patches/Txxx-short-slug.patch` 必须是一个完整 PR diff，包含提交给上游 PR 所需的全部改动，例如代码、测试、文档、配置、fixture、schema、changelog 或示例。

从临时仓库中生成 patch 的推荐命令：

```bash
git diff --binary --full-index > <benchmark_project>/patches/T001-short-slug.patch
```

patch 质量要求：

- 必须能从 `base_commit` 的干净 checkout 上应用。
- 应通过 `git apply --check` 验证。
- 不得混入无关格式化、调试输出、本地环境文件、密钥、缓存或生成噪音。
- 应尽量保持范围小而完整，方便维护者 review。
- 如果包含二进制或 fixture 改动，应使用 `--binary --full-index` 保留可应用性。
- patch 文件名应和 `tasks.jsonl` 中的 `id` 一致，例如 `T001-fix-timeout-handling.patch`。

如果上游 PR 最终需要多个 commit，benchmark 中仍以一个完整 PR patch 表达该 task 的最终差异。

## `tasks.jsonl` 字段

`tasks.jsonl` 是每个项目的机器可读主记录。每行是一个 JSON object，字段固定如下：

```json
{
  "id": "T001",
  "title": "Fix timeout handling in example connector",
  "repo_url": "https://github.com/example/project",
  "base_commit": "0123456789abcdef0123456789abcdef01234567",
  "source_type": "issue",
  "problem_statement": "Users see a timeout error when ...",
  "evidence_urls": ["https://github.com/example/project/issues/123"],
  "evidence_summary": "The issue includes a reproducible timeout report and maintainer confirmation.",
  "expected_change": "Handle retryable timeout errors and add a regression test.",
  "patch_path": "patches/T001-fix-timeout-handling.patch",
  "validation_commands": [
    "git apply --check <benchmark_project>/patches/T001-fix-timeout-handling.patch",
    "pytest tests/test_timeout.py"
  ],
  "validation_result": "pass: patch applies cleanly; targeted pytest passed",
  "status": "validated",
  "pr_url": "",
  "notes": "Validation performed from a clean checkout of base_commit."
}
```

字段含义：

- `id`：稳定 task 编号，使用 `T001`、`T002` 等格式。
- `title`：简短任务标题，应适合作为 PR 标题基础。
- `repo_url`：真实目标仓库 URL。
- `base_commit`：patch 应用和验证的固定基线 commit。
- `source_type`：问题来源类型，例如 `issue`、`bug`、`missing_feature`、`test_gap`、`documentation`、`ci`、`security`、`performance`、`maintenance`。
- `problem_statement`：清楚描述要解决的问题，相当于 SWE-bench 中的 issue 描述。
- `evidence_urls`：证据链接列表，可为空数组但不能伪造。
- `evidence_summary`：证据摘要，说明为什么这是项目真实需要解决的问题。
- `expected_change`：预期改动范围和完成标准。
- `patch_path`：相对项目目录的 patch 路径。
- `validation_commands`：实际或计划运行的验证命令。
- `validation_result`：验证结果摘要，必须如实记录失败、跳过或未能运行的部分。
- `status`：task 当前状态。
- `pr_url`：真实 PR URL，未提交时为空字符串。
- `notes`：其他必要备注，例如环境限制、风险边界或后续观察。

## `TASKS.md` 和 `SUMMARY.md`

`TASKS.md` 面向人工阅读，应保持简洁。建议使用表格：

```markdown
| ID | Title | Source | Evidence | Patch | Validation | PR | Status |
| --- | --- | --- | --- | --- | --- | --- | --- |
| T001 | Fix timeout handling | issue | #123 | patches/T001-fix-timeout-handling.patch | pytest passed | pending | validated |
```

`SUMMARY.md` 面向项目级复盘和统计，应记录：

- 目标 PR 数量和当前完成度。
- 候选 task 数、已产出 patch 数、验证通过数、已开 PR 数。
- 已 accepted、merged、rejected 或 abandoned 的数量。
- 主要失败原因，例如证据不足、环境不可复现、patch 无法应用、测试失败、维护者拒绝。
- 后续高价值方向。

## 状态定义

统一 task 状态如下：

- `candidate`：已发现候选问题，但未决定执行。
- `selected`：已选中，准备实现。
- `in_progress`：正在临时仓库或 worktree 中实现。
- `blocked`：因为环境、权限、账号、设备、外部服务或上游流程等原因阻塞。
- `patched`：已生成 `patches/*.patch`。
- `apply_checked`：patch 已在 `base_commit` 的干净 checkout 上通过 `git apply --check`。
- `validated`：patch 已应用并通过必要验证。
- `pr_ready`：PR 标题、描述、验证说明和风险说明已准备好。
- `pr_opened`：已提交真实 PR。
- `accepted`：如果能观察到，维护者已明确接受，但可能尚未合并。
- `merged`：如果能观察到，PR 已合并。
- `rejected`：如果能观察到，维护者已拒绝。
- `abandoned`：证据不足、方向不合适、实现成本过高或风险过大而放弃。

状态应单调更新。发现 patch 不再可应用或验证失效时，应回退到能准确表达现状的状态，并在 `validation_result` 或 `notes` 中说明原因。

## 验证要求

验证分为两类，应在 `validation_commands` 和 PR 描述中明确区分：

- 目标验证：证明本 task 描述的问题已被解决，类似 SWE-bench 的 `FAIL_TO_PASS`。例如新增回归测试、复现脚本通过、错误日志消失或目标行为符合文档。
- 回归验证：证明已有关键行为没有被改坏，类似 SWE-bench 的 `PASS_TO_PASS`。例如相关单元测试、集成测试、lint、typecheck、build 或项目要求的 acceptance tests。

最低验证要求：

1. 从 `base_commit` 的干净 checkout 开始。
2. 运行 `git apply --check <patch_path>`。
3. 应用 patch。
4. 运行和改动范围匹配的测试、构建或 lint。
5. 记录命令、结果和未覆盖范围。

测试通过不代表所有功能都正确，只能证明指定验证集合通过。PR 描述必须说明验证边界，尤其是未能运行完整测试、需要外部账号、需要真实设备或需要第三方服务时。

## PR 材料要求

每个 task 提交真实 PR 前，应准备以下材料：

- PR 标题：简短描述问题和改动。
- 问题说明：对应 `problem_statement`，说明用户影响或维护价值。
- 证据链接：issue、讨论、文档、日志、测试失败、代码位置或对比依据。
- 方案说明：说明主要改动、影响范围和兼容性。
- 验证说明：列出目标验证和回归验证命令及结果。
- 风险说明：说明行为变化、未覆盖测试、外部依赖、权限、设备或数据安全边界。

PR 应从同一个 patch 表达的 diff 创建。若 PR 后续根据维护者反馈发生变化，应更新 patch、`tasks.jsonl` 和状态，确保 benchmark 目录中的 patch 仍代表当前 PR 差异。

## 任务边界

- 不要把完整目标仓库复制到 benchmark 项目目录中。
- 不要提交纯格式化、纯依赖噪音或没有用户价值的改动。
- 不要绕过项目维护者的贡献流程。
- 不要修改许可证、行为边界、公共 API 或安全策略，除非有明确 issue 或维护者确认。
- 不要把 review 反馈当作后续修复计划的一部分；提交前应尽可能完成本地验证和自查。
- 不要用生成式内容伪造证据、benchmark 数据、用户反馈、维护者意见或测试结果。
- 不要为了凑够约 20 个 PR 降低质量。

## 成功标准

优先级从高到低：

1. PR 被合并。
2. PR 被维护者明确接受，但等待发布、CI、权限或后续整理。
3. PR 获得维护者正向 review，并进入可修改状态。
4. issue 或方案被维护者确认可做。
5. patch 能从 `base_commit` 干净应用，并通过目标验证和必要回归验证。
6. 发现的问题被证明真实存在，但实现尚未达到项目要求。

代码能运行、测试通过、patch 可应用、符合项目规范是基本要求。在此基础上，这个 benchmark 进一步关注改动是否真实解决项目问题，并能被维护者认可。
