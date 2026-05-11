---
name: app-shell-navigation-blueprint
description: Defines the base Ionic Angular app structure with shell, onboarding/auth/main/settings flows, guards, and consistent navigation. Use when starting a new app or reorganizing main navigation.
---

# app-shell-navigation-blueprint

## Objective

Ensure a consistent navigation base so features can scale without breaking main flows.

## Compatibility (Cursor, Codex, Claude Code)

- Vendor-agnostic navigation architecture checklist.
- Prefer explicit route trees, guard rules, and redirects that can be reviewed without running special tools.
- If auth/session rules are unknown, declare assumptions and list validation steps.

## Apply When

- starting an app from scratch
- reorganizing main routes
- creating onboarding/auth/main flow
- configuring tabs, stack, and guards

## Mandatory Requirements

- Define the initial shell (splash/onboarding/auth/main).
- Clearly separate authenticated and unauthenticated areas.
- Apply guards for access by session/profile state.
- Define return and deep link strategy.
- Include settings screen and safe session logout.

## Security + Resilience Baseline

- **Guards**: do not rely on UI hiding; enforce access by route guards.
- **Session restore**: handle cold start with persisted session safely; avoid infinite redirect loops.
- **Logout**: clear session + sensitive cached state and return to a safe public route.

## Recommended Flow

1. Map the user's main journeys.
2. Define the base route tree with lazy loading.
3. Configure session and permission guards.
4. Configure tabs/stack/modals navigation by context.
5. Validate the complete flow: cold start -> login -> main -> logout.

## Anti-Patterns (Do Not Do)

- Mix public and private routes without a guard.
- Create circular navigation without return criteria.
- Couple route decisions across multiple components.
- Ignore session restoration on startup.

## When to Ask for More Context

- mandatory/optional onboarding rules
- session and expiration policies
- roles/profiles and allowed routes
- expected behavior in deep links

## Scope Limits

- covers navigation architecture and app shell
- does not cover detailed UI for each screen
- does not cover API contracts by endpoint

## Quick Example (Input -> Output)

Input: "Define a shell with onboarding, login, and main tabs."

Expected output:
- base route tree with guards
- redirect criteria by session
- main modules/features structure
- end-to-end navigation flow checklist

## Additional Resources

- For route and guard templates, read `reference.md`.
