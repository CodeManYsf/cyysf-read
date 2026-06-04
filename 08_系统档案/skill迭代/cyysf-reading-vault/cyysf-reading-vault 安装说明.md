---
title: cyysf-reading-vault 安装说明
type: skill-install
status: active
created: 2026-06-04
tags:
  - reading/skill
  - reading/install
---

# cyysf-reading-vault 安装说明

## 新电脑恢复顺序

1. 克隆仓库：

```bash
git clone https://github.com/CodeManYsf/cyysf-read.git
```

2. 安装或恢复 `cyysf-reading-vault` skill。

3. 如需读取微信读书划线，再单独安装 `weread-skills`。

4. 打开 Obsidian，将仓库目录作为 vault。

5. 让智能体读取：

```text
README.md
AGENTS.md
vault.config.yaml
00_入口/知识库入口.md
```

## 安装版与仓库快照

- 安装版 skill：实际运行时使用。
- 仓库快照：`08_系统档案/skill迭代/cyysf-reading-vault/skill-source/`，用于迁移、对照和迭代。

如果安装版 skill 和仓库快照不一致，以本次任务更新后的安装版为准；随后应把安装版重新复制回仓库快照。
