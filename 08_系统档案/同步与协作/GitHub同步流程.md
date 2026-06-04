---
title: GitHub同步流程
type: method-guide
status: active
created: 2026-06-03
updated: 2026-06-04
tags:
  - reading/method
  - github
---

# GitHub同步流程

用途：每次完成阅读回顾、总结、书籍复盘或方法调整后，及时把阅读记录库提交并推送到 GitHub，避免换电脑、本地损坏或误删导致信息丢失。

## 当前判断

当前目录 `C:\Users\yisif\Desktop\阅读` 已经是 Git 仓库，并绑定远程仓库：

```text
https://github.com/CodeManYsf/cyysf-read.git
```

GitHub 仓库是唯一事实来源。Codex、WorkBuddy 或其他平台开始操作前，必须先确认本地是否和远程一致。

当前仓库分工：

```text
仓库 = 记录、模板、索引、系统档案
cyysf-reading-vault skill = 执行、分析、提问、归档、同步
weread-skills = 可选的微信读书输入工具
```

## 新环境恢复流程

如果换电脑或新平台需要维护知识库，优先从 GitHub 克隆：

```bash
git clone https://github.com/CodeManYsf/cyysf-read.git
cd cyysf-read
```

如果本地已有仓库，每次开始前执行：

```bash
git status
git pull --ff-only
```

## 每次任务后的同步流程

每次产生文件改动后，执行：

```bash
git status
git diff --stat
git add .
git commit -m "[平台] 阅读复盘：YYYY-MM-DD 主题"
git push
```

如果当天只是方法调整，可以使用：

```bash
git commit -m "[平台] 方法调整：YYYY-MM-DD 调整内容"
```

如果当天是读完一本书，可以使用：

```bash
git commit -m "[平台] 书籍结项：YYYY-MM-DD 书名"
```

## 提交信息规范

推荐格式：

```text
[Codex] 阅读复盘：2026-06-03 道商范蠡读后回顾
[WorkBuddy] 主题沉淀：2026-06-04 更新商业与经营
[Codex] 方法调整：2026-06-03 去掉奖励机制并增加GitHub同步
[WorkBuddy] 书籍结项：2026-06-04 完成道商范蠡复盘
```

## 每次提交前检查

提交前先确认：

```text
1. 今天新增或修改了哪些文件？
2. 阅读成果是否写入统一记录目录？
3. 每日思考种子是否已经进入书籍目录或工作台？
4. 本周是否需要集中整理主题卡片或行动实践？
5. README、AGENTS、vault.config.yaml 或系统档案是否需要同步更新？
6. 是否已经写入本次平台协作记录？
7. 有没有不该提交的临时文件、缓存、账号或 token？
```

## 不建议提交的内容

不建议提交：

- 临时缓存文件
- Obsidian 工作区状态文件
- 系统缩略图文件
- 任何包含账号、密钥、token 的文件

本项目已准备 `.gitignore`，用于排除常见临时文件。

## 和 Codex 协作时的固定提醒

以后每次你让我完成阅读回顾、总结或方法调整后，如果产生了文件改动，智能体应该直接按本流程检查、提交并推送。若只是讨论规划、没有改文件，则不提交。

```text
有文件改动时：写入协作记录 -> git status -> git add -> git commit -> git push
```

一句话原则：

```text
只要今天产生了值得保留的阅读成果，就不要让它只停留在本地。
```

## 多智能体平台规则

Codex、WorkBuddy 或其他智能体平台都要遵守：

1. 开始前先 `git pull --ff-only`。
2. 阅读 `AGENTS.md` 和 [[多智能体协作规范]]。
3. 结束前写入 `08_系统档案/多智能体协作记录/<平台>/`。
4. 提交信息带平台名。
5. 如果出现冲突或无法推送，不强行覆盖，先告诉用户。
