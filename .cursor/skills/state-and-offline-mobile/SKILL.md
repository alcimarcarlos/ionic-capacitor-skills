---
name: state-and-offline-mobile
description: Define estratégia de estado local, cache e sincronização offline/online para apps móveis, com foco em resiliência e previsibilidade. Use quando houver conectividade instável, fila offline, persistência temporária ou reconciliação de dados.
---

# state-and-offline-mobile

## Objetivo

Definir estratégia de estado e operação offline/online em apps móveis.

## Aplicar quando

- a tela depende de cache
- precisa funcionar sem internet estável
- existe sincronização posterior
- há filas locais ou persistência temporária

## Requisitos obrigatórios

- Separar estado efêmero (UI) de estado persistido (cache/fila local).
- Definir fonte de verdade por cenário (local, remota ou híbrida).
- Explicitar política de invalidação de cache e sincronização.
- Tratar reconciliação de conflitos quando houver escrita offline.
- Expor status para UI (`offline`, `syncing`, `error`, `ready`).

## Fluxo recomendado

1. Mapear dados críticos e tolerância à desatualização.
2. Definir armazenamento local (memória, storage, sqlite, etc.).
3. Definir estratégia de leitura (cache-first, network-first ou stale-while-revalidate).
4. Definir fila de ações offline e política de retry.
5. Definir tratamento de conflito (last-write-wins, merge, bloqueio).
6. Validar transição offline -> online com feedback na UI.

## Anti-padrões (não fazer)

- Persistir todo estado sem critério.
- Esconder falha de sincronização do usuário.
- Misturar regras de fila/sync diretamente na page.
- Ignorar idempotência em operações de reenvio.

## Formato de entrega esperado

1. Estratégia de estado e cache.
2. Fluxo offline/online com eventos principais.
3. Regras de sincronização e conflito.
4. Riscos e mitigação.
5. Checklist de testes em conectividade instável.

## Quando pedir mais contexto

- quais dados podem ficar desatualizados e por quanto tempo
- operações que precisam funcionar offline (read/write)
- regra de conflito esperada pelo negócio
- limite de armazenamento local e retenção
- comportamento esperado ao reconectar

## Limites desta skill

- cobre estado local, cache, fila e sincronização
- não cobre estrutura completa de páginas/rotas (usar `ionic-angular-architecture`)
- não cobre detalhes de permissão/plugin nativo (usar `capacitor-native-integration`)

## Exemplo rápido (entrada -> saída)

Entrada: "Salvar apontamentos offline e sincronizar quando voltar internet."

Saída esperada:
- store local com status `pending/synced/failed`
- fila de sync com retry exponencial e idempotência
- regra de conflito (ex.: last-write-wins com log de divergência)
- checklist: offline create, reconexão, erro de sync, retry manual

## Recursos adicionais

- Para estratégias de cache/sync por cenário, ler `reference.md`.

