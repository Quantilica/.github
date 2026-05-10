# Quantilica: Infraestrutura de Dados Públicos Brasileiros

A Quantilica é uma organização focada na coleta, normalização, exploração e publicação de dados públicos brasileiros (econômicos, estatísticos, meteorológicos, fiscais, trabalhistas e de saúde).

Este workspace é composto por um conjunto de projetos modulares que trabalham de forma coordenada para transformar dados brutos de fontes oficiais em ativos analíticos de alta qualidade.

---

## 📂 Visão Geral do Ecossistema

Os projetos estão organizados por domínios de dados e funções arquiteturais:

### Domínios de Dados
*   **IBGE/SIDRA:** `sidra-fetcher`, `sidra-sql`, `sidra-pipelines`
*   **DATASUS:** `datasus-fetcher`, `datasus-analytics`
*   **Fiscais e Tesouro:** `tesouro-direto-fetcher`, `rtnpy` (RTN), `b3-cotacaohistorica`
*   **Outros:** `comexdown` (Comércio Exterior), `inmet-fetcher` (Meteorologia), `pdet-fetcher` (Trabalho/CAGED/RAIS)

### Infraestrutura Comum
*   **`quantilica-core`**: Base estável de utilitários domain-neutral (HTTP, Storage, Logging, Metadata).
*   **`quantilica-io`**: Camada de processamento analítico (Parquet, Polars, Schema).
*   **`docs` / `quantilica.github.io`**: Documentação centralizada e portal da organização.

---

## 🏗️ Padrões Arquiteturais

Os projetos seguem três padrões principais de implementação:

1.  **Bibliotecas/CLIs de Coleta (Data Clients):** Pacotes enxutos focados em baixar e padronizar dados brutos (`fetcher`, `reader`, `storage`).
2.  **Apps Web de Exploração:** Interfaces Flask para consulta de metadados e visualização de catálogos (`create_app`, `PostgreSQL`, `Redis`).
3.  **ETL Declarativo / Pipelines:** Motores Python que executam transformações baseadas em arquivos de configuração TOML/SQL.

---

## 🛠️ Stack Tecnológica Padronizada

Para garantir a manutenibilidade, todos os projetos novos e migrados seguem esta stack:

*   **Linguagem:** Python >= 3.12
*   **Gerenciamento:** `uv` para pacotes e ambientes virtuais.
*   **Build System:** `hatchling`.
*   **Qualidade:** `ruff` para linting/formatação e `pytest` para testes unitários.
*   **Infra:** `quantilica-core` para logging estruturado, resiliência HTTP e manifestos de proveniência.

---

## 🗺️ Roadmap de Integração

A Quantilica está em processo de unificação técnica seguindo estas camadas:
1.  **Data Clients:** Bibliotecas que falam com fontes oficiais (Em progresso/Finalizado).
2.  **Storage Layer:** Armazenamento atômico e imutável com manifestos SHA256.
3.  **Metadata Registry:** Catálogo unificado de fontes e datasets.
4.  **Data Access Layer:** Abstração de acesso via Parquet e Polars.

---
*Para mais detalhes sobre a visão estratégica, consulte [.github/STRATEGY.md](STRATEGY.md).*
*Para detalhes técnicos e planos de infraestrutura, consulte [.github/ARCHITECTURE.md](ARCHITECTURE.md).*
