---
name: list-detail-search-and-filters
description: "Structures list and detail flows with search, filters, sorting, and pagination in Ionic Angular. Use when implementing catalog, history, query screens, or any list-detail experience in the app."
license: UNLICENSED
---

# list-detail-search-and-filters

## Objective

Standardize list-detail experiences with performance, predictable state, and good search/filter UX.

## Compatibility (Cursor, Codex, Claude Code)

- Vendor-agnostic list/detail playbook: explicit query contract, state model, and pagination rules.
- If backend pagination style is unknown, propose page-based vs cursor-based as an assumption and list validation steps.
- Prefer implementations that prevent duplicated requests and inconsistent merges.

## Apply When

- creating a list screen with detail item
- adding search with debounce
- implementing filters and sorting
- handling pagination, pull-to-refresh, and infinite scroll

## Mandatory Requirements

- Define list state (`loading`, `ready`, `empty`, `error`).
- Search with debounce and cancellation of concurrent requests.
- Filters with controlled state and predictable reset.
- Coherent pagination (cursor or page-based) with safe append.
- List -> detail navigation without losing context when returning.

## Performance + Correctness Baseline

- **Requests**: cancel/ignore stale requests; avoid parallel fetches for the same query; cache the last successful result when appropriate.
- **Pagination merge**: de-duplicate by stable id; handle “end reached” deterministically.
- **Rendering**: use `trackBy`; avoid heavy template expressions; prefer skeletons for perceived performance.

## Recommended Flow

1. Define the query contract (search, filters, sort, page/cursor).
2. Create local screen state (items, meta, applied filters).
3. Implement search with debounce and distinct.
4. Implement filters (open, apply, clear) with optional persistence.
5. Integrate navigation to detail with return to the previous point.
6. Validate error, empty, and end-of-list states.

## Anti-Patterns (Do Not Do)

- Trigger a request on every keystroke without debounce.
- Lose filters on navigate-and-return without justification.
- Duplicate items in pagination due to incorrect merge.
- Treat empty state as a technical error.

## When to Ask for More Context

- search fields and allowed operators
- available filters and valid combinations
- default sorting rule
- page size and scroll strategy
- expectation for filter persistence between sessions

## Scope Limits

- covers listing, search, filters, and detail flow
- does not cover deep offline cache/sync rules (use `state-and-offline-mobile`)
- does not cover full endpoint specification (use `api-data-access-laravel-backend`)
- does not replace render performance tuning (use `mobile-performance-and-rendering`)

## Quick Example (Input -> Output)

Input: "Orders screen with customer search, status filter, and detail."

Expected output:
- list state with pagination meta
- search with 300-500ms debounce
- applicable filters and clear button
- navigation to detail preserving filters and list position

## Additional Resources

- For query contracts and UX checklist, read `reference.md`.
