---
name: screen-state-matrix
description: Gera matriz obrigatoria de estados por tela para apps Ionic Angular, cobrindo loading, success, empty, error, unauthorized e offline. Use quando implementar ou revisar telas para evitar lacunas de UX e regressao funcional.
---

# screen-state-matrix

## Objetivo

Evitar telas incompletas garantindo cobertura de estados de interface e transicoes.

## Aplicar quando

- criar tela nova
- revisar feature pronta para release
- detectar bug de estado nao tratado
- validar completude de UX por fluxo

## Requisitos obrigatorios

- Mapear estados minimos: loading, success, empty, error.
- Mapear estados condicionais: unauthorized, offline, syncing.
- Definir evento que leva a cada estado.
- Definir acao de recuperacao (retry, refresh, login, suporte).
- Garantir que cada estado tenha representacao visual clara.

## Fluxo recomendado

1. Identificar fonte de dados e eventos da tela.
2. Listar estados possiveis e criterios de entrada.
3. Definir transicoes entre estados.
4. Definir componente/bloco visual por estado.
5. Validar matriz com casos de teste.

## Anti-padroes (nao fazer)

- Tratar erro como toast sem estado visual.
- Nao diferenciar empty de erro.
- Ignorar offline em fluxo dependente de rede.
- Implementar retry sem idempotencia basica.

## Quando pedir mais contexto

- comportamento esperado para dados vazios
- mensagem/acoes em cada falha
- prioridade de suporte offline
- regra para sessao expirada/nao autorizada

## Limites desta skill

- cobre completude de estado de tela
- nao cobre arquitetura completa de feature
- nao cobre detalhamento de contrato de API

## Exemplo rapido (entrada -> saida)

Entrada: "Tela de pedidos com listagem e refresh."

Saida esperada:
- matriz de estados e transicoes
- mapeamento visual por estado
- acoes de recuperacao por falha
- checklist de teste por estado

## Recursos adicionais

- Para template de matriz e casos de teste, ler `reference.md`.
