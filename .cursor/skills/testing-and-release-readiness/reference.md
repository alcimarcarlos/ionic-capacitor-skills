# Testing and Release Readiness Reference

## Suggested Approval Gate

- Build: `ionic build` completed
- Quality: lint/essential tests without failure
- Critical flows: manual smoke test approved
- Platform: minimum Android/iOS validation when native exists

## Risk Matrix

- **High**: login breakage, payment, data loss
- **Medium**: secondary flow regression, bug with workaround
- **Low**: visual detail without functional impact

## Completion Format

1. Gate status (`go` or `no-go`)
2. Executed evidence
3. Remaining risks
4. Next actions before release
