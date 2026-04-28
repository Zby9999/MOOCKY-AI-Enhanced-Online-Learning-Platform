# Memory

## 1. 当前目标

- [已确认] 当前项目是设计一个 AI 赋能在线学习网站，品牌名为 `MOOCKY`。
- [已确认] 当前设计系统正式命名为 `Lumen Atlas`；它是 MOOCKY 的设计系统名称，不替代产品品牌名。
- [已确认] 当前阶段重点是建立完整、可复用、可继续扩展的设计系统。
- [已确认] 当前最新完成页面是 `MyProgress` 正式页面，已接入 Landing Page 登录后的 Navi Bar `MyProgress` 入口，并已部署到稳定 Vercel 地址。
- [已确认] 当前正在制作课程详情页 `/course`，课程名固定为 `Neural Architecture`，小标题为 `Transformers & Attention`。
- [已确认] 设计系统需要服务后续流程：用户提供具体页面线框图，Codex 基于已确认系统规则产出可用高保真设计。
- [已确认] 本地 `docs/design-system.md` 是设计系统唯一事实来源；Figma Design Doc 是视觉沟通层，不替代源文档。

## 2. 已确认事实

- [已确认] 品牌标准写法是 `MOOCKY`，logo 由 wordmark 和 sparkle 星标组成。
- [已确认] 设计系统标准写法是 `Lumen Atlas`。
- [已确认] Figma 文件 key 是 `hoN23Dj67OVv6D0drKYY24`。
- [已确认] 可作为系统证据的 Figma 页面节点包括：`42:93`、`60:551`、`100:3535`、`180:1596`、`180:1831`、`180:1880`、`173:1582`。
- [已确认] Figma 节点 `257:2062` 仅作为 Button 组件库证据：用途、命名、状态、锁定视觉、dark variants、Button 特殊情况。不得用于推断其它页面布局、非按钮组件或全局视觉基础。
- [已确认] Figma 节点 `260:2775` 仅作为 AI answered rail state 证据：AI rail header、用户消息气泡、AI answer block、底部 AI Prompt Field、顶部操作按钮。不得用于推断非 AI 组件、非 AI 页面布局或新的全局视觉基础。
- [已确认] Figma 节点 `348:8253` 与 `348:8271` 仅作为 landing `RecommendedCourseCard` hover 交互证据：collapsed card、expanded lower panel、title transition、metadata reveal、arrow rotation、`160ms ease-out` smart-animation 参数。不得外推为全局卡片系统、暗色值或其它页面布局规则。
- [已确认] 其中 light evidence 是 `42:93` Landing、`60:551` 课程暂停页、`100:3535` 课程播放页。
- [已确认] dark evidence 是 `180:1596`、`180:1831`、`180:1880`，只能从这些 dark frame 理解暗色模式。
- [已确认] gradient appendix evidence 是 `173:1582`，现有 `Images` 画板需保留为渐变附录。
- [已确认] 同一 Figma 文件中的其他 frame 都是实验废案，未经用户再次批准不得作为系统证据。
- [已确认] 抽象条纹渐变是 MOOCKY 独特视觉风格，需要沿用到正式网页中。
- [已确认] 当前 v1 渐变以 yellow / blue / red / gold 的 warm spectral family 为主，未来会继续补全变体。
- [已确认] 核心元素和文字需达到 WCAG AA；装饰性或辅助性元素可适当放宽。
- [已确认] AI 是全站核心能力，不是装饰模块；当前确认的 AI 形态包括课程页 AI companion rail，以及 hero prompt / header search 中用于课程推荐和平台介绍的 AI 入口。
- [已确认] AI 共享交互状态为：`idle`、`promptSuggested`、`composerFocused`、`composing`、`sending`、`streaming`、`answered`、`error`、`emptyContext`。
- [已确认] `Button` 是唯一全局统一交互组件，其他组件默认按场景处理。
- [已确认] Button 现在按用途定义为 12 类：`standaloneIcon`、`auxiliaryAction`、`primaryAction`、`cardGuideAction`、`aiChatFunctionChip`、`aiQuestionPromptChip`、`searchPrompt`、`panelIconGroup`、`newsletterCompound`、`panelStandaloneIcon`、`floatingResume`、`categoryCard`。
- [已确认] 当前确认页面 archetype 包括 Marketing / Landing Shell、Learning / Course Shell、AI as Global Capability。
- [已确认] `MyProgress` 已从 prototype 前缀迁入正式路由 `/my-progress`；旧 `/prototypes/my-progress` 仅保留 redirect，避免历史链接断开。
- [已确认] 课程详情页的正式进入方式是从 `MyProgress` 页面点击 `Continue learning` 进入；它不是独立营销入口。
- [已确认] 最新稳定预览地址是 `https://moocky-frontend-engineering-shell.vercel.app/`；最新 production deployment 是 `https://moocky-frontend-engineering-shell-je1x77hfh.vercel.app/`。
- [已确认] Vercel deployment `dpl_E8dhBPzXFA3HPSgPMrAxryUZG4bp` 状态为 `READY`，target 为 `production`。

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
- [已确认] Button icon 只能通过受控 Lucide icon name / `LumenIcon` 管线进入组件；不得传 raw `ReactNode`、`<img>`、page-level SVG asset 或自定义 inline SVG。Button icon 的颜色与 stroke 必须继承 Button 的 `currentColor`，这样 Light/Dark Mode、hover、focus-visible 都自动跟随文字颜色变化。
- [已确认] Chatbox / AI Prompt Field 的发送箭头也继承 `currentColor`；发送按钮本身必须设置语义 surface contrast 前景色：light accent fill 上为白色，dark accent fill 上为黑色。不得为了修箭头单独给 icon 写死颜色。
- [已确认] FAQAccordion 的 chevron 是已记录的 icon size 特例：Lucide `chevron-down` 使用 `24px` viewport、`1.5px` stroke、`currentColor`，以保留旧 Figma `12px × 7.4px` filled chevron 的视觉占比；不得回退为图片资产。
- [已确认] Padding 粗分为三档：长按钮与细长操作控件 `12px`，卡片和标准组件容器 `16px`，更大模块与更宽内容容器 `24px`。核心规则不是数学等距，而是让内容物舒适、完整地落在容器视觉中心；可为 typography、icon、media、pill 几何或密度做小幅 optical adjustment，但不得因此新增常规 padding 档位。
- [已确认] 阴影策略需要极其克制：正常情况下不使用任何阴影效果，后续原型生成也不得默认给卡片、按钮、面板、rail、输入框增加阴影。原因：保持 MOOCKY 的低 chrome、安静层级。
- [已确认] 在复杂渐变、图片或媒体背景前，为了增加层次感，使用透明/半透明组件背景加 `8px` 背景模糊，而不是 drop shadow。Figma 节点 `74:594` 仅作为这一策略的聚焦参考，不作为其它系统规则证据。
- [已确认] Button 的颜色、样式、padding 策略、圆形按钮尺寸、长按钮高度、hover 效果和 dark variants 必须严格遵守 `257:2062`；可编辑内容仅限文字和非动作按键 icon。
- [已确认] Button 默认 hover 动效为 default 到 hover 的 `160ms ease-out` 过渡；`floatingResume` 是已批准的 Button 阴影例外，hover 可使用 `0px 0px 8px` glow。
- [已确认] 设计系统正式命名为 `Lumen Atlas`。原因：为 MOOCKY 的视觉与组件规范建立可被引用、可传播的系统名称。
- [已确认] 未来 wireframe 到高保真的扩展流程应先复用系统，缺失模式标记为 `Proposed Pattern` 或 `Open Question`，不能直接提升为全站规则。原因：避免单页偶然样式污染系统。
- [已确认] AI 用户问题显示为右对齐消息气泡，AI 回答显示为左对齐 `AIAnswerBlock`，回答块使用 Lucide `sparkle` 而不是 MOOCKY logo sparkle。
- [已确认] AI thinking 状态显示 `Thinking`，Lucide `sparkle` 可使用低动效 glow、旋转、缩放循环；v1 不需要 reduced-motion 版本。
- [已确认] AI Prompt Field 在用户输入时隐藏 starter prompt chips，清空时恢复；发送瞬间禁用输入并隐藏 chips；回答后在答案后出现最多 3 个推荐追问 chips。
- [已确认] AI 回答块上下文信息包括 `Current lesson`、`timestamp`、`course title`，放在类似 `Thought for 3m 32s` 样式的下一行。
- [已确认] AI 回答操作包括 copy、save、thumbs up、thumbs down，答案过长时提供 full-screen；不包含 regenerate。thumbs up/down 互斥并保留反馈状态。
- [已确认] AI 长回答是否进入 full-screen 按视觉高度判断，不按字数硬切。
- [已确认] AI refusal 使用 `AIAnswerBlock` 解释原因并引导回课程上下文，不作为普通 error 样式处理。
- [已确认] AI 个性化只通过语气和回答内容体现，不加持久个性化标签。
- [已确认] 原型阶段使用经过 system prompt 约束的 GPT API 作为 MOOCKY AI 支持，系统提示词和 API 输出契约写入 `docs/ai-system-prompt.md`。
- [已确认] GPT API 输出采用结构化 JSON envelope，正文放在 `answerMarkdown`，`contextTags`、`followUpChips`、`courseRecommendationChips` 由模型直接生成并由 UI 专门渲染。
- [已确认] GPT API 回答语言跟随用户输入语言；禁止在回答中暴露 hidden reasoning、chain-of-thought 或 `Thought for...` 文本。
- [已确认] AI 语气应理性、温和、准确、支持性，限制谄媚和过度迎合；hero/header 主要推荐课程和介绍平台，course rail 只有在确实适合时推荐其他课程。
- [已确认] `Recommended For You` 卡片默认全部收起；hover/focus 时 lower pill 以 `160ms ease-out` 展开为 `280px` panel，标题从 `Geist 20px` 过渡到 `DM Serif Text 24px`，描述/机构/评分信息淡入，Lucide `arrow-up-right` 从右向姿态转为右上姿态。动画实现必须避免 hover 起点切换 flex 布局；panel 内部层保持稳定位置。collapsed pill 的动画半径使用 `30px`（`60px` 高度的一半）而不是 `9999px`，避免插值成过大的椭圆。该交互目前仅确认用于 landing/discovery recommendation 模块。
- [已确认] MyProgress 使用共享 `reveal-on-view` 组件渐显动效，Footer 不参与 reveal；四个数据 metric chips 作为同一个 `statPanelGroup` 整体渐显，不分别 stagger。原因：四个指标属于一个信息组，逐个弹出会制造错误的信息层级。
- [已确认] Landing Page 登录后 Navi Bar 左侧 `MyProgress` 保持原按钮位置和样式，但变成链接并进入 `/my-progress`。原因：让 MyProgress 从登录后主流程进入，同时保持与原系统导航一致。
- [已确认] Demo 阶段的 `Log In` 是浏览器内的登录态切换：点击一次后写入 `moocky-demo-authenticated-v1`，Landing 与 AI workspace 的 Navi Bar 在路由切换和刷新后继续保持登录态，直到清除 localStorage。
- [已确认] MyProgress 页面自身也必须使用登录态 Navi Bar：右侧包含 header search、Notifications、MOOCKY coins、theme preview toggle、profile action；不得显示访客态 `Log In` / `Explore MOOCKY`。
- [已确认] MyProgress 中间四个大字数据记录为 `DataPanelMetricValue` 特殊用法，可使用 `Geist Semibold 32px / 40px`。原因：它们是可扫描的数据值，不是普通 Geist 大标题。
- [已确认] 课程详情页 `/course` 的入口文案在 MyProgress 中应使用 `Continue learning`，并保持链接到 `/course`。原因：演示路径需要从学习进度页自然进入当前课程。

## 4. 约束与偏好

- [已确认] 不允许擅自发明品牌理念、品牌策略或未确认的视觉语言。
- [已确认] 不要把单页偶然样式写成全站规则。
- [已确认] 不要从未批准 Figma frame 补证据；其他 frame 默认视为 exploratory / non-authoritative。
- [已确认] dark mode 不做自动反色，不从同文件其他 dark 实验稿推断。
- [已确认] dark mode 中与 light `#3E332E` 对应的 `text.primary` 已从 `#F2E1CA` 调整为低饱和暖白 `#EDE8E1`。这是全局 design token 变更，影响 dark headings、primary action text，以及当前继承 dark primary 的 AI reading text。
- [已确认] 不新增未经确认的组件族、页面 archetype 或 gradient family。
- [已确认] 组件规范中不确定内容必须进入 `Open Questions`，不能硬写成规则。
- [已确认] `tokens.json` token 名称需稳定、语义化、可扩展。
- [已确认] `AGENTS.md` 只写给 Codex 的执行规则，不重复完整设计系统。
- [已确认] Figma Design Doc 必须标注自己是 visual communication layer，不是 system authority。
- [已确认] 后续页面设计应沿用 MOOCKY 自身视觉语言，不做通用企业文档模板或默认 UI 风格。
- [已确认] 核心标题不得混用非确认字体，也不得把完整 Display 标题改成纯 `DM Serif Text`、纯 `Cormorant Infant` 或纯 `Gayathri`。
- [已确认] 非 `16px / 8px / pill` 的圆角、非 `16px / 1.5px` 的 icon 规格，都必须作为特殊情况记录。
- [已确认] Padding 微调只能服务于视觉中心与内容舒适放置；反复出现的微调必须记录为组件特殊情况，不能静默提升为全局规则。
- [已确认] 阴影不是默认层级工具；复杂背景前的前景控制组件优先使用半透明背景与 `8px` backdrop blur。
- [已确认] Figma Button 组件命名采用 API 风格 `Button/<Purpose>/<Theme>`；variant 命名为 `State=Default` 和 `State=Hover`。
- [已确认] `newsletterCompound` 实现时 input hover 与主按钮 hover 需要分开，但当前 Figma 组件库不新增拆分 variant，只在规则中说明。

## 5. 未完成事项

- [已确认] 高优先级：为未来具体页面线框图建立高保真落地流程，并持续区分 confirmed / inferred / open question。
- [已确认] 高优先级：继续补全真实页面中的组件状态，尤其 pressed、focus、loading、error、responsive collapse 等尚未完全确认状态。
- [已确认] 高优先级：继续补全 AI dark edge states、transcript-linked selected-context states、特殊 answer card 类型和详细 error taxonomy。
- [已确认] 中优先级：继续扩展 gradient asset library，但当前不得假定 v1 之外的完整资产族。
- [已确认] 中优先级：在后续页面中验证 dark mode 组件状态，不得从未批准 frame 推断。
- [待确认] 低优先级：是否需要把 Figma Design Doc 进一步做成可发布的团队 presentation / handoff 页面。
- [待确认] MyProgress 最终登录态鉴权流程如何接入。

## 6. 待确认问题

- [待确认] 未来完整 gradient family 的数量、命名、使用场景和资产清单尚未补全。
- [待确认] 移动端 header collapse、课程页 rail 移动端呈现、导航结构等 responsive 细节仍未最终确认。
- [待确认] Button 的 focus-visible、pressed、disabled、loading 精确视觉仍需补证据；default 和 hover 已由 `257:2062` 确认。
- [待确认] AI dark edge states、transcript-linked selected-context states、特殊 answer card 类型和详细 error taxonomy 尚未确认。
- [待确认] FAQ accordion 是 single-open 还是 multi-open 仍未确认。
- [待确认] 是否需要未来更轻量的 product footer pattern 尚未确认。
- [待确认] 非默认 icon size / stroke 的特殊规格有哪些，目前只确认默认规则。
- [待确认] 本机终端 `curl` 访问 Vercel 域名可能超时；本次部署通过 Vercel Inspect 确认 READY，并通过外部网页抓取确认稳定首页可打开，但后续仍应尽量完成稳定 URL 的 `200 OK` 检查。

## 7. 相关产物与文件

- [已确认] `docs/design-system.md`：设计系统唯一事实来源。
- [已确认] `docs/component-specs.md`：组件用途、结构、状态、属性、复用规则、禁止事项与 Open Questions。
- [已确认] `docs/ai-system-prompt.md`：MOOCKY AI 原型 GPT API system prompt、结构化输出契约和实现注意事项。
- [已确认] `tokens.json`：机器可读 tokens，包含语义色、字体、spacing、radius、icon、layout、gradient 等结构。
- [已确认] `AGENTS.md`：Codex 执行规则，包含证据白名单、dark mode、字体、圆角、Lucide icon、gradient 等约束。
- [已确认] `docs/design-system-audit.md`：早期高保真页面审计记录，不作为规范权威。
- [已确认] Figma 页面 `155:1557 Design Doc`：视觉设计文档页面。
- [已确认] Figma 文档板包括 `00 Cover & Authority`、`01 Brand & Principles`、`02 Foundations`、`03 Theme System`、`04 Page Archetypes`、`05 Component System`、`06 AI Capability + Extension Protocol + Open Questions`、`07 Gradient Appendix Reference`。
- [已确认] Figma `02 Foundations` 已更新：放大 Display Title Pair、加入 `16 / 8 / pill + 60% smoothing`、加入 Lucide icon 规则、优化 spacing / padding。
- [已确认] Figma `Buttons` section `257:2062` 用于 Button 组件库规则和英文说明。
- [已确认] Figma `260:2775` 用于 AI answered rail state、AIAnswerBlock、用户消息气泡和 AI Prompt Field 的聚焦参考。
- [已确认] Lucide 官方来源：https://lucide.dev 和 https://github.com/lucide-icons/lucide。
- [已确认] `app/my-progress/page.tsx`：MyProgress 正式页面，已加共享 `ViewportRevealRuntime`，并接入主要模块的 reveal 边界。
- [已确认] `app/my-progress/my-progress.module.css`：MyProgress 正式页面样式，包含 `statPanelGroup`、紧凑 footer、AI insights、Learning Coach、Active courses 等样式。
- [已确认] `app/course/page.tsx` 与 `app/course/CoursePageClient.tsx`：课程详情页正式路由与客户端课程学习工作台实现。
- [已确认] `app/hooks/useRevealOnView.ts`：共享 viewport reveal 运行时，供 Landing 和 MyProgress 复用。
- [已确认] `app/components/ViewportRevealRuntime.tsx`：在 server route 内挂载 reveal hook 的 client runtime。
- [已确认] Vercel 生产 AI API 依赖 `docs/ai-system-prompt.md`；`.vercelignore` 必须保留该文件进入部署包，否则 `/api/moocky-ai` 和 `/api/moocky-ai/stream` 会因 `ENOENT` 回退/失败。

## 8. 下次启动建议

- [已确认] 先读取 `memory.md`、`docs/design-system.md`、`docs/component-specs.md`、`tokens.json`、`AGENTS.md`，再开始任何设计或代码生成。
- [已确认] 如果涉及 Figma，先检查节点是否在 approved evidence list 内；不在白名单内则询问用户是否批准。
- [已确认] 如果用户提供新 wireframe，先归类到现有 archetype，再复用 tokens 与组件；缺失模式标记为 `Proposed Pattern` 或 `Open Question`。
- [已确认] 如果修改设计系统，先改 `docs/design-system.md`，再同步 `component-specs`、`tokens.json`、`AGENTS.md` 和 Figma Design Doc。
- [已确认] 如果继续优化 Figma Design Doc，优先保持英文主文档、证据边界、字体白名单、圆角 smoothing、Lucide icon 规则一致。
- [已确认] 如果用户说“部署预览”，按当前 production preview workflow 执行：先运行 `npm run build`，再运行 `vercel deploy --prod --yes`，然后验证稳定地址 `https://moocky-frontend-engineering-shell.vercel.app/`，最后更新 `AGENTS.md` 的 Latest Prototype Preview 和 `memory.md`。
- [已确认] 下次继续 MyProgress 时，先打开 `/my-progress` 检查 Landing 登录后入口、viewport reveal、metric group reveal、移动端 header 与 footer 是否仍符合当前设计意图。
