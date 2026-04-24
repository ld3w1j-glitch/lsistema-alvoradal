# Exclusão segura de auditoria

Esta versão adiciona uma função para o administrador excluir registros específicos da auditoria quando necessário.

## Como funciona

1. Acesse **Auditoria** no sistema.
2. Use os filtros para encontrar os registros desejados.
3. Marque os registros na tabela.
4. Informe o motivo da exclusão.
5. Digite a senha do admin.
6. Confirme a exclusão.

Antes de apagar, o sistema cria automaticamente um backup JSON em:

```text
backups/auditoria/
```

Depois da exclusão, o sistema registra uma nova entrada:

```text
AUDITORIA_REMOVIDA
```

Esse registro informa:

```text
- total de registros removidos
- motivo informado
- caminho do backup gerado
- usuário admin responsável
```

## Segurança

A exclusão exige:

```text
- usuário logado
- acesso ao módulo Auditoria
- permissão de admin
- senha do admin
```

A ideia é permitir limpeza controlada sem apagar tudo às cegas.
