---
name: code-generation-contract
description: Enforces a mandatory output contract for Ionic Angular code generation, ensuring architecture, integration, screen states, and validation consistency. Use when requesting implementation of any screen, flow, or feature.
---

# code-generation-contract

## Objective

Standardize the format and minimum completeness level of agent deliveries.

## Apply When

- generating a new screen/feature
- refactoring an existing flow
- requesting end-to-end implementation
- reviewing whether a response is complete enough to execute

## Mandatory Requirements

- Deliver file structure before code.
- Declare data contracts (DTO/interface) or explicit assumptions.
- Cover UI states (loading, success, empty, error).
- Include mobile considerations (web/Android/iOS).
- Include minimum test checklist per critical flow.

## Mandatory Output Format

1. Objective
2. File structure
3. Code
4. API integration
5. Mobile considerations
6. Tests and validations
7. Assumptions and pending items

## Anti-Patterns (Do Not Do)

- Deliver only a code snippet without integration context.
- Omit error and empty states.
- Omit risk/platform notes in a flow with native resources.
- Declare "done" without a minimum checklist.

## When to Ask for More Context

- expected endpoint and payload
- main business rule
- role/permission by flow
- platform priority and deadline

## Scope Limits

- covers delivery format and minimum quality
- does not replace domain-specific technical skills

## Quick Example (Input -> Output)

Input: "Create a detail screen with an approve action."

Expected output:
- feature file tree
- page/component/service/DTO
- screen states and error flow
- approval flow test checklist

## Additional Resources

- For detailed compliance checklist, read `reference.md`.
