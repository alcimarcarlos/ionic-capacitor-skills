# Capacitor Native Integration Reference

## Standard Integration Sequence

1. Verify plugin/platform availability.
2. Check current permission.
3. Request permission when needed.
4. Execute native action.
5. Handle error and web fallback.

## Suggested Permission States

- `granted`
- `denied`
- `prompt`
- `limited` (when applicable)

## Minimum Platform Checklist

- Android: initial permission, denial, permanent denial
- iOS: initial permission, denial, background return
- Web: functional fallback or explicit unavailable message
