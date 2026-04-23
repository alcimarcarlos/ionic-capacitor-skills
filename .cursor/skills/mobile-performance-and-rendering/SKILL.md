---
name: mobile-performance-and-rendering
description: Otimiza performance de renderizacao em apps Ionic Angular, cobrindo listas, imagens, ciclo de deteccao e carregamento progressivo. Use quando telas apresentarem lentidao, jank, consumo excessivo ou risco de regressao de performance.
---

# mobile-performance-and-rendering

## Objetivo

Melhorar fluidez e tempo de resposta da interface em web, Android e iOS.

## Aplicar quando

- listas grandes com scroll travando
- telas com carregamento visual lento
- consumo elevado de memoria/cpu
- revisao de performance antes de release

## Requisitos obrigatorios

- Evitar renderizacao desnecessaria em loops e bindings pesados.
- Aplicar estrategia de carregamento para imagens e conteudo.
- Usar paginacao/virtualizacao em listas extensas quando cabivel.
- Definir skeleton/loading perceptivel para reduzir espera percebida.
- Medir impacto com criterio objetivo antes/depois.

## Fluxo recomendado

1. Identificar gargalo principal (lista, imagem, change detection, network).
2. Aplicar otimizacao no ponto critico.
3. Reduzir trabalho de render por interacao.
4. Validar em dispositivo real quando possivel.
5. Registrar ganho e riscos residuais.

## Anti-padroes (nao fazer)

- Otimizar sem medir sintoma real.
- Carregar lista completa sem necessidade.
- Re-renderizar componentes a cada evento global.
- Ignorar performance em device de menor capacidade.

## Quando pedir mais contexto

- dispositivos alvo e baseline de performance
- tamanho medio/maximo de listas e midias
- metas de UX (tempo de abertura, scroll fluido)
- fluxo mais critico para usuario

## Limites desta skill

- cobre performance de UI/renderizacao
- nao cobre seguranca de dados sensiveis
- nao cobre modelagem completa de arquitetura
- nao define UX funcional de filtros/list-detail (usar `list-detail-search-and-filters`)

## Exemplo rapido (entrada -> saida)

Entrada: "Lista de pedidos trava no scroll."

Saida esperada:
- diagnostico do gargalo de render
- paginacao/virtualizacao e ajuste de bindings
- melhoria de carregamento de imagem/skeleton
- comparativo simples antes/depois

## Recursos adicionais

- Para checklist de diagnostico e tuning, ler `reference.md`.
