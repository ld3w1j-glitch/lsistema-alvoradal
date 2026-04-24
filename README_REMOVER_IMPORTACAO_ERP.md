# Remover importações recentes do ERP

Esta versão adiciona a opção de remover registros da lista **Importações recentes**.

## Funcionamento

- Apenas admin pode remover.
- A tela pede a senha do admin.
- Antes de remover, o sistema cria um backup em `backups/importacoes_erp/`.
- A ação é registrada na auditoria como `remover_importacao_erp`.

## Importante

Remover uma importação já aplicada não desfaz automaticamente o estoque. Isso foi feito para evitar alteração acidental de saldo.
