---
name: design-system-and-ui-consistency
description: Defines and applies visual consistency in Ionic Angular apps with tokens, base components, and UI states. Use when implementing new screens, refactoring interfaces, aligning with Figma, or reducing layout divergence.
---

# design-system-and-ui-consistency

## Objective

Ensure visual and behavioral consistency across Ionic/Angular screens based on the product design.

## Apply When

- implementing a new Figma-based screen
- fixing inconsistencies between components
- creating a reusable UI component
- standardizing visual states (loading, empty, error, success)

## Mandatory Requirements

- Consume tokens already defined in the theme (do not create hardcoded values per screen).
- Reuse base components before creating variants.
- Apply consistent spacing and visual hierarchy patterns.
- Ensure explicit UI states for loading, empty, and error.
- Prefer Ionic components for mobile structure and interaction.

## Recommended Flow

1. Map recurring screen elements in Figma.
2. Identify what becomes a token and what becomes a base component.
3. Implement/adjust the component with a simple props/inputs API.
4. Validate visual states and responsiveness.
5. Review consistency with existing screens.

## Anti-Patterns (Do Not Do)

- Duplicate inline styles without tokenization.
- Create a new variant to solve an isolated detail.
- Mix business rules with visual logic inside the component.
- Ignore error and empty states due to "lack of time".

## When to Ask for More Context

- exact Figma file/frame
- expected component variations
- existing visual guideline in the project
- behavior in different orientation/screen sizes

## Scope Limits

- covers visual consistency and UI composition
- does not define token/theme pipeline (use `design-tokens-pipeline`)
- does not cover API contracts (use `api-data-access-laravel-backend`)
- does not cover native plugin integration (use `capacitor-native-integration`)

## Quick Example (Input -> Output)

Input: "Create an offer card like Figma and use it in home and detail."

Expected output:
- spacing and typography tokenization
- reusable `offer-card.component` with variants
- coherent `loading` and `empty` states
- visual checklist comparing with Figma

## Additional Resources

- For consistency checklist and token template, read `reference.md`.
