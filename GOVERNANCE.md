# Governança — Quantilica

## Modelo Atual

A Quantilica opera atualmente sob o modelo **BDFL** (Benevolent Dictator For Life):

- **Mantenedor principal:** Komesu, D.K. ([@dankkom](https://github.com/dankkom))
- Decisões de arquitetura, nomenclatura e roadmap são tomadas pelo mantenedor principal.
- Contribuições externas são bem-vindas e avaliadas com base nos critérios do [CONTRIBUTING.md](CONTRIBUTING.md).

## Decisões Técnicas

Decisões arquiteturais significativas (novo pacote de fundação, mudança de dependência crítica, quebra de API) são documentadas no [ARCHITECTURE.md](ARCHITECTURE.md) antes de serem implementadas.

## Ciclo de Releases

Não há ciclo fixo. Releases são publicadas conforme funcionalidades são concluídas e testadas. O único pacote publicado no PyPI é o `datasus-fetcher`; os demais são instalados via `git+https`.

## Futuro

Conforme o projeto crescer em contribuidores e usuários, pretende-se migrar para um modelo de governança comunitária com comitê técnico. Isso está previsto na Fase 4 do [Roadmap Estratégico](STRATEGY.md).

## Conflitos e Decisões Controversas

Em caso de divergência técnica, o mantenedor principal tem voto de minerva. Discussões são abertas publicamente via GitHub Issues ou Discussions para transparência.
