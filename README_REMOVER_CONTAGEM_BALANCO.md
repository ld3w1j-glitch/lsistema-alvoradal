# Remover contagem de estoque

Foi adicionado um botão **Remover** na lista de contagens de estoque.

## Regras

- Apenas usuário admin pode remover contagens.
- A remoção exige confirmação da senha do admin.
- O sistema remove os itens da contagem e a contagem principal.
- A ação é registrada na auditoria como `remover_balanco_estoque`.

## Observação importante

Se a contagem já tiver sido confirmada, remover o registro da contagem **não desfaz automaticamente o estoque**. Para desfazer estoque confirmado, deve ser feito um ajuste/estorno específico, para não gerar alteração invisível no saldo.
