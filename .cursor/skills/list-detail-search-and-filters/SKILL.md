---
name: list-detail-search-and-filters
description: Estrutura fluxos de listagem e detalhe com busca, filtros, ordenacao e paginacao em Ionic Angular. Use quando implementar telas de catalogo, historico, consultas ou qualquer experiencia list-detail no app.
---

# list-detail-search-and-filters

## Objetivo

Padronizar experiencias list-detail com performance, previsibilidade de estado e boa UX de busca/filtro.

## Aplicar quando

- criar tela de lista com item de detalhe
- adicionar busca com debounce
- implementar filtros e ordenacao
- lidar com paginação, pull-to-refresh e infinite scroll

## Requisitos obrigatorios

- Definir estado da lista (`loading`, `ready`, `empty`, `error`).
- Busca com debounce e cancelamento de requisicoes concorrentes.
- Filtros com estado controlado e reset previsivel.
- Paginacao coerente (cursor ou page-based) com append seguro.
- Navegacao lista -> detalhe sem perder contexto quando retornar.

## Fluxo recomendado

1. Definir contrato de query (search, filters, sort, page/cursor).
2. Criar estado local da tela (itens, meta, filtros aplicados).
3. Implementar busca com debounce e distinct.
4. Implementar filtros (abrir, aplicar, limpar) com persistencia opcional.
5. Integrar navegacao para detalhe com retorno ao ponto anterior.
6. Validar estados de erro, vazio e fim de lista.

## Anti-padroes (nao fazer)

- Disparar request a cada tecla sem debounce.
- Perder filtros ao navegar e voltar sem justificativa.
- Duplicar itens em paginacao por merge incorreto.
- Tratar empty state como erro tecnico.

## Quando pedir mais contexto

- campos de busca e operadores permitidos
- filtros disponiveis e combinacoes validas
- regra de ordenacao default
- tamanho de pagina e estrategia de scroll
- expectativa de persistencia de filtros entre sessoes

## Limites desta skill

- cobre fluxo de listagem, busca, filtros e detalhe
- nao cobre regras profundas de cache/sync offline (usar `state-and-offline-mobile`)
- nao cobre especificacao total de endpoint (usar `api-data-access-laravel-backend`)
- nao substitui tuning de performance de render (usar `mobile-performance-and-rendering`)

## Exemplo rapido (entrada -> saida)

Entrada: "Tela de pedidos com busca por cliente, filtro por status e detalhe."

Saida esperada:
- estado de lista com meta de paginação
- busca com debounce de 300-500ms
- filtros aplicaveis e botao limpar
- navegacao para detalhe preservando filtros e posicao da lista

## Recursos adicionais

- Para contratos de query e checklist de UX, ler `reference.md`.
