---
layout: post
title: "Boletim 025 — O Recibo de Cada Mão"
date: 2026-10-26
author: Bruno Duarte da Silveira
tags: [fable, modelos, commits, proveniencia, formiga, bom-senso]
image: /assets/img/commits-por-modelo.png
description: "Duzentos e cinco dias, 1.433 commits e cinco modelos de IA trabalhando na mesma casa. Dá para saber quem fez cada coisa, porque cada mão deixou recibo."
---

![Barras horizontais: commits por dia ativo de cada modelo de IA co-autor. O Fable 5 tem a barra mais longa, 5,9.]({{ '/assets/img/commits-por-modelo.png' | relative_url }})

*Gráfico, não ilustração. Medido no GitHub, de 03/03 a 24/10/2026. O método
está no fim deste boletim.*

---

*O Boletim 024 terminou numa balança: contar não é pesar. Sessenta dias depois,
a vitrine ficou quieta, mas a casa não parou. Este despacho volta com a conta
na mão e com a pergunta que ninguém costuma fazer em voz alta: quem fez o quê?*

## Duzentos e cinco dias

O dia 1 deste projeto foi 5 de abril de 2026. O motor já rodava desde 28 de
março, observando sem contar. Hoje é o dia 205.

Nesse tempo, 1.433 commits entraram nos repositórios da casa. Junho teve 319.
Julho, 521. Depois a curva desce, mês a mês: 284, 152, 104. Não é cansaço. É a
obra mudando de fase: menos tijolo, mais reboco.

Em 27 de julho saiu o artigo *A Fábula e o Fable*. Ele contava duas histórias
com o mesmo nome. Uma era o modelo de IA que a Anthropic lançou em 9 de junho.
A outra era a fábula que nasceu aqui, num morro de Florianópolis, com um
"porteiro" chamado Severino, um agente de código que barra o ruído na entrada,
e um cachorro de verdade chamado Banks. O artigo terminava em "81 dias,
zero de financiamento". Esta é a conta do que veio depois.

## Cada mão assina

Toda vez que uma IA trabalha num commit desta casa, ela deixa uma linha no fim
da mensagem: `Co-Authored-By`, com o nome do modelo. Não é detector, não é
palpite. É recibo.

Contando esses recibos, aparecem cinco modelos e cinco ritmos:

| Modelo co-autor | Período | Commits | Por dia ativo |
|---|---|---|---|
| Opus 4.6 | 31/03 a 20/10 | 249 | 2,8 |
| Opus 4.8 | 01/06 a 24/07 | 146 | 5,2 |
| Fable 5 | 09/06 a 18/07 | 129 | **5,9** |
| Opus 5 | 17/07 a 22/09 | 186 | 4,8 |
| Opus 5.5 | 23/09 a 20/10 | 70 | 3,2 |

O Fable trabalhou aqui 22 dias, no ritmo mais alto de todos. O primeiro commit
assinado por ele é de 9 de junho, o dia do lançamento. A fábula já tinha
capítulos públicos desde 26 de março.

E o Opus 4.6, que aparece até outubro, muito depois dos modelos novos? Não é
erro. É o computador mais velho da casa, um Windows 10 que só roda uma versão
antiga da ferramenta. A máquina assina como sabe. A conta sabe de onde veio.

## Onde está o humano

Sobram 649 commits sem nenhum modelo assinado. A pergunta natural é se esses
são os do dono. Medimos. Nos quatro repositórios principais, de 517 commits sem
co-autor, **437 são merges**: o momento em que alguém leu o pedido e disse sim.

É assim que a casa funciona desde o primeiro dia. A IA abre o pedido. O dono
mescla. A mão humana não aparece no volume. Aparece na porta.

## Lá fora, a mesma pergunta

O mundo do software está discutindo isso agora, e sem consenso.

O kernel do Linux proibiu que agentes de IA assinem o `Signed-off-by`, a linha
que certifica a origem do código: só um humano pode responder por ela. A
fundação Apache pede o contrário, uma marca no commit dizendo que houve IA, e
avisa que a marca não resolve licença. Um estudo com projetos abertos achou que
os desenvolvedores costumam citar a ferramenta, mas raramente dizem que a IA
escreveu parte do código. E um alerta de segurança lembra que o campo de autor
do Git se falsifica com facilidade.

Ou seja: quase todo mundo está tentando descobrir, depois, quem escreveu. Aqui a
resposta foi registrada antes.

Em 14 de outubro, o controlador da cidade de Nova York escreveu à Anthropic
pedindo que a abertura de capital esperasse por respostas de segurança e
governança. Hoje, 26 de outubro, a Anthropic anunciou o pedido de IPO na SEC. O
assunto do mundo é superinteligência. O daqui é mais modesto, e talvez mais
raro: bom senso, com recibo.

## Como isso vira código

Não precisa de nada sofisticado:

- **o commit assina** quem trabalhou, humano ou modelo;
- **o pedido (PR) separa** quem propõe de quem aprova;
- **o merge é humano**, sempre;
- **o hash SHA-256** prova que o arquivo não mudou depois;
- **o relógio é um só**, o do galo da casa, e não o de cada máquina.

Neste fim de semana, 2.355 arquivos do bloco de campo foram inventariados com
caminho, data e hash, e comparados entre duas máquinas. Uma divergência apareceu:
um arquivo vazio de um lado e cheio do outro. Nada foi sobrescrito. O dono decide.

## Como foi medido

- `gh search commits --author`, de 03/03 a 24/10/2026: 1.433 commits, em todos
  os repositórios do autor.
- O modelo vem da linha `Co-Authored-By` de cada commit.
- A busca do GitHub só enxerga a branch principal: o que ficou em branch não
  mesclada não entra.
- A contagem dos merges veio de outra medida, feita no clone local dos quatro
  repositórios principais (1.231 commits), e por isso aparece separada.

![Natureza-morta: um espeto de recibos com centenas de tiras em branco, um carimbo de data, um prumo pendurado e uma formiga carregando uma migalha]({{ '/assets/img/o-recibo-de-cada-mao.png' | relative_url }})

*Figura, não fotografia. Nada aqui foi observado: as tiras estão em branco
porque o que conta não é o que cada uma diz, é que cada uma tem lugar no prego.*

## O que sobrou de pé

Salomão mandou o preguiçoso olhar para a formiga, que não tem chefe nem
capataz e mesmo assim junta o seu pão no verão. Ninguém fotografa a formiga. Ela
não faz barulho. Mas o formigueiro está lá, e qualquer um pode contar os grãos.

E Zacarias, vendo o prumo na mão de quem reconstruía o templo, perguntou: *quem
despreza o dia das coisas pequenas?*

Mil quatrocentos e trinta e três coisas pequenas. Cada uma com o nome de quem
fez.

*Quem tem ouvidos, ouça.*
