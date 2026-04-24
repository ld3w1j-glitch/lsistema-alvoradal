# Sistema Alvorada V3 - Segurança, Auditoria e MCP Integrado

Esta versão evolui a integração MCP/IA para uma camada mais segura e integrada ao sistema.

## Principais melhorias

- Assistente MCP/IA flutuante em várias páginas do sistema.
- Ações preparadas em modo rascunho: a IA sugere/prepara, mas não altera o estoque sozinha.
- Histórico de consultas MCP e exportações.
- Relatório gerencial automático com visualização no site e exportação em PDF.
- Modo manutenção para bloquear usuários comuns durante ajustes.
- Tratamento amigável de erros com código de erro.
- Painel de código fonte mais seguro:
  - confirmação de senha para salvar/restaurar;
  - backup automático;
  - histórico de edições;
  - visualização de diff;
  - restauração de backups;
  - auditoria de ações.
- Novas funções/cargos sugeridos:
  - Admin
  - Gerente
  - Estoque
  - Separador
  - Conferente
  - Balanço
  - Desenvolvedor
  - Visualizador

## Atenção no Railway

Alterações em HTML, CSS e JS costumam aparecer ao atualizar a página.

Alterações em arquivos Python geralmente precisam de reinício do serviço no Railway para valerem, pois o Gunicorn mantém o processo carregado.

## Segurança

Mesmo com o editor de código protegido, evite liberar o acesso `Código fonte` para usuários comuns.
O ideal é liberar apenas para Admin ou Desenvolvedor confiável.
