# Ionic/Capacitor/Angular Skills Starter

## PT_BR

Base de projeto com skills focadas no desenvolvimento de apps Ionic + Capacitor + Angular integrados com API Laravel.

### Objetivo

Este repositório nao e o app final. Ele e a base de trabalho para uso com agentes de IA:

- governanca do agente
- skills especializadas
- convencoes de arquitetura
- padroes de integracao com API Laravel
- padroes mobile hibridos com Ionic/Capacitor

### Estrutura

- `AGENTS.md`: governanca global do agente
- `.cursor/skills/*/SKILL.md`: skills especializadas
- `.cursor/skills/*/reference.md`: referencias detalhadas por skill
- `docs/mobile-guidelines.md`: diretrizes do projeto

### Compatibilidade (Claude, Cursor e Codex)

- Este pacote foi escrito para uso multiagente.
- `AGENTS.md` contem regras gerais de comportamento e formato de entrega.
- Os arquivos `.cursor/skills/*/SKILL.md` podem ser usados:
  - diretamente no Cursor (skills nativas), ou
  - como playbooks manuais no Claude/Codex (copiando o conteudo relevante para o prompt).
- Ao usar Claude/Codex, priorize:
  1. `AGENTS.md`
  2. a skill especifica do tema
  3. `feature-delivery-orchestrator` para fluxo ponta a ponta

### Skills Disponiveis

#### Base Atual

- `api-data-access-laravel-backend`: integracao HTTP com Laravel (DTOs, services, interceptors, auth e erros).
- `capacitor-native-integration`: plugins nativos, permissoes, ciclo de vida e fallback web.
- `ionic-angular-architecture`: organizacao por feature, pages/components/services e rotas.
- `state-and-offline-mobile`: estado local, cache, fila offline e sincronizacao.
- `testing-and-release-readiness`: testes, riscos e checklist de release gate.

#### Skills Prioritarias para Telas

- `design-system-and-ui-consistency`: consistencia visual e componentes base alinhados ao design.
- `forms-validation-and-input-masks`: formularios com validacao robusta, mascaras e UX de erro.
- `list-detail-search-and-filters`: fluxos lista/detalhe com busca, filtros e paginacao.
- `accessibility-and-i18n-mobile`: acessibilidade e internacionalizacao para UX inclusiva e multilingue.
- `mobile-performance-and-rendering`: performance de renderizacao, listas e carregamento visual.
- `security-and-sensitive-data-mobile`: protecao de sessao e tratamento de dados sensiveis no app mobile.

#### Estruturacao Completa do App

- `figma-to-feature-mapping`: converte telas em backlog tecnico por feature, rota, estado e criterio de aceite.
- `code-generation-contract`: define formato minimo obrigatorio de saida para geracao consistente de codigo.
- `app-shell-navigation-blueprint`: define app shell, areas autenticadas/publicas, guards e fluxo principal.
- `screen-state-matrix`: garante cobertura de estados e transicoes de tela.
- `design-tokens-pipeline`: padroniza tokens visuais e aplicacao em tema/componentes.
- `feature-delivery-orchestrator`: orquestra o fluxo completo de entrega de feature, do design ao release gate.

### Quando Usar Cada Skill

- **Laravel API**: sempre que houver endpoint, contrato de dados ou autenticacao HTTP.
- **Capacitor Native**: ao tocar camera, arquivos, notificacoes, biometria ou permissoes.
- **Ionic Angular Architecture**: ao criar/refatorar feature, rotas ou estrutura de pastas.
- **State/Offline**: em conectividade instavel, cache e sincronizacao posterior.
- **Testing/Release**: ao fechar feature e antes de merge/release.
- **Design System/UI**: ao implementar telas baseadas em Figma ou corrigir inconsistencia visual.
- **Forms/Validation**: em qualquer fluxo de entrada de dados do usuario.
- **List/Detail/Filters**: em catalogo, historico, consulta e navegacao lista -> detalhe.
- **Figma Mapping**: ao iniciar desenvolvimento a partir de design e transformar frames em backlog tecnico.
- **Generation Contract**: para garantir entregas completas e consistentes em qualquer tarefa de codigo.
- **App Shell/Navigation**: ao estruturar fluxo base de onboarding, auth, tabs e configuracoes.
- **State Matrix**: para evitar lacunas de UX em loading/vazio/erro/offline/unauthorized.
- **Tokens Pipeline**: ao alinhar tema visual e reduzir estilos hardcoded.
- **Delivery Orchestrator**: quando todas as skills devem ser coordenadas em sequencia para entrega ponta a ponta.
- **Accessibility and i18n**: para validar inclusao, semantica e suporte a idiomas.
- **Mobile Performance**: para otimizar fluidez, scroll e tempo de resposta em telas criticas.
- **Data Security**: para tratar sessao, armazenamento e protecao de dados sensiveis.

### Como Usar

1. Abra esta pasta no seu ambiente de desenvolvimento.
2. Mantenha `AGENTS.md` na raiz.
3. Mantenha as skills em `.cursor/skills/` (ou replique a mesma estrutura em outra pasta se seu agente nao usa skills nativas do Cursor).
4. Solicite tarefas ao agente citando claramente o contexto do modulo.
5. Para geracao de codigo, informe sempre:
   - objetivo da tela ou fluxo
   - endpoint/API envolvido
   - regra de negocio
   - perfil de usuario
   - impacto offline/online

### Fluxo Recomendado

1. Definir modulo
2. Definir contrato com backend Laravel
3. Gerar page/component/service/store
4. Validar integracao Capacitor
5. Validar UX Ionic
6. Revisar testes e build

### Exemplo de Uso no Claude/Codex

Prompt sugerido:

```text
Siga o arquivo AGENTS.md deste projeto e use como base as skills:
- feature-delivery-orchestrator
- ionic-angular-architecture
- api-data-access-laravel-backend

Tarefa:
<descreva aqui a feature>
```

---

## EN

Project base with skills focused on developing Ionic + Capacitor + Angular apps integrated with a Laravel API.

### Objective

This repository is not the final app. It is the working base for use with AI agents:

- agent governance
- specialized skills
- architecture conventions
- Laravel API integration patterns
- hybrid mobile patterns with Ionic/Capacitor

### Structure

- `AGENTS.md`: global agent governance
- `.cursor/skills/*/SKILL.md`: specialized skills
- `.cursor/skills/*/reference.md`: detailed references by skill
- `docs/mobile-guidelines.md`: project guidelines

### Compatibility (Claude, Cursor, and Codex)

- This package was written for multi-agent use.
- `AGENTS.md` contains general behavior rules and the delivery format.
- `.cursor/skills/*/SKILL.md` files can be used:
  - directly in Cursor (native skills), or
  - as manual playbooks in Claude/Codex (by copying the relevant content into the prompt).
- When using Claude/Codex, prioritize:
  1. `AGENTS.md`
  2. the topic-specific skill
  3. `feature-delivery-orchestrator` for end-to-end flow

### Available Skills

#### Current Base

- `api-data-access-laravel-backend`: HTTP integration with Laravel (DTOs, services, interceptors, auth, and errors).
- `capacitor-native-integration`: native plugins, permissions, lifecycle, and web fallback.
- `ionic-angular-architecture`: organization by feature, pages/components/services, and routes.
- `state-and-offline-mobile`: local state, cache, offline queue, and synchronization.
- `testing-and-release-readiness`: tests, risks, and release gate checklist.

#### Priority Skills for Screens

- `design-system-and-ui-consistency`: visual consistency and base components aligned with the design.
- `forms-validation-and-input-masks`: forms with robust validation, masks, and error UX.
- `list-detail-search-and-filters`: list/detail flows with search, filters, and pagination.
- `accessibility-and-i18n-mobile`: accessibility and internationalization for inclusive, multilingual UX.
- `mobile-performance-and-rendering`: rendering performance, lists, and visual loading.
- `security-and-sensitive-data-mobile`: session protection and sensitive data handling in the mobile app.

#### Full App Structuring

- `figma-to-feature-mapping`: converts screens into a technical backlog by feature, route, state, and acceptance criterion.
- `code-generation-contract`: defines the mandatory minimum output format for consistent code generation.
- `app-shell-navigation-blueprint`: defines the app shell, authenticated/public areas, guards, and main flow.
- `screen-state-matrix`: enforces coverage of screen states and transitions.
- `design-tokens-pipeline`: standardizes visual tokens and their application in theme/components.
- `feature-delivery-orchestrator`: orchestrates the complete feature delivery flow, from design to release gate.

### When to Use Each Skill

- **Laravel API**: whenever there is an endpoint, data contract, or HTTP authentication.
- **Capacitor Native**: when touching camera, files, notifications, biometrics, or permissions.
- **Ionic Angular Architecture**: when creating/refactoring a feature, routes, or folder structure.
- **State/Offline**: in unstable connectivity, cache, and later synchronization.
- **Testing/Release**: when closing a feature and before merge/release.
- **Design System/UI**: when implementing Figma-based screens or fixing visual inconsistency.
- **Forms/Validation**: in any user data input flow.
- **List/Detail/Filters**: in catalog, history, query, and list -> detail navigation.
- **Figma Mapping**: when starting development from a design and turning frames into a technical backlog.
- **Generation Contract**: to ensure complete and consistent deliveries in any code task.
- **App Shell/Navigation**: when structuring the base flow for onboarding, auth, tabs, and settings.
- **State Matrix**: to avoid UX gaps in loading/empty/error/offline/unauthorized.
- **Tokens Pipeline**: when aligning the visual theme and reducing hardcoded styles.
- **Delivery Orchestrator**: when all skills must be coordinated in sequence for end-to-end delivery.
- **Accessibility and i18n**: to validate inclusion, semantics, and language support.
- **Mobile Performance**: to optimize smoothness, scroll, and response time on critical screens.
- **Data Security**: to handle session, storage, and sensitive data protection.

### How to Use

1. Open this folder in your development environment.
2. Keep `AGENTS.md` at the root.
3. Keep skills in `.cursor/skills/` (or replicate the same structure in another folder if your agent does not use native Cursor skills).
4. Ask the agent for tasks while clearly citing the module context.
5. For code generation, always provide:
   - objective of the screen or flow
   - involved endpoint/API
   - business rule
   - user role
   - offline/online impact

### Recommended Flow

1. Define module
2. Define contract with Laravel backend
3. Generate page/component/service/store
4. Validate Capacitor integration
5. Validate Ionic UX
6. Review tests and build

### Usage Example in Claude/Codex

Suggested prompt:

```text
Follow this project's AGENTS.md file and use these skills as a base:
- feature-delivery-orchestrator
- ionic-angular-architecture
- api-data-access-laravel-backend

Task:
<describe the feature here>
```
