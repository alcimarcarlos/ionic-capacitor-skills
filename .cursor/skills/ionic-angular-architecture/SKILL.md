---
name: ionic-angular-architecture
description: Organiza arquitetura Ionic Angular por feature com pages enxutas, components reutilizáveis, services de domínio e rotas previsíveis. Use quando criar/refatorar telas, navegação, módulos ou estrutura de pastas.
---

# ionic-angular-architecture

## Objetivo

Definir estrutura de app Ionic + Angular com boa separação de responsabilidades.

## Aplicar quando

- criar nova feature
- reorganizar páginas
- definir estrutura de pastas
- criar componentes reutilizáveis
- desenhar rotas e navegação

## Requisitos obrigatórios

- Organizar por feature (pasta da funcionalidade com page/components/services/models).
- Manter page components enxutos (orquestração + binding de UI).
- Isolar regras de negócio em services/facades/use-cases.
- Preferir componentes Ionic para estrutura visual e UX mobile.
- Separar model de API de model de apresentação.
- Definir rotas com lazy loading e guards quando necessário.

## Fluxo recomendado

1. Definir fronteiras da feature (dados, UI e navegação).
2. Propor árvore de arquivos com responsabilidade por camada.
3. Implementar page/container com mínimo de lógica.
4. Implementar components reutilizáveis e services de domínio.
5. Configurar rotas, guards e resolvers quando fizer sentido.
6. Validar estados de loading/erro/vazio/sucesso na tela.

## Anti-padrões (não fazer)

- Concentrar lógica de negócio dentro de page component.
- Reutilizar componente acoplado a endpoint específico.
- Misturar decisões de navegação com chamada HTTP em vários pontos.
- Criar estrutura por tipo técnico global quando a feature exige coesão local.

## Formato de entrega esperado

1. Objetivo e escopo da feature.
2. Árvore de arquivos proposta.
3. Responsabilidade de cada arquivo.
4. Código base (page/component/service/route).
5. Pontos de atenção de navegação, estado e evolução futura.

## Quando pedir mais contexto

- fluxo de navegação esperado (origem/destino/guards)
- responsabilidades da feature e limites com outras features
- regras de negócio principais da tela
- dependências externas (API, plugin nativo, storage)
- padrão existente no projeto (standalone, módulos, convenções)

## Limites desta skill

- cobre organização de UI, navegação e separação de responsabilidades
- não cobre detalhes profundos de integração nativa (usar `capacitor-native-integration`)
- não cobre especificação completa de contratos Laravel (usar `api-data-access-laravel-backend`)

## Exemplo rápido (entrada -> saída)

Entrada: "Criar feature de pedidos com lista e detalhe."

Saída esperada:
- árvore `features/orders/{pages,components,services,models}`
- `orders.page.ts` apenas orquestrando estado e eventos de UI
- `orders-facade.service.ts` com regras de negócio
- rotas com lazy loading para lista/detalhe e guard quando necessário

## Recursos adicionais

- Para templates de estrutura por feature, ler `reference.md`.

