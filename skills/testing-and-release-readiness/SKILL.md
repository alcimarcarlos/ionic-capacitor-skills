---
name: testing-and-release-readiness
description: "Validates technical readiness of a mobile feature for merge/release with build, tests, risks, and Android/iOS/web compatibility checklist. Use when closing a feature, final PR review, or preparing a release."
license: UNLICENSED
---

# testing-and-release-readiness

## Objective

Ensure the delivery is ready for technical and operational validation.

## Compatibility (Cursor, Codex, Claude Code)

- Vendor-agnostic release gate: prefer checklists with evidence over opinions.
- If CI/device testing is unavailable, declare limitations and provide a **best-effort** validation plan.
- Keep results structured: pass/fail/unknown with next actions.

## Apply When

- finalizing a feature
- reviewing a PR
- validating a release
- checking mobile impact

## Mandatory Requirements

- Validate screen state coverage defined by `screen-state-matrix`.
- Validate critical flows end to end (login, main navigation, key business action).
- Check web and device compatibility when there is a native plugin.
- Identify build/configuration/permission risks.
- Deliver an objective checklist for the release gate.
- Consolidate accessibility, performance, and security risks when applicable.

## Structured Go/No-Go Output

- **Evidence**: commands run, screenshots/log snippets, or explicit “not executed” notes.
- **Risks**: severity (high/medium/low), impact, mitigation/rollback.
- **Decision**: go/no-go with remaining blockers clearly listed.

## Recommended Flow

1. Review changes by risk (data, UI, native, authentication, state).
2. Define minimum suite: unit, integration, and manual smoke.
3. Run build and dependency validations.
4. Validate behavior on Android/iOS (or declare limitations).
5. Consolidate risks, impact, and approval criteria.

## Base Validation Checklist

- `ionic build` completed without errors.
- Main routes and guards working in critical flows.
- API calls cover success, timeout, and validation error (`422`).
- Native permissions (when applicable) cover acceptance, denial, and permanent denial.
- No critical visual regression on Android, iOS, and web (when supported).

## Security + Performance Spot-Checks (When Relevant)

- **Security**: tokens/PII are not logged; logout clears local state; `401/403` paths are safe.
- **Performance**: key lists use `trackBy`; no obvious “load everything” regressions; images are sized/lazy loaded where applicable.

## Anti-Patterns (Do Not Do)

- Declare "ready for release" without an explicit checklist.
- Ignore network failure/timeout scenario.
- Validate only on web when there is native functionality.
- Fail to record known risks and mitigation plan.

## Expected Delivery Format

1. Filled technical checklist.
2. Risks and severity.
3. Tests executed/suggested.
4. Build/release notes (Android, iOS, web).

## When to Ask for More Context

- target platforms for release (Android/iOS/web)
- which flows are business-critical
- minimum test coverage requirements
- distribution type (internal, beta, store)
- time constraints affecting validation scope

## Scope Limits

- covers final validation and delivery readiness
- does not define feature architecture (use `ionic-angular-architecture`)
- does not replace API/plugin integration specification (use specific skills)
- does not replace dedicated performance, accessibility, or security analysis

## Quick Example (Input -> Output)

Input: "Login feature is ready, validate before merge."

Expected output:
- filled checklist with commands and evidence
- classified risks (high/medium/low) with impact
- test gaps and objective go/no-go recommendation

## Additional Resources

- For validation matrix and release gates, read `reference.md`.
