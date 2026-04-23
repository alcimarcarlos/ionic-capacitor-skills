# Mobile Agent Governance

Você atua como agente técnico para apps mobile híbridos.

## Compatibilidade de agentes

Este guia é agnóstico de fornecedor e deve funcionar com Claude, Cursor e Codex.

- Trate instruções deste arquivo como prioridade de comportamento.
- Quando a plataforma não suportar "skills" nativamente, use os `SKILL.md` como playbooks manuais.
- Mantenha o formato de entrega padrão independentemente do agente.

## Stack-alvo

- Ionic
- Capacitor
- Angular
- TypeScript
- API Laravel
- autenticação por token/sessão conforme backend

## Regras gerais

- Responder em PT-BR.
- Gerar código e nomes técnicos em inglês quando fizer sentido técnico.
- Priorizar arquitetura clara, componentização e previsibilidade.
- Não inventar contratos de API. Quando não houver contrato explícito, pedir ou inferir com ressalvas.
- Não colocar regra de negócio complexa dentro de page components.
- Preferir separação por feature/module.
- Para integrações nativas, isolar acesso em services/adapters.
- Sempre considerar diferenças entre web, Android e iOS.
- Em fluxos de dados, priorizar DTOs/interfaces explícitas.
- Em telas Ionic, preferir componentes do ecossistema Ionic antes de HTML genérico.
- Não concluir entregas de tela sem cobrir estados: loading, success, empty, error.
- Quando faltar contrato de API, declarar suposição explicitamente e marcar ponto de validação.
- Em features com risco mobile, explicitar diferenças web, Android e iOS na resposta.
- Incluir teste mínimo por fluxo crítico antes de considerar a tarefa concluída.

## Forma de entrega padrão

Quando gerar uma solução, entregar nesta ordem:

1. Objetivo
2. Estrutura de arquivos
3. Código
4. Integração com API
5. Pontos de atenção mobile
6. Testes e validações
7. Suposições e pendências de validação

## Prompt base recomendado (multiagente)

Use este template ao iniciar tarefas em qualquer agente:

```text
Contexto:
- Stack: Ionic + Capacitor + Angular + TypeScript + API Laravel
- Objetivo da tarefa: <descreva>
- Tela/fluxo: <descreva>
- Regras de negócio: <descreva>
- Endpoint/payload: <descreva ou marque suposição>
- Perfil/permissão: <descreva>
- Impacto offline/online: <descreva>

Instruções de entrega:
- Seguir AGENTS.md e skills relevantes
- Entregar no formato: Objetivo, Estrutura de arquivos, Código, Integração com API, Pontos mobile, Testes, Suposições
```

## Regras específicas do contexto mobile

- Assuma integração com backend Laravel.
- Assuma necessidade frequente de autenticação, listagens, filtros.
- Preferir services para consumo de API.
- Preferir interceptors para autenticação, headers e tratamento comum de erro.
- Tratar estados de carregamento, erro, vazio e sucesso nas telas.
- Quando houver risco de operação offline/intermitente, considerar cache local e estratégia de sincronização.

## Quando pedir mais contexto

Pedir mais contexto quando faltar:

- endpoint
- payload
- regra de negócio
- perfis/permissões
- comportamento offline
- plugin nativo específico

