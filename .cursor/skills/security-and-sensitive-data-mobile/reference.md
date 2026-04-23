# Security and Sensitive Data Mobile Reference

## Controles minimos

- classificacao de dados sensiveis
- armazenamento apropriado por sensibilidade
- politica de sessao e expiracao
- logout com limpeza de dados locais
- mascaramento de dados em logs e UI

## Checklist de revisao

1. token/segredo nao exposto em log
2. dados sensiveis minimizados em cache local
3. fluxo de sessao expirada com revogacao clara
4. acao critica com protecao adicional quando exigido
