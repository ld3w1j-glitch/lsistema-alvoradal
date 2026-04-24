# Sistema Alvorada — MCP V2 + Painel ADM de Código

Esta versão adiciona duas melhorias principais:

## 1. MCP/IA integrado nas páginas

Além da central `/mcp`, agora o administrador vê um assistente MCP/IA contextual em:

- Painel
- Estoque
- Lotes
- Relatórios

O assistente consegue analisar a página atual, consultar estoque, lotes, categorias/linhas e gerar uma resposta resumida. Para exportar o resultado em PDF ou Excel, use a central **MCP/IA**.

Também foram adicionados:

- histórico de consultas MCP;
- consultas salvas;
- contexto por página;
- registro de exportações;
- estrutura separada em `controle_separacao/intelligence/` para evoluir a inteligência sem deixar o `core.py` ainda mais confuso.

## 2. Painel ADM para navegar e editar código fonte

No menu do admin existe a opção **Código fonte**.

Ela permite:

- navegar pelas pastas do projeto;
- abrir arquivos de texto como `.py`, `.html`, `.css`, `.js`, `.json`, `.md`, `.txt`, `.yml`;
- editar o conteúdo;
- salvar com backup automático em `.code_backups/`;
- usar `Ctrl+S` para salvar;
- usar `Tab` dentro do editor.

Arquivos sensíveis e binários ficam bloqueados:

- `dados.db`;
- `.env`;
- `.sqlite`, `.db`;
- `.exe`, `.dll`, `.so`;
- `.venv`, `venv`, `.git`, `__pycache__`.

## Observação importante no Railway

Arquivos HTML, CSS e JS normalmente aparecem ao atualizar a página.

Alterações em arquivos Python podem precisar reiniciar o serviço no Railway, porque produção com Gunicorn não recarrega código Python automaticamente como o Flask debug local.

Além disso, alterações feitas diretamente no painel do Railway podem ser temporárias no container. Para manter definitivo, depois copie a alteração para o repositório GitHub.
