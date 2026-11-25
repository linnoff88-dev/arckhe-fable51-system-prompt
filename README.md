# Fable 5.1 ê¢â¬â prompt de sistema (projeto de referêÂªncia)

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="48" />
  <p><strong>Arckhé AI</strong></p>
</div>


**ê°Å¸â¡Â§ê°Å¸â¡Â· [PortuguêÂªs](README.md) êÂ· ê°Å¸â¡Âºê°Å¸â¡Â¸ [English](README.en.md) êÂ· ê°Å¸â¡Âªê°Å¸â¡Â¸ [EspaêÂ±ol](README.es.md)**

## ê°Å¸ââ Guia de uso

Guia completo (landing + passo a passo): **https://linnoff88-dev.github.io/

Material de referêÂªncia sobre o **prompt de sistema do Claude Fable 5.1**: o que a Anthropic publica, o que aparece na extraêÂ§êÂ£o pêÂºblica do runtime do Claude.ai, o que mudou em relaêÂ§êÂ£o ao Fable 5, e as fichas prêÂ¡ticas derivadas disso. êâ° o **projeto**; o **curso** que ensina esse conteêÂºdo vive separado (ver o fim).

## Duas fontes, dois pesos

| Fonte | O que êÂ© | ConfianêÂ§a |
|---|---|---|
| [Prompt central oficial](https://platform.claude.com/docs/en/release-notes/system-prompts/claude-fable-5-1) (Anthropic) | O que a Anthropic publica e assina, com histêÂ³rico de versêÂµes | êÅ¡nica fonte autenticada |
| Dump do runtime (repositêÂ³rio [CL4R1T4S](https://github.com/elder-plinius/CL4R1T4S/tree/main/ANTHROPIC), pasta ANTHROPIC) | Runtime montado: prompt central + memêÂ³ria + busca + artefatos + roteamento + schemas de ferramentas. Congelado em 2026-09-02. | ExtraêÂ§êÂ£o **nêÂ£o autenticada** pela Anthropic |
| Field Guide (Mark Kashef, 2026-09-02; traduêÂ§êÂ£o PT-BR) | ComparaêÂ§êÂ£o Fable 5 êâ 5.1 no mesmo mêÂ©todo de contagem | ReproduzêÂ­vel; compara dois dumps nêÂ£o autenticados |

Moldura para tudo neste repositêÂ³rio: **oficial êâ extraêÂ­do** e **modelo êâ produto ao redor**. O Fable 5.1 pontua mais alto *e* o sistema ao redor cresceu 2,3x; nada prova que um causou o outro.

## O que tem aqui

```
fable51-system-prompt/
  README.md               este arquivo
  ANALISE.md              os trêÂªs nêÂºmeros, as 28 ferramentas em 6 grupos, regras de comportamento, o paradoxo
  INDICE-DO-DUMP.md       mapa gerado do dump: 40 seêÂ§êÂµes com linhas e tamanho, ferramentas e skills encontradas
  fichas/
    01-ficha-dos-5-testes.md       ficha de registro + os 5 testes do comprador (memêÂ³ria, conversas, visuais, skills, controle)
    02-escrever-para-o-fable.md    tirar o andaime, dizer o quando, formato > fêÂ³rmula, esforêÂ§o, esqueleto set/2026
    03-custo-e-esforco.md          tabela de preêÂ§os, nêÂ­veis de esforêÂ§o, "rode barato e refaêÂ§a", onde o barato ganha
  build/indice.py         gera o êÂ­ndice a partir do dump
  guia/index.html         landing + guia (GitHub Pages) êÂ· capa/capa.png capa do catêÂ¡logo
  doc/                    material-fonte LOCAL (ignorado no git ê¢â¬â ver abaixo)
```

### `doc/` nêÂ£o êÂ© publicado

A pasta `doc/` guarda o dump (`Claude-Fable-5.1.md`, 275.723 bytes, md5 `be4cb3a5103be5c1c581afac2a04b1d0`) e os dois PDFs do Field Guide (EN de autoria de Mark Kashef; PT-BR). SêÂ£o material de terceiros / extraêÂ§êÂ£o nêÂ£o autenticada; ficam sêÂ³ na mêÂ¡quina, como jêÂ¡ era no repositêÂ³rio do curso. O dump original estêÂ¡ pêÂºblico no repositêÂ³rio CL4R1T4S linkado acima. Para regenerar o êÂ­ndice: `python3 build/indice.py` na raiz.

## Os trêÂªs nêÂºmeros (resumo)

- Prompt capturado: **17.501 ê¢â â 40.046 palavras (2,3x)**.
- **+28 ferramentas** (46 no total, nenhuma removida).
- **75% do crescimento** = memêÂ³ria + schemas de ferramentas. SêÂ³ `memory_filesystem` ocupa 38% do dump atual.

Detalhe em [ANALISE.md](ANALISE.md).

## Como usar

1. Quer saber **o que existe** no prompt e onde: [INDICE-DO-DUMP.md](INDICE-DO-DUMP.md) (ordem de leitura sugerida no fim).
2. Quer **testar na sua conta** se as novidades aparecem: [fichas/01-ficha-dos-5-testes.md](fichas/01-ficha-dos-5-testes.md).
3. Quer **reescrever seus prompts** para a nova geraêÂ§êÂ£o: [fichas/02-escrever-para-o-fable.md](fichas/02-escrever-para-o-fable.md).
4. Quer **gastar menos**: [fichas/03-custo-e-esforco.md](fichas/03-custo-e-esforco.md).

Tudo datado: dump de 2026-09-02, anêÂ¡lise de 2026-09-05. O produto muda; reaudite a cada geraêÂ§êÂ£o.

## Curso

- **Fable 5.1 na prêÂ¡tica ê¢â¬â o que mudou, como usar, como gastar menos** (3 trilhas, 9 mêÂ³dulos): repositêÂ³rio [`linnoff88-dev/fable51-system`](https://github.com/linnoff88-dev/fable51-system) êÂ· pêÂ¡gina https://linnoff88-dev.github.io/
- Relacionado: **Arquitetura de IntenêÂ§êÂ£o ê¢â¬â Dia 4, A Virada** (modelos que operam na intenêÂ§êÂ£o): https://linnoff88-dev.github.io/

---
ARCKHê AI êÂ· 2026

---

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="32" />
  <p><strong>Arckhé AI</strong></p>
</div>