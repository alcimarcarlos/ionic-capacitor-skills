# API Data Access Reference

## Template de saída recomendado

1. Contrato do endpoint (método, rota, auth, payload, resposta, erros).
2. Estrutura de arquivos (`dto`, `service`, `interceptor`).
3. Código principal tipado.
4. Estratégia de erro e autenticação.
5. Checklist de validação.

## Convenções

- DTO de request: `CreateOrderRequestDto`
- DTO de response: `OrderResponseDto`
- Service por recurso: `OrdersApiService`
- Métodos em verbo de negócio: `list`, `getById`, `create`, `cancel`

## Erros Laravel comuns

- `401`: sessão/token inválido ou expirado
- `403`: usuário sem permissão
- `422`: erro de validação de campos
- `500`: falha interna do servidor
