# Histórico vinculado ao usuário com estorno de estoque

Esta versão adiciona uma tela segura para o administrador revisar históricos finalizados vinculados a um usuário e remover esses históricos devolvendo as quantidades ao estoque.

## Onde acessar

Painel ADM > Usuários > botão **Histórico/Estorno** no usuário desejado.

## Como funciona

1. O sistema lista separações finalizadas em que o usuário aparece como responsável, conferente ou criador.
2. O admin seleciona os históricos que deseja remover.
3. O sistema mostra uma prévia com os produtos e quantidades que voltarão para o estoque.
4. O admin confirma com a própria senha.
5. O sistema devolve o estoque, registra movimentações do tipo `ESTORNO_HISTORICO`, muda o histórico para cancelado e grava auditoria.

## Segurança

- Apenas admin acessa.
- Exige senha antes de confirmar.
- Não altera nada na etapa de prévia.
- Mantém rastreabilidade em auditoria e movimentações de estoque.
- Não apaga fisicamente a separação; ela é cancelada com observação para preservar histórico técnico.
