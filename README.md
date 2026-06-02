# Quartel General — Boletins (a Vitrine pública) 🌐

Site público (GitHub Pages) com os **Boletins técnicos** do treinamento do BRAIN.
Este repo é a **Vitrine**. O **Cofre** (código, fórmula, experimentos) é privado e fica em `treinamento-quartel-general`.

> **Modelo Cofre & Vitrine:** o motor é privado; a narrativa/aprendizado é pública.
> Modelo Maurício de Sousa aplicado ao código.

## O muro editorial (o "C" do POLC — Controle)
Nada cruza pra cá sem passar pelo filtro do dono:
- ✅ Sem **fórmula** (o segredo do motor fica no cofre)
- ✅ Sem **segredos** (chaves, .env, credenciais)
- ✅ Sem **dado pessoal/real**
- ✅ Revisado pelo dono antes do commit

## Como adicionar um Boletim
1. Crie um arquivo em `_posts/AAAA-MM-DD-titulo.md`.
2. Comece com o cabeçalho (front matter):
   ```
   ---
   layout: post
   title: "Boletim 00X — Título"
   date: 2026-06-02
   author: Bruno Duarte da Silveira
   tags: [tag1, tag2]
   ---
   ```
3. Escreva em markdown. Commit + push. O site atualiza sozinho.

## Como publicar (GitHub Pages)
1. Crie um repo **público** no GitHub chamado `quartel-general-boletins`.
2. `git push` (o MO 4.8 te ajuda a conectar o remote).
3. No GitHub: **Settings → Pages → Build from branch → `main` / root**.
4. O site nasce em: `https://SEU-USUARIO.github.io/quartel-general-boletins/`

---

*Apache-2.0 no cofre; aqui os textos são do autor. Rigor com alma.*
