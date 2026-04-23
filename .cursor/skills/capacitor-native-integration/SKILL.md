---
name: capacitor-native-integration
description: Implementa integrações nativas com Capacitor de forma segura e multiplataforma, cobrindo plugins, permissões, lifecycle e fallback web. Use quando houver câmera, arquivos, notificações, biometria, network ou qualquer API nativa.
---

# capacitor-native-integration

## Objetivo

Garantir integração nativa organizada, resiliente e compatível entre web, Android e iOS.

## Aplicar quando

- usar plugin Capacitor
- lidar com permissões
- criar bridge nativa
- tratar eventos de lifecycle
- sincronizar comportamento web/mobile

## Requisitos obrigatórios

- Isolar cada plugin em service/adapter dedicado.
- Definir interface de domínio para reduzir acoplamento com API do plugin.
- Tratar permissões de forma explícita (pré-check, request e recusa).
- Incluir fallback para web quando a funcionalidade permitir.
- Considerar `NgZone` ao atualizar UI a partir de callback nativo.
- Tratar ciclo de vida (`App.addListener`) quando o fluxo depender de foreground/background.

## Fluxo recomendado

1. Validar plugin e versões compatíveis com plataforma alvo.
2. Definir adapter com métodos de alto nível para o domínio.
3. Implementar guardas de plataforma (`Capacitor.isNativePlatform()`).
4. Implementar fluxo de permissão com estados claros.
5. Tratar exceções nativas e converter para erros de domínio.
6. Validar comportamento em web + Android + iOS.

## Anti-padrões (não fazer)

- Chamar plugin direto no componente de tela.
- Assumir que plugin disponível na web sem fallback.
- Ignorar estado de permissão negada/permanente.
- Atualizar estado de UI sem considerar contexto de zona Angular.

## Formato de entrega esperado

1. Adapter/service nativo com interface de uso.
2. Fluxo de permissão e fallback web.
3. Observações por plataforma (Android/iOS/web).
4. Checklist de validação manual em dispositivo.

## Quando pedir mais contexto

- plugin exato e versão alvo
- plataformas alvo (Android, iOS, web)
- comportamento esperado quando permissão é negada
- necessidade de operar offline/foreground/background
- requisitos de UX (mensagem, retry, bloqueio de ação)

## Limites desta skill

- cobre integração com APIs nativas e permissões
- não cobre modelagem de DTO/contratos HTTP (usar `api-data-access-laravel-backend`)
- não cobre estratégia ampla de estado/sync offline (usar `state-and-offline-mobile`)

## Exemplo rápido (entrada -> saída)

Entrada: "Integrar câmera com fallback web e tratar permissão negada."

Saída esperada:
- `camera.adapter.ts` com `takePhoto()` e `isAvailable()`
- fluxo explícito: check permission -> request -> denied/permanent denied
- fallback web com `<input type="file">` ou mensagem de indisponibilidade
- checklist Android/iOS/web validando sucesso, recusa e cancelamento

## Recursos adicionais

- Para guia de permissões e lifecycle, ler `reference.md`.

