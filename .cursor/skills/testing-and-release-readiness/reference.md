# Testing and Release Readiness Reference

## Gate de aprovação sugerido

- Build: `ionic build` concluído
- Qualidade: lint/testes essenciais sem falha
- Fluxos críticos: smoke test manual aprovado
- Plataforma: validação mínima Android/iOS quando houver nativo

## Matriz de risco

- **Alto**: quebra de login, pagamento, perda de dados
- **Médio**: regressão de fluxo secundário, bug com workaround
- **Baixo**: detalhe visual sem impacto funcional

## Formato de conclusão

1. Status do gate (`go` ou `no-go`)
2. Evidências executadas
3. Riscos remanescentes
4. Próximas ações antes de release
