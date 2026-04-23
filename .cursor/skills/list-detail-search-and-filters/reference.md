# List Detail Search and Filters Reference

## Contrato de query sugerido

- `search`: string opcional
- `filters`: objeto com pares chave/valor
- `sort`: campo + direcao (`asc`/`desc`)
- `page` e `per_page` (ou `cursor`)

## Checklist de UX para lista

- loading inicial com skeleton
- empty state com acao sugerida
- erro com retry
- pull-to-refresh
- fim de lista claro no infinite scroll

## Preservacao de contexto

1. guardar filtros atuais
2. guardar posicao/scroll da lista
3. restaurar estado ao voltar do detalhe
