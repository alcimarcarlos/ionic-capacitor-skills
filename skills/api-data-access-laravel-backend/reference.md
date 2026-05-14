# API Data Access Reference

## Recommended Output Template

1. Endpoint contract (method, route, auth, payload, response, errors).
2. File structure (`dto`, `service`, `interceptor`).
3. Main typed code.
4. Error and authentication strategy.
5. Validation checklist.

## Conventions

- Request DTO: `CreateOrderRequestDto`
- Response DTO: `OrderResponseDto`
- Service by resource: `OrdersApiService`
- Methods using business verbs: `list`, `getById`, `create`, `cancel`

## Common Laravel Errors

- `401`: invalid or expired session/token
- `403`: user without permission
- `422`: field validation error
- `500`: internal server failure
