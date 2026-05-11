---
name: feature-delivery-orchestrator
description: Orchestrates end-to-end mobile feature delivery, from Figma to release, activating technical skills in the correct order and applying quality gates. Use when the goal is to implement a complete feature with architectural consistency and delivery readiness.
---

# feature-delivery-orchestrator

## Objective

Ensure a single, predictable flow for delivering complete features in Ionic/Capacitor/Angular.

## Compatibility (Cursor, Codex, Claude Code)

- Vendor-agnostic orchestration: it’s a sequencing + quality gate playbook.
- Each phase should produce **explicit artifacts** (file tree, DTOs, routes, state matrix, checklists) that can be reviewed without trusting the assistant.
- When design/contract is missing, proceed with **assumptions** + validation items; do not silently invent.

## Apply When

- implementing a new feature end to end
- turning design screens into technical delivery
- reducing rework caused by the wrong implementation order
- validating readiness before merge/release

## Mandatory Requirements

- Execute phases in order without skipping gates.
- Declare assumptions when contract/rule is missing.
- Cover screen states and mobile risks.
- Deliver a final go/no-go checklist.

## Cross-Cutting Gates (Always Apply)

- **Clean boundaries**: pages thin, business logic in services/use-cases, API boundary via DTOs.
- **Security**: session/token handling reviewed, sensitive data redaction, logout cleanup defined.
- **Performance**: large lists/media considered, avoid “load all”, measure/verify improvements.

## Mandatory Orchestration Sequence

1. `figma-to-feature-mapping`
   map frames, flows, backlog, and acceptance criteria.
2. `app-shell-navigation-blueprint`
   ensure the feature fits into the shell and main navigation.
3. `ionic-angular-architecture`
   define file structure and responsibilities.
4. `design-tokens-pipeline` + `design-system-and-ui-consistency`
   align the visual base and interface composition.
5. `screen-state-matrix`
   cover screen states and transitions.
6. `api-data-access-laravel-backend` and/or `capacitor-native-integration`
   integrate the required data and native resources.
7. `forms-validation-and-input-masks` and/or `list-detail-search-and-filters`
   complete input and list/detail flows.
8. `state-and-offline-mobile`
   apply cache/sync when there is connectivity risk.
9. `code-generation-contract`
   validate delivery format and technical completeness.
10. `testing-and-release-readiness`
    run the final gate and decide go/no-go.

## Mandatory Gates by Phase

- Gate 1 (Discovery): backlog by screen + acceptance criteria.
- Gate 2 (Structure): approved routes and architecture.
- Gate 3 (Implementation): UI states + integration completed.
- Gate 4 (Quality): technical checklist and mapped risks.
- Gate 5 (Release): final go/no-go recommendation.

## Anti-Patterns (Do Not Do)

- Implement code before mapping screens and flow.
- Finish a feature without a state matrix.
- Skip platform validation in a native flow.
- Declare done without a final release gate.

## When to Ask for More Context

- exact feature scope (screens and priority)
- available API contract or contract to infer
- required native dependencies
- definition of done and delivery deadline

## Scope Limits

- coordinates the sequence between skills
- does not replace technical implementation skills
- does not define product business rules without context

## Quick Example (Input -> Output)

Input: "Deliver the orders feature from Figma to merge."

Expected output:
- phased plan with activated skills
- deliverables and gates by phase
- final checklist with go/no-go and pending items

## Additional Resources

- For operational playbook and templates, read `reference.md`.
