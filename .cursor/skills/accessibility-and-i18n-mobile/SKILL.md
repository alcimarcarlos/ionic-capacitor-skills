---
name: accessibility-and-i18n-mobile
description: Garante acessibilidade e internacionalizacao em apps Ionic Angular, cobrindo contraste, foco, semantica, leitor de tela e textos localizados. Use quando implementar ou revisar telas para qualidade de UX inclusiva e suporte multilíngue.
---

# accessibility-and-i18n-mobile

## Objetivo

Garantir que telas sejam acessiveis e internacionalizaveis desde a implementacao inicial.

## Aplicar quando

- criar/refatorar telas e componentes
- revisar experiencia de formulario e navegacao
- adicionar novos idiomas ou ajustar textos
- preparar feature para producao com padrao de qualidade

## Requisitos obrigatorios

- Garantir contraste minimo entre texto e fundo.
- Definir labels acessiveis em botoes, inputs e icones interativos.
- Preservar ordem de foco e navegacao por teclado quando aplicavel.
- Externalizar textos para camada de i18n (sem hardcode em template).
- Tratar pluralizacao e fallback de traducao.

## Fluxo recomendado

1. Mapear elementos interativos da tela.
2. Definir semantica e labels acessiveis.
3. Aplicar i18n em todos os textos visiveis.
4. Validar truncamento/overflow para strings longas.
5. Executar checklist de acessibilidade e localizacao.

## Anti-padroes (nao fazer)

- Usar apenas cor para indicar erro/sucesso.
- Renderizar icone clicavel sem label acessivel.
- Deixar texto hardcoded no HTML/TS.
- Assumir tamanho fixo de string em todos os idiomas.

## Quando pedir mais contexto

- idiomas alvo e prioridade de rollout
- padrao de i18n adotado no projeto
- requisitos de acessibilidade do produto
- componentes com maior criticidade de uso

## Limites desta skill

- cobre acessibilidade e localizacao da interface
- nao cobre integracao API/DTO
- nao cobre otimizacao de performance profunda
- nao substitui regras de validacao de formulario (usar `forms-validation-and-input-masks`)

## Exemplo rapido (entrada -> saida)

Entrada: "Validar tela de login para acessibilidade e pt/en."

Saida esperada:
- labels acessiveis em campos e botoes
- mensagens de erro localizadas
- ajuste de contraste e foco visivel
- checklist de validacao a11y + i18n

## Recursos adicionais

- Para checklist e criterios de validacao, ler `reference.md`.
