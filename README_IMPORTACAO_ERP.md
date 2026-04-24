# Importação de estoque do ERP

Esta versão adiciona uma tela para importar o arquivo de saldo gerado pelo ERP da empresa.

## Caminho no sistema

Entre como admin e acesse:

- Menu `Importar ERP`; ou
- Tela `Estoque` > botão `Importar ERP`.

## Como funciona

1. Envie o arquivo `.xls`, `.xlsx` ou `.xlsm` gerado pelo ERP.
2. O sistema lê a planilha e cria uma prévia.
3. A prévia mostra:
   - produtos novos;
   - produtos com saldo diferente;
   - produtos sem alteração;
   - delta total entre estoque atual e ERP;
   - linha/categoria vinda da hierarquia do relatório.
4. O admin escolhe o modo de aplicação.

## Modos de aplicação

- `Atualizar saldo pelo ERP e cadastrar novos`: usa o saldo do ERP como saldo atual do sistema.
- `Cadastrar novos, sem alterar saldo dos existentes`: cria produtos que ainda não existem, mas não altera produtos existentes.
- `Atualizar cadastro/categoria, sem mexer no saldo`: atualiza descrição, código de barras, custo e categoria, mas mantém a quantidade atual.

## Segurança

A importação não altera o estoque automaticamente no upload. Primeiro ela cria uma prévia. A alteração só acontece quando o admin clica em `Aplicar no estoque`.

Cada alteração gera movimentação no histórico de estoque e registro na auditoria.

## Formato reconhecido

O parser foi feito para relatórios no padrão:

- `SALDO NO ESTOQUE - DETALHE DA LOJA ...`
- `DATA BASE: dd/mm/aaaa`
- Cabeçalho com colunas como:
  - Código Item
  - Código Barras
  - Nível
  - Descrição
  - Preço Custo
  - Preço Venda
  - Saldo Qtd

O arquivo enviado como exemplo tinha extensão `.xls`, mas internamente estava no formato Excel moderno, então o sistema aceita esse caso.
