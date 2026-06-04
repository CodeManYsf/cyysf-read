---
title: 多智能体协作说明
type: agents-guide
status: active
created: 2026-06-03
updated: 2026-06-04
tags:
  - reading/agents
  - collaboration
---

# 多智能体协作说明

这是一个个人阅读记录库。Codex、WorkBuddy 或其他智能体平台都可以协助维护，但所有平台必须以 GitHub 仓库为唯一事实来源。

## 开始前必须阅读

任何智能体开始操作前，先阅读：

1. `README.md`
2. `vault.config.yaml`
3. `00_入口/知识库入口.md`
4. `AGENTS.md`

如果当前平台是 Codex，并且已安装 `cyysf-reading-vault` skill，应优先使用该 skill。

## 仓库与 skill 分工

```text
仓库 = 记录、模板、索引、系统档案
cyysf-reading-vault skill = 执行、分析、提问、整理、同步
weread-skills = 可选的微信读书输入工具
```

仓库不负责承载完整执行说明；执行细节优先读取 skill。

## 核心原则

1. GitHub 仓库是唯一事实来源。
2. 阅读内容统一进入记录目录，不按平台拆分。
3. 平台操作记录进入 `08_系统档案/多智能体协作记录/<平台>/`。
4. 用户先思考，智能体后整理。
5. 不删除用户或其他平台已有记录，除非用户明确要求。
6. 每次开始前先同步最新仓库内容。
7. 每次完成后写平台协作记录，再提交并推送。
8. 如果遇到 Git 冲突、远程落后、无法推送等情况，停止并说明，不强行覆盖。

## 标准流程

```text
1. git status
2. git pull --ff-only
3. 读取 README.md、vault.config.yaml、AGENTS.md
4. 完成用户指定的阅读记录、总结或方法调整
5. 写入对应平台协作记录
6. git status
7. git add .
8. git commit -m "[平台] 类型：日期 主题"
9. git push
```

## 提交信息格式

```text
[Codex] 阅读复盘：2026-06-04 道商范蠡
[WorkBuddy] 行动实践：2026-06-11 复盘慎言实验
[Codex] 方法调整：2026-06-04 重构阅读仓库目录
```

## 禁止事项

1. 不要把阅读内容拆成“Codex 记录”和“WorkBuddy 记录”。
2. 不要在没有同步远程仓库的情况下直接修改大量内容。
3. 不要强推覆盖远程仓库。
4. 不要提交账号、密钥、token 或私人凭证。
5. 不要把微信读书能力写死到本仓库；微信读书输入由 `weread-skills` 单独负责。
