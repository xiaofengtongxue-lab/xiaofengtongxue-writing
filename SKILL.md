---
name: xiaofengtongxue-writing
description: >-
  Apply the user's personal writing guidance only to tutorial-oriented content,
  including planning, outlining, drafting, restructuring, or revising
  plain-language technical tutorials, illustrated beginner guides, hands-on
  lessons, tutorial chapters, course notes, or full educational books whose
  primary purpose is progressive teaching. Trigger on requests framed as
  教程、大白话教程、图解教程、入门教学、手把手、从零学习、教学章节、课程讲义、技术科普书、教程书籍,
  or equivalent tutorial and book-writing requests. Do not use for general
  articles, reports, marketing copy, product specifications, reference manuals,
  summaries, translations, emails, fiction, or other writing whose primary
  purpose is not teaching. For mismatches, follow normal writing behavior
  without applying this skill.
---

# 我的写作

## 判断是否适用

1. 先判断内容的首要目的是否是让读者循序渐进地学会、理解或实践某项知识。
2. 只有教程、教学章节、教学课程或教程型书籍匹配当前技能。
3. 不要因为内容涉及技术、解释或代码，就把普通文章、报告、产品文档、参考手册或宣传文案判定为教程。
4. 如果请求不匹配，立即停止应用本技能，按照未加载任何个人写作技能时的默认方式完成任务；无需向用户说明回退过程。
5. 如果一个请求混合多种内容，只对其中明确的教程部分应用本技能，其他部分保持默认写作方式。
6. 用户显式调用 `$xiaofengtongxue-writing` 但任务不是教程时，简要说明当前个人规范只覆盖教程类，然后按默认写作方式继续，除非用户要求扩展技能。

## 规则优先级与交付媒介

1. 开始前读取并遵守当前任务适用的用户要求、`AGENTS.md`、仓库规范和现有内容约定；不要用本技能覆盖更高优先级或更具体的规则。
2. 仓库规则负责品牌名称、frontmatter、标题层级、链接格式、构建验证、发布边界和文件位置；本技能只补充其中未定义的教程结构、教学节奏和默认表达方式。
3. 先判断交付媒介是公开教程文章、教程书章节、课程讲义、互动实验还是内部知识库。口语程度、第一人称和开篇方式应服从媒介，不要把公开博客的招呼语机械复制到书籍每一章。
4. 修改已有教程时，先识别并保留作者已经形成的声音、事实和有效结构；只有用户要求重构时才重新选择主线或明显改变叙述方式。

## 按范围加载规范

- 任何匹配本技能的任务都先完整阅读 [references/tutorial-writing.md](references/tutorial-writing.md)。
- 任务涉及教程书中的章节、整本教程书、系列课程或多篇连续内容时，额外完整阅读 [references/tutorial-books.md](references/tutorial-books.md)。
- 按交付物边界而不是字数判断范围：很长的单篇教程仍是单篇；即使只修改一章，只要它属于一本书，也要考虑全书连续性。
- 不要为单篇文章读取书籍规范，也不要读取与当前任务无关的未来写作类型。

## 工作流程

1. 判断适用范围和交付媒介，读取当前任务规则、原稿以及对应 reference，再开始设计或修改内容。
2. 明确读者起点、阅读动机、完成后获得的能力和材料可信程度，选择一条主要教学主线并形成与之匹配的提纲。
3. 按 reference 执行写作：在刚好需要时加入术语、类比、代码、图、验证和排错，同时核验事实、版本、命令、代码与输出；不得编造作者经历或技术结果。
4. 使用对应 reference 和仓库检查项复核教学节奏、作者声音、真实性、图示作用、链接与交付格式。

## 当前能力边界

当前个人写作体系只定义“教程类”。其他体裁继续使用默认写作方式；以后新增体裁时，为其建立独立参考文件，并同步调整 frontmatter 中的触发描述。
