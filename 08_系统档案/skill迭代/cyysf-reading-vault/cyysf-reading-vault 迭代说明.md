---
title: cyysf-reading-vault 迭代说明
type: skill-iteration
status: active
created: 2026-06-04
tags:
  - reading/skill
  - reading/system
---

# cyysf-reading-vault 迭代说明

这里保存 `cyysf-reading-vault` skill 的设计、版本、安装和接口约定。

## 定位

```text
仓库负责记录，skill 负责执行。
```

仓库保存阅读记录、模板、索引、方法档案、协作日志和 skill 迭代档案；skill 负责在智能体运行时读取仓库结构、提问、分析、整理、归档和同步 GitHub。

## 为什么放在仓库里

1. 换电脑后，仓库可以直接恢复阅读记录和 skill 设计历史。
2. 后续修改 skill 时，可以知道为什么这样设计。
3. Codex、WorkBuddy 或其他平台都能理解仓库与 skill 的分工。
4. 安装版 skill 和仓库记录解耦，避免把执行说明散落在阅读记录里。

## 当前文件

- [[cyysf-reading-vault 设计原则]]
- [[skill接口约定]]
- [[cyysf-reading-vault 安装说明]]
- [[cyysf-reading-vault 版本记录]]
- [[cyysf-reading-vault 待优化问题]]

## 源码快照

`skill-source/` 保存当前安装版 skill 的源码快照，仅用于迁移和迭代参考。真正运行时仍以本机安装到 Codex 的 skill 为准。
