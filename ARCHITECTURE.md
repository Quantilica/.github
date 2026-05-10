# Arquitetura Técnica e Fundações

Este documento descreve as decisões de arquitetura e o planejamento das bibliotecas base que sustentam a infraestrutura da Quantilica.

---

## 🏗️ Princípios de Design

A regra de ouro da nossa infraestrutura é a **Neutralidade de Domínio**.
*   O pacote `quantilica-core` **não deve saber** o que é SIDRA, DATASUS ou Tesouro Nacional.
*   Ele deve lidar exclusivamente com abstrações técnicas (HTTP, Cache, Storage, Logging).
*   Lógicas específicas de parsing e regras de negócio pertencem aos respectivos pacotes de domínio.

## 📦 Pacotes de Fundação

A infraestrutura é dividida em dois pilares técnicos para equilibrar leveza e poder de processamento.

### 1. `quantilica-core` (Infraestrutura de I/O)
Base estável e leve para todos os projetos. Sem dependências binárias pesadas.
*   **`http.py` / `ftp.py`**: Clients resilientes com suporte a manifestos.
*   **`storage.py`**: Interface `BaseDataRepository` para normalização de caminhos.
*   **`manifests.py`**: Proveniência e integridade (SHA256).
*   **`metadata.py`**: Modelos de dados genéricos.

### 2. `quantilica-io` (Data Access Layer)
Camada de processamento e padronização analítica. Depende do Polars.
*   **`reader.py`**: Leitura multi-formato (CSV, Excel, DBF) integrada a manifestos.
*   **`writer.py`**: Conversão otimizada para **Parquet** com metadados injetados.
*   **`schema.py`**: Contratos de dados e validação de tipos.

---

## 🏗️ Princípios de Design

| Tipo | Padrão Esperado | Exemplos |
| :--- | :--- | :--- |
| **Client** | Biblioteca Python + CLI simples | `sidra-fetcher`, `tddata` |
| **Pipeline** | Motor ETL + definições TOML/SQL | `sidra-sql`, `sidra-pipelines` |
| **Data Package** | Download + Transformação + Export | `rtnpy`, `inmet-fetcher` |

---

## 📊 Governança de Dados

A evolução técnica da arquitetura foca na transição para uma **Camada de Abstração de Dados**:
*   **Formatos Analíticos**: Migração obrigatória de CSV/XLSX para **Parquet**.
*   **Contratos de Dados**: Validação de schemas no momento da ingestão.
*   **Content-Addressable Storage**: Uso de hashes de conteúdo para evitar duplicidade e garantir imutabilidade.

---
*Para o roadmap de negócios e crescimento, veja [STRATEGY.md](STRATEGY.md).*
