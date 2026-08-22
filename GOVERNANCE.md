# Governança — Quantilica

## Modelo Atual

A Quantilica opera atualmente sob o modelo **BDFL** (Benevolent Dictator For Life):

- **Mantenedor principal:** Komesu, D.K. ([@dankkom](https://github.com/dankkom))
- Decisões de arquitetura, nomenclatura e roadmap são tomadas pelo mantenedor principal.
- Contribuições externas são bem-vindas e avaliadas com base nos critérios do [CONTRIBUTING.md](CONTRIBUTING.md).

## Decisões Técnicas

Decisões arquiteturais significativas (novo pacote de fundação, mudança de dependência crítica, quebra de API) são registradas como **ADRs** e resumidas no [ARCHITECTURE.md](ARCHITECTURE.md) antes de serem implementadas. O `ARCHITECTURE.md` é a visão canônica pública; os ADRs detalham contexto, alternativas descartadas e trade-offs.

## Ciclo de Releases

Não há ciclo fixo. Releases são publicadas conforme funcionalidades são concluídas e testadas, seguindo [Keep a Changelog](https://keepachangelog.com/) + SemVer.

A distribuição é **bifurcada**:

- **PyPI:** `quantilica-core` e `quantilica-cli` (âncoras do ecossistema).
- **GitHub Releases + índice próprio (PEP 503):** todos os `*-fetcher`, `quantilica-analytics` e `quantilica-catalog`. Instalação canônica via `quantilica install <fonte>` ou `uv add <pacote> --index https://index.quantilica.com/simple/`.

## Futuro

Conforme o projeto crescer em contribuidores e usuários, pretende-se migrar para um modelo de governança comunitária com comitê técnico. Isso está previsto na Fase 4 do [Roadmap Estratégico](https://docs.quantilica.com/roadmap).

## Conflitos e Decisões Controversas

Em caso de divergência técnica, o mantenedor principal tem voto de minerva. Discussões são abertas publicamente via GitHub Issues ou Discussions para transparência.
