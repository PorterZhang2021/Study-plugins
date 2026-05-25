# Study Plugins

个人 AI 学习辅助 Skills 仓库，用来沉淀和分发面向项目学习、代码理解、知识复盘的可复用 skill。

当前仓库包含两个学习辅助 skill：`project-understanding-coach` 和 `series-column-learning`。

## Repository Layout

| 目录 | 内容 |
| --- | --- |
| `skills/` | 可被 Codex 单独安装和复用的 skill。 |
| `skills/project-understanding-coach/` | 通过运行链路和逻辑提问来帮助理解陌生项目的学习教练 skill。 |
| `skills/series-column-learning/` | 面向技术专栏、课程和系列教程的一问一答式深度学习 skill。 |

## Skills

| Skill | 适用平台 | 说明 |
| --- | --- | --- |
| `project-understanding-coach` | Codex | 帮助用户按运行时逻辑理解陌生代码库、遗留项目或框架项目；优先梳理输入输出、控制流、数据流和可复用设计，而不是逐文件解释。 |
| `series-column-learning` | Kimi / Codex | 帮助用户学习技术专栏、课程或系列教程；通过章节设置、问题设计、场景推导、讨论纠偏和笔记沉淀来加深理解。 |

## project-understanding-coach

这个 skill 适合在这些场景中使用：

- 想学习一个陌生项目，但不想一上来陷入所有文件和类名。
- 想复刻一个项目，先理解它的核心运行链路。
- 想把项目拆成一组逻辑问题，并一问一答地学习。
- 想记录学习笔记，只保存双方已经确认的共同结论。

它的默认工作方式是：

1. 先确认学习目标，例如理解、复刻、调试、扩展或重写。
2. 找到最小运行链路，例如 `start -> prepare dependencies -> receive input -> process input -> return output`。
3. 一次只问一个逻辑问题，围绕每一步为什么存在、输入输出是什么、去掉会坏在哪里、哪些部分可复用。
4. 只在用户要求时扩展术语解释或实现细节。
5. 写笔记时记录共同结论，而不是做批改式对照。

## series-column-learning

这个 skill 适合在这些场景中使用：

- 正在学习极客时间专栏、面试精讲系列、技术课程等连续章节内容。
- 希望围绕每一章设计概念题和应用题。
- 希望用真实工作场景推导概念，而不是背定义。
- 希望先讨论、纠偏、确认理解，再把最终答案写入笔记。

它的默认工作方式是：

1. 先确认当前章节和已有学习上下文。
2. 基于文章内容设计概念题和应用题。
3. 一次解释一个问题，并用工作场景展开。
4. 让用户用自己的话组织答案。
5. 讨论边界场景并修正误解。
6. 用户确认理解后，再写入学习笔记。

## Install In Codex

可以使用 Codex 内置的 `skill-installer` 从 GitHub 安装单个 skill：

```text
使用 skill-installer，从 PorterZhang2021/Study-plugins 安装 skills/project-understanding-coach
```

安装 `series-column-learning`：

```text
使用 skill-installer，从 PorterZhang2021/Study-plugins 安装 skills/series-column-learning
```

等价安装源：

```text
repo: PorterZhang2021/Study-plugins
path: skills/project-understanding-coach
```

或：

```text
repo: PorterZhang2021/Study-plugins
path: skills/series-column-learning
```

安装完成后重启 Codex，使新 skill 生效。

## Manual Install

也可以手动复制这个目录：

```text
skills/project-understanding-coach/
```

到 Codex skills 目录：

```text
~/.codex/skills/project-understanding-coach/
```

复制后重启 Codex。

## Skill 开发规范

- 每个 skill 一个目录，目录名使用 kebab-case。
- 目录下必须包含 `SKILL.md` 作为主入口。
- 辅助 agent 或提示配置放在 `agents/` 子目录。
- `SKILL.md` 顶部包含 YAML frontmatter：

```yaml
---
name: project-understanding-coach
description: Help users pair with Codex to understand unfamiliar codebases...
---
```

## Git

当前仓库远程地址：

```text
git@github.com:PorterZhang2021/Study-plugins.git
```
