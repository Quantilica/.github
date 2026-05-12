# Arquitetura Técnica

Este documento foi movido para o site oficial de documentação da Quantilica para garantir que a versão mais recente esteja sempre disponível e formatada corretamente.

👉 **Leia o racional completo em: [docs.quantilica.io/concepts/arquitetura](https://docs.quantilica.io/concepts/arquitetura.md)**

---

## Resumo Executivo

A arquitetura da Quantilica segue o princípio da **Neutralidade de Domínio**, separando a infraestrutura de I/O (`quantilica-core`) da camada de acesso a dados analíticos (`quantilica-io`).

### Estrutura de Pacotes
- **Fetchers:** Coletores leves de dados brutos.
- **Pipelines:** Orquestração e transformação SQL/TOML.
- **CLI Host:** Ponto de entrada unificado para todas as ferramentas.

---
*Atualizado em: 12 de maio de 2026*
