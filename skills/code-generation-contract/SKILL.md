---
name: code-generation-contract
description: "Enforces a mandatory output contract for Ionic Angular code generation, ensuring architecture, integration, screen states, and validation consistency. Use when requesting implementation of any screen, flow, or feature."
license: UNLICENSED
---

# code-generation-contract

## Objective

Standardize the format and minimum completeness level of agent deliveries.

## Compatibility (Cursor, Codex, Claude Code)

- This skill is **agent-vendor agnostic**: treat it as a playbook that any coding assistant can follow.
- Prefer **deterministic, step-by-step** deliveries over conversational or “hand-wavy” guidance.
- Do not rely on vendor-specific features (special tooling, hidden memory, proprietary commands) to be “complete”.
- If key inputs are missing, proceed with **explicit assumptions** and mark them as validation items (do not invent contracts silently).

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

## Clean Architecture + Structured Logic Baseline

- Keep page/components **thin**: UI binding + orchestration only.
- Place business rules in **services/facades/use-cases** with typed inputs/outputs.
- Use **DTOs** at the boundary; map to UI models where it reduces coupling.
- Treat error handling as **structured outcomes** (typed error objects/enums), not ad-hoc strings.

## Security + Performance Baseline (Always Check)

- **Security**: never log/store secrets; redact tokens/PII; least-privilege permissions; handle `401/403/422` explicitly; clear session on logout.
- **Performance**: avoid repeated heavy bindings; prefer `trackBy` for lists; debounce expensive inputs; paginate/virtualize when list size can grow.

## Mandatory Output Format

1. Objective
2. File structure
3. Code
4. API integration
5. Mobile considerations
6. Tests and validations
7. Assumptions and pending items

## Definition of Done (Delivery Gate)

- File tree + responsibilities are clear enough to implement without guesswork.
- DTOs/contracts are specified or assumptions are explicitly listed.
- Screen state handling includes: loading, success, empty, error (and `unauthorized` when relevant).
- The minimum test/validation checklist is actionable (commands or concrete steps).

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
