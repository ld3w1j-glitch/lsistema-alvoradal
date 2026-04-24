# Sistema Alvorada — pronto para Railway

Este pacote já está preparado para subir no Railway como aplicação Flask.

## Arquivos importantes

- `app.py`: entrada principal da aplicação.
- `requirements.txt`: dependências Python.
- `Procfile`: comando de produção com Gunicorn.
- `railway.json`: configuração de build/deploy, healthcheck e start command.
- `runtime.txt`: versão do Python.
- `dados.db`: banco SQLite inicial com usuários, lojas e estoque.
- `stock_seed.json`: carga base de produtos.

## Como subir

1. Extraia este ZIP.
2. Envie a pasta extraída para um repositório no GitHub.
3. No Railway, crie um projeto novo e escolha **Deploy from GitHub repo**.
4. Depois do deploy, abra **Settings > Networking > Generate Domain** para gerar o link público.

## Login inicial

Usuário:

```txt
admin
```

Senha:

```txt
123456
```

Depois de entrar, troque a senha do admin na área de usuários/minha conta.

## Banco de dados

Por padrão, o sistema usa o `dados.db` que vai junto no projeto.

Para produção real, o ideal é adicionar um **Volume** no Railway. Quando existir `RAILWAY_VOLUME_MOUNT_PATH`, o sistema salva o banco dentro do volume. Se o volume estiver vazio, ele copia automaticamente o `dados.db` inicial para lá.

## Variáveis opcionais

Você pode configurar estas variáveis no Railway:

```txt
SECRET_KEY=uma-chave-grande-e-aleatoria
DEFAULT_ADMIN_USERNAME=admin
DEFAULT_ADMIN_PASSWORD=123456
DEFAULT_ADMIN_NAME=Administrador
```

`PORT` não precisa ser criado manualmente. O Railway já fornece essa variável para o serviço.

## MCP

O servidor MCP continua no projeto em:

```txt
controle_separacao/mcp_server.py
```

Para uso local com cliente MCP compatível:

```bash
python -m controle_separacao.mcp_server
```

No Railway, o deploy principal roda o site Flask. O MCP em modo `stdio` é melhor para uso local ou em cliente compatível configurado separadamente.

## Página MCP/IA de teste

Esta versão inclui a tela **MCP/IA** dentro do próprio site. Ela permite testar consultas do MCP em formato de conversa, sem precisar configurar um cliente externo.

Depois do deploy, entre como administrador e clique em **MCP/IA** no menu.

Observação: MCP em `stdio` é indicado para uso local com cliente MCP. Para conversar dentro do site/Railway, use a página **MCP/IA**, que chama as mesmas consultas em modo leitura.
