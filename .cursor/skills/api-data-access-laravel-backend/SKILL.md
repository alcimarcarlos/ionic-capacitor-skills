---
name: api-data-access-laravel-backend
description: Padroniza integração Ionic/Angular com APIs Laravel, incluindo services HTTP, DTOs, interceptors, autenticação e tratamento de erro. Use quando houver consumo de endpoints, contratos de request/response, paginação, filtros ou fluxo de auth no backend Laravel.
---

# api-data-access-laravel-backend

## Objetivo

Padronizar a camada de dados do app Ionic/Angular para integração confiável com APIs Laravel.

## Aplicar quando

- consumir/criar endpoint REST
- modelar request/response DTO
- implementar autenticação por token/sessão
- configurar interceptor (auth, headers, erro global)
- tratar paginação, filtros, ordenação e mensagens de erro

## Requisitos obrigatórios

- Definir DTOs e tipos explícitos para request e response.
- Separar `ApiService` por recurso/domínio (ex.: `AuthApiService`, `OrdersApiService`).
- Centralizar comportamento comum em interceptor (Authorization, refresh, tratamento de `401/403/422/500`).
- Não executar `HttpClient` direto em page/component.
- Tratar estado de loading, erro e vazio no consumidor.

## Fluxo recomendado

1. Confirmar contrato do endpoint (método, rota, payload, headers, resposta e códigos de erro).
2. Criar DTOs (`RequestDto`, `ResponseDto`) e mapear para model de UI quando necessário.
3. Implementar service com métodos curtos e tipados.
4. Aplicar interceptor para autenticação e tratamento de erro comum.
5. Definir estratégia de paginação/filtro e normalização da resposta Laravel.
6. Validar cenários de sucesso, validação (`422`), não autenticado (`401`) e indisponibilidade.

## Anti-padrões (não fazer)

- Acoplar tela ao payload bruto da API.
- Repetir header/token em todos os métodos manualmente.
- Usar `any` em payload/resposta sem justificativa.
- Silenciar erro sem retornar contexto útil para UI.

## Formato de entrega esperado

1. Contrato inferido/confirmado do endpoint.
2. Estrutura de arquivos sugerida.
3. Código de DTOs + service + interceptor (se aplicável).
4. Estratégia de tratamento de erro e autenticação.
5. Checklist rápido de validação.

## Quando pedir mais contexto

- endpoint exato e método HTTP
- payload de request/response real
- formato de autenticação (Bearer, cookie/sessão, refresh token)
- regras de paginação/filtro/ordenação
- mensagens/códigos de erro esperados pelo backend

## Limites desta skill

- cobre integração HTTP e contratos de dados
- não cobre plugin nativo/permissão de dispositivo (usar `capacitor-native-integration`)
- não define arquitetura completa de page/feature (usar `ionic-angular-architecture`)

## Exemplo rápido (entrada -> saída)

Entrada: "Criar consumo de `GET /api/orders?page=1` com token e paginação."

Saída esperada:
- `orders.dto.ts` com `OrderItemDto` e `PaginatedResponseDto<OrderItemDto>`
- `orders-api.service.ts` com `list(params)` tipado
- interceptor com `Authorization` e tratamento de `401/422`
- checklist: sucesso, lista vazia, token expirado, erro de validação

## Recursos adicionais

- Para templates e convenções detalhadas, ler `reference.md`.

