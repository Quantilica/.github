# Plano de Implementação: `quantilica-io` 📊

Este documento detalha a criação do pacote `quantilica-io`, a camada de processamento e padronização analítica da Quantilica.

---

## 🎯 Objetivo

Desacoplar a lógica de processamento de dados (leitura, limpeza, conversão para Parquet) do `quantilica-core`, mantendo o núcleo leve e focado exclusivamente em I/O (HTTP/FTP) e infraestrutura de metadados.

## 🏗️ Arquitetura

O `quantilica-io` atuará como uma ponte entre os arquivos brutos baixados pelos fetchers e os ativos analíticos prontos para consumo.

### Dependências Principais
- `quantilica-core` (Metadados e Storage)
- `polars` (Engine de processamento de alto desempenho)
- `pyarrow` (Suporte para escrita Parquet e schemas complexos)

### Módulos Planejados

#### 1. `quantilica_io.reader`
Abstração de leitura multi-formato integrada aos manifestos do core.
- Suporte a: `CSV`, `JSON`, `Excel`, `DBF` (comum no DATASUS).
- Integração com `quantilica_core.storage.LocalStorage`.
- Detecção automática de encoding.

#### 2. `quantilica_io.schema`
Definição de contratos de dados para garantir consistência entre datasets.
- Classe `DataContract`: Define nomes de colunas padronizados, tipos e campos obrigatórios.
- Validação preventiva: Erro imediato se a fonte oficial alterar o layout do arquivo.

#### 3. `quantilica_io.writer`
Conversão padronizada para formatos analíticos.
- `to_parquet()`: Escrita otimizada com compressão `zstd` e inclusão de metadados de proveniência no header do arquivo Parquet.
- Particionamento inteligente baseado nos metadados do dataset.

---

## 🗺️ Roadmap de Implementação

### Fase 1: Fundação (Setup do Projeto)
1. Criar diretório `quantilica-io`.
2. Configurar `pyproject.toml` (Build system: `hatchling`).
3. Integrar CI/CD base (Ruff + Pytest).

### Fase 2: Motor Parquet
1. Implementar `ParquetConverter`: Uma classe que recebe um `DownloadManifest` e produz um `.parquet`.
2. Garantir que o `sha256` do arquivo original seja gravado como metadado customizado dentro do arquivo Parquet (rastreabilidade total).

### Fase 3: Padronização de Tipos (Schemas)
1. Criar utilitários para conversão automática de colunas comuns:
   - Datas (RFC 3339).
   - Valores monetários.
   - Códigos geográficos (IBGE).

### Fase 4: Integração nos Fetchers
1. Adicionar `quantilica-io` como dependência opcional (`dev`) nos fetchers.
2. Refatorar o comando `read` do `inmet-fetcher` e `pdet-fetcher` para usar o core-io.

---

## ✅ Benefícios

1. **Purismo nos Fetchers**: Um usuário que queira apenas baixar os dados do SIDRA não precisa instalar 50MB de binários do Polars/Arrow.
2. **Reuso de Código**: A lógica complexa de lidar com enconding `latin-1` ou separadores `;` do governo brasileiro é escrita apenas uma vez.
3. **Interoperabilidade**: Todos os arquivos Parquet gerados pela Quantilica seguem o mesmo padrão, permitindo consultas SQL (via DuckDB) em múltiplos datasets simultaneamente sem conflitos de tipo.
