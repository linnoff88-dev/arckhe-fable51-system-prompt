# Fable 5.1 â€” prompt de sistema (projeto de referÃªncia)

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="48" />
  <p><strong>Arckhé AI</strong></p>
</div>


**ðŸ‡§ðŸ‡· [PortuguÃªs](README.md) Â· ðŸ‡ºðŸ‡¸ [English](README.en.md) Â· ðŸ‡ªðŸ‡¸ [EspaÃ±ol](README.es.md)**

## ðŸ“– Guia de uso

Guia completo (landing + passo a passo): **https://linnoff88-dev.github.io/

Material de referÃªncia sobre o **prompt de sistema do Claude Fable 5.1**: o que a Anthropic publica, o que aparece na extraÃ§Ã£o pÃºblica do runtime do Claude.ai, o que mudou em relaÃ§Ã£o ao Fable 5, e as fichas prÃ¡ticas derivadas disso. Ã‰ o **projeto**; o **curso** que ensina esse conteÃºdo vive separado (ver o fim).

## Duas fontes, dois pesos

| Fonte | O que Ã© | ConfianÃ§a |
|---|---|---|
| [Prompt central oficial](https://platform.claude.com/docs/en/release-notes/system-prompts/claude-fable-5-1) (Anthropic) | O que a Anthropic publica e assina, com histÃ³rico de versÃµes | Ãšnica fonte autenticada |
| Dump do runtime (repositÃ³rio [CL4R1T4S](https://github.com/elder-plinius/CL4R1T4S/tree/main/ANTHROPIC), pasta ANTHROPIC) | Runtime montado: prompt central + memÃ³ria + busca + artefatos + roteamento + schemas de ferramentas. Congelado em 2026-09-02. | ExtraÃ§Ã£o **nÃ£o autenticada** pela Anthropic |
| Field Guide (Mark Kashef, 2026-09-02; traduÃ§Ã£o PT-BR) | ComparaÃ§Ã£o Fable 5 Ã— 5.1 no mesmo mÃ©todo de contagem | ReproduzÃ­vel; compara dois dumps nÃ£o autenticados |

Moldura para tudo neste repositÃ³rio: **oficial Ã— extraÃ­do** e **modelo Ã— produto ao redor**. O Fable 5.1 pontua mais alto *e* o sistema ao redor cresceu 2,3x; nada prova que um causou o outro.

## O que tem aqui

```
fable51-system-prompt/
  README.md               este arquivo
  ANALISE.md              os trÃªs nÃºmeros, as 28 ferramentas em 6 grupos, regras de comportamento, o paradoxo
  INDICE-DO-DUMP.md       mapa gerado do dump: 40 seÃ§Ãµes com linhas e tamanho, ferramentas e skills encontradas
  fichas/
    01-ficha-dos-5-testes.md       ficha de registro + os 5 testes do comprador (memÃ³ria, conversas, visuais, skills, controle)
    02-escrever-para-o-fable.md    tirar o andaime, dizer o quando, formato > fÃ³rmula, esforÃ§o, esqueleto set/2026
    03-custo-e-esforco.md          tabela de preÃ§os, nÃ­veis de esforÃ§o, "rode barato e refaÃ§a", onde o barato ganha
  build/indice.py         gera o Ã­ndice a partir do dump
  guia/index.html         landing + guia (GitHub Pages) Â· capa/capa.png capa do catÃ¡logo
  doc/                    material-fonte LOCAL (ignorado no git â€” ver abaixo)
```

### `doc/` nÃ£o Ã© publicado

A pasta `doc/` guarda o dump (`Claude-Fable-5.1.md`, 275.723 bytes, md5 `be4cb3a5103be5c1c581afac2a04b1d0`) e os dois PDFs do Field Guide (EN de autoria de Mark Kashef; PT-BR). SÃ£o material de terceiros / extraÃ§Ã£o nÃ£o autenticada; ficam sÃ³ na mÃ¡quina, como jÃ¡ era no repositÃ³rio do curso. O dump original estÃ¡ pÃºblico no repositÃ³rio CL4R1T4S linkado acima. Para regenerar o Ã­ndice: `python3 build/indice.py` na raiz.

## Os trÃªs nÃºmeros (resumo)

- Prompt capturado: **17.501 â†’ 40.046 palavras (2,3x)**.
- **+28 ferramentas** (46 no total, nenhuma removida).
- **75% do crescimento** = memÃ³ria + schemas de ferramentas. SÃ³ `memory_filesystem` ocupa 38% do dump atual.

Detalhe em [ANALISE.md](ANALISE.md).

## Como usar

1. Quer saber **o que existe** no prompt e onde: [INDICE-DO-DUMP.md](INDICE-DO-DUMP.md) (ordem de leitura sugerida no fim).
2. Quer **testar na sua conta** se as novidades aparecem: [fichas/01-ficha-dos-5-testes.md](fichas/01-ficha-dos-5-testes.md).
3. Quer **reescrever seus prompts** para a nova geraÃ§Ã£o: [fichas/02-escrever-para-o-fable.md](fichas/02-escrever-para-o-fable.md).
4. Quer **gastar menos**: [fichas/03-custo-e-esforco.md](fichas/03-custo-e-esforco.md).

Tudo datado: dump de 2026-09-02, anÃ¡lise de 2026-09-05. O produto muda; reaudite a cada geraÃ§Ã£o.

## Curso

- **Fable 5.1 na prÃ¡tica â€” o que mudou, como usar, como gastar menos** (3 trilhas, 9 mÃ³dulos): repositÃ³rio [`linnoff88-dev/fable51-system`](https://github.com/linnoff88-dev/fable51-system) Â· pÃ¡gina https://linnoff88-dev.github.io/
- Relacionado: **Arquitetura de IntenÃ§Ã£o â€” Dia 4, A Virada** (modelos que operam na intenÃ§Ã£o): https://linnoff88-dev.github.io/

---
ARCKHÉ AI Â· 2026

---

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="32" />
  <p><strong>Arckhé AI</strong></p>
</div>