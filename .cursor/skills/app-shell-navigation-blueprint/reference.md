# App Shell Navigation Blueprint Reference

## Blocos de rota sugeridos

- `onboarding/*`
- `auth/*`
- `app/tabs/*`
- `settings/*`
- `fallback/not-found`

## Checklist de navegacao

1. cold start sem sessao -> onboarding/auth
2. cold start com sessao valida -> app
3. sessao expirada -> redireciona auth
4. logout limpa estado sensivel
5. retorno de detalhe preserva contexto da lista
