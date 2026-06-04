# Agent Collaboration

## Platforms

Supported operation sources include:

- Codex
- WorkBuddy
- Other agents

The repository is unified. Reading content does not get separated by platform.

## Agent Logs

Write platform operation logs here:

```text
08_系统档案/多智能体协作记录/Codex/
08_系统档案/多智能体协作记录/WorkBuddy/
08_系统档案/多智能体协作记录/其他平台/
```

Use a filename like:

```text
YYYY-MM-DD_任务名.md
```

## Log Template

```markdown
---
title: YYYY-MM-DD 平台 任务名
type: agent-log
platform: Codex
日期: YYYY-MM-DD
status: done
tags:
  - agents/codex
  - collaboration/log
---

# 智能体协作记录

日期：
平台：
任务：

## 操作概述

## 修改文件

## Git 提交

提交信息：
提交哈希：

## 备注
```

## Git Rules

Start clean when possible:

```bash
git status --short
git pull --ff-only
```

End with:

```bash
git status --short
git add .
git commit -m "[Codex] 类型：YYYY-MM-DD 主题"
git push
```

Use the actual platform name in the commit prefix.

Before substantial work, read `README.md`, `AGENTS.md`, `vault.config.yaml`, and the relevant active entry or record files.

## Conflict Rules

If pull or push fails because of remote divergence, local edits, or conflicts:

1. Stop.
2. Report the exact issue.
3. Do not force-push.
4. Do not discard local changes.
5. Ask the user how to proceed if the safe next step is unclear.

## Commit Message Examples

```text
[Codex] 方法调整：2026-06-03 增加阅读仓库 skill
[WorkBuddy] 阅读复盘：2026-06-04 道商范蠡读后回顾
[Codex] 主题沉淀：2026-06-04 更新商业与经营
```
