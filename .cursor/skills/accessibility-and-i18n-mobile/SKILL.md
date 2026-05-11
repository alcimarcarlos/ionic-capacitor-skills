---
name: accessibility-and-i18n-mobile
description: Ensures accessibility and internationalization in Ionic Angular apps, covering contrast, focus, semantics, screen readers, and localized text. Use when implementing or reviewing screens for inclusive UX quality and multilingual support.
---

# accessibility-and-i18n-mobile

## Objective

Ensure screens are accessible and internationalizable from the initial implementation.

## Compatibility (Cursor, Codex, Claude Code)

- Vendor-agnostic UX quality checklist: apply regardless of tooling/assistant.
- Prefer **explicit, testable** acceptance criteria (what to check, where, and expected behavior).
- If the project i18n/a11y stack is unknown, propose a default and mark it as an assumption to validate.

## Apply When

- creating/refactoring screens and components
- reviewing form and navigation experience
- adding new languages or adjusting copy
- preparing a feature for production with a quality standard

## Mandatory Requirements

- Ensure minimum contrast between text and background.
- Define accessible labels on buttons, inputs, and interactive icons.
- Preserve focus order and keyboard navigation when applicable.
- Externalize text to the i18n layer (no hardcoding in templates).
- Handle pluralization and translation fallback.

## Structured Checklist (Baseline)

- **Semantics**: correct roles/labels; icon-only buttons have `aria-label`/accessible text.
- **Focus**: visible focus styles; predictable tab order; modals trap focus when applicable.
- **Errors**: error messages are announced/readable; do not rely on color alone.
- **i18n**: no hardcoded UI strings; pluralization supported; long strings do not break layout.
  - Treat error strings from API as either localized keys or map them to localized messages.

## Recommended Flow

1. Map the screen's interactive elements.
2. Define semantics and accessible labels.
3. Apply i18n to all visible text.
4. Validate truncation/overflow for long strings.
5. Run the accessibility and localization checklist.

## Anti-Patterns (Do Not Do)

- Use color alone to indicate error/success.
- Render a clickable icon without an accessible label.
- Leave hardcoded text in HTML/TS.
- Assume fixed string length across all languages.

## When to Ask for More Context

- target languages and rollout priority
- i18n pattern adopted in the project
- product accessibility requirements
- components with higher usage criticality

## Scope Limits

- covers interface accessibility and localization
- does not cover API/DTO integration
- does not cover deep performance optimization
- does not replace form validation rules (use `forms-validation-and-input-masks`)

## Quick Example (Input -> Output)

Input: "Validate the login screen for accessibility and pt/en."

Expected output:
- accessible labels in fields and buttons
- localized error messages
- contrast adjustment and visible focus
- a11y + i18n validation checklist

## Additional Resources

- For checklist and validation criteria, read `reference.md`.
