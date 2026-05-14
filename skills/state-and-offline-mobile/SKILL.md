---
name: state-and-offline-mobile
description: "Defines local state, cache, and offline/online synchronization strategy for mobile apps, focused on resilience and predictability. Use when there is unstable connectivity, offline queue, temporary persistence, or data reconciliation."
license: UNLICENSED
---

# state-and-offline-mobile

## Objective

Define state and offline/online operation strategy in mobile apps.

## Compatibility (Cursor, Codex, Claude Code)

- Vendor-agnostic resilience playbook: define states, policies, and tests explicitly.
- If storage/runtime constraints are unknown, choose a conservative default and mark it as an assumption.
- Prefer designs that are debuggable: explicit status flags and deterministic transitions.

## Apply When

- the screen depends on cache
- it needs to work without stable internet
- later synchronization exists
- there are local queues or temporary persistence

## Mandatory Requirements

- Separate ephemeral state (UI) from persisted state (cache/local queue).
- Define the source of truth by scenario (local, remote, or hybrid).
- Explicitly define cache invalidation and synchronization policy.
- Handle conflict reconciliation when offline writes exist.
- Expose status to the UI (`offline`, `syncing`, `error`, `ready`).

## Structured Offline Model (Baseline)

- **Status model**: `ready | loading | offline | syncing | error`.
- **Queue model**: operations are idempotent where possible; each item has `pending | running | failed | done`.
- **Policies**: cache TTL, invalidation rules, retry strategy (bounded + backoff), and conflict rule.
- **Security**: avoid storing secrets/PII unnecessarily in offline cache; encrypt at rest when required by policy.

## Recommended Flow

1. Map critical data and staleness tolerance.
2. Define local storage (memory, storage, sqlite, etc.).
3. Define reading strategy (cache-first, network-first, or stale-while-revalidate).
4. Define offline action queue and retry policy.
5. Define conflict handling (last-write-wins, merge, blocking).
6. Validate offline -> online transition with UI feedback.

## Anti-Patterns (Do Not Do)

- Persist all state without criteria.
- Hide synchronization failure from the user.
- Mix queue/sync rules directly in the page.
- Ignore idempotency in retry operations.

## Expected Delivery Format

1. State and cache strategy.
2. Offline/online flow with main events.
3. Synchronization and conflict rules.
4. Risks and mitigation.
5. Test checklist under unstable connectivity.

## When to Ask for More Context

- which data may become stale and for how long
- operations that need to work offline (read/write)
- conflict rule expected by the business
- local storage and retention limits
- expected behavior when reconnecting

## Scope Limits

- covers local state, cache, queue, and synchronization
- does not cover full page/route structure (use `ionic-angular-architecture`)
- does not cover native plugin/permission details (use `capacitor-native-integration`)

## Quick Example (Input -> Output)

Input: "Save notes offline and sync when internet returns."

Expected output:
- local store with `pending/synced/failed` status
- sync queue with exponential retry and idempotency
- conflict rule (for example: last-write-wins with divergence log)
- checklist: offline create, reconnect, sync error, manual retry

## Additional Resources

- For cache/sync strategies by scenario, read `reference.md`.
