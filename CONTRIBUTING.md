# Guia de Contribuição — Quantilica

Obrigado pelo seu interesse em contribuir para a Quantilica! Somos uma organização dedicada a abrir e normalizar dados públicos brasileiros.

---

## Padrões Técnicos

Para manter a consistência em todo o ecossistema, seguimos regras rigorosas. Consulte o [ARCHITECTURE.md](ARCHITECTURE.md) para o racional técnico completo.

1. **Fundação:** Todos os coletores de dados devem utilizar o pacote [`quantilica-core`](https://github.com/Quantilica/quantilica-core).
2. **Linguagem:** Python >= 3.12.
3. **Ambiente:** Gerenciamento de dependências via `uv`.
4. **Qualidade:** `ruff` para linting/formatação e `pytest` para testes.
5. **Cobertura:** Novos PRs devem manter 80%+ de cobertura de testes.
6. **Proveniência:** Todo artefato de dado baixado deve gerar um `.manifest.json` compatível com o core.
7. **Nomenclatura:** Novos repositórios de coleta seguem o padrão `<fonte>-fetcher`.

---

## Como Contribuir

### Reportando Bugs (Scrapers Quebrados)

Sites governamentais mudam com frequência. Se um fetcher parou de funcionar:

1. Verifique se a fonte oficial está online.
2. Abra uma Issue usando o template **Bug Report**, descrevendo o erro e anexando o log do `quantilica-core` quando disponível.

### Sugerindo Novas Fontes

Quer que a Quantilica suporte uma nova base de dados?

1. Abra uma Issue usando o template **Feature Request / Nova Fonte**.
2. Descreva a URL da fonte, o formato dos dados (CSV, API, FTP) e a periodicidade de atualização.

### Enviando Código (Pull Requests)

1. Faça um fork do repositório e crie uma branch: `git checkout -b feat/descricao-curta`.
2. Implemente as mudanças, garantindo cobertura de testes >= 80%.
3. Execute o linting: `uv run ruff check .`
4. Execute os testes: `uv run pytest`
5. Abra o PR como **Draft** enquanto o trabalho estiver em andamento.
6. Marque como **Ready for Review** quando estiver pronto — inclua uma descrição clara do que muda e por quê.
7. PRs são mergeados via **squash merge** para manter o histórico linear.

---

## Versionamento e Releases

O projeto segue **Semantic Versioning** (MAJOR.MINOR.PATCH):

- **PATCH**: correções de bugs, atualizações de URLs/endpoints governamentais.
- **MINOR**: novas funcionalidades compatíveis com versões anteriores.
- **MAJOR**: mudanças de API incompatíveis.

Releases são publicadas sem ciclo fixo — conforme funcionalidades são concluídas. Para `datasus-fetcher` (único pacote no PyPI), uma tag git dispara o workflow de publicação automática.

---

*Ao contribuir, você concorda que seu código será licenciado sob a licença MIT do projeto.*

*Atualizado em: 10 de maio de 2026*
