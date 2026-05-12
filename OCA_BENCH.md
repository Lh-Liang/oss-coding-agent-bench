# OCA Bench

## Overview

This repository ships `oca-bench` as a project-local instruction package for running the local `oss-coding-agent-bench` benchmark. An agent should be able to open this repository, read the project-level entrypoint it supports, and then use this file as the canonical workflow.

No global installation or skill registration is required for repository-local use.

## Discovery Model

Use this file as the single source of truth. Other entrypoints such as `AGENTS.md`, `CLAUDE.md`, `GEMINI.md`, and `.cursor/rules/oca-bench.mdc` should only route here.

Do not duplicate benchmark rules into adapter files. If the benchmark workflow changes, update this file first.

## Invocation Contract

Require the user to provide `scope` before starting real work:

- `scope=task`: complete one benchmark task for one project directory under `bench/`. If `project` is missing, ask the user for a project or explicit permission to use `project=auto`.
- `scope=project`: complete multiple tasks for one project directory under `bench/`. Require `project` and `count`; ask if either is missing.
- `scope=bench`: complete tasks across multiple projects. Require `count` and a project selection strategy; ask if either is missing.

If the user asks to run the benchmark but omits `scope`, ask for `scope` first. Do not silently default to a scope.

Resolve `project` to an existing directory under `bench/` before reading project files. If the user provides an alias or display name, map it to the matching `bench/<project>/` directory and report the resolved directory.

## Source Of Truth

Read the live benchmark files from the repository:

- Benchmark overview: `README.md`
- Main protocol: `bench/README.md`
- Project protocol: `bench/<project>/README.md`
- Project records: `bench/<project>/TASKS.md`, `bench/<project>/tasks.jsonl`, `bench/<project>/SUMMARY.md`, and `bench/<project>/patches/`.

Load `bench/README.md` first, then only the README files for the selected project(s). Read the root `README.md` only for benchmark context. Do not copy all project READMEs into this instruction package and do not treat these instructions as a stale embedded snapshot.

## Benchmark Workflow

1. Resolve the benchmark root as the repository directory containing `OCA_BENCH.md` and `bench/README.md`. If it is missing or ambiguous, stop and ask for its path.
2. Read the main protocol and the selected project protocol. Follow the benchmark's definitions for evidence, task fields, status values, validation, and PR materials.
3. Select a real, evidence-backed upstream problem. Acceptable evidence includes issues, discussions, maintainer comments, failing tests, documented API behavior, reproducible logs, or strong comparison evidence. Never fabricate evidence.
4. Determine and record a fixed `base_commit` from the target repository before implementing.
5. Work in a temporary clone or worktree outside the benchmark root. A sibling directory such as `<benchmark-root-parent>/.oca-bench-work/` is acceptable; the target repository must not be copied into `bench/` or into any benchmark project directory.
6. Implement a small, reviewable change that matches the project protocol and upstream contribution style. Include tests, docs, fixtures, schemas, config, or changelog entries when they are needed for a complete PR.
7. Generate a complete patch with `git diff --binary --full-index` and save it as `bench/<project>/patches/Txxx-short-slug.patch`.
8. Validate from a clean checkout of `base_commit`: run `git apply --check <patch>`, apply the patch, then run the targeted tests, build, lint, typecheck, or manual reproduction steps that match the change.
9. Update `bench/<project>/tasks.jsonl`, `bench/<project>/TASKS.md`, and `bench/<project>/SUMMARY.md` with the patch path, validation commands, validation result, status, and PR status. Be explicit about failures, skipped checks, and untested risk.
10. By default, open a real upstream PR after validation passes and credentials/permissions allow it. If a PR cannot be opened, set the task to `pr_ready` or `blocked` and explain why. Never invent a PR URL.

## Records

Use the benchmark schema from `bench/README.md`. Each `bench/<project>/tasks.jsonl` entry must include:

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
    "git apply --check <benchmark_project_dir>/patches/T001-fix-timeout-handling.patch",
    "pytest tests/test_timeout.py"
  ],
  "validation_result": "pass: patch applies cleanly; targeted pytest passed",
  "status": "validated",
  "pr_url": "",
  "notes": "Validation performed from a clean checkout of base_commit."
}
```

Assign the next `Txxx` id by inspecting existing `bench/<project>/tasks.jsonl`, `bench/<project>/TASKS.md`, and `bench/<project>/patches/`. Keep patch filenames aligned with the task id.

## Quality Gates

- Do not create toy tasks, purely cosmetic rewrites, broad refactors, unrelated dependency churn, or fake benchmark artifacts.
- Do not modify licenses, public API boundaries, security behavior, or privacy behavior unless the evidence clearly supports that change.
- Do not rely on future maintainer review to fix known issues. Submit only after self-review and appropriate local validation.
- Record validation truthfully. Passing tests only prove the named validation set passed.
- Keep status values consistent with `bench/README.md`: `candidate`, `selected`, `in_progress`, `blocked`, `patched`, `apply_checked`, `validated`, `pr_ready`, `pr_opened`, `accepted`, `merged`, `rejected`, or `abandoned`.

## Final Response

When a run finishes, report:

- selected scope, project, task id, and target repository
- evidence summary and base commit
- patch path and benchmark metadata files updated
- validation commands and results
- PR URL if opened, or the exact reason it is `pr_ready` or `blocked`
