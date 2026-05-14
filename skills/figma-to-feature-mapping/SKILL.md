---
name: figma-to-feature-mapping
description: "Converts Figma screens into a technical implementation backlog for Ionic Angular, including features, routes, components, states, and acceptance criteria. Use when starting development from a design or reviewing functional screen coverage."
license: UNLICENSED
---

# figma-to-feature-mapping

## Objective

Turn Figma frames into an executable and traceable implementation plan in the app.

## Compatibility (Cursor, Codex, Claude Code)

- Vendor-agnostic planning playbook: output should be reviewable without relying on any specific assistant.
- Prefer **structured artifacts**: route map, file tree, state matrix, and acceptance criteria.
- If Figma interaction rules are ambiguous, capture them as explicit questions/assumptions with validation steps.

## Apply When

- starting a Figma-based feature
- breaking screens into technical tasks
- identifying state and behavior gaps
- reviewing navigation and component coverage

## Mandatory Requirements

- Map each frame to its corresponding route/flow.
- Identify reusable components and page components.
- List screen states: loading, success, empty, error.
- Relate user events to technical actions (navigate, submit, open modal).
- Define an objective acceptance criterion per screen.

## Clean Architecture Baseline (Planning Stage)

- Plan feature boundaries by **cohesion** (screens + services + models that change together).
- Identify boundary contracts early (DTOs, route params, storage/offline needs).
- Avoid mixing business rules into pages in the plan; allocate them to services/use-cases.

## Recommended Flow

1. List frames and the functional objective of each one.
2. Group frames by feature/module.
3. Map routes, guards, and transitions between screens.
4. Define file structure by feature.
5. Create a technical backlog with implementation order.
6. Validate dependencies with API, state, and plugins.

## Anti-Patterns (Do Not Do)

- Implement a screen without mapping error/empty states.
- Treat every frame as a new component without evaluating reuse.
- Ignore return flow and navigation between screens.
- Create a backlog without measurable acceptance criteria.

## When to Ask for More Context

- exact frame or set of priority frames
- interaction behavior not visible in the layout
- release priority by flow
- permission/profile rules by screen

## Scope Limits

- covers design-to-technical-backlog mapping
- does not replace API modeling (use `api-data-access-laravel-backend`)
- does not replace detailed visual implementation (use `design-system-and-ui-consistency`)

## Quick Example (Input -> Output)

Input: "Map onboarding + login + home from Figma."

Expected output:
- routes and navigation flow
- components by screen and reusable items
- state matrix by screen
- prioritized backlog with acceptance criteria

## Additional Resources

- For mapping template and checklist, read `reference.md`.
