# Correção: erro ao excluir usuário com histórico

Erro corrigido:

```text
sqlite3.IntegrityError: FOREIGN KEY constraint failed
Página: /usuarios/<id>/excluir
Área: excluir_usuario
```

## Causa

O usuário possuía registros ligados a ele no sistema, como auditoria, movimentações, separações, consultas MCP, balanços ou importações ERP. O SQLite protege esses registros com chave estrangeira, então apagar fisicamente o usuário quebraria o histórico.

## Ajuste feito

Agora, ao clicar em **Excluir**:

- Se o usuário não tiver nenhum vínculo, ele é excluído normalmente.
- Se o usuário já tiver histórico, ele é **desativado com segurança** em vez de ser apagado.
- O sistema mostra uma mensagem amigável informando os vínculos encontrados.
- A ação fica registrada na auditoria.
- O último admin ativo continua protegido.

Esse comportamento é mais seguro para uso real, porque preserva o histórico do sistema.
