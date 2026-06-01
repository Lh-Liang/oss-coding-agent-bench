# Semgrep Rules

目标仓库：https://github.com/semgrep/semgrep-rules

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录该项目近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 Semgrep Rules 中寻找一个真实静态分析规则贡献点。Semgrep 使用类似源码的 pattern rules 查找安全漏洞、bug 和代码规范问题，规则通常由 YAML、metadata 和测试样例组成。

你可以优先参考这些问题来源：

- 真实漏洞模式、框架安全文档、issue 或已有规则的误报/漏报。
- 某规则缺少 positive/negative fixtures、CWE/OWASP metadata 或清楚 message。
- 框架 API、危险配置或 agent 生成代码常见风险尚未覆盖。
- Rule registry 文档或修复建议不够可操作。

建议修改方向：

- 优先修复已有规则的 false positive/false negative，并补负例测试。
- 新规则必须基于真实风险，而不是纯风格偏好。
- Pattern 要尽量窄，message 要说明为什么危险以及如何修复。
- 避免包含未公开漏洞细节或过度泛化规则。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括安全文档、漏洞样例、issue 或当前 rule 输出。
- 方案设计和影响范围，说明目标语言、框架、pattern 和误报边界。
- 规则或文档改动，包括 YAML rule、metadata、positive/negative fixtures 和说明。
- 验证结果，例如 semgrep test、命中 diff 和负例检查。
- PR 标题和 PR 描述，说明风险、修复建议和测试覆盖。

最终目标：提交一个低误报、可测试、能进入 Semgrep rules 集合的 PR。
