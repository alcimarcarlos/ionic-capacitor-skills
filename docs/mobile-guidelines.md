# Mobile Guidelines

## Principles

- Hybrid app with a near-native experience.
- UI consistent with Ionic.
- Integration layer decoupled from the visual component.
- Prepared for different business domains and operational routines.

## Suggested Structure

```text
src/app/
  core/
    api/
    auth/
    guards/
    interceptors/
    models/
    services/
  features/
    feature-a/
    feature-b/
    feature-c/
    dashboard/
  shared/
    components/
    pipes/
    directives/
    utils/
```

## Patterns

- `core/` for cross-cutting infrastructure
- `features/` by business domain
- `shared/` for reuse
- services without UI logic
- lean pages
- reusable components

## Laravel Backend

- work with DTOs/interfaces
- map payloads explicitly
- avoid directly coupling the component to the raw API response
- handle pagination, filters, authentication, and domain errors

## Capacitor

- encapsulate plugins in adapters/services
- handle permissions
- handle web/native differences
- use `NgZone` when native events do not reflect in the UI
