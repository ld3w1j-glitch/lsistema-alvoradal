# Correção — Remover importação ERP

Esta versão corrige o erro:

`werkzeug.routing.exceptions.BuildError: Could not build url for endpoint 'remover_importacao_erp_confirmar'`

## O que foi corrigido

- Criada a rota GET `/estoque/importar-erp/<id>/remover` com endpoint `remover_importacao_erp_confirmar`.
- Criada a rota POST `/estoque/importar-erp/<id>/remover` com endpoint `remover_importacao_erp`.
- Mantida a confirmação com senha do admin.
- Mantido backup automático antes de remover.
- Mantido registro na auditoria.
- Adicionado botão Remover também na lista de importações recentes.

## Observação

Remover uma importação ERP remove apenas o histórico da importação e os itens da prévia. Se a importação já foi aplicada, o estoque não é desfeito automaticamente.
