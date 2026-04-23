# Forms Validation and Input Masks Reference

## Matriz minima de validacao

- Obrigatorio: mensagem simples e direta
- Formato invalido: explicar formato esperado
- Tamanho minimo/maximo: informar limite
- Erro remoto (`422`): mapear para campo ou erro global

## Padrao de mensagens

- curto, objetivo, sem termo tecnico
- uma mensagem por campo por vez
- priorizar erro mais critico primeiro

## Checklist de submit

1. botao desabilitado quando invalido
2. loading durante envio
3. evitar duplo envio
4. sucesso com feedback claro
5. falha com possibilidade de correcao/reenvio
