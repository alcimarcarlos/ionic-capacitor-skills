---
name: api-data-access-laravel-backend
description: "Standardizes Ionic/Angular integration with Laravel APIs, including HTTP services, DTOs, interceptors, authentication, and error handling. Use when consuming endpoints, request/response contracts, pagination, filters, or auth flows in the Laravel backend."
license: UNLICENSED
---

# api-data-access-laravel-backend

## Objective

Standardize the Ionic/Angular app data layer for reliable integration with Laravel APIs.

## Compatibility (Cursor, Codex, Claude Code)

- Use as a **vendor-agnostic** playbook; do not depend on proprietary agent features.
- If endpoint/contract details are unknown, proceed with **declared assumptions** and a validation checklist.
- Prefer **typed, testable, single-responsibility** services over “smart components”.

## Apply When

- consuming/creating a REST endpoint
- modeling request/response DTOs
- implementing token/session authentication
- configuring an interceptor (auth, headers, global error)
- handling pagination, filters, sorting, and error messages

## Mandatory Requirements

- Define explicit DTOs and types for request and response.
- Separate `ApiService` by resource/domain (for example: `AuthApiService`, `OrdersApiService`).
- Centralize common behavior in an interceptor (Authorization, refresh, handling `401/403/422/500`).
- Do not execute `HttpClient` directly in a page/component.
- Handle loading, error, and empty states in the consumer.

## Architecture + Structured Logic Baseline

- Treat the API layer as a **boundary**: DTOs in/out, mapping at edges, no UI concerns.
- Prefer **small methods** with clear intent (`list`, `getById`, `create`, `update`, `delete`).
- Return **structured results** to UI layers (success payload vs typed error), not loosely-shaped objects.
- Keep retry/refresh logic centralized to avoid divergent behavior across features.

## Security + Performance Baseline

- **Security**: avoid logging raw payloads/headers; redact tokens/PII; validate auth failure paths; handle `403` distinctly from `401`.
- **Performance**: avoid duplicate in-flight requests; cache where safe; debounce search; prefer pagination/cursor patterns for large datasets.

## Recommended Flow

1. Confirm the endpoint contract (method, route, payload, headers, response, and error codes).
2. Create DTOs (`RequestDto`, `ResponseDto`) and map to a UI model when needed.
3. Implement a service with short, typed methods.
4. Apply an interceptor for authentication and common error handling.
5. Define pagination/filter strategy and Laravel response normalization.
6. Validate success, validation (`422`), unauthenticated (`401`), and unavailable scenarios.

## Anti-Patterns (Do Not Do)

- Couple the screen to the raw API payload.
- Repeat header/token logic manually in every method.
- Use `any` in payload/response without justification.
- Silence errors without returning useful context to the UI.

## Expected Delivery Format

1. Inferred/confirmed endpoint contract.
2. Suggested file structure.
3. DTO + service + interceptor code (if applicable).
4. Error handling and authentication strategy.
5. Quick validation checklist.

## When to Ask for More Context

- exact endpoint and HTTP method
- real request/response payload
- authentication format (Bearer, cookie/session, refresh token)
- pagination/filter/sorting rules
- error messages/codes expected from the backend

## Scope Limits

- covers HTTP integration and data contracts
- does not cover native plugin/device permission (use `capacitor-native-integration`)
- does not define full page/feature architecture (use `ionic-angular-architecture`)

## Quick Example (Input -> Output)

Input: "Create consumption for `GET /api/orders?page=1` with token and pagination."

Expected output:
- `orders.dto.ts` with `OrderItemDto` and `PaginatedResponseDto<OrderItemDto>`
- `orders-api.service.ts` with typed `list(params)`
- interceptor with `Authorization` and `401/422` handling
- checklist: success, empty list, expired token, validation error

## Additional Resources

- For detailed templates and conventions, read `reference.md`.
