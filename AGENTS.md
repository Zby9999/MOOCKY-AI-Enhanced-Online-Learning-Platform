# AGENTS

## Purpose

This file gives Codex execution rules for the MOOCKY design system. It is not a restatement of the full system.

## Source Priority

1. `docs/design-system.md`
2. `docs/component-specs.md`
3. `tokens.json`
4. This file

If a rule changes, update the source of truth first.

## Core Execution Rules

- Treat `docs/design-system.md` as the only normative design source.
- Treat `docs/component-specs.md` as an implementation companion, not an authority.
- Treat `tokens.json` as the machine-readable contract for implementation.
- Do not invent missing design rules in code.

## Figma Evidence Whitelist

Only the following Figma nodes are approved as system evidence:

- `42:93`
- `60:551`
- `100:3535`
- `180:1596`
- `180:1831`
- `180:1880`
- `173:1582`

If a node is outside this whitelist, treat it as exploratory and non-authoritative unless the user explicitly approves it later.

## Working With New Wireframes

When the user provides a new wireframe:

1. Classify it against the current archetypes first.
2. Reuse existing foundations and tokens before introducing anything new.
3. Reuse the global button family everywhere.
4. Treat all non-button components as scene-scoped unless promoted by the design system.
5. If a needed pattern is missing, mark it as `Proposed Pattern` or `Open Question` instead of silently inventing it.

## Theme Rules

- Do not derive dark mode by inversion.
- Read dark mode only from approved dark reference frames: `180:1596`, `180:1831`, and `180:1880`.
- Do not use other dark experiments in the same Figma file as evidence.
- If a dark value is missing locally, document the gap instead of filling it from unapproved frames.

## Display Typography Rules

- Large editorial titles must use the strict two-font construction from `docs/design-system.md`.
- Set only the first word in `Cormorant Infant Medium Italic` with `-4px` letter spacing.
- Set the remaining words in `Gayathri Thin` with `-1px` letter spacing and optically matched size.
- Do not use this display-title construction below `42px`.
- Use `Geist Regular 16px` in shallow brown for unbacked section labels.
- Use `DM Serif Text` for titles inside backed cards, buttons, and modules.
- Do not create full display titles in only `Cormorant Infant`, only `Gayathri`, or `DM Serif Text`.
- Do not introduce font families outside `Cormorant Infant`, `Gayathri`, `DM Serif Text`, and `Geist`.

## Radius And Icon Rules

- Use `60%` corner smoothing for every rounded corner.
- Treat `16px`, `8px`, and `pill` as the only regular radius choices.
- Use `16px` for most cards, modules, rails, panels, inputs, and controls.
- Use `8px` for compact media, icon containers, and small inline elements.
- Use `pill` for capsule buttons, chips, rounded fields, and pill controls.
- Document any other radius as a special case before using it.
- Use Lucide for all icons: https://lucide.dev and https://github.com/lucide-icons/lucide.
- Default icons are `16px` with `1.5px` stroke.
- Treat any other icon size or stroke width as a special case tied to a confirmed component need.

## Gradient Rules

- Brand gradients are controlled assets, not freeform decoration.
- Use only approved gradient asset families from `tokens.json`.
- Do not approximate approved gradients with ad hoc CSS unless the design system is updated to permit that.
- v1 defaults to the warm spectral core family only.

## Documentation Rules

- If a design-system rule changes, update `docs/design-system.md` before updating any derivative file.
- If a component boundary changes, update `docs/component-specs.md` after the system document.
- Never let `tokens.json` encode unresolved assumptions.
