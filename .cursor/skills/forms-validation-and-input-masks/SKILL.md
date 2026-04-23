---
name: forms-validation-and-input-masks
description: Implementa formularios mobile com validacao robusta, mascaras e UX de erro consistente em Ionic Angular. Use quando criar ou refatorar telas de cadastro, login, perfil, filtros e qualquer entrada de dados do usuario.
---

# forms-validation-and-input-masks

## Objetivo

Padronizar formularios com validacao, mascaras e feedback claro para reduzir erro de preenchimento e retrabalho.

## Aplicar quando

- criar formulario de cadastro/login/perfil
- validar campos obrigatorios e formatos
- aplicar mascara de telefone, documento, moeda ou data
- melhorar experiencia de submit e mensagens de erro

## Requisitos obrigatorios

- Usar `ReactiveForms` para formularios com regra de negocio.
- Validar no cliente com mensagens claras por campo.
- Tratar validacao de backend (`422`) com mapeamento para campos.
- Bloquear submit invalido e mostrar estado de envio.
- Aplicar mascara apenas quando agrega UX e nao quebra acessibilidade.

## Fluxo recomendado

1. Definir contrato dos campos (tipo, obrigatoriedade, formato).
2. Criar `FormGroup` com validators sincronos/assincronos.
3. Implementar mascaras e normalizacao de entrada.
4. Mapear erros locais e remotos para mensagens consistentes.
5. Validar fluxo completo: preencher, erro, correcao e submit.

## Anti-padroes (nao fazer)

- Validar somente no backend sem feedback imediato.
- Mostrar erro tecnico bruto para usuario final.
- Permitir multiplos submits em paralelo.
- Usar mascara que altera valor sem controle de parse.

## Quando pedir mais contexto

- campos obrigatorios e regras de cada campo
- formato esperado pelo backend (valor mascarado ou limpo)
- comportamento de erro por campo e erro global
- necessidade de validacao assincorna (ex.: email unico)

## Limites desta skill

- cobre UX de formulario, validacao e entrada de dados
- nao cobre navegacao entre telas (usar `ionic-angular-architecture`)
- nao cobre contratos HTTP completos (usar `api-data-access-laravel-backend`)

## Exemplo rapido (entrada -> saida)

Entrada: "Tela de cadastro com nome, telefone e email."

Saida esperada:
- `FormGroup` com validators (`required`, `email`, `minLength`)
- mascara de telefone com persistencia do valor limpo
- tratamento de `422` mapeando erro por campo
- botao submit com estado `loading` e bloqueio de duplo clique

## Recursos adicionais

- Para matriz de validacao e padrao de mensagens, ler `reference.md`.
