# Ionic Angular Architecture Reference

## Estrutura sugerida por feature

`features/<feature-name>/`

- `pages/`
- `components/`
- `services/`
- `models/`
- `<feature-name>.routes.ts`

## Responsabilidades

- `page`: orquestra UI e eventos de tela
- `component`: bloco reutilizável de interface
- `service/facade`: regra de negócio e integração
- `model`: contratos de dados da feature

## Checklist rápido de arquitetura

- page sem regra de negócio complexa
- rotas com lazy loading quando aplicável
- estado de loading/erro/vazio mapeado
- acoplamento mínimo entre feature e API bruta
