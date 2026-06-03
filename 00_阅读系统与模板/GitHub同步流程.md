---
title: GitHub同步流程
type: method-guide
status: active
created: 2026-06-03
tags:
  - reading/method
  - github
---

# GitHub同步流程

用途：每次完成阅读回顾、总结、书籍复盘或方法调整后，及时把阅读知识库提交并推送到 GitHub，避免换电脑、本地损坏或误删导致信息丢失。

## 当前判断

当前目录 `C:\Users\yisif\Desktop\阅读` 还不是 Git 仓库。首次同步前，需要先在 GitHub 创建一个 repository，然后在本地初始化 Git 并绑定远程仓库。

## 首次迁移流程

在 GitHub 创建仓库后，在本目录执行：

```bash
git init
git add .
git commit -m "初始化阅读知识库"
git branch -M main
git remote add origin <你的 GitHub 仓库地址>
git push -u origin main
```

示例：

```bash
git remote add origin https://github.com/your-name/reading-knowledge-base.git
```

## 每次复盘后的同步流程

每次完成回顾和总结后，执行：

```bash
git status
git diff --stat
git add README.md AGENTS.md 00_知识库入口.md 00_阅读系统与模板 01_每日阅读回收 02_每周阅读复盘 03_书籍卡片 04_主题卡片库 05_行动原则库 07_Obsidian视图 08_模板 09_索引 10_智能体协作记录
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
2. 每日回收是否已经写入？
3. 主题卡片是否已经落库？
4. 行动原则是否需要新增或更新？
5. README 或方法方案是否需要同步更新？
6. 是否已经写入本次智能体协作记录？
7. 有没有不该提交的临时文件？
```

## 不建议提交的内容

不建议提交：

- 临时缓存文件
- Obsidian 工作区状态文件
- 系统缩略图文件
- 任何包含账号、密钥、token 的文件

本项目已准备 `.gitignore`，用于排除常见临时文件。

## 和 Codex 协作时的固定提醒

以后每次你让我完成阅读回顾、总结或方法调整后，我都应该在最后提醒：

```text
这次是否要提交并推送到 GitHub？
```

如果你确认，我再执行：

```bash
git status
git add ...
git commit -m ...
git push
```

一句话原则：

```text
只要今天产生了值得保留的阅读成果，就不要让它只停留在本地。
```

## 多智能体平台规则

Codex、WorkBuddy 或其他智能体平台都要遵守：

1. 开始前先 `git pull --ff-only`。
2. 阅读 `AGENTS.md` 和 [[多智能体协作规范]]。
3. 结束前写入 `10_智能体协作记录/<平台>/`。
4. 提交信息带平台名。
5. 如果出现冲突或无法推送，不强行覆盖，先告诉用户。
