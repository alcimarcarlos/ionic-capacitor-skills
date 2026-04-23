---
name: app-shell-navigation-blueprint
description: Define estrutura base do app Ionic Angular com shell, fluxos de onboarding/auth/main/settings, guards e navegacao consistente. Use quando iniciar app novo ou reorganizar navegacao principal.
---

# app-shell-navigation-blueprint

## Objetivo

Garantir base de navegacao consistente para escalar features sem quebrar fluxos principais.

## Aplicar quando

- iniciar app do zero
- reorganizar rotas principais
- criar fluxo onboarding/auth/main
- configurar tabs, stack e guards

## Requisitos obrigatorios

- Definir shell inicial (splash/onboarding/auth/main).
- Separar claramente areas autenticada e nao autenticada.
- Aplicar guards para acesso por estado de sessao/perfil.
- Definir estrategia de retorno e deep link.
- Incluir tela de configuracoes e saida segura da sessao.

## Fluxo recomendado

1. Mapear jornadas principais do usuario.
2. Definir arvore de rotas base com lazy loading.
3. Configurar guards de sessao e permissao.
4. Configurar navegacao tabs/stack/modals por contexto.
5. Validar fluxo completo: cold start -> login -> main -> logout.

## Anti-padroes (nao fazer)

- Misturar rotas publicas e privadas sem guard.
- Navegacao circular sem criterio de retorno.
- Acoplar decisao de rota em multiplos componentes.
- Ignorar restauracao de sessao no startup.

## Quando pedir mais contexto

- regras de onboarding obrigatorio/opcional
- politicas de sessao e expiracao
- papeis/perfis e rotas permitidas
- comportamento esperado em deep links

## Limites desta skill

- cobre arquitetura de navegacao e app shell
- nao cobre UI detalhada de cada tela
- nao cobre contratos de API por endpoint

## Exemplo rapido (entrada -> saida)

Entrada: "Definir shell com onboarding, login e tabs principais."

Saida esperada:
- arvore de rotas base com guards
- criterio de redirecionamento por sessao
- estrutura de modulos/features principais
- checklist de fluxo de navegacao ponta a ponta

## Recursos adicionais

- Para template de rotas e guardas, ler `reference.md`.
