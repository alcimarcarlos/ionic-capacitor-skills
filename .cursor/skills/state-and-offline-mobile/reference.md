# State and Offline Mobile Reference

## Estratégias de leitura

- `cache-first`: resposta rápida com atualização posterior
- `network-first`: prioriza dado fresco com fallback local
- `stale-while-revalidate`: retorna cache e revalida em paralelo

## Estratégia de fila offline

- registrar ação com idempotency key
- marcar `pending`
- reenviar em reconexão com retry exponencial
- marcar `synced` ou `failed` com causa

## Cenários de teste mínimos

- criar dado offline e sincronizar ao reconectar
- falha temporária de rede com retry automático
- conflito de versão e regra de resolução aplicada
- feedback visual correto para `offline/syncing/error/ready`
