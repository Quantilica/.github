# Guia de Contribuição - Quantilica

Obrigado pelo seu interesse em contribuir para a Quantilica! Somos uma organização dedicada a abrir e normalizar dados públicos brasileiros.

---

## 🛠️ Nossos Padrões Técnicos

Para manter a consistência em todo o ecossistema, seguimos regras rigorosas:

1.  **Fundação:** Todos os coletores de dados devem utilizar o pacote [`quantilica-core`](https://github.com/Quantilica/quantilica-core).
2.  **Linguagem:** Utilizamos Python >= 3.12.
3.  **Ambiente:** O gerenciamento de dependências é feito via `uv`.
4.  **Qualidade:** Usamos `ruff` para linting e `pytest` para testes.
5.  **Proveniência:** Todo artefato de dado baixado deve gerar um `.manifest.json` compatível com o core.

---

## 🚀 Como contribuir?

### Reportando Bugs (Scrapers Quebrados)
Sites governamentais mudam com frequência. Se um fetcher parou de funcionar:
1.  Verifique se a fonte oficial está online.
2.  Abra uma Issue descrevendo o erro e, se possível, anexe o log gerado pelo `quantilica-core`.

### Sugerindo Novas Fontes
Quer que a Quantilica suporte uma nova base de dados?
1.  Abra uma Issue de "Proposta de Nova Fonte".
2.  Descreva a URL da fonte, o formato dos dados (CSV, API, FTP) e a periodicidade de atualização.

### Enviando Código (Pull Requests)
1.  Faça um fork do repositório.
2.  Crie uma branch para sua feature (`git checkout -b feat/nova-fonte`).
3.  Garanta que os testes passem (`uv run pytest`).
4.  Execute o linting (`uv run ruff check .`).
5.  Abra o PR descrevendo claramente as mudanças.

---

## 🏷️ Nomenclatura
Novos repositórios de coleta devem seguir o padrão: `<fonte>-fetcher`.

---
*Ao contribuir, você concorda que seu código será licenciado sob a licença MIT do projeto.*
