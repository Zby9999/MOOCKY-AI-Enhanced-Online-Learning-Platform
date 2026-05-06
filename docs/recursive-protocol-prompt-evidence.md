# Recursive Protocol-Guided Agentic Prototyping Prompt Evidence

## Purpose

This file fixes the key prompts and prompt-derived protocol fragments that can be cited as evidence for **Recursive Protocol-Guided Agentic Prototyping**.

These fragments show how the workflow evolved from simple AI-assisted prototyping into a recursive protocol system: prompts produced execution rules, execution rules produced design-system documents, implementation revealed gaps, and those gaps were written back into new rules.

Use this file as an evidence index when writing the professor-facing research memo or DOCX.

## Evidence Status

- Status: confirmed project evidence.
- Language for final paper: English, with Chinese notes allowed only for internal planning.
- Citation style in draft writing: cite by evidence ID, source file, and section title.
- Scope: these are workflow/protocol prompts and prompt-derived rules, not product feature copy.

## Evidence P1: Initial Audit Prompt

### Evidence ID

`P1_INITIAL_AUDIT_PROMPT`

### Source

- File: `Project Portfolio Doc/GPT-Conversation-memory.md`
- Section: `4.1 Codex 审计页面的初始任务`
- Local anchor line at time of capture: line `369`

### Prompt Fragment

```text
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

### Why It Matters

This prompt marks the shift from one-shot page generation to protocol-guided design-system extraction. It asks the agent to inspect, classify, and document before changing the UI.

### Suggested Use In Paper

Use this as evidence that the workflow began with an audit-first protocol, where the agent was asked to produce structured design knowledge before implementation.

## Evidence P2: Per-Change Classification Prompt

### Evidence ID

`P2_UI_CHANGE_CLASSIFICATION_PROMPT`

### Source

- File: `Project Portfolio Doc/GPT-Conversation-memory.md`
- Section: `4.2 每轮 UI 改动后的归类要求`
- Local anchor line at time of capture: line `395`

### Prompt Fragment

```text
For every UI change, classify it as one of:
- token
- reusable component
- layout rule
- interaction/state rule
- page-specific exception

If the change introduces a reusable rule, update the relevant design-system file.
If it is not confirmed, place it in candidates.md or open-questions.md.
```

### Why It Matters

This prompt created the recursive loop. Each implementation change had to be classified, and reusable or uncertain decisions had to be written back into the documentation system.

### Suggested Use In Paper

Use this as the core evidence for "recursive" behavior: implementation was not an endpoint, but a trigger for rule classification and documentation updates.

## Evidence P3: Agent Execution Boundary Prompt

### Evidence ID

`P3_AGENT_EXECUTION_BOUNDARY_PROMPT`

### Source

- File: `Project Portfolio Doc/GPT-Conversation-memory.md`
- Section: `4.3 给 Codex 的执行边界`
- Local anchor line at time of capture: line `413`

### Prompt Fragment

```text
Do not freely redesign the product.
Do not invent new visual styles.
Do not hardcode colors, font sizes, spacing, radius, shadows, borders, or motion values.
Use existing tokens and components whenever possible.
If a style or component is not confirmed, document it as a candidate instead of promoting it to a global rule.
```

### Why It Matters

This prompt constrained the AI agent as a design-system-aware implementer rather than an unconstrained visual designer.

### Suggested Use In Paper

Use this as evidence for human control and agent governance: the designer defined boundaries, while the agent executed within them.

## Evidence P4: Open-Question Confirmation Prompt

### Evidence ID

`P4_OPEN_QUESTION_CONFIRMATION_PROMPT`

### Source

- File: `Project Portfolio Doc/GPT-Conversation-memory.md`
- Section: `4.4 不确定项确认轮`
- Local anchor line at time of capture: line `427`

### Prompt Fragment

```text
Before finalizing the design system, list the key open questions that require user confirmation.
Only include questions that affect global consistency, reusable components, tokens, layout rules, or interaction rules.
For each question, provide:
- why it matters
- impacted files/components
- recommended default
- what will change if confirmed
```

### Why It Matters

This prompt introduced a human-in-the-loop checkpoint before uncertain observations could become system rules.

### Suggested Use In Paper

Use this to show that the workflow did not allow AI-generated assumptions to silently become design-system authority.

## Evidence P5: Source Priority Protocol

### Evidence ID

`P5_SOURCE_PRIORITY_PROTOCOL`

### Source

- File: `AGENTS.md`
- Section: `Source Priority`
- Local anchor line at time of capture: line `7`

### Protocol Fragment

```text
1. docs/design-system.md
2. docs/component-specs.md
3. tokens.json
4. design-system/tokens.json
5. design-system/components.md
6. design-system/layout-rules.md
7. design-system/interaction-rules.md
8. design-system/decisions.md
9. design-system/candidates.md
10. AGENTS.md

If a rule changes, update the source of truth first.
```

### Why It Matters

This protocol turned multiple Markdown and JSON files into an ordered governance stack. It prevented later agent work from treating all documentation as equal.

### Suggested Use In Paper

Use this as the clearest evidence for "protocol-guided": the agent was given an explicit hierarchy of design and implementation authorities.

## Evidence P6: Core Execution Rules

### Evidence ID

`P6_CORE_EXECUTION_RULES`

### Source

- File: `AGENTS.md`
- Section: `Core Execution Rules`
- Local anchor line at time of capture: line `22`

### Protocol Fragment

```text
- Treat docs/design-system.md as the only normative design source.
- Treat docs/component-specs.md as an implementation companion, not an authority.
- Treat tokens.json as the machine-readable contract for implementation.
- Treat design-system/* as the v0.1 seed implementation layer that translates the normative system into reusable tokens, components, layout rules, interaction rules, decisions, and candidates.
- Do not invent missing design rules in code.
```

### Why It Matters

This protocol made the agent's interpretation of documentation explicit. It also separated design authority, implementation companion notes, machine-readable contracts, and seed-layer documentation.

### Suggested Use In Paper

Use this when explaining how Markdown rules became operational instructions rather than passive documentation.

## Evidence P7: Seed Page Execution Protocol

### Evidence ID

`P7_SEED_PAGE_EXECUTION_PROTOCOL`

### Source

- File: `AGENTS.md`
- Section: `Seed Page Execution Rules`
- Local anchor line at time of capture: line `68`

### Protocol Fragment

```text
The current landing page is the Lumen Atlas v0.1 seed page, not a disposable prototype.

Before every UI change, classify the change as exactly one of:
- design token
- reusable component
- layout rule
- interaction/state rule
- one-off page-specific style

If a style, structure, or behavior may be reused on two or more pages, do not leave it only in the current page implementation. Promote it into the design-system seed layer or record it as a candidate.

Do not hardcode colors, font sizes, radii, shadows, spacing, or motion values for the convenience of one page.
```

### Why It Matters

This protocol redefined the landing page from a disposable prototype into a seed surface for future design-system growth.

### Suggested Use In Paper

Use this to explain how the prototype and the design system co-evolved.

## Evidence P8: Figma MCP Double-Evidence Protocol

### Evidence ID

`P8_FIGMA_DOUBLE_EVIDENCE_PROTOCOL`

### Source

- File: `AGENTS.md`
- Section: `Figma MCP Double-Evidence Workflow`
- Local anchor line at time of capture: line `148`

### Protocol Fragment

```text
For future modifications, component parity work, and new page creation that reference Figma:

1. Use Figma MCP/Inspect before coding for the exact node or variant being implemented.
2. Capture structured specs from MCP/Inspect for Auto Layout padding, gap, dimensions, constraints, typography, fills, variables, component state names, assets, and motion values when available.
3. Capture or fetch a screenshot of the same node or variant as the visual reference.
4. Implement from the structured specs first, mapping values to existing tokens before adding new ones.
5. Verify in browser screenshots with Playwright after implementation, including 1440px, 1024px, and 390px, and both Light Mode and Dark Mode whenever the surface supports themes.
6. Compare screenshots by spacing, font size, color, alignment, border radius, shadow, interaction state, and responsive behavior.
7. Do not claim full parity when either MCP/Inspect specs or screenshot verification are missing.
```

### Why It Matters

This protocol turned Figma into a structured evidence source rather than a loose visual inspiration board.

### Suggested Use In Paper

Use this as evidence for the workflow's verification and evidence-bound design-to-code translation.

## Evidence P9: Prototype Playwright Acceptance Protocol

### Evidence ID

`P9_PLAYWRIGHT_ACCEPTANCE_PROTOCOL`

### Source

- File: `AGENTS.md`
- Section: `Prototype Playwright Acceptance`
- Local anchor line at time of capture: line `261`

### Protocol Fragment

```text
After completing any prototype UI update, run a Playwright acceptance pass before final output whenever the local app can be built and opened.

1. Open the local page with Playwright.
2. Capture screenshots at 1440px, 1024px, and 390px viewport widths in both Light Mode and Dark Mode.
3. Compare both Light Mode and Dark Mode screenshots against the available reference screenshots or approved Figma reference for the updated page or component.
4. List visual differences by category:
   - spacing
   - font size
   - color
   - alignment
   - border radius
   - shadow
   - responsive behavior
5. Fix confirmed differences without changing unrelated sections or components.
6. Verify hover/focus states in both modes for every updated interactive component.
7. Repeat the Playwright screenshot comparison loop up to 3 rounds.
8. In the final response, report any differences that still cannot be fully matched.
```

### Why It Matters

This protocol established the monitoring and acceptance layer of the workflow.

### Suggested Use In Paper

Use this as evidence that the workflow evaluated prototypes beyond code completion, including viewport behavior, theme behavior, interaction states, and residual visual differences.

## Evidence P10: Decision Log For Landing As Seed Page

### Evidence ID

`P10_SEED_PAGE_DECISION_LOG`

### Source

- File: `design-system/decisions.md`
- Section: `2026-04-26: Treat Landing as Seed Page`
- Local anchor line at time of capture: line `5`

### Decision Fragment

```text
Decision: The landing page is no longer just a prototype page. It is the v0.1 seed page for Lumen Atlas.

Implications:
- Every UI change must be classified before implementation.
- Reusable styles and structures must be promoted into the design system instead of living only in page CSS.
- After each UI tuning round, update design-system/tokens.json, design-system/components.md, design-system/layout-rules.md, design-system/interaction-rules.md, and design-system/decisions.md.
- Ambiguous patterns go to design-system/candidates.md.
```

### Why It Matters

This is the decision-log proof that the seed-page protocol was not only a prompt, but became a durable project rule.

### Suggested Use In Paper

Use this when explaining how the workflow converted prompt instructions into persistent design-system governance.

## Evidence P11: Decision Log For Playwright Acceptance

### Evidence ID

`P11_PLAYWRIGHT_ACCEPTANCE_DECISION_LOG`

### Source

- File: `design-system/decisions.md`
- Section: `2026-04-26: Playwright Acceptance`
- Local anchor line at time of capture: line `79`

### Decision Fragment

```text
Decision: UI updates must be checked with Playwright at 1440px, 1024px, and 390px when the local app can be built and opened.

Reason: The seed page is used to validate reusable layout and component rules across desktop and narrow responsive states.
```

### Why It Matters

This confirms that acceptance checks became part of the design-system governance process.

### Suggested Use In Paper

Use this when explaining how the workflow evaluated responsive behavior as part of reusable design validation.

## Evidence P12: Decision Log For Viewport Reveal Runtime

### Evidence ID

`P12_VIEWPORT_REVEAL_RUNTIME_DECISION_LOG`

### Source

- File: `design-system/decisions.md`
- Section: `2026-04-27: Staggered Section Reveal`
- Local anchor line at time of capture: line `116`

### Decision Fragment

```text
Decision: Promote staggered viewport reveal to a confirmed interaction rule. Reveal items are visible by default, transition from opacity 0 to 1 and translateY(14px) to 0 only while marked reveal-pending, and same-batch reveal items enter top-to-bottom with a 160ms stagger capped at 320ms.

Confirmed behavior:
- Runtime evaluates first-viewport reveal items immediately on mount.
- Section-level components remain the default reveal boundary.
- Footer is excluded from viewport reveal on every interface.
- Reduced-motion users bypass translate movement and stagger delay.
```

### Why It Matters

This decision shows how implementation and acceptance findings produced a reusable interaction rule.

### Suggested Use In Paper

Use this as a concrete example of recursive rule growth: a UI behavior became a shared runtime and then a default rule for new pages.

## Evidence P13: Decision Log For Double-Evidence Workflow

### Evidence ID

`P13_DOUBLE_EVIDENCE_DECISION_LOG`

### Source

- File: `design-system/decisions.md`
- Section: `2026-04-27: Figma MCP And Screenshot Double Evidence`
- Local anchor line at time of capture: line `148`

### Decision Fragment

```text
Decision: Future Figma-backed modifications, component parity work, and new page creation must use a double-evidence workflow. MCP/Inspect is required before implementation for exact specs, and screenshots/Playwright are required after implementation for visual acceptance.

Required evidence:
- MCP/Inspect: exact node or variant, Auto Layout padding and gap, dimensions, constraints, typography, fills, variables, component states, assets, and motion values when available.
- Screenshot/Playwright: final composition, spacing, font size, color, alignment, radius, shadow, interaction state, responsive behavior, and Light/Dark Mode checks when themed.

Reason: Screenshot-only implementation can look close while missing spacing-sensitive values.
```

### Why It Matters

This decision closes the loop between Figma evidence, code implementation, and browser verification.

### Suggested Use In Paper

Use this as one of the central evidence points for Recursive Protocol-Guided Agentic Prototyping.

## Evidence P14: Runtime AI System Prompt Contract

### Evidence ID

`P14_RUNTIME_AI_SYSTEM_PROMPT_CONTRACT`

### Source

- File: `docs/ai-system-prompt.md`
- Section: `System Prompt`
- Local anchor line at time of capture: line `31`

### Protocol Fragment

```text
You are MOOCKY AI, the AI learning support layer for MOOCKY, an AI-enhanced online learning platform.

Your behavior must follow the Lumen Atlas design system:
- Be rational, warm, calm, precise, and supportive.
- Avoid flattery, sycophantic phrasing, hype, gamified encouragement, or sales-heavy language.
- Do not overpraise the user or mirror their assumptions uncritically.
- Help the learner feel oriented and capable.
- Guide the learner toward relevant course content when useful.

Output contract:
- Return only a valid JSON object.
- Do not wrap the JSON in Markdown.
- Do not add commentary outside the JSON.
- Use a structured envelope with answerMarkdown, contextTags, followUpChips, and courseRecommendationCards.
```

### Why It Matters

This shows that the protocol logic extended beyond visual implementation into runtime AI behavior. The product-facing AI was also governed by structured prompts and UI-owned state rules.

### Suggested Use In Paper

Use this cautiously as a secondary example. It is not the core design-to-code workflow evidence, but it supports the broader claim that MOOCKY used protocol documents to govern both agent implementation and runtime AI behavior.

## Recommended Citation Set

For the professor-facing memo, cite the following first:

1. `P1_INITIAL_AUDIT_PROMPT`
2. `P2_UI_CHANGE_CLASSIFICATION_PROMPT`
3. `P5_SOURCE_PRIORITY_PROTOCOL`
4. `P7_SEED_PAGE_EXECUTION_PROTOCOL`
5. `P8_FIGMA_DOUBLE_EVIDENCE_PROTOCOL`
6. `P9_PLAYWRIGHT_ACCEPTANCE_PROTOCOL`
7. `P13_DOUBLE_EVIDENCE_DECISION_LOG`

These seven pieces are enough to support the central story:

> A design-to-code workflow became recursive when prompt instructions were converted into a persistent protocol stack, and that protocol stack guided the AI agent through evidence selection, implementation, verification, and rule updates.

## Notes For Future Writing

- Do not claim these are all raw user prompts. Some are preserved prompt fragments; others are prompt-derived project rules.
- Use the phrase "prompt and prompt-derived protocol evidence" when discussing this set.
- The strongest phrase for the paper is: "The prompts did not remain conversational instructions; they were progressively externalized into persistent Markdown protocols."
- The safest claim is: "This case shows how a human designer can use prompt-derived Markdown protocols to constrain and recursively shape an AI coding agent's design-to-code behavior."

