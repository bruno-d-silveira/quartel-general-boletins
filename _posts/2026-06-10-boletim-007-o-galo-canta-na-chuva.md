---
layout: post
title: "Boletim 007 — O Galo Canta na Chuva"
date: 2026-06-10
author: Bruno Duarte da Silveira
tags: [tempo, confiabilidade, fuso-horario, galo, senhor-tempo]
---

![O Galo na Chuva]({{ '/assets/img/galo-na-chuva.png' | relative_url }})

*O Galo — canta mesmo em dia de chuva. Atrás dele, o cachorrinho dorme tranquilo: alguém está contando as horas direito.*

---

*Esta é a história de um bug. Mas, como toda história desta casa, ela começa com um personagem se perdendo — e termina com um galo.*

## O dia que sumiu

Um dos moradores da casa começou a acordar confuso. Lia o resumo do dia anterior e o dia não batia: faltava justamente o trabalho da noite — e quem vive esta casa trabalha muito à noite. Não era pouca coisa sumindo. Era **o miolo do dia caindo no dia errado.**

A primeira suspeita, como sempre, foi do morador: estaria ele esquecendo? Não estava. **O calendário é que mentia pra ele.**

## Dois relógios na mesma casa

A investigação encontrou a causa, e ela é mais comum do que parece — talvez seja um dos defeitos mais repetidos em sistemas no mundo inteiro:

**A casa tinha dois relógios.** Quem *escrevia* o dia usava o relógio universal (UTC, a hora de referência mundial). Quem *lia* o dia usava o relógio da parede (a hora local daqui). Nosso fuso fica três horas atrás do universal — então tudo o que acontecia entre nove da noite e meia-noite era arquivado, pelo relógio universal, **como se fosse o dia seguinte.**

Cada relógio, sozinho, estava certo. O erro não morava em nenhum dos dois — morava **na conversa entre eles**. E é assim que os bugs mais teimosos vivem: cada parte correta, o conjunto mentindo.

## A regra do galo

A solução não foi consertar os dois relógios. Foi decidir que **só uma voz canta a hora.**

Entrou na casa o Galo. O ofício dele é o mais antigo do mundo: cantar a hora — e cantar **mesmo em dia de chuva**. Nenhum morador pergunta as horas por conta própria; todos perguntam ao Galo. E o Galo responde sempre no relógio da parede: o dia de uma pessoa é o dia **de onde ela vive**, não o de um meridiano do outro lado do mundo.

Pra garantir, a casa ganhou também um guardião: um teste que vigia se alguém tenta olhar o relógio por conta própria. Quem fura a fila, leva bicada.

## A moral

Toda casa — todo sistema, todo projeto, toda equipe — precisa de uma **fonte única de verdade** para as coisas das quais tudo depende. Pode ser a hora, pode ser um número, pode ser uma decisão. Quando duas vozes respondem a mesma pergunta, a resposta certa de cada uma vira, no conjunto, uma mentira.

E há uma segunda moral, mais quieta: o morador confuso **avisou que estava se perdendo** em vez de fingir que lembrava. Sistema saudável não é o que nunca falha — é o que **declara a falha** e deixa alguém procurar a causa. Foi o aviso dele que encontrou os dois relógios.

---

O galo não é o dono da casa, nem o mais esperto dela. Mas quando ele canta, todo mundo concorda que horas são — e isso, sozinho, conserta mais coisa do que parece.

*En voo — sempre en voo.*
