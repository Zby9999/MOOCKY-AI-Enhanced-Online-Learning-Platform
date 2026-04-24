# Memory

## 1. 当前目标

- [已确认] 当前项目是设计一个 AI 赋能在线学习网站，品牌名为 `MOOCKY`。
- [已确认] 当前设计系统正式命名为 `Lumen Atlas`；它是 MOOCKY 的设计系统名称，不替代产品品牌名。
- [已确认] 当前阶段重点是建立完整、可复用、可继续扩展的设计系统。
- [已确认] 设计系统需要服务后续流程：用户提供具体页面线框图，Codex 基于已确认系统规则产出可用高保真设计。
- [已确认] 本地 `docs/design-system.md` 是设计系统唯一事实来源；Figma Design Doc 是视觉沟通层，不替代源文档。

## 2. 已确认事实

- [已确认] 品牌标准写法是 `MOOCKY`，logo 由 wordmark 和 sparkle 星标组成。
- [已确认] 设计系统标准写法是 `Lumen Atlas`。
- [已确认] Figma 文件 key 是 `hoN23Dj67OVv6D0drKYY24`。
- [已确认] 可作为系统证据的 Figma 节点仅包括：`42:93`、`60:551`、`100:3535`、`180:1596`、`180:1831`、`180:1880`、`173:1582`。
- [已确认] 其中 light evidence 是 `42:93` Landing、`60:551` 课程暂停页、`100:3535` 课程播放页。
- [已确认] dark evidence 是 `180:1596`、`180:1831`、`180:1880`，只能从这些 dark frame 理解暗色模式。
- [已确认] gradient appendix evidence 是 `173:1582`，现有 `Images` 画板需保留为渐变附录。
- [已确认] 同一 Figma 文件中的其他 frame 都是实验废案，未经用户再次批准不得作为系统证据。
- [已确认] 抽象条纹渐变是 MOOCKY 独特视觉风格，需要沿用到正式网页中。
- [已确认] 当前 v1 渐变以 yellow / blue / red / gold 的 warm spectral family 为主，未来会继续补全变体。
- [已确认] 核心元素和文字需达到 WCAG AA；装饰性或辅助性元素可适当放宽。
- [已确认] AI 是全站核心能力，不是装饰模块；当前确认的 AI 形态是课程页 AI companion rail。
- [已确认] `Button` 是唯一全局统一交互组件，其他组件默认按场景处理。
- [已确认] 当前确认页面 archetype 包括 Marketing / Landing Shell、Learning / Course Shell、AI as Global Capability。

## 3. 关键决策

- [已确认] 建立 4 个正式系统产物：`docs/design-system.md`、`docs/component-specs.md`、`tokens.json`、`AGENTS.md`。原因：分别承载唯一事实来源、组件执行说明、机器可读 tokens、Codex 执行规则。
- [已确认] `docs/design-system-audit.md` 是证据审计档案，不是规范权威来源。原因：避免早期提取结论覆盖后续确认规则。
- [已确认] Figma `Design Doc` 页面创建英文可视化设计文档。原因：方便团队沟通与设计评审，但不作为事实来源。
- [已确认] Figma Design Doc 保留 `Images` 画板，不删除、不覆盖。原因：它是渐变资产附录来源。
- [已确认] 暗色模式从“Figma variants”宽泛表述改为“只读取批准 dark frame”。原因：避免再次引用实验废案。
- [已确认] Display 大标题必须使用两字体组合：首单词 `Cormorant Infant Medium Italic`，其余文字 `Gayathri Thin`。原因：这是用户确认的核心标题语言。
- [已确认] Display 大标题任何段落都不得小于 `42px`。原因：低于该尺寸会破坏观感和字体组合的成立条件。
- [已确认] 小标题有两套规则：无背景衬托时用 `Geist Regular 16px` 浅棕色；有按钮或模块衬托时用 `DM Serif Text`。原因：对应 landing page 和卡片内标题的已确认用法。
- [已确认] 系统中只允许出现 `Cormorant Infant`、`Gayathri`、`DM Serif Text`、`Geist` 四种字体。原因：防止视觉语言混杂。
- [已确认] 常规圆角只有 `16px`、`8px`、`pill`，所有圆角使用 `60%` corner smoothing。原因：保持柔和几何的一致性。
- [已确认] 所有 icon 必须来自 Lucide，默认 `16px`、`1.5px` stroke。原因：统一图标来源和产品扫描感。
- [已确认] 阴影策略需要极其克制：正常情况下不使用任何阴影效果，后续原型生成也不得默认给卡片、按钮、面板、rail、输入框增加阴影。原因：保持 MOOCKY 的低 chrome、安静层级。
- [已确认] 在复杂渐变、图片或媒体背景前，为了增加层次感，使用透明/半透明组件背景加 `8px` 背景模糊，而不是 drop shadow。Figma 节点 `74:594` 仅作为这一策略的聚焦参考，不作为其它系统规则证据。
- [已确认] 设计系统正式命名为 `Lumen Atlas`。原因：为 MOOCKY 的视觉与组件规范建立可被引用、可传播的系统名称。
- [已确认] 未来 wireframe 到高保真的扩展流程应先复用系统，缺失模式标记为 `Proposed Pattern` 或 `Open Question`，不能直接提升为全站规则。原因：避免单页偶然样式污染系统。

## 4. 约束与偏好

- [已确认] 不允许擅自发明品牌理念、品牌策略或未确认的视觉语言。
- [已确认] 不要把单页偶然样式写成全站规则。
- [已确认] 不要从未批准 Figma frame 补证据；其他 frame 默认视为 exploratory / non-authoritative。
- [已确认] dark mode 不做自动反色，不从同文件其他 dark 实验稿推断。
- [已确认] 不新增未经确认的组件族、页面 archetype 或 gradient family。
- [已确认] 组件规范中不确定内容必须进入 `Open Questions`，不能硬写成规则。
- [已确认] `tokens.json` token 名称需稳定、语义化、可扩展。
- [已确认] `AGENTS.md` 只写给 Codex 的执行规则，不重复完整设计系统。
- [已确认] Figma Design Doc 必须标注自己是 visual communication layer，不是 system authority。
- [已确认] 后续页面设计应沿用 MOOCKY 自身视觉语言，不做通用企业文档模板或默认 UI 风格。
- [已确认] 核心标题不得混用非确认字体，也不得把完整 Display 标题改成纯 `DM Serif Text`、纯 `Cormorant Infant` 或纯 `Gayathri`。
- [已确认] 非 `16px / 8px / pill` 的圆角、非 `16px / 1.5px` 的 icon 规格，都必须作为特殊情况记录。
- [已确认] 阴影不是默认层级工具；复杂背景前的前景控制组件优先使用半透明背景与 `8px` backdrop blur。

## 5. 未完成事项

- [已确认] 高优先级：为未来具体页面线框图建立高保真落地流程，并持续区分 confirmed / inferred / open question。
- [已确认] 高优先级：继续补全真实页面中的组件状态，尤其 hover、pressed、focus、loading、error、responsive collapse 等尚未完全确认状态。
- [已确认] 中优先级：继续扩展 gradient asset library，但当前不得假定 v1 之外的完整资产族。
- [已确认] 中优先级：在后续页面中验证 dark mode 组件状态，不得从未批准 frame 推断。
- [待确认] 低优先级：是否需要把 Figma Design Doc 进一步做成可发布的团队 presentation / handoff 页面。

## 6. 待确认问题

- [待确认] 未来完整 gradient family 的数量、命名、使用场景和资产清单尚未补全。
- [待确认] 移动端 header collapse、课程页 rail 移动端呈现、导航结构等 responsive 细节仍未最终确认。
- [待确认] Button 各 variant 在 hover / pressed / focus-visible / disabled / loading 下的精确视觉差异仍需补证据。
- [待确认] AI companion 的 typing、streaming、error、answer card、transcript-linked states 尚未确认。
- [待确认] FAQ accordion 是 single-open 还是 multi-open 仍未确认。
- [待确认] 是否需要未来更轻量的 product footer pattern 尚未确认。
- [待确认] 非默认 icon size / stroke 的特殊规格有哪些，目前只确认默认规则。

## 7. 相关产物与文件

- [已确认] `docs/design-system.md`：设计系统唯一事实来源。
- [已确认] `docs/component-specs.md`：组件用途、结构、状态、属性、复用规则、禁止事项与 Open Questions。
- [已确认] `tokens.json`：机器可读 tokens，包含语义色、字体、spacing、radius、icon、layout、gradient 等结构。
- [已确认] `AGENTS.md`：Codex 执行规则，包含证据白名单、dark mode、字体、圆角、Lucide icon、gradient 等约束。
- [已确认] `docs/design-system-audit.md`：早期高保真页面审计记录，不作为规范权威。
- [已确认] Figma 页面 `155:1557 Design Doc`：视觉设计文档页面。
- [已确认] Figma 文档板包括 `00 Cover & Authority`、`01 Brand & Principles`、`02 Foundations`、`03 Theme System`、`04 Page Archetypes`、`05 Component System`、`06 AI Capability + Extension Protocol + Open Questions`、`07 Gradient Appendix Reference`。
- [已确认] Figma `02 Foundations` 已更新：放大 Display Title Pair、加入 `16 / 8 / pill + 60% smoothing`、加入 Lucide icon 规则、优化 spacing / padding。
- [已确认] Lucide 官方来源：https://lucide.dev 和 https://github.com/lucide-icons/lucide。

## 8. 下次启动建议

- [已确认] 先读取 `memory.md`、`docs/design-system.md`、`docs/component-specs.md`、`tokens.json`、`AGENTS.md`，再开始任何设计或代码生成。
- [已确认] 如果涉及 Figma，先检查节点是否在 approved evidence list 内；不在白名单内则询问用户是否批准。
- [已确认] 如果用户提供新 wireframe，先归类到现有 archetype，再复用 tokens 与组件；缺失模式标记为 `Proposed Pattern` 或 `Open Question`。
- [已确认] 如果修改设计系统，先改 `docs/design-system.md`，再同步 `component-specs`、`tokens.json`、`AGENTS.md` 和 Figma Design Doc。
- [已确认] 如果继续优化 Figma Design Doc，优先保持英文主文档、证据边界、字体白名单、圆角 smoothing、Lucide icon 规则一致。
