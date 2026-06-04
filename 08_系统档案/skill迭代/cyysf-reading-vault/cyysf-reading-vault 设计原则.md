---
title: cyysf-reading-vault 设计原则
type: skill-design
status: active
created: 2026-06-04
tags:
  - reading/skill
  - reading/design
---

# cyysf-reading-vault 设计原则

## 核心分工

```text
仓库 = 记录层
skill = 执行层
weread-skills = 输入工具
```

## 记录层

仓库只负责保存：

1. 读前目标与读法判断。
2. 每日思考种子。
3. 阶段复盘与读后总结。
4. 整书脉络。
5. 主题卡片与行动原则。
6. 多智能体协作日志。
7. 方法迭代和 skill 迭代档案。

## 执行层

`cyysf-reading-vault` skill 负责：

1. 判断当前任务属于读前、每日、每周、读后、主题、行动还是同步。
2. 先让用户表达自己的理解，再进行整理。
3. 控制日常维护成本，不把每条划线都强制落库。
4. 每周集中整理主题卡片和行动实践。
5. 读完一本书后回到读前目标复盘。
6. 根据 A/B/C 档决定是否做整书脉络。
7. 每次产生文件改动后写协作记录、提交并推送。

## 解耦原则

1. skill 不依赖某一台电脑上的绝对路径；本地路径只是默认值。
2. skill 优先读取仓库中的 `vault.config.yaml`。
3. 微信读书能力不写入本 skill，由 `weread-skills` 单独提供。
4. 阅读成果必须回写到仓库，不保存在智能体平台内部。
5. 历史方法可以归档，但日常执行只看当前入口和配置。
