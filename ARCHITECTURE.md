# Arquitetura Técnica

Este documento foi movido para o site oficial de documentação da Quantilica para garantir que a versão mais recente esteja sempre disponível e formatada corretamente.

👉 **Leia o racional completo em: [docs.quantilica.com/concepts/arquitetura](https://docs.quantilica.com/concepts/arquitetura)**

---

## Resumo Executivo

A arquitetura da Quantilica segue o princípio da **Neutralidade de Domínio**, separando a infraestrutura de I/O (`quantilica-core`) da camada de acesso a dados analíticos (`quantilica-analytics`).

### Estrutura de Pacotes
- **Fetchers:** Coletores leves de dados brutos.
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
