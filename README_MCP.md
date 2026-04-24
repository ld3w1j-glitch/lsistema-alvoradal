# Integração MCP - Sistema Alvorada

Este projeto agora possui um servidor MCP em modo leitura.

O objetivo é permitir que uma IA compatível com MCP consulte informações reais do Sistema Alvorada sem alterar o banco de dados.

## O que foi adicionado

Arquivos novos:

- `controle_separacao/mcp_server.py`
- `mcp_server.py`
- `mcp_config_exemplo.json`
- `README_MCP.md`

Dependência nova no `requirements.txt`:

- `mcp[cli]`

## Ferramentas MCP disponíveis

- `status_sistema` — mostra um resumo geral do sistema e o caminho do banco usado.
- `consultar_produto` — consulta produto por código interno ou código de barras.
- `listar_produtos_estoque` — lista produtos ativos do estoque, com filtro opcional por linha/categoria.
- `listar_estoque_baixo` — lista produtos com estoque abaixo do limite informado, com filtro opcional por linha/categoria.
- `listar_categorias_linha` — lista as linhas/categorias automáticas encontradas nas descrições dos produtos.
- `listar_lojas` — lista lojas cadastradas.
- `listar_lotes_abertos` — lista lotes/separações ainda não finalizados.
- `consultar_lote` — consulta um lote pelo código e retorna lojas, separações e itens.
- `listar_movimentacoes_estoque`
- `pesquisar_geral` — pesquisa produtos, lojas, lotes e movimentações pelo mesmo termo — mostra histórico recente de movimentações do estoque.

## Segurança

Esta primeira versão foi feita em modo leitura.

Ela não possui ferramenta para:

- adicionar produto;
- remover produto;
- alterar quantidade;
- apagar histórico;
- finalizar separação;
- alterar usuários.

Isso evita que uma IA conectada faça alterações acidentais no sistema.

## Como instalar as dependências

No terminal, dentro da pasta do projeto:

```bash
pip install -r requirements.txt
```

## Como testar o servidor MCP manualmente

Dentro da pasta do projeto:

```bash
python -m controle_separacao.mcp_server
```

Esse comando inicia o servidor MCP via `stdio`, que é o modo usado por muitos clientes MCP locais.

## Exemplo de configuração para cliente MCP

Use o arquivo `mcp_config_exemplo.json` como base.

Ajuste o caminho do banco:

```json
"DB_PATH": "C:\\CAMINHO\\DO\\SISTEMA\\dados.db"
```

Se você rodar o cliente MCP direto da pasta do sistema, pode remover o `DB_PATH`, porque o sistema já usa `dados.db` da própria pasta.

## Exemplos de perguntas para a IA

Depois de conectar o MCP no cliente compatível, você poderá perguntar:

- Quais produtos estão com estoque baixo?
- Consulte o produto de código 123.
- Mostre os lotes abertos.
- Analise o lote LT-XXXX e me diga o que falta separar.
- Mostre as últimas movimentações de estoque do produto 123.

## Observação

O site Flask continua rodando normalmente com:

```bash
python app.py
```

O MCP é uma entrada separada para IA consultar o mesmo banco do sistema.


## Exportação pela tela MCP/IA

A página **MCP/IA** do sistema agora possui botões para:

- imprimir o resultado;
- exportar a consulta em Excel `.xlsx`;
- exportar a consulta em PDF.

A exportação usa a mesma consulta feita na tela e não altera nenhum dado.


## Melhorias adicionadas nesta versão

- Busca avançada de produtos com filtro por linha/categoria.
- Filtro de saldo mínimo e saldo máximo.
- Opção para mostrar apenas produtos com saldo positivo.
- Ordenação por descrição, código, linha, quantidade ou valor estimado.
- Resumo por linha/categoria com total de itens, quantidade total, valor estimado, itens zerados e estoque baixo.
- Sugestões de produtos no campo de busca.
- Filtro local dentro da tabela exibida.
- Cabeçalhos da tabela clicáveis para ordenar o resultado na tela.
- Botão para copiar a tabela.
- Exportação Excel com aba de resumo.
- Exportação PDF com quadro de resumo.

Exemplos de consulta:

```text
resumo por linha limite 50
buscar farinha limite 50
estoque baixo até 10 linha linguiça
listar produtos linha pão de alho limite 30
```
