# Quantilica 📊
### Infraestrutura de Dados Públicos Brasileiros

A **Quantilica** é uma organização dedicada a transformar a complexidade dos dados públicos brasileiros em ativos analíticos de alta qualidade. Desenvolvemos ferramentas modulares e resilientes para a coleta, normalização e governança de dados econômicos, fiscais, meteorológicos e de saúde.

---

## 🚀 O que fazemos?

Abstraímos a instabilidade e a inconsistência das fontes oficiais (APIs obsoletas, FTPs lentos e arquivos sem tipo) para fornecer uma experiência unificada e moderna de acesso a dados.

### Nossos Principais Domínios
- 🏛️ **Fiscais e Tesouro:** Coletores para Tesouro Direto, Resultado do Tesouro Nacional (RTN) e BCB.
- 📈 **Estatísticas e Economia:** Integração profunda com SIDRA/IBGE e Comércio Exterior (Comex Stat).
- 🏥 **Saúde:** Extração e normalização de microdados do DATASUS.
- 💼 **Trabalho:** Processamento de dados do Programa de Disseminação de Estatísticas do Trabalho (PDET).
- ☁️ **Meteorologia:** Coleta automatizada de dados históricos do INMET.

---

## 🛠️ Nossos Padrões (Fundação Quantilica)

Todos os nossos projetos são construídos sobre o [**`quantilica-core`**](https://github.com/Quantilica/quantilica-core), garantindo:
- **Resiliência:** Lógica de rede padronizada com retries e backoff exponencial.
- **Proveniência:** Cada dado baixado possui um manifesto SHA256 para rastreabilidade total.
- **Analytical-Ready:** Foco na transição de formatos brutos para **Parquet** de alta performance.
- **Observabilidade:** Logs estruturados e monitoramento proativo das fontes governamentais.

---

## 🗺️ Visão de Futuro

Estamos evoluindo para nos tornarmos a **Camada de Abstração de Dados (Data Access Layer)** definitiva para o Brasil:
1.  **CLI Unificada:** [`quantilica-cli`](https://github.com/Quantilica/quantilica-cli) — interface única com descoberta de fetchers via plugins. *(Disponível em v0.1.0)*
2.  **Data Contracts:** Garantia de integridade e alerta automático de mudanças nas fontes.
3.  **Unified Hub:** Portal para busca global e download de dados pré-processados.

---

## 👋 Como contribuir?

Somos uma iniciativa aberta! Se você tem experiência com dados públicos brasileiros ou quer ajudar a melhorar nossa infraestrutura em Python:
1.  Explore nossos repositórios terminados em `-fetcher`.
2.  Leia o nosso [Roadmap Estratégico](https://github.com/Quantilica/.github/blob/main/STRATEGY.md).
3.  Abra uma Issue ou sugira uma nova fonte de dados.

---
*Transformando dados públicos em conhecimento acionável.*
