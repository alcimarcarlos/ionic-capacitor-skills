---
name: design-tokens-pipeline
description: Padroniza pipeline de tokens de design para Ionic Angular, conectando cores, tipografia e espacamento do design aos estilos do app. Use quando alinhar UI com Figma, criar tema ou reduzir inconsistencias visuais.
---

# design-tokens-pipeline

## Objetivo

Criar fluxo consistente de definicao e aplicacao de tokens para acelerar implementacao visual sem divergencias.

## Aplicar quando

- iniciar tema visual do app
- alinhar telas com design
- reduzir variacoes de estilo ad hoc
- criar base para dark mode/brand variants

## Requisitos obrigatorios

- Definir tokens semanticos (nao valores hardcoded no componente).
- Centralizar tokens em arquivo de tema (`variables.scss` e auxiliares).
- Separar token global de override por componente quando necessario.
- Evitar cores/tamanhos diretos em paginas.
- Definir naming consistente para tokens.

## Fluxo recomendado

1. Levantar tokens principais do design (cor, tipo, espaco, raio).
2. Nomear tokens semanticos por papel de UI.
3. Publicar tokens globais no tema do app.
4. Aplicar tokens nos componentes base.
5. Validar consistencia e contrastes minimos.

## Anti-padroes (nao fazer)

- Copiar valor do Figma direto para cada componente.
- Criar token duplicado com semantica ambigua.
- Misturar token de marca com token de papel de interface.
- Ignorar acessibilidade de contraste ao definir paleta.

## Quando pedir mais contexto

- tema claro/escuro obrigatorio ou opcional
- variacoes de marca por cliente
- prioridade de componentes para tokenizacao inicial
- regra de acessibilidade e contraste alvo

## Limites desta skill

- cobre pipeline de tema e tokens
- nao cobre backlog funcional de telas
- nao cobre contratos de dados e integracao API

## Exemplo rapido (entrada -> saida)

Entrada: "Aplicar identidade visual nas telas de login e home."

Saida esperada:
- tokens semanticos definidos no tema
- componentes base usando tokens
- remocao de estilos hardcoded das telas
- checklist de consistencia visual e contraste

## Recursos adicionais

- Para naming e checklist de adocao progressiva, ler `reference.md`.
