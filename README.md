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
| `accessibility-and-i18n-mobile` | Mobile accessibility and i18n in Ionic Angular: contrast, focus, ARIA, translations. Trigger on inclusive UX. |
| `api-data-access-laravel-backend` | Ionic/Angular integration with Laravel APIs: HTTP services, DTOs, interceptors, auth. Trigger on backend consumption. |
| `app-shell-navigation-blueprint` | Ionic Angular navigation blueprint: app shell, auth flows, guards, tab routing. Trigger on app routing. |
| `capacitor-native-integration` | Capacitor native integration: plugins, permissions, lifecycle, web fallbacks. Trigger on camera, storage, native APIs. |
| `code-generation-contract` | Mandatory output contract for Ionic Angular: file tree, contracts, screen states, tests. Trigger on screen generation. |
| `design-system-and-ui-consistency` | Ionic Angular design consistency: tokens, base components, typography, layout states. Trigger on UI refactoring. |
| `design-tokens-pipeline` | Design token pipeline for Ionic Angular: colors, spacing, CSS variables, Figma alignment. Trigger on styling/theming. |
| `feature-delivery-orchestrator` | Orchestrates mobile feature delivery from Figma to release across skills and gates. Trigger on complete feature flows. |
| `figma-to-feature-mapping` | Converts Figma screens into Ionic Angular technical backlog: routes, components, acceptance criteria. Trigger on design intake. |
| `forms-validation-and-input-masks` | Mobile forms in Ionic Angular: reactive forms, masks, validation, error UX. Trigger on form input screens. |
| `ionic-angular-architecture` | Ionic Angular architecture: feature modules, lean pages, domain services, clean routes. Trigger on component/feature architecture. |
| `ionic-systematic-debugging` | Ionic/Capacitor systematic debugging: minimal test reproducers, bridge isolation. Trigger when diagnosing mobile bugs. |
| `list-detail-search-and-filters` | List and detail flows in Ionic Angular: search, filters, pagination, virtual scroll. Trigger on catalog and list screens. |
| `mobile-performance-and-rendering` | Mobile rendering performance: virtual scroll, image optimization, change detection, trackBy. Trigger on performance fixes. |
| `screen-state-matrix` | Mandatory screen state matrix for Ionic: loading, success, empty, error, offline. Trigger when building screen states. |
| `security-and-sensitive-data-mobile` | Mobile security in Ionic/Capacitor: secure storage, session cleanup, biometrics, tokens. Trigger on sensitive data/auth. |
| `state-and-offline-mobile` | Mobile offline state & sync: local cache, network resilience, offline queue, conflict handling. Trigger on offline capabilities. |
| `testing-and-release-readiness` | Mobile release readiness: unit/E2E tests, build checks, iOS/Android compatibility checklist. Trigger before merge/release. |

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
