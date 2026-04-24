# MCP/IA - Consulta inteligente dentro do Sistema Alvorada

Esta versão adiciona uma página no próprio sistema para consultar os dados do MCP sem depender de Cursor, Claude Desktop ou outro cliente externo.

## Como acessar

1. Rode o site normalmente:

```bash
python app.py
```

2. Entre com um usuário administrador.
3. Clique no menu **MCP/IA**.

## O que melhorou

- Pesquisa livre por nome de produto, código, código de barras ou termo.
- Consulta avançada com tipo de busca, termo, limite de resultados e limite para estoque baixo.
- Resultado em conversa e também em tabela.
- Botão para **imprimir** o resultado.
- Exportação do resultado em **Excel (.xlsx)**.
- Exportação do resultado em **PDF**.
- Suporte a perguntas mais naturais, por exemplo:
  - `farinha`
  - `pesquisar farinha limite 50`
  - `estoque baixo até 5`
  - `produto 123`
  - `lote LT-001`
  - `movimentações do produto 123`
  - `listar lojas`
  - `status do sistema`

## Importante

Esta página continua em **modo leitura**. Ela consulta os dados, mas não altera estoque, não apaga produtos e não edita o banco.

## Filtro por linha/categoria

A página **MCP/IA** agora também tem o campo **Linha/Categoria dos itens**.

Esse filtro agrupa os produtos pela descrição, sem alterar o banco de dados. Exemplos de linhas que podem aparecer:

- PÃO DE ALHO
- LINGUIÇA
- FRANGO
- QUEIJOS
- BEBIDAS
- FARINHAS
- OUTROS

Você pode usar de duas formas:

1. Pela tela, selecionando a linha/categoria no campo ao lado da consulta.
2. Digitando na conversa, por exemplo:

```text
listar produtos linha pão de alho limite 30
estoque baixo linha linguiça até 10
pesquisar farinha linha farinhas limite 50
listar categorias limite 50
```

O resultado filtrado também pode ser impresso ou exportado para Excel/PDF.


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
