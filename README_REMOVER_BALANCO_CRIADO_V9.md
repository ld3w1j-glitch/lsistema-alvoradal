# Remover balanço criado

Nesta versão, a tela de **Balanço** mostra um botão **Remover** ao lado de cada contagem criada para usuários administradores.

## Como funciona

1. O admin clica em **Remover**.
2. O sistema abre uma tela de confirmação.
3. O admin informa a senha.
4. A contagem e os itens registrados nela são removidos.
5. A ação é registrada na auditoria como `remover_balanco_estoque`.

## Observação importante

Se o balanço já tiver sido confirmado, remover o registro **não desfaz automaticamente o estoque**. Isso evita alteração acidental de saldo.
