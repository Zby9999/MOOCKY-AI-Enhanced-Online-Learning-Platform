# Lumen Atlas Design System

## Authority

This document is the single source of truth for Lumen Atlas, the MOOCKY design system.

- If this document conflicts with [`component-specs.md`](./component-specs.md), this document wins.
- [`tokens.json`](../tokens.json) is the machine-readable expression of the rules defined here.
- [`design-system-audit.md`](./design-system-audit.md) is an evidence archive, not a normative source.
- [`AGENTS.md`](../AGENTS.md) is an execution guide for Codex and must not override system rules.

## Evidence Scope

This system is grounded in the following confirmed Figma evidence:

- Landing page: `42:93`
- Course page, paused / progress rail: `60:551`
- Course page, playing / AI rail: `100:3535`
- Landing page, dark mode: `180:1596`
- Course page, paused / progress rail, dark mode: `180:1831`
- Course page, playing / AI rail, dark mode: `180:1880`
- Gradient asset library sample: `173:1582`
- Confirmed conversation decisions captured after the audit

Only these six page nodes plus the approved gradient appendix and explicitly confirmed focused references may be used as system evidence.

- Other frames in the same Figma file are exploratory and non-authoritative by default.
- They must not be used to infer new rules unless the user explicitly approves them later.

Focused references are narrow by definition:

- Node `74:594` is approved only as evidence for the translucent foreground surface plus `8px` backdrop blur strategy over complex gradient/media backgrounds.
- It must not be used to infer unrelated typography, color, radius, layout, or component-system rules.

This document defines:

- global foundations
- confirmed page archetypes
- extension rules for future wireframes

This document does not invent full-page patterns for screens that have not been designed yet.

## Brand Foundations

### Canonical Identity

- Design system name must be written as `Lumen Atlas`.
- `Lumen Atlas` names the design system, not the learner-facing product brand.
- Brand name must be written as `MOOCKY`.
- The canonical logo is the `MOOCKY` wordmark plus the sparkle mark as a single lockup.
- The sparkle mark must not be detached and used as a replacement logo.

### Visual Intent

MOOCKY combines editorial identity with calm product utility.

- Editorial expression should lead identity-setting moments.
- Product utility should lead task-heavy interfaces.
- The system should feel intelligent, warm, and spatially calm rather than loud or gamified.

### Editorial Boundary

Editorial display typography is not limited to the hero only, but it must remain attached to one of the following:

- page-defining titles
- brand-defining statements
- section-level identity moments

Editorial type must not become the default style for dense product UI, system labels, or operational controls.

## Core Design Principles

### 1. Calm Surfaces, Strong Hierarchy

- Use spacing, typography, and image treatment before introducing chrome.
- Default surfaces should remain light, quiet, and minimally ornamented.
- Borders should carry more hierarchy than shadows in the light theme.

### 2. Editorial Identity, Product Restraint

- Use expressive display typography for brand moments.
- Use compact, highly legible UI typography for navigation, metadata, forms, and controls.
- Avoid overextending editorial styling into dense product flows.

### 3. Rounded, Soft Geometry

- Rounded geometry is foundational across buttons, pills, fields, cards, rails, and overlays.
- The system should feel soft and intelligent rather than sharp or industrial.

### 4. AI as a Core Product Capability

- AI is a global product capability, not a decorative add-on.
- The currently confirmed AI surface is the course companion rail.
- Future AI surfaces must inherit the same design logic: assistive, embedded, and contextual.

### 5. Brand Gradients Are Assets, Not Decoration

- Abstract stripe/mesh gradients are part of the official brand language.
- They are not placeholder art.
- They must be treated as named brand assets with controlled usage.

## Visual Language

### Surface Hierarchy

#### Light Theme

- `canvas` is warm off-white.
- `surface` is white or near-white.
- `border` is subtle and semi-transparent.
- `shadow` is absent by default and only appears as an explicitly documented special case.

#### Dark Theme

- Dark mode is in scope.
- Dark mode must follow the approved dark reference frames only, not automatic inversion.
- Approved dark reference frames are `180:1596`, `180:1831`, and `180:1880`.
- Other dark explorations in the same Figma file must not be used as evidence.

### Iconography

- All icons must come from Lucide: https://lucide.dev and https://github.com/lucide-icons/lucide.
- Default icon size is `16px`.
- Default icon stroke width is `1.5px`.
- Icons should support scanning and action recognition.
- Icons must not become decorative clutter.
- Any non-`16px` icon size or non-`1.5px` stroke must be treated as a special case tied to a confirmed component need.

### Media Language

- Browse and recommendation surfaces may use approved abstract gradient assets.
- Active lesson playback may use real media.
- Real media should signal active engagement.
- Brand gradients should signal discovery, identity, and thematic atmosphere.

## Foundation Rules

### Color System

#### Light Theme Roles

- `bg.canvas`: page background
- `surface.base`: default card and control surface
- `surface.overlay`: translucent overlays and media chrome
- `text.primary`: primary heading and strong action text
- `text.secondary`: secondary headings and muted labels
- `text.body`: paragraph copy and descriptive text
- `border.soft`: subtle structure
- `border.medium`: stronger separators and outlines
- `accent.brand`: main filled CTA and active accent
- `accent.support`: softer secondary brand brown
- `status.success`: live/completed learning status

#### Dark Theme Roles

- `bg.canvas`: shared dark page canvas
- `surface.shell`: deep shell and footer shell
- `surface.base`: default dark panel, pill, and rail item surface
- `surface.active`: differentiated active dark item surface
- `text.primary`: warm light headline and primary action text
- `text.secondary`: warm subdued labels and supporting text
- `text.muted`: cool muted inactive lesson and suggestion text
- `text.placeholder`: dark input placeholder text
- `border.soft`: lowest-contrast structural border
- `border.medium`: clearer dark-theme separator and outline
- `accent.brand`: dark-theme gold action and emphasis
- `accent.brandMuted`: softer gold metadata emphasis
- `status.successBg`: dark learning success surface
- `status.successFg`: dark learning success text

#### Color Rules

- Do not introduce cold neutral ramps as a default replacement for the warm system.
- Do not introduce extra brand accent families beyond the approved system.
- Use semantic roles in implementation; do not style directly from raw color picks unless extending the token source.

### Gradient System

#### Approved v1 Family

The v1 core brand gradient family is the warm spectral set:

- yellow
- blue
- red
- gold

These appear as multiple approved image assets and variants.

#### Gradient Rules

- Use gradient assets via tokens, not ad hoc CSS approximations.
- Treat each approved gradient as a named brand asset.
- Use gradients primarily in discovery, marketing, and learning-atmosphere moments.
- Do not use gradients as generic panel backgrounds in dense utility UI unless the pattern is explicitly confirmed.

#### Not Yet in v1

- Purple/pink/blue gradient families are not part of the v1 default family.
- They may be added later, but are not current defaults.

### Typography System

#### Typeface Roles

- `display title first word`: `Cormorant Infant`
- `display title remainder`: `Gayathri`
- `module title`: `DM Serif Text`
- `ui text`: `Geist`

No other font family is permitted in the design system.

#### Role Rules

- `Cormorant Infant` + `Gayathri` form a strict editorial display pair and must not be treated as interchangeable standalone display fonts.
- Display titles must set the first word in `Cormorant Infant Medium Italic` with `-4px` letter spacing.
- Display titles must set all remaining words in `Gayathri Thin` with `-1px` letter spacing.
- Display-title font sizes must be optically matched so the Cormorant first word and the Gayathri remainder appear the same visual height.
- Display titles must not be used when any part of the display-title pair would be smaller than `42px`.
- Do not use a full display title in only `Cormorant Infant`, only `Gayathri`, or `DM Serif Text`.
- `Geist` is the default UI typeface.
- `Geist Regular` at `16px` with shallow brown coloring is used for unbacked section labels such as `Most Popular This Week` and `Explore Domains`.
- `DM Serif Text` is used for titles inside supported cards, buttons, or modules, such as `Explore Domains` cards and `Recommended For You` cards.
- Font families outside `Cormorant Infant`, `Gayathri`, `DM Serif Text`, and `Geist` must not appear in product UI, design docs, or implementation tokens.

#### Type Hierarchy

- Large display titles should dominate identity moments.
- Large display titles must use the strict first-word Cormorant plus remaining-word Gayathri construction.
- Large display titles must not use any text segment below `42px`; use a small-title rule instead.
- Section labels without a supporting card, button, or module background use `Geist Regular`, `16px`, shallow brown.
- Titles inside supported cards, buttons, or modules use `DM Serif Text`.
- Body copy should remain short, readable, and moderate in density.
- Small labels should support controls, metadata, and secondary guidance.

### Spacing, Radius, Border, Shadow

#### Spacing

- Spacing should follow a reusable scale, not one-off values.
- Prefer tokenized spacing over page-specific spacing decisions.
- Section spacing must remain generous on marketing surfaces and more compact in learning surfaces.

#### Radius

- All rounded corners must use `60%` corner smoothing.
- The regular radius set is `16px`, `8px`, and `pill`.
- `16px`: primary radius for most cards, modules, rails, panels, inputs, and controls.
- `8px`: secondary radius matched to the `16px` system, used for compact media, icon containers, and small inline elements.
- `pill`: regular radius category for capsule buttons, chips, rounded fields, and pill controls.
- Any radius value outside `16px`, `8px`, and `pill` must be documented as a special case before use.

#### Border

- `0.5px`: subtle segmented controls where already confirmed
- `1px`: default structural outline
- `2px`: emphasis only when visually confirmed

#### Shadow

- Normal surfaces must not use shadows by default.
- Light theme defaults to no shadow use unless a special case is explicitly documented.
- Approved dark frames rely on surface contrast and borders before shadow depth.
- Shadows must never substitute for spacing or hierarchy.
- Future prototypes must not add ambient card, button, rail, panel, input, or control shadows as a default layer strategy.

#### Translucent Blur Layering

When a foreground component needs legibility and depth over complex gradient, image, or media backgrounds, use a translucent surface plus background blur instead of a shadow.

- The confirmed strategy is a translucent component background with `8px` backdrop blur and no drop shadow.
- Use this for foreground controls, floating buttons, compact labels, and media/gradient overlays that sit directly on visually complex backgrounds.
- In light theme, prefer existing translucent surface roles such as `surface.overlay` or `surface.frost` before adding new color tokens.
- Do not use translucent blur as generic decoration on normal quiet surfaces.
- Do not use it to turn dense utility UI into glass panels.
- If the component is not in front of a complex background, prefer a normal surface, border, and spacing.
- Dark-theme translucent blur values must come from approved dark evidence or be recorded as a gap.

## Layout System

### Confirmed Desktop Widths

- Desktop artboard width: `1440px`
- Header inner width: `1132px`
- Marketing content max width: `1212px`
- Learning content column: `810px`
- Learning rail width: `384px`
- Learning two-column gap: `12px`

### Marketing Shell

- Centered content shell
- Generous vertical spacing
- Editorial first impression
- Discovery modules, recommendation modules, FAQ, newsletter footer

### Learning Shell

- Utility-first header
- Two-column desktop layout
- Sticky right rail
- Main media or lesson content on the left
- Progress / AI support on the right

### Footer Rule

- The long-form newsletter footer is a brand-touchpoint module.
- It is valid on marketing and learning surfaces already confirmed in the approved light and dark frames.
- Future dense product workspaces may adopt a lighter product footer when those pages are designed.

## Responsive Strategy

- The system is desktop-first.
- Learning rail collapses on small screens into a drawer or tab-based access pattern.
- Responsive behavior may simplify layout, but it must not destroy the underlying hierarchy.
- Until breakpoint thresholds are formally confirmed, responsiveness should preserve pattern intent rather than invent new desktop rules.

## Accessibility Baseline

- Core text must meet AA contrast requirements.
- Core interactive elements must meet AA contrast requirements.
- Focus visibility is mandatory for core interactive elements.
- Decorative or auxiliary elements may be visually softer if they do not block comprehension or task completion.
- Accessibility fixes must preserve meaning first, visual fidelity second.

This document does not yet define a full media accessibility policy for captions, transcripts, and advanced playback accommodations.

## Content and Voice

### Brand Voice

- The overall product voice is editorial, thoughtful, and confident.
- The product should not sound gamified, salesy, or overloaded with hype.

### UI Voice

- Section names should remain concrete and legible.
- CTA copy should remain direct.
- AI prompts may use first-person learner intent.
- Product UI must stay readable even when brand voice is expressive.

### Language Baseline

- English is the current content baseline for the design system.
- Future multilingual expansion should extend from the same hierarchy, not rebuild it.

## Component Governance

### Global vs Scene-Scoped Components

- `Button` is the only globally unified interactive component family.
- All other components are scene-scoped by default.
- Visual similarity does not automatically imply a shared implementation API.

### Promotion Rule

A scene component may become global only when both conditions are true:

- it repeats across multiple page domains
- the user explicitly confirms that its behavior and visual boundary should be shared

## Confirmed Page Archetypes

### 1. Marketing / Landing Shell

Must include:

- editorial brand entry
- discovery-oriented content modules
- controlled use of gradient art
- spacious section rhythm

Must avoid:

- dense product chrome
- dashboard-style panel mosaics as the default first impression

### 2. Learning / Course Shell

Must include:

- utility header
- lesson-first content hierarchy
- contextual support in a secondary rail

Must avoid:

- marketing-style hero overload inside the study workspace
- decorative surfaces that weaken task clarity

### 3. AI as a Global Capability

The currently confirmed AI pattern is a companion rail in the learning shell.

Future AI surfaces:

- may appear elsewhere in the product
- must still feel contextual and supportive
- must not silently replace the current learning-first hierarchy without explicit design confirmation

## Extension Protocol For Future Wireframes

When a future page is introduced through a wireframe:

1. Map it to an existing archetype first.
2. Reuse existing foundations and the global button family.
3. Prefer scene-scoped components that already match the page domain.
4. If the wireframe requires a new rule or module, label it `Proposed Pattern`.
5. Do not promote a `Proposed Pattern` into the system until it is confirmed through a new high-fidelity design or direct user approval.

### Extension Deliverable Rule

For future collaboration:

- wireframes become high-fidelity designs using the current system
- new patterns remain provisional until confirmed
- the system grows by promotion, not by assumption
- dark-mode conclusions must come from approved dark reference frames only
- prototypes should use no shadows by default and use translucent `8px` backdrop-blur foreground surfaces only when needed over complex backgrounds

## Open Questions

These items remain intentionally unresolved and must not be silently decided in code or documentation:

- Exact responsive breakpoint thresholds for mobile, tablet, desktop, and wide layouts
- Full approved gradient library beyond the v1 warm spectral family
- Whether purple/pink/blue gradients should become a secondary approved family
- Full localization strategy beyond the current English baseline
- Full interaction-state matrices for non-button components, including hover, loading, and error behaviors
- Full media accessibility policy for captions, transcripts, and advanced playback support
- Carousel and overflow behavior for future recommendation rails outside the currently shown examples
