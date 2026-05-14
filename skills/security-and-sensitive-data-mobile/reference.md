# Security and Sensitive Data Mobile Reference

## Minimum Controls

- sensitive data classification
- appropriate storage by sensitivity
- session and expiration policy
- logout with local data cleanup
- data masking in logs and UI

## Review Checklist

1. token/secret not exposed in log
2. sensitive data minimized in local cache
3. expired session flow with clear revocation
4. critical action with additional protection when required
