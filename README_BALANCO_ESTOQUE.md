# Balanço / Contagem de estoque

Esta versão adiciona uma página nova no menu: **Balanço**.

Fluxo:

1. Criar uma nova contagem de estoque.
2. Registrar mercadorias pelo código ou código de barras.
3. O sistema salva a quantidade que estava no estoque no momento da contagem.
4. A tela mostra comparação: quantidade do sistema x quantidade contada.
5. Antes de confirmar, é possível imprimir, exportar Excel ou PDF.
6. Somente admin pode clicar em **Confirmar e atualizar estoque**.
7. Ao confirmar, o estoque é atualizado com base na contagem e uma movimentação `BALANCO_ESTOQUE` é registrada no histórico.

Arquivos alterados/adicionados:

- `controle_separacao/core.py`
- `templates/partials/_topbar.html`
- `templates/balancos.html`
- `templates/balanco_detalhe.html`

Observação: o Railway cria as novas tabelas automaticamente na inicialização do app.
