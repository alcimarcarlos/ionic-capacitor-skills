---
name: figma-to-feature-mapping
description: Converte telas do Figma em backlog tecnico de implementacao Ionic Angular, com features, rotas, componentes, estados e criterios de aceite. Use quando iniciar desenvolvimento a partir de um design ou revisar cobertura funcional de telas.
---

# figma-to-feature-mapping

## Objetivo

Transformar frames do Figma em plano de implementacao executavel e rastreavel no app.

## Aplicar quando

- iniciar feature baseada em Figma
- quebrar telas em tarefas tecnicas
- identificar lacunas de estado e comportamento
- revisar cobertura de navegacao e componentes

## Requisitos obrigatorios

- Mapear cada frame para rota/fluxo correspondente.
- Identificar componentes reutilizaveis e componentes de pagina.
- Listar estados de tela: loading, success, empty, error.
- Relacionar eventos de usuario com acao tecnica (navegar, enviar, abrir modal).
- Definir criterio de aceite objetivo por tela.

## Fluxo recomendado

1. Listar frames e objetivo funcional de cada um.
2. Agrupar frames por feature/modulo.
3. Mapear rotas, guardas e transicoes entre telas.
4. Definir estrutura de arquivos por feature.
5. Criar backlog tecnico com ordem de implementacao.
6. Validar dependencias com API, estado e plugins.

## Anti-padroes (nao fazer)

- Implementar tela sem mapear estado de erro/vazio.
- Tratar todo frame como componente novo sem avaliar reuso.
- Ignorar fluxo de retorno e navegacao entre telas.
- Criar backlog sem criterio de aceite mensuravel.

## Quando pedir mais contexto

- frame exato ou conjunto de frames prioritarios
- comportamento de interacao nao visivel no layout
- prioridade de release por fluxo
- regras de permissao/perfil por tela

## Limites desta skill

- cobre mapeamento de design para backlog tecnico
- nao substitui modelagem de API (usar `api-data-access-laravel-backend`)
- nao substitui implementacao visual detalhada (usar `design-system-and-ui-consistency`)

## Exemplo rapido (entrada -> saida)

Entrada: "Mapear onboarding + login + home a partir do Figma."

Saida esperada:
- rotas e fluxo de navegacao
- componentes por tela e itens reutilizaveis
- matriz de estados por tela
- backlog priorizado com criterios de aceite

## Recursos adicionais

- Para template de mapeamento e checklist, ler `reference.md`.
