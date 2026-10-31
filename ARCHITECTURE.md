# Arquitetura Técnica

Este documento foi movido para o site oficial de documentação da Quantilica para garantir que a versão mais recente esteja sempre disponível e formatada corretamente.

👉 **Leia o racional completo em: [docs.quantilica.com/conceitos/arquitetura](https://docs.quantilica.com/conceitos/arquitetura)**

---

## Resumo Executivo

A arquitetura da Quantilica segue o princípio da **Neutralidade de Domínio**, separando a infraestrutura de I/O (`quantilica-core`) da camada de acesso a dados analíticos (`quantilica-analytics`).

### Preservação Histórica ("Nada se Apaga")
- **Camada Bruta Imutável (`raw`):** Todo artefato baixado recebe o carimbo temporal da publicação oficial (`{base}@{timestamp}.{ext}`) e um manifesto `.manifest.json` (SHA-256, schema v2). Republicações ou retificações dos órgãos públicos geram novas versões lado a lado sem jamais apagar ou sobrescrever arquivos anteriores.
- **Camada Analítica (`Lake Hive`):** A função `select_current()` (`quantilica.core.lake`) elege de forma determinística a versão bruta vigente de cada partição para conversão em Parquet particionado.

### Estrutura de Pacotes
- **Fetchers:** Coletores leves de dados brutos e conversores opcionais para o Lake Hive (`[analysis]`).
- **Pipelines:** Orquestração e transformação SQL/TOML.
- **CLI Host:** Ponto de entrada unificado para todas as ferramentas.

---

## Superfícies Públicas

| Superfície | Endereço | Tecnologia | Papel |
|---|---|---|---|
| Landing | `quantilica.com` | Hugo (GitHub Pages) | Apresentação da organização e links |
| Documentação | `docs.quantilica.com` | MkDocs (GitHub Pages) | Guias, normas, cookbook, roadmap |
| Índice de pacotes | `index.quantilica.com` | Estático PEP 503 (GitHub Pages) | Instalação dos fetchers via pip/uv (`quantilica install`) |
| Portal | `*.quantilica.com` (subdomínios por módulo) | FastAPI + HTMX | Aplicações interativas de dados |

Repositórios internos (planos, conhecimento, portal) permanecem privados e **não são referenciados** na documentação pública.

---
*Atualizado em: 22 de agosto de 2026*
