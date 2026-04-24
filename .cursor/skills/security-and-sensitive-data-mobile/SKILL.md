---
name: security-and-sensitive-data-mobile
description: Defines security practices for sensitive data in Ionic Capacitor apps, covering secure storage, session, biometrics, and protection of information in transit and at rest. Use when there is authentication, tokens, personal data, or critical operations.
---

# security-and-sensitive-data-mobile

## Objective

Reduce data exposure risk and strengthen session controls in the mobile app.

## Apply When

- implementing login/session/token
- storing sensitive data locally
- protecting critical operations with biometrics/pin
- reviewing security risk before release

## Mandatory Requirements

- Do not store sensitive secrets in insecure storage.
- Centralize session and expiration strategy.
- Avoid logging sensitive data (token, document, full email).
- Define a session cleanup policy on logout.
- Protect critical actions with an additional layer when required.

## Recommended Flow

1. Classify data by sensitivity level.
2. Define storage and lifecycle by data type.
3. Implement session control and secure renewal.
4. Review logs, errors, and traces to avoid leakage.
5. Validate risk and recovery scenarios.

## Anti-Patterns (Do Not Do)

- Persist a token in an easily extractable location without justification.
- Display complete sensitive data on screen/log.
- Keep session active without expiration control.
- Handle auth failure without revocation/cleanup action.

## When to Ask for More Context

- compliance and internal policy requirements
- sensitivity level of the data
- authentication strategy (token, session, biometrics)
- session duration and renewal rules

## Scope Limits

- covers session security and sensitive data in the app
- does not cover pentest or backend infrastructure security
- does not cover detailed screen UX

## Quick Example (Input -> Output)

Input: "Review security for login and profile flow."

Expected output:
- sensitive data and storage map
- session/logout/expiration adjustments
- log review and masking
- risks and mitigation checklist

## Additional Resources

- For minimum controls checklist, read `reference.md`.
