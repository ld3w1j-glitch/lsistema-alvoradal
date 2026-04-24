# Correção de permissão — Criar pedidos e Lotes

Esta versão corrige o acesso de usuários comuns às áreas **Criar pedidos** e **Lotes**.

## O que foi alterado

- Removido bloqueio que exigia `admin` para acessar `/separacoes/nova`.
- Removido bloqueio que exigia `admin` para acessar `/lotes`.
- Removido bloqueio que exigia `admin` para acessar `/lotes/<codigo>/grade`.
- O acesso agora respeita as permissões do usuário configuradas no painel de usuários.
- Usuários operacionais comuns dos tipos `separador`, `conferente`, `estoque` e `gerente` passam a receber acesso a `pedidos` e `lotes` quando o sistema inicializa/migra permissões.
- Botões de Novo lote / Montar pedido agora aparecem com base em `user_has_access`, não apenas por `role == admin`.

## O que continua protegido

- Ações críticas de admin continuam restritas por suas rotas específicas.
- Estoque, auditoria, código fonte, usuários e configurações continuam dependendo das permissões próprias.

## Arquivos principais alterados

- `controle_separacao/core.py`
- `templates/separacoes.html`
- `templates/lotes.html`
