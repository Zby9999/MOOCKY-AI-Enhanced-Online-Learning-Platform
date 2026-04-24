# MOOCKY Component Specs

## Rules of Use

- [`design-system.md`](./design-system.md) is the authority. This document is derivative.
- Only `Button` is globally unified.
- All other components are scene-scoped unless promoted by the design system.
- When a state or rule is not confirmed, record it in `Open Questions` instead of inventing it.
- Dark-state evidence in this file may only come from approved dark reference frames `180:1596`, `180:1831`, and `180:1880`.
- All rounded component containers must use `60%` corner smoothing.
- Regular component radii are limited to `16px`, `8px`, and `pill`; any other radius must be documented as a special case.
- All icons must come from Lucide. The default icon spec is `16px` size with `1.5px` stroke; other sizes or strokes are special cases.

## LogoLockup

### Purpose

Represent the canonical MOOCKY brand mark.

### Structure

- wordmark text
- sparkle mark
- fixed lockup relationship

### States

- default light
- default dark, confirmed in approved landing and learning dark frames

### Props

- `theme`: `light | dark`
- `size`: `header | compact | display`
- `href`: optional destination

### Reuse Rules

- Use for global brand entry points.
- Keep sparkle attached to the wordmark.

### Prohibited Uses

- Do not use sparkle alone as the primary logo.
- Do not replace the lockup with ad hoc typographic treatments.

### Open Questions

- Exact responsive behavior for very narrow headers.

## Button

### Purpose

Provide the single globally unified action family across MOOCKY.

### Structure

- container
- label
- optional leading icon
- optional trailing icon

### States

- visual variants: `brand`, `surface`, `ghost`, `icon-only`
- densities: `compact`, `regular`
- interaction states: `default`, `hover`, `pressed`, `focus-visible`, `disabled`, `loading`

### Props

- `variant`: `brand | surface | ghost | icon-only`
- `density`: `compact | regular`
- `iconPlacement`: `leading | trailing | only | none`
- `theme`: `light | dark`
- `disabled`: boolean
- `loading`: boolean
- `href`: optional

### Reuse Rules

- Use the same button family in marketing and learning surfaces.
- Express page differences through variant and context, not separate button systems.

### Prohibited Uses

- Do not create separate marketing and learning button families.
- Do not encode scene identity with new button geometry.

### Open Questions

- Exact hover and pressed visual deltas for each non-default theme.

## MarketingHeader

### Purpose

Provide brand-first navigation for landing and marketing-facing surfaces.

### Structure

- logo lockup
- primary navigation
- secondary actions
- optional login / explore actions

### States

- default light
- default dark, confirmed in approved landing dark frame `180:1596`
- compact responsive state: open question

### Props

- `navItems`
- `secondaryActions`
- `theme`
- `sticky`: boolean

### Reuse Rules

- Use on landing pages and future marketing shells.
- Keep the header visually light and editorially aligned.

### Prohibited Uses

- Do not reuse this as the authenticated learning header.
- Do not overload with dense utility controls.

### Open Questions

- Exact mobile collapse pattern.

## LearningHeader

### Purpose

Provide utility-first navigation and quick access for study surfaces.

### Structure

- logo lockup
- learning context entry
- compact search / intent field
- utility icon cluster
- account entry

### States

- default light
- default dark, confirmed in approved course dark frames `180:1831` and `180:1880`
- compact responsive state: open question

### Props

- `contextLabel`
- `searchPlaceholder`
- `utilityActions`
- `profileAction`
- `theme`

### Reuse Rules

- Use on authenticated learning pages.
- Preserve high scanability and compact density.

### Prohibited Uses

- Do not merge with marketing navigation logic.
- Do not add brand-hero content into this shell.

### Open Questions

- Exact mobile navigation collapse behavior.

## HeroPromptField

### Purpose

Capture high-level learner intent on hero and onboarding-like surfaces.

### Structure

- prompt shell
- text field or pseudo-input
- submit action

### States

- default light
- default dark, confirmed in approved landing dark frame `180:1596`
- active / focused: partially confirmed
- loading / submitting: open question

### Props

- `placeholder`
- `submitAction`
- `theme`
- `intentContext`

### Reuse Rules

- Use on hero and intent-capture surfaces.
- Pair with suggestion chips when the page needs guided starting points.

### Prohibited Uses

- Do not reuse as the compact learning header search.
- Do not turn it into a generic form field without the intent-capture framing.

### Open Questions

- Validation, error, and loading treatments.

## HeaderSearchField

### Purpose

Provide compact intent or search entry inside the learning header.

### Structure

- compact rounded field
- leading search icon
- placeholder text

### States

- default light
- default dark, confirmed in approved course dark frames `180:1831` and `180:1880`
- focused: partially implied
- filled / active: open question

### Props

- `placeholder`
- `value`
- `theme`
- `widthMode`

### Reuse Rules

- Keep compact and header-scoped.
- Use for utility search and learning goals inside the study shell.

### Prohibited Uses

- Do not replace the hero prompt field with this component.
- Do not use as a primary page CTA module.

### Open Questions

- Search result reveal pattern and mobile behavior.

## GoalChip

### Purpose

Offer short guided prompts or intent shortcuts.

### Structure

- pill container
- optional icon
- short label

### States

- default light
- default dark, confirmed as outlined prompt chips in approved AI rail frame `180:1880`
- selected: open question
- hover / pressed: open question

### Props

- `label`
- `icon`
- `context`: `hero | ai-suggestion`
- `theme`

### Reuse Rules

- Use for suggestion-level actions.
- Keep copy short and intent-led.

### Prohibited Uses

- Do not use as a primary CTA.
- Do not overload with long explanatory copy.

### Open Questions

- Whether chips can become persistent filters or remain ephemeral suggestions only.

## SegmentedControl

### Purpose

Switch between closely related views inside a shared content region.

### Structure

- outer segmented shell
- segment items
- active indicator
- optional utility icon

### States

- active item
- inactive item
- approved dark learning variants confirmed in `180:1831` and `180:1880`
- hover / focus-visible: open question

### Props

- `items`
- `activeItem`
- `context`: `lesson-tabs | rail-mode-switch`
- `theme`
- `utilityAction`: optional

### Reuse Rules

- Share the behavior pattern across scenes.
- Keep visuals scene-scoped unless later promoted.

### Prohibited Uses

- Do not assume a single cross-scene visual implementation.
- Do not replace primary navigation with segmented controls.

### Open Questions

- Exact focus and keyboard interaction spec.

## DomainTile

### Purpose

Surface a compact learning domain or benefit area.

### Structure

- card shell
- icon
- title
- optional description

### States

- default light
- default dark, confirmed in approved landing and learning dark frames
- highlighted: partially confirmed in some contexts

### Props

- `icon`
- `title`
- `description`: optional
- `theme`
- `tone`

### Reuse Rules

- Use as a compact educational taxonomy or benefit tile.
- Allow descriptive text only in contexts that need more explanation.

### Prohibited Uses

- Do not overload with heavy metadata.
- Do not convert into a generic dashboard stat card.

### Open Questions

- Whether selectable or purely navigational variants are needed.

## LandingFeaturedCourseModule

### Purpose

Show a high-emphasis featured course cluster on marketing surfaces.

### Structure

- section label
- primary feature block
- companion vertical or stacked cards
- optional more action

### States

- default light
- default dark, confirmed in approved landing dark frame `180:1596`

### Props

- `sectionLabel`
- `primaryCourse`
- `secondaryCourses`
- `moreAction`
- `theme`

### Reuse Rules

- Use for curated editorial discovery.
- Preserve asymmetry and visual hierarchy.

### Prohibited Uses

- Do not flatten into equal-weight card grids.
- Do not use as a generic search results list.

### Open Questions

- Carousel/overflow behavior at smaller breakpoints.

## RecommendedCourseCard

### Purpose

Represent a course recommendation in browse and discovery contexts.

### Structure

- media area
- optional overlay label
- title
- description or metadata block
- institution or review metadata
- action

### States

- editorial full-card
- image-first overlay-pill card
- compact recommendation style
- approved dark marketing variants confirmed in `180:1596`

### Props

- `title`
- `summary`
- `mediaAsset`
- `label`: optional
- `provider`: optional
- `reviews`: optional
- `action`
- `theme`

### Reuse Rules

- Treat recommendation cards as a family, not a single locked layout.
- Preserve strong media-to-text hierarchy.

### Prohibited Uses

- Do not convert into dense utility tables.
- Do not use unapproved image treatments outside the gradient/media rules.

### Open Questions

- Exact hover lift and scroll/overflow behavior.

## FAQAccordion

### Purpose

Reveal short explanatory answers in a calm, low-friction format.

### Structure

- item shell
- question row
- indicator icon
- optional answer body

### States

- collapsed light
- collapsed dark, confirmed in approved landing dark frame `180:1596`
- expanded

### Props

- `items`
- `allowMultiple`: open question
- `theme`

### Reuse Rules

- Use for short explanatory Q&A on marketing or support-adjacent surfaces.
- Keep answer density restrained.

### Prohibited Uses

- Do not use as a substitute for complex documentation navigation.
- Do not turn into nested accordions.

### Open Questions

- Single-open versus multi-open behavior.

## InstructorCard

### Purpose

Provide a compact profile of the course instructor and supporting credibility.

### Structure

- avatar
- name
- role
- supporting bullet facts
- outbound or contact actions

### States

- default
- dark variant, confirmed in approved course dark frames `180:1831` and `180:1880`

### Props

- `avatar`
- `name`
- `role`
- `facts`
- `actions`
- `theme`

### Reuse Rules

- Use inside learning and course-detail contexts.
- Keep the card concise and credibility-led.

### Prohibited Uses

- Do not expand into a full profile page template.
- Do not overload with unrelated social proof.

### Open Questions

- Whether a compact inline variant is needed for smaller screens.

## CurriculumRail

### Purpose

Provide progress tracking and lesson navigation within the learning shell.

### Structure

- rail shell
- rail mode segmented control
- progress bar
- curriculum header
- progress summary chip
- list of lesson items
- collapse action

### States

- progress mode light
- progress mode dark, confirmed in approved course dark frame `180:1831`
- item states: `completed`, `current`, `upcoming`
- collapsed rail action

### Props

- `items`
- `completedCount`
- `totalCount`
- `activeItemId`
- `theme`

### Reuse Rules

- Use as the study-progress rail inside the learning shell.
- Keep it sticky on desktop when layout permits.

### Prohibited Uses

- Do not repurpose as a generic sidebar navigation.
- Do not remove progress context from the rail.

### Open Questions

- Exact mobile presentation beyond drawer/tab guidance.

## AICompanionRail

### Purpose

Provide contextual AI support as a secondary learning surface.

### Structure

- rail shell
- rail mode segmented control
- AI status row
- suggested prompt list
- composer area

### States

- AI mode idle light
- AI mode idle dark, confirmed in approved course dark frame `180:1880`
- AI mode with starter prompts, confirmed in approved light and dark AI rail frames
- composer ready, confirmed in approved light and dark AI rail frames
- responding / streamed answer: open question

### Props

- `statusLabel`
- `promptSuggestions`
- `composerPlaceholder`
- `theme`
- `conversationState`

### Reuse Rules

- Use as the canonical current AI companion surface.
- Keep the AI visually supportive, not dominant over lesson content.

### Prohibited Uses

- Do not let the rail replace the lesson as the main viewport focus.
- Do not invent chat paradigms not confirmed by the system.

### Open Questions

- Typing, loading, error, transcript-linked, and answer-card states.

## LessonMediaPanel

### Purpose

Present the active lesson media state within the learning shell.

### Structure

- media frame
- cover or live media
- playback controls
- auxiliary control cluster

### States

- paused / cover-led, confirmed in approved light and dark paused course frames
- playing / live-media, confirmed in approved light and dark playing course frames

### Props

- `mediaType`
- `coverAsset`
- `playbackState`
- `controls`
- `theme`

### Reuse Rules

- Use as the main lesson media surface in course pages.
- Switch from gradient-led to real media when the lesson becomes active.

### Prohibited Uses

- Do not use decorative gradients as a replacement for real active media.
- Do not invent extra control groups not grounded in the design system.

### Open Questions

- Full playback state matrix and advanced accessibility behaviors.

## FooterNewsletter

### Purpose

Provide a large brand-touchpoint footer with newsletter capture and legal/social links.

### Structure

- editorial heading
- supporting copy
- email field
- subscribe button
- legal links
- social handles

### States

- default light
- dark variant, confirmed in approved landing and course dark frames

### Props

- `headline`
- `supportingCopy`
- `emailPlaceholder`
- `legalLinks`
- `socialLinks`
- `theme`

### Reuse Rules

- Use on marketing and approved learning surfaces where a brand-touchpoint footer is appropriate.
- Preserve the strict editorial heading treatment: first word in `Cormorant Infant Medium Italic` with `-4px`, remaining words in `Gayathri Thin` with `-1px`, optically size-matched.
- Do not use the editorial heading treatment below `42px`; switch to the appropriate small-title rule.

### Prohibited Uses

- Do not force this footer into dense productivity workspaces.
- Do not reduce it to a generic utility footer without explicit design confirmation.

### Open Questions

- Future lightweight product-footer pattern for denser internal product areas.
