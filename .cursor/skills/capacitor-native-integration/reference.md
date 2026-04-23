# Capacitor Native Integration Reference

## Sequência padrão de integração

1. Verificar disponibilidade do plugin/plataforma.
2. Checar permissão atual.
3. Solicitar permissão quando necessário.
4. Executar ação nativa.
5. Tratar erro e fallback web.

## Estados de permissão sugeridos

- `granted`
- `denied`
- `prompt`
- `limited` (quando aplicável)

## Checklist mínimo por plataforma

- Android: permissão inicial, recusa, recusa permanente
- iOS: permissão inicial, recusa, retorno de background
- Web: fallback funcional ou mensagem explícita de indisponibilidade
