---
name: feature-delivery-orchestrator
description: Orquestra a entrega de feature mobile de ponta a ponta, do Figma ao release, acionando skills tecnicas na ordem correta e aplicando gates de qualidade. Use quando o objetivo for implementar uma feature completa com consistencia arquitetural e readiness de entrega.
---

# feature-delivery-orchestrator

## Objetivo

Garantir fluxo unico e previsivel para entregar features completas em Ionic/Capacitor/Angular.

## Aplicar quando

- implementar feature nova fim a fim
- transformar telas de design em entrega tecnica
- reduzir retrabalho por ordem errada de implementacao
- validar prontidao antes de merge/release

## Requisitos obrigatorios

- Executar fases em ordem, sem pular gates.
- Declarar suposicoes quando faltar contrato/regra.
- Cobrir estados de tela e riscos mobile.
- Entregar checklist final de go/no-go.

## Sequencia obrigatoria de orquestracao

1. `figma-to-feature-mapping`  
   mapear frames, fluxos, backlog e criterios de aceite.
2. `app-shell-navigation-blueprint`  
   garantir encaixe da feature no shell e navegacao principal.
3. `ionic-angular-architecture`  
   definir estrutura de arquivos e responsabilidades.
4. `design-tokens-pipeline` + `design-system-and-ui-consistency`  
   alinhar base visual e composicao de interface.
5. `screen-state-matrix`  
   cobrir estados e transicoes de tela.
6. `api-data-access-laravel-backend` e/ou `capacitor-native-integration`  
   integrar dados e recursos nativos necessarios.
7. `forms-validation-and-input-masks` e/ou `list-detail-search-and-filters`  
   completar fluxos de entrada e listagem/detalhe.
8. `state-and-offline-mobile`  
   aplicar cache/sync quando houver risco de conectividade.
9. `code-generation-contract`  
   validar formato e completude da entrega tecnica.
10. `testing-and-release-readiness`  
    executar gate final e decidir go/no-go.

## Gates obrigatorios por fase

- Gate 1 (Descoberta): backlog por tela + criterios de aceite.
- Gate 2 (Estrutura): rotas e arquitetura aprovadas.
- Gate 3 (Implementacao): estados de UI + integracao concluida.
- Gate 4 (Qualidade): checklist tecnico e riscos mapeados.
- Gate 5 (Release): recomendacao final de go/no-go.

## Anti-padroes (nao fazer)

- Implementar codigo antes de mapear telas e fluxo.
- Concluir feature sem matriz de estados.
- Pular validacao de plataforma em fluxo nativo.
- Declarar pronto sem gate final de release.

## Quando pedir mais contexto

- escopo exato da feature (telas e prioridade)
- contrato API disponivel ou a inferir
- dependencias nativas exigidas
- criterio de pronto e prazo de entrega

## Limites desta skill

- coordena a sequencia entre skills
- nao substitui skills tecnicas de implementacao
- nao define regra de negocio do produto sem contexto

## Exemplo rapido (entrada -> saida)

Entrada: "Entregar feature de pedidos do Figma ao merge."

Saida esperada:
- plano por fases com skills acionadas
- entregaveis e gates por fase
- checklist final com go/no-go e pendencias

## Recursos adicionais

- Para playbook operacional e templates, ler `reference.md`.
