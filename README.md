# Ionic Capacitor Angular Skills

## Objetivo

Skills para apps Ionic + Capacitor + Angular integrados a APIs Laravel, cobrindo arquitetura, UX mobile, dados, offline, plugins nativos, segurança, acessibilidade, performance e release readiness.

Este pacote não é uma aplicação final. Ele é uma coleção portátil de instruções para agentes de código trabalharem em projetos reais com padrões consistentes.

## Compatibilidade

| Agente | Entrada recomendada |
| --- | --- |
| Cursor | `.cursor/rules/skills.mdc` e aliases em `.cursor/skills/<skill-name>` |
| Codex | `skills/<skill-name>/SKILL.md` ou cópia/symlink em `$CODEX_HOME/skills` |
| Claude Code | `CLAUDE.md`, depois `skills/<skill-name>/SKILL.md` |
| GitHub Copilot | `.github/copilot-instructions.md`, apontando para `AGENTS.md` e `skills/` |

## Estrutura

- `AGENTS.md`: instruções operacionais para agentes.
- `CLAUDE.md`: ponto de entrada curto para Claude Code.
- `.cursor/rules/skills.mdc`: regra de descoberta para Cursor.
- `.cursor/skills/<skill-name>`: symlink para `skills/<skill-name>`.
- `.github/copilot-instructions.md`: instruções curtas para GitHub Copilot.
- `skills/<skill-name>/SKILL.md`: fonte canônica da skill.
- `skills/<skill-name>/reference.md`: detalhes carregados somente quando a skill pedir.

## Stack Coberta

- Ionic
- Capacitor
- Angular
- TypeScript
- Laravel API

## Como Escolher Skills

1. Leia `AGENTS.md` para as regras gerais da coleção.
2. Escolha a menor skill que cobre a tarefa.
3. Use `feature-delivery-orchestrator` como baseline quando a tarefa cruzar vários temas.
4. Leia `reference.md` apenas quando a skill ou a complexidade da tarefa pedir.
5. Valide com os comandos disponíveis no projeto alvo.

## Skills Disponíveis

| Skill | Quando usar |
| --- | --- |
| `accessibility-and-i18n-mobile` | Ensures accessibility and internationalization in Ionic Angular apps, covering contrast, focus, semantics, screen readers, and localized text. Use when implementing or reviewing screens for inclusive UX quality and multilingual support. |
| `api-data-access-laravel-backend` | Standardizes Ionic/Angular integration with Laravel APIs, including HTTP services, DTOs, interceptors, authentication, and error handling. Use when consuming endpoints, request/response contracts, pagination, filters, or auth flows in the Laravel backend. |
| `app-shell-navigation-blueprint` | Defines the base Ionic Angular app structure with shell, onboarding/auth/main/settings flows, guards, and consistent navigation. Use when starting a new app or reorganizing main navigation. |
| `capacitor-native-integration` | Implements native integrations with Capacitor in a safe, cross-platform way, covering plugins, permissions, lifecycle, and web fallback. Use when there is camera, files, notifications, biometrics, network, or any native API. |
| `code-generation-contract` | Enforces a mandatory output contract for Ionic Angular code generation, ensuring architecture, integration, screen states, and validation consistency. Use when requesting implementation of any screen, flow, or feature. |
| `design-system-and-ui-consistency` | Defines and applies visual consistency in Ionic Angular apps with tokens, base components, and UI states. Use when implementing new screens, refactoring interfaces, aligning with Figma, or reducing layout divergence. |
| `design-tokens-pipeline` | Standardizes the design token pipeline for Ionic Angular, connecting design colors, typography, and spacing to app styles. Use when aligning UI with Figma, creating a theme, or reducing visual inconsistencies. |
| `feature-delivery-orchestrator` | Orchestrates end-to-end mobile feature delivery, from Figma to release, activating technical skills in the correct order and applying quality gates. Use when the goal is to implement a complete feature with architectural consistency and delivery readiness. |
| `figma-to-feature-mapping` | Converts Figma screens into a technical implementation backlog for Ionic Angular, including features, routes, components, states, and acceptance criteria. Use when starting development from a design or reviewing functional screen coverage. |
| `forms-validation-and-input-masks` | Implements mobile forms with robust validation, masks, and consistent error UX in Ionic Angular. Use when creating or refactoring signup, login, profile, filter screens, and any user data input. |
| `ionic-angular-architecture` | Organizes Ionic Angular architecture by feature with lean pages, reusable components, domain services, and predictable routes. Use when creating/refactoring screens, navigation, modules, or folder structure. |
| `list-detail-search-and-filters` | Structures list and detail flows with search, filters, sorting, and pagination in Ionic Angular. Use when implementing catalog, history, query screens, or any list-detail experience in the app. |
| `mobile-performance-and-rendering` | Optimizes rendering performance in Ionic Angular apps, covering lists, images, detection cycle, and progressive loading. Use when screens show slowness, jank, excessive consumption, or performance regression risk. |
| `screen-state-matrix` | Generates a mandatory state matrix per screen for Ionic Angular apps, covering loading, success, empty, error, unauthorized, and offline. Use when implementing or reviewing screens to avoid UX gaps and functional regressions. |
| `security-and-sensitive-data-mobile` | Defines security practices for sensitive data in Ionic Capacitor apps, covering secure storage, session, biometrics, and protection of information in transit and at rest. Use when there is authentication, tokens, personal data, or critical operations. |
| `state-and-offline-mobile` | Defines local state, cache, and offline/online synchronization strategy for mobile apps, focused on resilience and predictability. Use when there is unstable connectivity, offline queue, temporary persistence, or data reconciliation. |
| `testing-and-release-readiness` | Validates technical readiness of a mobile feature for merge/release with build, tests, risks, and Android/iOS/web compatibility checklist. Use when closing a feature, final PR review, or preparing a release. |

## Qualidade e Validação

Execute o menor conjunto relevante que existir no projeto alvo:

- `npm test`
- `npm run lint`
- `npm run build`
- `ionic build`
- `npx cap sync`
- `npx cap doctor`

## Notas de Uso

- Cubra estados loading, success, empty, error, unauthorized e offline quando aplicável.
- Isole integrações nativas em serviços/adapters com fallback web.
- Declare contratos de API e suposições quando o backend não estiver definido.

## Instalação por Symlink

Para Codex:

```bash
mkdir -p "$HOME/.codex/skills"
for d in skills/*; do
  name="$(basename "$d")"
  ln -sfn "$(pwd)/$d" "$HOME/.codex/skills/$name"
done
```

Para Claude Code:

```bash
mkdir -p "$HOME/.claude/skills"
for d in skills/*; do
  name="$(basename "$d")"
  ln -sfn "$(pwd)/$d" "$HOME/.claude/skills/$name"
done
```

Para Cursor em um projeto consumidor:

```bash
mkdir -p .cursor/skills
for d in skills/*; do
  name="$(basename "$d")"
  ln -sfn "../../skills/$name" ".cursor/skills/$name"
done
```

## Prompt Base

```text
Siga AGENTS.md, escolha a menor skill aplicável em skills/<nome>/SKILL.md e carregue reference.md somente se necessário.

Contexto:
- Stack: Ionic, Capacitor, Angular, TypeScript, Laravel API
- Objetivo: <descreva a tarefa>
- Restrições: <auth, dados, UX, performance, compatibilidade>
- Validação esperada: <testes/build/lint>
```
