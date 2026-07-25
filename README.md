# xiaofengtongxue-writing

小枫同学的个人写作 Skill。

它不是一套固定模板，也不是只服务于某一种文章的提示词集合。这个项目希望逐步沉淀一套按内容类型选择写作指导、结构、语气和约束的长期写作系统。

目前首先实现的是**教程类写作**。后续会根据真实写作需求增加更多内容类型，并持续用实际文章检验和优化现有规范。

## 当前能力

当前版本支持规划、撰写、重构和修改以下教程内容：

- 大白话技术教程
- 图解教程与零基础入门指南
- 手把手实操课程和课程讲义
- 单篇教学文章
- 教程书籍、连续章节和系列课程

教程模块不会用一个固定目录处理所有内容。它会先判断读者真正要解决的问题，再从首次成功、任务完成、项目驱动、原理图解、链路追踪、故障排查、对比选型、互动练习和课程单元等结构中选择合适的主线。

不属于教程的内容不会强行套用当前规范，而是回到 Codex 默认的写作方式。

## 设计原则

- **按内容类型加载规范**：每一种写作类型拥有自己的适用范围和参考文件。
- **先判断任务，再选择结构**：不追求一套万能公式走天下。
- **服从具体媒介**：公开文章、书籍章节、课程讲义和内部知识库可以使用不同的叙述距离。
- **大白话不牺牲准确性**：保留必要术语，并让类比最终回到真实机制。
- **不编造作者经历**：区分作者亲历、当前验证、常见问题和构造案例。
- **持续从真实输出中迭代**：规范不是一次定稿，而是在实际写作和前向测试中逐步修正。

## 项目结构

```text
xiaofengtongxue-writing/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── tutorial-writing.md
    └── tutorial-books.md
```

- [`SKILL.md`](SKILL.md)：判断是否触发、加载哪些规范以及如何执行。
- [`references/tutorial-writing.md`](references/tutorial-writing.md)：单篇教程和通用教程写作规范。
- [`references/tutorial-books.md`](references/tutorial-books.md)：教程书籍、连续章节和跨章一致性规范。
- [`agents/openai.yaml`](agents/openai.yaml)：Codex 中展示和调用 Skill 所需的界面配置。

README 面向仓库使用者。Codex 真正执行的指令仍然放在 `SKILL.md` 和 `references/` 中，避免把项目说明混进运行时上下文。

## 安装

将仓库克隆到 Codex 的个人 Skills 目录：

```bash
git clone https://github.com/xiaofengtongxue-lab/xiaofengtongxue-writing.git \
  ~/.codex/skills/xiaofengtongxue-writing
```

重新启动 Codex 或开启一个新任务后即可使用。

## 使用

Skill 允许隐式触发。当任务的主要目的是循序渐进地教会读者一项知识或实践能力时，Codex 可以自动应用当前教程规范。

也可以显式调用：

```text
使用 $xiaofengtongxue-writing，为零基础读者写一篇 Docker 入门教程。
```

```text
使用 $xiaofengtongxue-writing，规划一本大白话计算机网络教程书。
```

## 后续迭代

教程只是这套写作 Skill 的第一个版本。后续新增内容类型时，将继续遵守下面的扩展方式：

1. 先明确这种内容的目标、读者、适用场景和排除边界。
2. 为它建立独立的写作参考文件，不污染其他内容类型。
3. 更新 `SKILL.md` 的路由与触发描述，让 Codex 只加载当前任务真正需要的规范。
4. 使用真实写作任务进行前向测试，再根据结果持续调整。

项目会继续优化教程结构、作者声音、图示策略、真实性约束和书籍连续性，也会逐步扩展到新的写作类别。
