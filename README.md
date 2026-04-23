# Ionic/Capacitor/Angular Skills Starter

Base de projeto com skills voltadas ao desenvolvimento de apps Ionic + Capacitor + Angular integrados a uma API Laravel.

## Objetivo

Este repositório não é o app final. Ele é a base de trabalho para uso com agentes de IA:

- governança do agente
- skills especializadas
- convenções de arquitetura
- padrões de integração com API Laravel
- padrões de mobile híbrido com Ionic/Capacitor

## Estrutura

- `AGENTS.md`: governança global do agente
- `.cursor/skills/*/SKILL.md`: skills especializadas
- `.cursor/skills/*/reference.md`: referências detalhadas por skill
- `docs/mobile-guidelines.md`: diretrizes do projeto

## Skills disponíveis

### Base atual

- `api-data-access-laravel-backend`: integração HTTP com Laravel (DTOs, services, interceptors, auth e erros).
- `capacitor-native-integration`: plugins nativos, permissões, lifecycle e fallback web.
- `ionic-angular-architecture`: organização por feature, pages/components/services e rotas.
- `state-and-offline-mobile`: estado local, cache, fila offline e sincronização.
- `testing-and-release-readiness`: checklist de testes, riscos e gate de release.

### Prioritárias para telas

- `design-system-and-ui-consistency`: consistência visual e componente base alinhado ao design.
- `forms-validation-and-input-masks`: formulários com validação robusta, máscaras e UX de erro.
- `list-detail-search-and-filters`: fluxos de listagem/detalhe com busca, filtros e paginação.
- `accessibility-and-i18n-mobile`: acessibilidade e internacionalização para UX inclusiva e multilíngue.
- `mobile-performance-and-rendering`: performance de renderização, listas e carregamento visual.
- `security-and-sensitive-data-mobile`: proteção de sessão e dados sensíveis no app mobile.

### Estruturação de app completo

- `figma-to-feature-mapping`: converte telas em backlog técnico por feature, rota, estado e critério de aceite.
- `code-generation-contract`: define formato mínimo obrigatório de saída para gerar código consistente.
- `app-shell-navigation-blueprint`: define app shell, áreas autenticadas/públicas, guards e fluxo principal.
- `screen-state-matrix`: força cobertura de estados de tela e transições.
- `design-tokens-pipeline`: padroniza tokens visuais e aplicação no tema/componentes.
- `feature-delivery-orchestrator`: orquestra o fluxo completo de entrega da feature, do design ao gate de release.

## Quando usar cada skill

- **API Laravel**: sempre que houver endpoint, contrato de dados ou autenticação HTTP.
- **Capacitor Nativo**: quando tocar câmera, arquivos, notificações, biometria ou permissões.
- **Arquitetura Ionic Angular**: ao criar/refatorar feature, rotas e estrutura de pastas.
- **Estado/Offline**: em conectividade instável, cache e sincronização posterior.
- **Testing/Release**: no fechamento de feature e antes de merge/release.
- **Design System/UI**: ao implementar telas baseadas em Figma ou corrigir inconsistência visual.
- **Forms/Validação**: em qualquer fluxo de entrada de dados do usuário.
- **List/Detail/Filtros**: em catálogo, histórico, consulta e navegação lista -> detalhe.
- **Figma Mapping**: ao iniciar desenvolvimento a partir de design e transformar frames em backlog técnico.
- **Contrato de Geração**: para garantir entregas completas e consistentes em qualquer tarefa de código.
- **App Shell/Navegação**: ao estruturar fluxo base de onboarding, auth, tabs e settings.
- **Matriz de Estados**: para não deixar lacunas de UX em loading/empty/error/offline/unauthorized.
- **Pipeline de Tokens**: ao alinhar tema visual e reduzir estilos hardcoded.
- **Orquestrador de Entrega**: quando precisar coordenar todas as skills em sequência para entrega ponta a ponta.
- **Acessibilidade e i18n**: para validar inclusão, semântica e suporte a idiomas.
- **Performance Mobile**: para otimizar fluidez, scroll e tempo de resposta em telas críticas.
- **Segurança de Dados**: para tratar sessão, armazenamento e proteção de dados sensíveis.

## Como usar

1. Abra esta pasta no seu ambiente de desenvolvimento.
2. Mantenha o `AGENTS.md` na raiz.
3. Mantenha as skills em `.cursor/skills/`.
4. Peça tarefas ao agente citando claramente o contexto do módulo.
5. Para geração de código, informe sempre:
   - objetivo da tela ou fluxo
   - endpoint/API envolvida
   - regra de negócio
   - perfil do usuário
   - impacto offline/online

## Fluxo recomendado

1. Definir módulo
2. Definir contrato com backend Laravel
3. Gerar page/component/service/store
4. Validar integração Capacitor
5. Validar UX Ionic
6. Revisar testes e build

