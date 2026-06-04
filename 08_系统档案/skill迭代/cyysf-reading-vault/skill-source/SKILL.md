---
name: cyysf-reading-vault
description: Maintain the user's cyysf-read reading knowledge vault. Use when working on CodeManYsf/cyysf-read, the user's record-first reading vault, Obsidian reading notes, WeRead highlight reviews, daily thinking seeds, book records, theme cards, action practice, multi-agent coordination with WorkBuddy, skill iteration archives, or GitHub sync for this reading repository.
---

# CYYSF Reading Vault

Use this skill to maintain the `CodeManYsf/cyysf-read` reading vault. The repository is the record layer; this skill is the execution layer for reading workflows, analysis, filing, and GitHub sync.

## Mandatory Start

1. Locate the working copy. Default local path: `C:\Users\yisif\Desktop\阅读`. Remote: `https://github.com/CodeManYsf/cyysf-read.git`.
2. Run `git status --short`.
3. If the repository is clean, run `git pull --ff-only` before editing.
4. If there are local changes or pull conflicts, do not overwrite. Explain the situation and work with the existing changes.
5. Read these repository files before substantial work:
   - `README.md`
   - `AGENTS.md`
   - `vault.config.yaml`
   - `00_入口/知识库入口.md`

For detailed repository structure, read `references/repo-map.md`. For reading workflows, read `references/workflows.md`. For multi-agent rules, read `references/agent-collaboration.md`.

## Core Principles

- GitHub is the source of truth; local folders are working copies.
- Repository files store records, templates, indexes, system archives, and skill iteration notes.
- This skill handles execution, questions, analysis, filing decisions, and GitHub sync.
- `weread-skills` is optional and separate; use it only as an input tool for WeRead highlights or notes.
- Reading content stays in the unified vault directories. Do not split content by agent platform.
- Agent operation logs go in `08_系统档案/多智能体协作记录/<platform>/`.
- The user thinks first; the agent organizes, asks questions, summarizes, and files records after the user has given their own reflections.
- Daily reading should stay lightweight: capture 1-3 thinking seeds, not every highlight.
- Weekly review is where the agent should organize themes, action practice, and stage reviews.
- Do not force daily theme-card or action-principle updates unless the user explicitly asks or the insight is already concrete.
- New books should include reading-method judgment: initial A/B/C level, 20%-30% reassessment, and final level at completion.
- Do not treat every book as an A-level intensive read. Default to B unless the user’s current problem strongly justifies A.
- A-level books may get a quick reread and whole-book structure note after completion; B/C books should stay lighter.
- The paused reward/points mechanism is not active.
- Keep changes scoped. Do not restructure the vault unless the user explicitly asks.
- Do not force-push, hard reset, or discard user/other-agent changes.

## Where To Write

- Weekly workbench: `00_入口/本周阅读工作台.md`
- Project status: `00_入口/项目状态.md`
- Book records: `01_书籍记录/<book>/`
- Daily thinking seeds: `01_书籍记录/<book>/02_每日思考/`
- Stage reviews: `01_书籍记录/<book>/03_阶段复盘/`
- Book completion: `01_书籍记录/<book>/04_读后总结.md`
- Whole-book structure: `01_书籍记录/<book>/05_整书脉络.md`
- Book method log: `01_书籍记录/<book>/06_方法实践记录.md`
- Theme cards: `02_主题知识库/<theme>/`
- Action principles and practice board: `03_行动实践库/`
- Raw inputs: `04_原始输入/`
- Obsidian views/templates/indexes: `05_Obsidian视图/`, `06_模板/`, `07_索引/`
- System archives and method iteration: `08_系统档案/`
- Agent logs: `08_系统档案/多智能体协作记录/Codex/`, `08_系统档案/多智能体协作记录/WorkBuddy/`, or `08_系统档案/多智能体协作记录/其他平台/`

## Standard End

After completing a task:

1. Write or update the appropriate agent log in `08_系统档案/多智能体协作记录/<platform>/`.
2. Run `git status --short` and inspect the changed files.
3. Commit with a platform-prefixed message, for example:
   - `[Codex] 阅读复盘：2026-06-03 道商范蠡读后回顾`
   - `[WorkBuddy] 方法调整：2026-06-04 更新同步流程`
4. Push to GitHub.
5. Report the commit hash and whether the working tree is clean.

If the user only asks for planning or analysis, do not edit or commit unless they ask to execute.
