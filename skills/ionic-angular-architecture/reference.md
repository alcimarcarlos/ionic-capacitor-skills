# Ionic Angular Architecture Reference

## Suggested Structure by Feature

`features/<feature-name>/`

- `pages/`
- `components/`
- `services/`
- `models/`
- `<feature-name>.routes.ts`

## Responsibilities

- `page`: orchestrates UI and screen events
- `component`: reusable interface block
- `service/facade`: business rule and integration
- `model`: feature data contracts

## Quick Architecture Checklist

- page without complex business rules
- routes with lazy loading when applicable
- loading/error/empty state mapped
- minimum coupling between feature and raw API
