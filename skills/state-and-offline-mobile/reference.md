# State and Offline Mobile Reference

## Reading Strategies

- `cache-first`: fast response with later update
- `network-first`: prioritizes fresh data with local fallback
- `stale-while-revalidate`: returns cache and revalidates in parallel

## Offline Queue Strategy

- register action with idempotency key
- mark as `pending`
- resend on reconnection with exponential retry
- mark as `synced` or `failed` with cause

## Minimum Test Scenarios

- create data offline and sync on reconnect
- temporary network failure with automatic retry
- version conflict and applied resolution rule
- correct visual feedback for `offline/syncing/error/ready`
