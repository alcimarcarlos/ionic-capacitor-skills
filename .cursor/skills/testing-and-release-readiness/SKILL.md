---
name: testing-and-release-readiness
description: Valida prontidão técnica de feature mobile para merge/release com checklist de build, testes, riscos e compatibilidade Android/iOS/web. Use no fechamento de feature, revisão final de PR ou preparação de release.
---

# testing-and-release-readiness

## Objetivo

Garantir que a entrega esteja pronta para validação técnica e operacional.

## Aplicar quando

- finalizar feature
- revisar PR
- validar release
- checar impacto mobile

## Requisitos obrigatórios

- Validar cobertura de estados de tela definida pela `screen-state-matrix`.
- Validar fluxos críticos ponta a ponta (login, navegação principal, ação de negócio-chave).
- Verificar compatibilidade web e dispositivo quando houver plugin nativo.
- Identificar riscos de build/configuração/permissões.
- Entregar checklist objetivo para gate de release.
- Consolidar riscos de acessibilidade, performance e segurança quando aplicável.

## Fluxo recomendado

1. Revisar mudanças por risco (dados, UI, nativo, autenticação, estado).
2. Definir suite mínima: unit, integração e smoke manual.
3. Executar validações de build e dependências.
4. Validar comportamento em Android/iOS (ou declarar limitações).
5. Consolidar riscos, impacto e critérios de aprovação.

## Checklist base de validação

- `ionic build` concluído sem erro.
- Rotas e guards principais funcionando nos fluxos críticos.
- chamadas de API cobrem sucesso, timeout e erro de validação (`422`).
- permissões nativas (quando aplicável) cobrem aceite, recusa e recusa permanente.
- sem regressão visual crítica em Android, iOS e web (quando suportado).

## Anti-padrões (não fazer)

- Declarar "pronto para release" sem checklist explícito.
- Ignorar cenário de falha de rede/timeout.
- Validar apenas em web quando há funcionalidade nativa.
- Não registrar riscos conhecidos e plano de mitigação.

## Formato de entrega esperado

1. Checklist técnico preenchido.
2. Riscos e severidade.
3. Testes executados/sugeridos.
4. Observações de build/release (Android, iOS, web).

## Quando pedir mais contexto

- plataformas alvo para release (Android/iOS/web)
- quais fluxos são considerados críticos para o negócio
- requisitos mínimos de cobertura de teste
- tipo de distribuição (interna, beta, loja)
- restrições de prazo que afetam escopo de validação

## Limites desta skill

- cobre validação final e readiness de entrega
- não define arquitetura da feature (usar `ionic-angular-architecture`)
- não substitui especificação de integração API/plugin (usar skills específicas)
- não substitui análise dedicada de performance, acessibilidade ou segurança

## Exemplo rápido (entrada -> saída)

Entrada: "Feature de login pronta, validar antes do merge."

Saída esperada:
- checklist preenchido com comandos e evidências
- riscos classificados (alto/médio/baixo) com impacto
- lacunas de teste e recomendação objetiva de go/no-go

## Recursos adicionais

- Para matriz de validação e gates de release, ler `reference.md`.

