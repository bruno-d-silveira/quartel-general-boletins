---
layout: post
title: "Boletim 021 — A Carta que Chegou e Não Foi Aberta"
date: 2026-07-24
author: Bruno Duarte da Silveira
tags: [handoff, proveniencia, passarinho, reconciliacao, testes, instrumento, recibo]
image: /assets/img/passarinho-voo02-reconciliado.gif
description: "Um trabalho terminado às 23h07 de 16 de julho passou oito dias sem nunca rodar. Não foi apagado nem rejeitado: ficou num pen drive, ao lado do documento que explicava o que era."
---

![O mesmo voo do Boletim 019 — agora com a fragata que cresce]({{ '/assets/img/passarinho-voo02-reconciliado.gif' | relative_url }})

*O mesmo voo do Boletim 019: semente 153, cento e trinta e oito quadros,
cinco árvores desviadas, pouso na pista. Os números não mudaram porque a
física não mudou. O que mudou está no bicho: ele **cresce** durante a
travessia — filhote `>` na floresta, juvenil `=>` no mar. Essa era a
versão que existia desde 16 de julho e nunca tinha rodado. Selo
`5F61C6C4…` no cofre.*

---

*No Boletim 019, a casa mostrou o primeiro film reel e cravou: o artefato
é o fato. Estava certo. Faltava a segunda metade da frase — o fato
precisa de procedência.*

---

## O que se descobriu hoje

Um trabalho terminado em 16 de julho, às 23h07, **passou oito dias sem
nunca rodar**. Não foi apagado, não foi rejeitado, não deu erro. Ficou
num pen drive, dentro de uma pasta, ao lado do documento que explicava
exatamente o que ele era e o que precisava ser feito com ele.

Enquanto isso, a casa seguiu trabalhando por cima da versão anterior —
com competência, e sem nenhum sinal de que faltava alguma coisa.

## A linha do tempo, pelo `git log`

O jogo do passarinho — o easter egg do motor, aquele mesmo do film reel —
foi construído por três mãos em três momentos. Cada uma entregou o que
prometeu:

| Quando | Quem | O que entregou | Onde foi parar |
|---|---|---|---|
| 16/07, 01h12 | Polvo | A base: física de fragata, três fases, circuito olímpico, evento no data lake — **461 linhas** | Repositório, PR #72 |
| 16/07, 23h07 | Fable 5 | A versão final: quarta fase, quatro finais, oito constelações, o bicho que cresce, correção do teclado — **685 linhas** | **Pen drive. Só.** |
| 17/07, 13h44 | Fable 5 | As cores da casa e as sete estrelas nomeadas — **86 linhas** | Repositório, sobre a base de 01h12 |
| 17/07, 14h35 | Fable 5 | O primeiro film reel (o GIF do Boletim 019) | Gravado da versão sem a quarta fase |
| 23/07, 21h45 | Polvo | Tipagem estática: 54 erros zerados em 18 arquivos | Sobre o ramo que já estava separado |
| 24/07 | 4.8 | A reconciliação | Este boletim |

Ninguém errou de ofício. O que falhou foi o **elo**: a entrega das 23h07
chegou fisicamente à casa e nunca foi conferida contra o repositório.

## O diagnóstico: handoff sem recibo

O documento que veio junto com o trabalho tinha uma lista de quatro
tarefas. **As quatro continuam desmarcadas até hoje** — a primeira delas
é literalmente *"aplicar no motor"*.

E a falha foi nas duas direções. No pacote de ida, quem escreveu a base
prometeu deixar um arquivo de apoio no pen drive. Ele não estava lá — o
próprio documento de volta registra a ausência, em uma linha, e segue o
trabalho sem ela. Duas máquinas, um pen drive, dois turnos de trabalho, e
**nenhum mecanismo que perguntasse: o que eu mandei chegou? o que chegou
foi aplicado?**

Aqui há uma ironia que a casa registra sem desconto. Este sistema tem um
carteiro. Tem um passarinho verde que só levanta voo com aprovação
explícita, frase-código, lacre e recibo — e testes que garantem que nada
voa sem o sim do dono. Todo esse cuidado existe para os dados. **Para o
próprio trabalho da casa, o transporte era um pen drive e a esperança.**

Vale registrar também o que *não* foi a causa. Houve um travamento de
máquina naquela semana, documentado na hora, com relatório de recuperação
que concluía: *zero dados perdidos*. A conclusão estava correta — e ainda
assim faltava coisa. **Nada se perdeu; algo nunca foi conferido.** São
falhas diferentes, e só a segunda sobrevive a um relatório de incidente
bem-feito.

## O que foi feito

A reconstrução foi mecânica justamente porque os dois ramos descendiam do
mesmo ponto. Nada precisou ser reescrito, e **nada do trabalho de
ninguém foi descartado**:

- A versão final voltou a ser a base, e as 86 linhas de cor foram
  enxertadas nela. O arquivo saiu de 534 para **802 linhas** — a soma real
  do que já existia, não código novo.
- As sete estrelas nomeadas ficaram sobre o mar como prólogo; a mesma
  constelação volta desenhada inteira na quarta fase. Não competem: são
  trechos diferentes da travessia.
- O film reel foi **regravado da versão certa**. Mesma semente, mesmos
  138 quadros, mesmas 5 árvores — a prova de que a física não foi tocada.
- **Dezenove funções de teste, trinta e sete casos**, para um componente
  que não tinha nenhum. Suíte completa do repositório: 115 passando, zero
  regressão.

## O instrumento, descrito pela primeira vez

Aproveitou-se a ocasião para escrever o que nunca tinha sido escrito: o
que esse jogo **mede**. Ele não é só um easter egg — é um instrumento que
manda resultado para o data lake.

Três correções que só aparecem quando se lê o código em vez de admirar a
tela:

**Ele não mede tempo de reação.** Não existe, em lugar nenhum, registro
de latência entre um estímulo e uma tecla. O que existe é um **limiar de
velocidade sustentável**: na quarta fase o jogo dobra de velocidade a cada
25 segundos, e a medida é a velocidade em que o controle acabou. É uma
medida boa — monotônica, com unidade, comparável consigo mesma. Não é a
outra, e chamar de tempo de reação seria mentira confortável.

**E é uma medida composta.** Como a física roda por quadro e não por
segundo, quando a taxa dobra a gravidade efetiva quadruplica. A
dificuldade cresce mais rápido que a velocidade. Serve para comparar o
piloto com ele mesmo; não serve para comparar com literatura.

**Faltavam três coisas para os dados formarem série** — e as três foram
corrigidas hoje: o evento não dizia de que versão do jogo tinha saído
(e, como se viu, havia duas em circulação); o terreno era sorteado sem
guardar a semente, então duas partidas não eram comparáveis; e das três
tentativas do circuito, só a melhor era gravada — apagando exatamente a
variação dentro da sessão, que é o sinal mais interessante.

## Ensinar a pescar

O padrão desta semana vale para qualquer equipe, com ou sem IA — e vale
especialmente para quem trabalha com vários assistentes ao mesmo tempo:

1. **Entrega sem recibo é rascunho.** Enquanto ninguém confirmou que
   chegou *e* que foi aplicado, o trabalho não existe. O `git log` é o
   recibo; o pen drive é o envelope.

2. **"Zero dados perdidos" não é o mesmo que "nada faltando".** Um
   relatório de incidente só enxerga o que ele sabe procurar. Perda
   silenciosa não aparece em log nenhum — aparece quando alguém compara.

3. **Todo dado que vira série precisa dizer de onde veio.** Versão e
   semente custam duas linhas e são a diferença entre um histórico e uma
   pilha de números que não se comparam.

4. **Antes de escrever sobre um componente, abra o componente.** A
   descrição bonita de um sistema é fácil de produzir sem ler o código —
   e é exatamente assim que se publica uma frase errada com toda
   confiança.

5. **O gargalo raramente é a capacidade; é a costura.** Três entregas
   competentes valeram menos que duas, porque ninguém conferiu a junta.

## O elo que faltava

A casa nomeou essa raiz ontem, ao começar um manual de operação para os
próprios agentes: *cada conversa começa do zero*. Este boletim é a prova
empírica do custo disso — oito dias de um trabalho pronto parado, e um
film reel publicado a partir da versão que não era a final.

O artefato continua sendo o fato. Só que agora ele vem com endereço,
carimbo e recibo — como toda carta que se preze.

---

*Este boletim conversa com a série de artigos científicos do autor no
LinkedIn. O anterior, sobre a contagem honesta, defendeu que ciência boa
mostra a conta inteira. Esta semana a conta era da própria casa.*
