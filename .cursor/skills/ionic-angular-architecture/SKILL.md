---
name: ionic-angular-architecture
description: Organizes Ionic Angular architecture by feature with lean pages, reusable components, domain services, and predictable routes. Use when creating/refactoring screens, navigation, modules, or folder structure.
---

# ionic-angular-architecture

## Objective

Define an Ionic + Angular app structure with strong separation of responsibilities.

## Compatibility (Cursor, Codex, Claude Code)

- This skill is **agent-vendor agnostic**. Follow it as an architecture checklist, not as a tool-specific workflow.
- When project conventions are unknown, propose a structure and label it as an **assumption** to be validated against the repo.
- Prefer **predictable module boundaries** and explicit dependencies over implicit “shared” coupling.

## Apply When

- creating a new feature
- reorganizing pages
- defining folder structure
- creating reusable components
- designing routes and navigation

## Mandatory Requirements

- Organize by feature (feature folder with page/components/services/models).
- Keep page components lean (orchestration + UI binding).
- Isolate business rules in services/facades/use-cases.
- Prefer Ionic components for visual structure and mobile UX.
- Separate API model from presentation model.
- Define routes with lazy loading and guards when needed.

## Structured Logic + Clean Boundaries

- UI layer: events/state binding only (no business rules, no direct HTTP).
- Domain/use-case layer: pure(ish) functions where possible, explicit inputs/outputs, unit-test friendly.
- Data layer: DTOs, mapping, caching/retries, and error normalization.
- Cross-cutting concerns: interceptors/guards/adapters (auth, logging, permissions, platform).

## Security + Performance Baseline

- **Security**: least privilege for permissions/guards; never leak sensitive data in UI logs; protect critical routes/actions.
- **Performance**: avoid over-rendering; use `OnPush` where appropriate; `trackBy` for lists; lazy-load feature routes/modules.

## Recommended Flow

1. Define feature boundaries (data, UI, and navigation).
2. Propose a file tree with responsibility by layer.
3. Implement page/container with minimal logic.
4. Implement reusable components and domain services.
5. Configure routes, guards, and resolvers when useful.
6. Validate loading/error/empty/success states on the screen.

## Anti-Patterns (Do Not Do)

- Concentrate business logic inside a page component.
- Reuse a component coupled to a specific endpoint.
- Mix navigation decisions with HTTP calls in multiple places.
- Create a global technical-type structure when the feature needs local cohesion.

## Expected Delivery Format

1. Feature objective and scope.
2. Proposed file tree.
3. Responsibility of each file.
4. Base code (page/component/service/route).
5. Navigation, state, and future evolution considerations.

## When to Ask for More Context

- expected navigation flow (origin/destination/guards)
- feature responsibilities and boundaries with other features
- main business rules of the screen
- external dependencies (API, native plugin, storage)
- existing project pattern (standalone, modules, conventions)

## Scope Limits

- covers UI organization, navigation, and separation of responsibilities
- does not cover deep native integration details (use `capacitor-native-integration`)
- does not cover complete Laravel contract specification (use `api-data-access-laravel-backend`)

## Quick Example (Input -> Output)

Input: "Create an orders feature with list and detail."

Expected output:
- `features/orders/{pages,components,services,models}` tree
- `orders.page.ts` only orchestrating state and UI events
- `orders-facade.service.ts` with business rules
- lazy-loaded routes for list/detail and guard when needed

## Additional Resources

- For feature structure templates, read `reference.md`.
