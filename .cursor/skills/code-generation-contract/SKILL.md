---
name: code-generation-contract
description: Impoe contrato de saida obrigatorio para geracao de codigo Ionic Angular, garantindo consistencia de arquitetura, integracao, estados de tela e validacao. Use quando solicitar implementacao de qualquer tela, fluxo ou feature.
---

# code-generation-contract

## Objetivo

Padronizar o formato e o nivel minimo de completude das entregas do agente.

## Aplicar quando

- gerar nova tela/feature
- refatorar fluxo existente
- solicitar implementacao ponta a ponta
- revisar se resposta esta completa para execucao

## Requisitos obrigatorios

- Entregar estrutura de arquivos antes do codigo.
- Declarar contratos de dados (DTO/interface) ou suposicoes explicitas.
- Cobrir estados de UI (loading, success, empty, error).
- Incluir pontos de atencao mobile (web/Android/iOS).
- Incluir checklist de teste minimo por fluxo critico.

## Formato de saida obrigatorio

1. Objetivo
2. Estrutura de arquivos
3. Codigo
4. Integracao com API
5. Pontos de atencao mobile
6. Testes e validacoes
7. Suposicoes e pendencias

## Anti-padroes (nao fazer)

- Entregar apenas trecho de codigo sem contexto de integracao.
- Omitir estado de erro e vazio.
- Omitir risco/plataforma em fluxo com recurso nativo.
- Declarar "pronto" sem checklist minimo.

## Quando pedir mais contexto

- endpoint e payload esperados
- regra de negocio principal
- perfil/permissao por fluxo
- prioridade de plataforma e prazo

## Limites desta skill

- cobre padrao de entrega e qualidade minima
- nao substitui skills tecnicas especificas por dominio

## Exemplo rapido (entrada -> saida)

Entrada: "Crie tela de detalhe com acao de aprovar."

Saida esperada:
- arvore de arquivos da feature
- page/component/service/DTO
- estados da tela e fluxo de erro
- checklist de teste do fluxo de aprovacao

## Recursos adicionais

- Para checklist detalhado de conformidade, ler `reference.md`.
