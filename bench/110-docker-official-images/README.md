# Docker Official Images

目标仓库：https://github.com/docker-library/official-images

准入依据：`github-open-source-projects/00-github-pr-activity-2026-05-30.md` 记录该项目近三个月内存在非成员作者的合并 PR。

## 1. 任务要求、问题来源和建议方向

你要在 Docker Official Images 生态中寻找一个真实容器分发贡献点。official-images 仓库维护 Docker Hub 官方镜像集合的 library metadata，定义版本、tag、Git commit、目录和架构。

你可以优先参考这些问题来源：

- 已有 official image 的版本更新、构建失败、checksum、架构 metadata 或 tag 不一致。
- 上游 image 仓库 Dockerfile、测试或 README 暴露的问题。
- issue、PR review、build logs 或官方镜像文档中的维护请求。
- library definition file 与上游 release 或 supported architectures 不一致。

建议修改方向：

- 优先修复已有 official image 的小版本更新、metadata 或构建问题。
- 新 official image 门槛高，不适合作为起步 benchmark 任务。
- 区分 official-images 索引 PR 和上游 image 仓库 PR，必要时两边都要处理。
- Dockerfile 改动要可复现、最小、安全，并通过 smoke test。

## 2. 交付要求和最终目标

你需要交付：

- 问题来源和证据说明，包括上游 release、构建日志、library metadata 或 issue。
- 方案设计和影响范围，说明 image、tags、architectures、source commit 和兼容性。
- 代码或 metadata 改动，包括 Dockerfile、library file、README 或 test。
- 验证结果，例如 docker build、container smoke test、metadata validation 或 CI。
- PR 标题和 PR 描述，说明上游变更、验证方式和风险。

最终目标：提交一个提高官方镜像正确性、可构建性或 metadata 准确性的 PR。
