---
name: design-system-and-ui-consistency
description: Define e aplica consistencia visual em apps Ionic Angular com tokens, componentes base e estados de UI. Use quando implementar telas novas, refatorar interface, alinhar com Figma ou reduzir divergencias de layout.
---

# design-system-and-ui-consistency

## Objetivo

Garantir consistencia visual e comportamental entre telas Ionic/Angular com base no design do produto.

## Aplicar quando

- implementar tela nova baseada em Figma
- corrigir inconsistencias entre componentes
- criar componente reutilizavel de UI
- padronizar estados visuais (loading, empty, error, success)

## Requisitos obrigatorios

- Consumir tokens ja definidos no tema (nao criar valores hardcoded por tela).
- Reutilizar componentes base antes de criar variacoes.
- Aplicar padrao de espacos e hierarquia visual consistente.
- Garantir estados de UI explicitos para carregamento, vazio e erro.
- Preferir componentes Ionic para estrutura e interacao mobile.

## Fluxo recomendado

1. Mapear os elementos recorrentes da tela no Figma.
2. Identificar o que vira token e o que vira componente base.
3. Implementar/ajustar componente com API simples de props/inputs.
4. Validar estados visuais e responsividade.
5. Revisar consistencia com telas ja existentes.

## Anti-padroes (nao fazer)

- Duplicar estilos inline sem tokenizacao.
- Criar variante nova para resolver detalhe isolado.
- Misturar regras de negocio com logica visual no componente.
- Ignorar estados de erro e vazio por "falta de tempo".

## Quando pedir mais contexto

- arquivo/frame exato do Figma
- variacoes esperadas do componente
- guideline visual ja existente no projeto
- comportamento em orientacao/tamanho de tela diferente

## Limites desta skill

- cobre consistencia visual e composicao de UI
- nao define pipeline de tokens/tema (usar `design-tokens-pipeline`)
- nao cobre contratos de API (usar `api-data-access-laravel-backend`)
- nao cobre integracao nativa de plugin (usar `capacitor-native-integration`)

## Exemplo rapido (entrada -> saida)

Entrada: "Criar card de oferta igual ao Figma e usar em home e detalhe."

Saida esperada:
- tokenizacao de espacamento e tipografia
- `offer-card.component` reutilizavel com variantes
- estados `loading` e `empty` coerentes
- checklist visual comparando com o Figma

## Recursos adicionais

- Para checklist de consistencia e template de tokens, ler `reference.md`.
