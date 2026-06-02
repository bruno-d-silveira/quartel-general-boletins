---
layout: post
title: "Boletim 001 — Montando o Quartel General"
date: 2026-06-02
author: Bruno Duarte da Silveira
tags: [setup, seguranca, licenca, POLC]
---

Todo projeto sério começa antes da primeira linha de código que importa: começa na **organização**. Este é o despacho inaugural do Quartel General — o campo de treino onde construo as peças em volta do BRAIN.

## Por que um "quartel general"

Eu carrego um fundamento do curso de administração: **POLC** — Planejamento, Organização, Liderança e Controle. Antes de sair codando, eu monto o terreno. Um lugar separado pra treinar, prototipar e errar à vontade — sem encostar no motor de verdade.

## Decisão 1 — Segurança desde o commit zero

A primeira coisa que entrou no repositório não foi código. Foi o `.gitignore`.

Ele bloqueia, desde o início, tudo que **nunca** pode vazar: `.env`, chaves (`*.key`, `*.pem`), credenciais, e o ambiente Python (`.venv/`). A lógica é simples: é muito mais fácil **nunca deixar entrar** do que tentar remover depois — porque o histórico do Git tem memória longa. Um segredo commitado uma vez fica lá pra sempre.

> Lição: trate o `.gitignore` como o porteiro da casa. Ele trabalha antes de todo mundo.

## Decisão 2 — A licença (e uma armadilha que quase ninguém vê)

Escolher licença não é burocracia — é estratégia. Comparei três:

- **MIT** — a mais permissiva, mas não fala nada sobre patentes.
- **Apache 2.0** — permissiva **e** com concessão de patente explícita. Padrão de fundações e uso corporativo.
- **AGPL-3.0** — copyleft forte; fecha a "brecha do SaaS" (quem roda o software modificado na nuvem é obrigado a abrir o código).

A armadilha que aprendi pesquisando: existe um padrão que se repete — um projeto pega tração com uma licença permissiva, um gigante da nuvem lança uma versão gerenciada por cima, e o projeto original fica pra trás. Licença permissiva não protege contra isso.

Pra este campo de treino, fui de **Apache 2.0** (proteção de patente + amplo uso). Mas registrei a nota: pro produto-missão — que existe justamente pra **não** alimentar monopólio de dados — a **AGPL-3.0** é mais alinhada. Licença é uma decisão viva.

## Decisão 3 — Cofre e Vitrine

O Quartel General é **privado** (o cofre). Mas o **aprendizado** é público — é este boletim que você está lendo (a vitrine). A fórmula fica guardada; a lição é de todos.

É o princípio que guia o projeto inteiro: **ensinar a pescar, não dar o peixe.**

## Próximo despacho

Construir o esqueleto do **Carteiro** — a peça que pega o que foi anotado offline e entrega a quem precisa ler. Aos poucos. Tijolo por tijolo.

*En voo — sempre en voo.*
