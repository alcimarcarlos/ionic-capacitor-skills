---
name: screen-state-matrix
description: "Generates a mandatory state matrix per screen for Ionic Angular apps, covering loading, success, empty, error, unauthorized, and offline. Use when implementing or reviewing screens to avoid UX gaps and functional regressions."
license: UNLICENSED
---

# screen-state-matrix

## Objective

Avoid incomplete screens by ensuring coverage of interface states and transitions.

## Compatibility (Cursor, Codex, Claude Code)

- Vendor-agnostic completeness tool: produce a matrix that can be reviewed independently of the assistant.
- Keep states and transitions **explicit** (entry criteria, UI representation, recovery actions).
- If offline/auth behavior is unknown, make assumptions explicit and list validation steps.

## Apply When

- creating a new screen
- reviewing a feature ready for release
- detecting an untreated state bug
- validating UX completeness by flow

## Mandatory Requirements

- Map minimum states: loading, success, empty, error.
- Map conditional states: unauthorized, offline, syncing.
- Define the event that leads to each state.
- Define the recovery action (retry, refresh, login, support).
- Ensure each state has a clear visual representation.

## Structured State Output (Recommended Shape)

- **State**: name and meaning.
- **Entry criteria**: what must be true to enter it.
- **UI**: what the user sees (component/block).
- **Actions**: primary and secondary actions.
- **Recovery**: retry/login/offline guidance.
- **Telemetry** (optional): what to log (redacted) for diagnosis.

## Recommended Flow

1. Identify the screen's data source and events.
2. List possible states and entry criteria.
3. Define transitions between states.
4. Define visual component/block per state.
5. Validate the matrix with test cases.

## Anti-Patterns (Do Not Do)

- Treat an error as a toast without a visual state.
- Fail to differentiate empty from error.
- Ignore offline in a network-dependent flow.
- Implement retry without basic idempotency.

## When to Ask for More Context

- expected behavior for empty data
- message/actions for each failure
- offline support priority
- rule for expired/unauthorized session

## Scope Limits

- covers screen state completeness
- does not cover full feature architecture
- does not cover API contract details

## Quick Example (Input -> Output)

Input: "Orders screen with listing and refresh."

Expected output:
- state and transition matrix
- visual mapping by state
- recovery actions by failure
- test checklist by state

## Additional Resources

- For matrix template and test cases, read `reference.md`.
