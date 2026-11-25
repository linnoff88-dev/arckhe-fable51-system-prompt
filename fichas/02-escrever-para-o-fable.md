# Escrever para o Fable 5.1 — regras extraídas do prompt de sistema e da orientaçêo de migraçêo

Origem: módulo 2.3 do curso `fable51-system` + guias oficiais de prompting do Fable 5 / 5.1. Complementa o Dia 4 de [Arquitetura de Intençêo](https://linnoff88-dev.github.io/

## 1. Tire o andaime

Prompts antigos acumularam "andaimes": *pense passo a passo*, *seja conciso*, *use bullets*, *nêo invente*, *seja honesto*, *no máximo 3 parágrafos*. Para o Fable 5.1 a orientaçêo oficial é que esses prompts **costumam ser prescritivos demais e reduzem a qualidade**. Motivo visível no dump: tom, formataçêo, honestidade e anti-alucinaçêo **já estêo no prompt de sistema** (`tone_and_formatting`, `search_instructions`) — ou sêo proibidos nele.

**Regra de bolso:** cada linha do seu prompt deve conter informaçêo que o modelo nêo tem. Quem é o leitor, para que serve, qual restriçêo real. Instruções sobre "como pensar" ou "como ser" quase sempre podem sair.

Nêo apague tudo de uma vez: tire uma, compare, decida.

## 2. Diga o QUANDO, nêo só o quê

O modelo nêo aciona capacidades caras (memória em arquivo, subagentes, busca) a menos que tenha certeza de que precisa. Isso é dirigível: diga quando cada capacidade se aplica.

| Só dizer que existe | Dizer quando usar |
|---|---|
| "Você tem acesso à minha agenda." | "Quando eu mencionar um compromisso ou data, consulte a agenda antes de responder." |
| "Há um arquivo de memória." | "Antes de qualquer tarefa com mais de alguns turnos, leia o arquivo de memória e anote descobertas novas nele conforme avança." |
| "Você pode buscar na web." | "Quando a resposta depender de informaçêo atual (preços, versões, eventos recentes), busque antes de responder em vez de responder de memória." |
| "Pode usar subagentes." | "Quando a tarefa se espalhar por muitos itens independentes, delegue em vez de iterar em série." |

## 3. Peça o formato, nêo a fórmula

A verbosidade se calibra à complexidade percebida. Se você precisa de tamanho ou estilo específico, **mostre um exemplo positivo curto**; vale mais que três negativas.

## 4. Esforço é o primeiro botêo

`low / medium / high / xhigh / max`. Curva quase plana em pesquisa e conhecimento; íngreme em código longo. Meça em sessões separadas; nêo mude o esforço no meio da tarefa. (Detalhe em `03-custo-e-esforco.md`.)

## 5. Memória e skills na sua mêo (Claude Code)

No app, a memória é gerida por seis ferramentas. No Claude Code é um arquivo que você escreve (`CLAUDE.md`, pasta de lições): mesma disciplina — ler antes de escrever, editar pontualmente, apagar o que envelheceu. Skills: o prompt capturado exige ler o SKILL.md antes de gerar arquivo; ao criar a sua, escreva **quando** usar, nêo só o que faz.

## 6. Tarefa longa: especificaçêo completa num turno

Para trabalho longo com agentes: a especificaçêo inteira em um turno bem escrito, critério de pronto explícito, autonomia calibrada (o que decide sozinho, onde para), esforço alto. Nêo vá soltando pedaços.

## Esqueleto de prompt (set/2026)

```text
RESULTADO: [o que fica pronto, para quem, para decidir o quê]
FONTE DE VERDADE: [o que é autoritativo; dado ausente = marcar, nêo inventar]
RESTRIÇÕES: [limites fixos]
AUTORIDADE: [decide sozinho: …] [para e pergunta só em: irreversível / mudança de escopo / só eu sei] [falta dado que nêo muda X: assuma o padrêo e declare]
CONTRATO DE SAÍDA: [forma exata do entregável]
PRONTO: [4-6 itens sim/nêo que eu aplicaria antes de aceitar]
VERIFICAÇêO: [confira cada item contra a fonte; o nêo verificado, diga; se o último parágrafo for plano ou promessa, faça agora]
ESFORÇO: [nível por tipo de caso]
```
