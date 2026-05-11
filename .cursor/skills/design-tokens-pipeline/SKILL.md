---
name: design-tokens-pipeline
description: Standardizes the design token pipeline for Ionic Angular, connecting design colors, typography, and spacing to app styles. Use when aligning UI with Figma, creating a theme, or reducing visual inconsistencies.
---

# design-tokens-pipeline

## Objective

Create a consistent token definition and application flow to speed up visual implementation without divergence.

## Compatibility (Cursor, Codex, Claude Code)

- Vendor-agnostic theming/token playbook.
- Prefer a **progressive adoption** plan (small set of tokens first) over a big-bang refactor.
- If the project theming strategy is unknown, propose one and mark it as an assumption to validate against the repo.

## Apply When

- starting the app visual theme
- aligning screens with design
- reducing ad hoc style variations
- creating a base for dark mode/brand variants

## Mandatory Requirements

- Define semantic tokens (not hardcoded values in the component).
- Centralize tokens in theme files (`variables.scss` and helpers).
- Separate global tokens from component overrides when needed.
- Avoid direct colors/sizes in pages.
- Define consistent token naming.

## Clean UI Architecture Baseline

- Tokens represent **meaning**, not raw values (e.g., `--color-surface`, not `--gray-100`).
- Keep component APIs stable: consume tokens inside base components, not scattered per screen.
- Validate accessibility as part of token definition (contrast, focus visibility).

## Recommended Flow

1. Gather main design tokens (color, type, space, radius).
2. Name semantic tokens by UI role.
3. Publish global tokens in the app theme.
4. Apply tokens in base components.
5. Validate consistency and minimum contrast.

## Anti-Patterns (Do Not Do)

- Copy a Figma value directly into each component.
- Create duplicate tokens with ambiguous semantics.
- Mix brand tokens with interface role tokens.
- Ignore contrast accessibility when defining the palette.

## When to Ask for More Context

- required or optional light/dark theme
- brand variations by client
- component priority for initial tokenization
- target accessibility and contrast rule

## Scope Limits

- covers theme and token pipeline
- does not cover functional screen backlog
- does not cover data contracts and API integration

## Quick Example (Input -> Output)

Input: "Apply the visual identity to login and home screens."

Expected output:
- semantic tokens defined in the theme
- base components using tokens
- removal of hardcoded styles from screens
- visual consistency and contrast checklist

## Additional Resources

- For naming and progressive adoption checklist, read `reference.md`.
