# Mobile Guidelines

## Princípios

- App híbrido com experiência próxima de nativo.
- UI consistente com Ionic.
- Camada de integração desacoplada do componente visual.
- Preparado para diferentes domínios de negócio e rotinas operacionais.

## Estrutura sugerida

```text
src/app/
  core/
    api/
    auth/
    guards/
    interceptors/
    models/
    services/
  features/
    feature-a/
    feature-b/
    feature-c/
    dashboard/
  shared/
    components/
    pipes/
    directives/
    utils/
```

## Padrões

- `core/` para infraestrutura transversal
- `features/` por domínio de negócio
- `shared/` para reutilização
- services sem lógica de UI
- pages enxutas
- componentes reaproveitáveis

## Backend Laravel

- trabalhar com DTOs/interfaces
- mapear payloads explicitamente
- evitar acoplamento direto do componente à resposta bruta da API
- tratar paginação, filtros, autenticação e erros de domínio

## Capacitor

- encapsular plugins em adapters/services
- tratar permissões
- tratar diferenças web/native
- usar `NgZone` quando eventos nativos não refletirem na UI

