# List Detail Search and Filters Reference

## Suggested Query Contract

- `search`: optional string
- `filters`: object with key/value pairs
- `sort`: field + direction (`asc`/`desc`)
- `page` and `per_page` (or `cursor`)

## List UX Checklist

- initial loading with skeleton
- empty state with suggested action
- error with retry
- pull-to-refresh
- clear end of list in infinite scroll

## Context Preservation

1. store current filters
2. store list position/scroll
3. restore state when returning from detail
