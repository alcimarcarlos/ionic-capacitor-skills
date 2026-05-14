# App Shell Navigation Blueprint Reference

## Suggested Route Blocks

- `onboarding/*`
- `auth/*`
- `app/tabs/*`
- `settings/*`
- `fallback/not-found`

## Navigation Checklist

1. cold start without session -> onboarding/auth
2. cold start with valid session -> app
3. expired session -> redirect to auth
4. logout clears sensitive state
5. returning from detail preserves list context
