# Moocky AI 赋能学习平台设计｜GPT 交互 Memory for Codex

> 生成日期：2026-04-30  
> 文档用途：记录用户与 GPT 围绕 Moocky AI 项目、Codex 协作方式、设计系统沉淀方法、Memory 文档需求所发生的主要交互。  
> 阅读对象：Codex、后续接手该项目的 GPT、或任何需要理解“为什么现在这样推进项目”的协作助手。  
> 重点说明：本文档的重点不是复述项目内容，而是记录“用户问了什么、GPT 如何理解并回答、这些回答形成了哪些协作约束”。项目内容仅作为交互背景出现。

---


## 1. 用户的长期目标与 GPT 的理解

在多轮对话中，用户反复表达的真实目标不是单纯“做一个页面”，而是：

> 想让 Codex 更高效地完成可交互前端原型，同时在过程中建立可复用、可扩展、可追踪的设计系统，减少人工反复修正。

GPT 对这个目标的理解是：

1. 用户不是只需要一次性的页面实现。
2. 用户希望 Codex 能在后续页面中复用已有视觉、组件和交互规则。
3. 用户希望通过 Memory、design-system 文档和 AGENTS 规则，让 Codex 后续执行更稳定。
4. 用户担心 Codex 自由发挥后产生大量临时样式、硬编码和风格漂移。
5. 用户希望 GPT 不只是给产品建议，还要帮助建立“人与 Codex 协作的工作流”。

这也是为什么 GPT 后续回答重点落在：

- 如何约束 Codex；
- 如何从第一个页面抽取设计系统；
- 如何区分 confirmed / inferred / candidate / unknown；
- 如何让每轮 UI 改动都能回流到设计系统文档。

---

## 2. 交互时间线总览

以下是可还原的主要交互线索。

### 2.1 早期相关交互：学习平台文案与 AI 搜索入口

用户曾围绕 Moocky AI 学习平台中的搜索入口、CTA 文案、AI 个性化学习目标输入进行讨论。

用户关注的问题大致是：

- 学习平台的主搜索框应该如何表达？
- 按钮文案应该如何体现“AI 帮我找课程/学习路径”？
- placeholder 应该让用户输入什么？
- 搜索入口是否应覆盖课程、服务、资源、学习路径，而不只是普通关键词搜索？

GPT 给出的方向包括：

- 主 CTA 可考虑使用：`Find My Course`。
- 搜索框 placeholder 可考虑使用：`Describe your learning goal`。
- 也可考虑更自然的表达，如：`What do you want to learn today?`。
- 这个输入框不应只是普通搜索框，而应被视为“用户用自然语言输入学习目标 → AI 理解 → 推荐课程/路径/资源”的核心入口。

对 Codex 的意义：

- 后续实现页面时，不应把该区域当成普通 search bar。
- 更合适的组件命名可能是 `LearningGoalSearch`、`HeroSearchBlock` 或 `AICourseMatchSearch`。
- 这个模块应作为产品核心入口候选，而不是一次性装饰性组件。

可信度说明：该部分来自可检索到的历史项目上下文，但具体是否属于当前 Moocky 主线仍需用户确认。

---

### 2.2 用户提出 Codex 效率问题：希望自动生成前端原型并沉淀设计系统

用户近期描述的一个关键问题是：

- 正在尝试让 Codex 自动生成可交互前端原型。
- 但目前效率不高。
- Codex 经常需要人工修正。
- 用户希望 Codex 能更自主地建立设计系统，并完成页面。
- 用户询问 GPT 如何加速这个流程。

GPT 的判断是：

> 问题不只是 Codex 写代码效率，而是 Codex 缺少稳定的设计约束和沉淀机制。没有设计系统约束时，Codex 很容易每次局部修补、临时硬编码、越改越散。

GPT 给出的核心建议是：

1. 不要让 Codex 自由总结或自由创造完整设计系统。
2. 要把 Codex 当作“受设计系统约束的前端生产代理”。
3. 第一个高保真页面应作为 design system v0.1 的 seed page。
4. Codex 的第一步不是重做页面，而是审计页面。
5. 先提取 tokens、components、layout rules、interaction rules，再装配和重构页面。
6. 每次视觉或交互修改都要归类，避免只做一次性 patch。

GPT 建议的归类框架是：

```txt
token
reusable component
layout rule
interaction/state rule
page-specific exception
```

对 Codex 的意义：

- Codex 不应只回答“已修改页面”。
- Codex 每轮都应说明这次改动属于哪一类。
- 若改动引入了新颜色、字号、间距、圆角、阴影、状态或组件，必须写入相应设计系统文档。
- 如果规则尚未确认，应进入 candidates 或 open questions，而不是直接固化。

---

### 2.3 GPT 建议：不要一次性凭空生成完整设计系统

用户希望让 Codex 建立一套完整可复用设计系统。GPT 对此做了限制性建议：

> 可以建立设计系统，但不要一开始就让 Codex 凭空生成“完整系统”。更安全的方式是从真实页面中抽取 v0.1。

GPT 的理由是：

1. 第一个页面中有些样式可能是全站通用规则。
2. 有些样式可能只是当前页面的视觉实验。
3. 单页样式不足以证明它们全部应成为全站规范。
4. 如果 Codex 过早把所有样式写成全局规则，后续页面会被错误约束。
5. 因此需要将样式分为 confirmed、inferred、candidate、page-specific exception 和 unknown。

GPT 推荐的策略是：

```txt
当前高保真页面
→ 审计和提取
→ 标记 confirmed / inferred / unknown
→ 用户确认关键问题
→ 写入 decisions
→ 固化为 design system v0.1
```

对 Codex 的意义：

- Codex 在首次审计时应谨慎，不要把所有观察到的样式直接提升为正式规范。
- Codex 应主动输出未决问题，让用户判断哪些规则可全站复用。
- `decisions.md` 应成为最终确认依据。

---

### 2.4 用户关注 design-system 文档与 AGENTS.md 的作用分工

用户曾围绕设计系统文件与 Codex 执行规则之间的关系提出问题，核心关切是：

- `design-system.md` 或设计系统文档到底记录什么？
- `AGENTS.md` 应该写什么？
- 两者是否重复？
- 怎样让 Codex 以后稳定遵守这些规则？

GPT 的回答方向是：

- 设计系统文档回答“产品和界面应该是什么样”。
- `AGENTS.md` 回答“Codex 在这个项目里应该如何工作”。
- 二者需要分工，而不是混成一个文件。

可采用的分层方式：

```txt
/design-system/tokens.json
/design-system/components.md
/design-system/layout-rules.md
/design-system/interaction-rules.md
/design-system/candidates.md
/design-system/decisions.md
/design-system/open-questions.md
AGENTS.md
```

GPT 对这些文件的定位如下：

- `tokens.json`：存颜色、字号、间距、圆角、阴影、动效等可复用值。
- `components.md`：记录按钮、输入框、卡片、导航、课程卡片等组件规范。
- `layout-rules.md`：记录容器宽度、栅格、section 间距、响应式布局。
- `interaction-rules.md`：记录 hover、focus、active、disabled、loading、empty、error 等状态。
- `candidates.md`：记录尚未确认但可能复用的样式或组件。
- `decisions.md`：记录用户已确认的设计决策。
- `open-questions.md`：记录需要用户确认的问题。
- `AGENTS.md`：约束 Codex 行为，例如禁止硬编码、优先复用组件、改动后同步文档。

对 Codex 的意义：

- Codex 修改代码前，应先读取 `AGENTS.md` 和 `/design-system/`。
- Codex 不应把 `AGENTS.md` 当成设计系统本体。
- Codex 不应把 `design-system` 文件当成普通说明文档，而应把它作为实现约束。

---

### 2.5 用户关心：是否可以先让 Codex 提问确认不确定项

用户还关心一个流程问题：

> 在正式固化设计系统前，能否先让 Codex 提出不确定项，让用户确认后再写入最终规范？

GPT 的回答是：可以，而且这比直接固化更稳妥。

GPT 推荐三阶段流程：

```txt
阶段 1：高保真页面抽取审计
→ 产出 design-system-audit.md 或 extraction-report.md

阶段 2：不确定项确认轮
→ 产出 open-questions.md
→ 用户回答关键问题
→ 写入 design-decisions.md / decisions.md

阶段 3：正式固化设计系统
→ 生成或更新 design-system.md、component-specs.md、tokens.json、AGENTS.md
```

GPT 特别强调：

- 不确定项清单不应过长。
- 问题应聚焦会影响全站一致性和复用性的关键点。
- 每个问题最好标明优先级、影响范围和默认建议。
- 用户确认前，Codex 不应把这些内容写成 confirmed rule。

对 Codex 的意义：

- Codex 应具备“提出设计系统问题”的能力，而不是只执行页面修改。
- 但 Codex 的问题要收敛，不能把所有小细节都抛给用户。
- Codex 应优先询问会影响多个页面、多个组件或全局 token 的事项。

---

### 2.6 用户要求生成 Memory 文档：GPT 第一次产出偏项目内容

用户提出：

> “将此处的交互总结为详细的 Memory 文档，方便我与 Codex 回顾整个项目。”

GPT 生成了一个 Markdown 文件：

```txt
moocky-ai-memory-codex.md
```

该文件的内容偏向“项目回顾”和“Codex 执行说明”，主要包括：

- 项目身份：Moocky AI 赋能学习平台设计。
- 当前阶段：已有第一个高保真原型页面，正在打磨并沉淀设计系统。
- 产品方向：AI 个性化搜索、学习目标输入、课程/路径/资源推荐。
- 设计系统策略：第一个页面作为 design system v0.1 seed page。
- Codex 协作规则：禁止硬编码、优先 tokens、更新文档。
- `/design-system/` 推荐目录结构。
- `AGENTS.md` 草案。
- 当前待办清单。
- 组件规格模板。
- design token 分层原则。
- 风险提示。
- 下一步 Codex prompt。

这份旧文档的价值是：

- 能帮助 Codex 快速理解项目方向。
- 能作为项目级 Memory 或执行约束。
- 能指导 Codex 下一步做页面审计和设计系统提取。

但它的问题是：

- 对“用户与 GPT 是如何一步步讨论到这些结论的”记录不足。
- 它把结果写得比较完整，但没有充分记录互动过程。
- 它更像项目 brief，而不是 conversation log。

---

### 2.7 用户纠正 Memory 方向：需要记录与 GPT 的交互细节

用户随后明确指出：

> “我发现memory文件主要聚焦于项目内容，但是与GPT的交互没有怎么提及，我需要的是一份记录与GPT交互的文档。”

用户进一步说明需要包括：

- 用户提出了怎样的问题；
- GPT 是如何解答的；
- 可以提到项目内容；
- 但项目内容不是重点。

GPT 对这条反馈的理解是：

1. 用户不是要删除项目内容，而是要改变主次。
2. 新文档应围绕“交互过程”展开。
3. 项目内容只用于解释交互背景和结论来源。
4. Codex 需要理解的不只是“要做什么”，还包括“为什么这样做”。
5. 后续 Memory 应分成两类：
   - 项目内容 Memory；
   - GPT 交互 Memory。

因此，本文件即为第二类：GPT 交互 Memory。

---

## 3. GPT 回答中形成的关键判断

以下判断来自多轮互动，是 GPT 对用户需求的核心解释。

### 3.1 用户真正需要的是 Codex 协作系统，而不是单一 prompt

GPT 没有把问题简化为“给 Codex 一个更好的 prompt”。

GPT 的判断是：

- 用户面对的是持续性项目问题。
- 单个 prompt 只能解决一轮任务。
- 真正需要的是：Memory + AGENTS.md + design-system 文档 + 审计报告 + decisions 记录。

因此，GPT 建议把 Codex 的工作变成可追踪流程。

### 3.2 第一个高保真页面应作为 seed，而不是最终标准

GPT 多次强调：

- 第一个页面很重要，因为它体现了初始视觉方向。
- 但它不能自动代表完整设计系统。
- 需要从中抽取候选规则，再通过用户确认升级。

这解决的是“过早系统化”的风险。

### 3.3 Codex 不能被当作自由设计师

GPT 对 Codex 的角色定位是：

```txt
Codex = 受约束的前端执行者 + 设计系统整理者
不是 = 自由发挥的视觉设计师
```

这意味着 Codex 可以：

- 审计页面；
- 找硬编码；
- 抽取组件；
- 更新 tokens；
- 写文档；
- 执行最小重构。

但 Codex 不应：

- 擅自改变品牌方向；
- 发明新颜色和新视觉风格；
- 把局部样式变成全站规范；
- 跳过用户确认；
- 只修改代码不更新文档。

### 3.4 Memory 文档应记录“结论形成过程”

用户这次反馈指出了一个重要偏好：

- 只记录项目结论是不够的。
- 用户希望看到 GPT 如何理解问题、如何拆解、如何给出建议。
- 这有助于后续 Codex 或 GPT 理解指令背后的上下文。

因此，后续类似 Memory 文档应避免只写最终方案，也应记录：

- 用户原始问题；
- GPT 的判断；
- GPT 给出的解决路径；
- 哪些地方是明确结论；
- 哪些地方是待确认假设；
- 用户后来如何修正 GPT 的输出方向。

---

## 4. 重要 Prompt 与指令片段记录

以下是本项目交互中形成的可复用 Prompt / 指令思路。并非全部为用户原文或 GPT 原文，而是对互动成果的整理。

### 4.1 Codex 审计页面的初始任务

```txt
Please audit the current Moocky AI prototype page and existing design-system files.

Create or update:
- /design-system/extraction-report.md
- /design-system/candidates.md
- /design-system/open-questions.md

Do not change the visual design yet unless required for the audit.

In the report, classify every observed style, component, layout pattern, and interaction rule as:
- confirmed
- inferred
- candidate
- page-specific exception
- unknown / needs confirmation

Also list all hardcoded visual values and propose a minimal token/component refactor plan.
```

用途：让 Codex 先做审计，不要直接改页面。

---

### 4.2 每轮 UI 改动后的归类要求

```txt
For every UI change, classify it as one of:
- token
- reusable component
- layout rule
- interaction/state rule
- page-specific exception

If the change introduces a reusable rule, update the relevant design-system file.
If it is not confirmed, place it in candidates.md or open-questions.md.
```

用途：避免 Codex 只做局部 patch。

---

### 4.3 给 Codex 的执行边界

```txt
Do not freely redesign the product.
Do not invent new visual styles.
Do not hardcode colors, font sizes, spacing, radius, shadows, borders, or motion values.
Use existing tokens and components whenever possible.
If a style or component is not confirmed, document it as a candidate instead of promoting it to a global rule.
```

用途：把 Codex 限定为执行者和整理者，而非自由设计师。

---

### 4.4 不确定项确认轮

```txt
Before finalizing the design system, list the key open questions that require user confirmation.
Only include questions that affect global consistency, reusable components, tokens, layout rules, or interaction rules.
For each question, provide:
- why it matters
- impacted files/components
- recommended default
- what will change if confirmed
```

用途：让用户先确认关键设计决策，再固化规范。

---

## 5. 用户偏好与协作风格记录

从这些交互可以总结出用户偏好：

1. 用户希望 GPT 直接帮助建立可执行工作流，而不是只给概念建议。
2. 用户重视 Codex 后续能否读懂和执行，因此文档要能被复制、落地、追踪。
3. 用户希望设计系统随着页面打磨同步沉淀，而不是最后再补文档。
4. 用户不希望 Codex 频繁自由发挥，尤其不希望视觉风格漂移。
5. 用户重视交互记录本身，希望知道某个结论是怎样从对话中产生的。
6. 用户会主动纠正 GPT 的输出方向；GPT 后续应快速调整结构，而不是继续扩写错误方向。
7. 用户倾向于使用 Codex 作为长期协作伙伴，因此 Memory 文档需要服务于“后续回顾”和“上下文恢复”。

对后续 GPT / Codex 的含义：

- 回答应尽量给出可执行文件结构、任务步骤、检查清单和 prompt。
- 需要明确区分“已确认事实”“GPT 推断”“待用户确认”。
- 生成 Memory 时，要优先记录交互脉络和决策过程，而不是只写项目介绍。

---

## 6. 与项目内容有关但不是本文重点的背景

项目背景可简要记录如下，供 Codex 理解上下文：

- 项目名：Moocky AI 赋能学习平台设计。
- 当前主线：AI 驱动的学习平台 / 教育产品 / 高保真网页原型。
- 当前关键任务：打磨第一个高保真原型页面，并将其作为 design system v0.1 的 seed page。
- 核心产品入口：用户用自然语言描述学习目标，由 AI 推荐课程、学习路径或资源。
- 可参考文案：`Find My Course`、`Describe your learning goal`。
- 当前设计系统方向：tokens、components、layout rules、interaction rules、candidates、decisions、open questions。

待确认背景：

- 历史上下文中出现过青少年理财/目标管理模块，例如 Deposit、Withdraw、Save Now、Weekly Wrap 等。该内容可能来自用户早期其他项目或产品探索，不应默认并入当前 Moocky 学习平台。
- 除非用户再次明确确认，Codex 不应把青少年理财模块作为当前 Moocky 页面功能范围。

---

## 9. Codex 读取本文档后的行动建议

Codex 读取本文后，应理解以下重点：

1. 这份文档记录的是用户与 GPT 的交互过程，不是最终设计系统规范。
2. 旧版 `moocky-ai-memory-codex.md` 更像项目内容 Memory；本文档是交互 Memory。
3. 用户现在更关心“GPT 为什么这样建议”和“用户如何提出问题”。
4. Codex 后续执行时，应同时参考：
   - 项目 Memory；
   - GPT 交互 Memory；
   - 仓库中的实际代码；
   - `/design-system/` 文件；
   - `AGENTS.md`。
5. 如果文档之间有冲突，应优先以用户最新反馈和仓库实际状态为准。
6. 在没有检查实际代码前，不要假设 tokens、components 或页面结构已经存在。

---

## 10. 后续给 GPT 的 Memory 生成要求

当用户以后再次要求“总结交互”或“生成 Memory”时，GPT 应按以下格式优先组织：

```txt
1. 用户提出的问题
2. GPT 当时如何理解问题
3. GPT 给出的回答/方案
4. 用户是否修正或补充了方向
5. 这轮互动形成的决策
6. 哪些内容是待确认的
7. 对 Codex 或后续 GPT 的影响
```

不要只输出：

- 项目介绍；
- 功能列表；
- 技术目录；
- 待办清单；
- 设计系统规范。

这些可以作为附录或背景，但不应成为交互 Memory 的主体。

---

## 11. 给 Codex 的简短工作摘要

用户正在通过 GPT 与 Codex 协作推进 Moocky AI 学习平台的前端原型和设计系统。用户一开始关注 Codex 自动生成原型效率低、需要反复人工修正的问题。GPT 的核心建议是：不要让 Codex 自由发挥，而要把 Codex 约束为设计系统驱动的前端执行者；以第一个高保真页面作为 design system v0.1 seed page；先审计页面，再提取 tokens、components、layout rules 和 interaction rules；不确定项进入 candidates 或 open questions；用户确认后写入 decisions；每次 UI 修改都必须同步更新设计系统文档。用户后来要求生成 Memory 文档，GPT 第一次生成的版本偏项目内容，用户纠正说需要记录与 GPT 的交互细节。因此当前新版 Memory 的重点是记录用户的问题、GPT 的解答方式、结论形成过程和后续对 Codex 的执行影响。
