---
name: security-and-sensitive-data-mobile
description: Define praticas de seguranca para dados sensiveis em apps Ionic Capacitor, cobrindo armazenamento seguro, sessao, biometria e protecao de informacao em transito e em repouso. Use quando houver autenticacao, tokens, dados pessoais ou operacoes criticas.
---

# security-and-sensitive-data-mobile

## Objetivo

Reduzir risco de exposicao de dados e fortalecer controles de sessao no app mobile.

## Aplicar quando

- implementar login/sessao/token
- armazenar dados sensiveis localmente
- proteger operacoes criticas com biometria/pin
- revisar risco de seguranca antes de release

## Requisitos obrigatorios

- Nao armazenar segredo sensivel em storage inseguro.
- Centralizar estrategia de sessao e expiracao.
- Evitar log de dados sensiveis (token, documento, email completo).
- Definir politica de limpeza de sessao no logout.
- Proteger acao critica com camada adicional quando exigido.

## Fluxo recomendado

1. Classificar dados por nivel de sensibilidade.
2. Definir armazenamento e ciclo de vida por tipo de dado.
3. Implementar controle de sessao e renovacao segura.
4. Revisar logs, erros e traces para evitar vazamento.
5. Validar cenarios de risco e recuperacao.

## Anti-padroes (nao fazer)

- Persistir token em local de facil extracao sem justificativa.
- Exibir dado sensivel completo em tela/log.
- Manter sessao ativa sem controle de expiracao.
- Tratar falha de auth sem acao de revogacao/limpeza.

## Quando pedir mais contexto

- requisitos de compliance e politica interna
- nivel de sensibilidade dos dados
- estrategia de autenticacao (token, sessao, biometria)
- tempo de sessao e regras de renovacao

## Limites desta skill

- cobre seguranca de sessao e dados sensiveis no app
- nao cobre pentest ou seguranca de infraestrutura backend
- nao cobre UX detalhada de telas

## Exemplo rapido (entrada -> saida)

Entrada: "Revisar seguranca do fluxo de login e perfil."

Saida esperada:
- mapa de dados sensiveis e armazenamento
- ajustes de sessao/logout/expiracao
- revisao de logs e mascaramento
- checklist de riscos e mitigacao

## Recursos adicionais

- Para checklist de controles minimos, ler `reference.md`.
