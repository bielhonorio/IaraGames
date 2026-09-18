# IARA GAMES 🎮

> Jogos 100% brasileiros — Sprint 01: Uma Nova Jornada

Plataforma de distribuição de jogos independentes brasileiros. Este repositório contém a primeira versão conceitual e visual do projeto **Iara Games**, desenvolvida como parte da disciplina de Web Design (FIAP).

---

## 📖 Contexto e Proposta do Projeto

<!--
TODO: Escrever aqui um breve parágrafo explicando o que é a Iara Games,
qual problema ela resolve e para quem é destinada.

Sugestão de estrutura:
- O que é a plataforma
- Por que "Iara" como nome/tema (conexão com a lenda + identidade "amazofuturista")
- Público-alvo (jogadores? desenvolvedores/estúdios independentes brasileiros?)
- Diferencial em relação a outras plataformas
-->

*(preencher com o time)*

### Pesquisa de plataformas de distribuição de jogos

Como referência de mercado, analisamos 3 plataformas de distribuição de jogos já consolidadas:

<!--
TODO: Preencher com 3 plataformas pesquisadas (ex: Steam, Epic Games Store, itch.io)
Sugestão de tópicos por plataforma:
- O que ela faz bem (referência positiva)
- O que poderia ser diferente na Iara Games
-->

1. **[Nome da plataforma]** — *(observações)*
2. **[Nome da plataforma]** — *(observações)*
3. **[Nome da plataforma]** — *(observações)*

---

## 🎨 Design (GDW)

### Paleta de cores

A paleta conecta **natureza e tecnologia**, unindo tons profundos (inspirados na floresta amazônica) com cores vibrantes de contraste, seguindo o conceito de identidade **"Amazofuturismo"**.

Optamos por organizar as cores em **duas camadas** no CSS: tokens de cor "crus" (a cor em si) e variáveis semânticas (o papel que cada cor cumpre na interface — fundo, texto, CTA, link). Isso facilita manutenção: se uma cor mudar, o ajuste é feito em um único lugar, e toda a interface se atualiza.

| Cor | Hex | Uso na interface |
|---|---|---|
| 🔵 Azul Noite | `#0F172E` | Fundo principal |
| 🟢 Verde Floresta | `#1B4034` | Cards, menus, áreas secundárias |
| 🟢 Verde Terra | `#283415` | Fundos de apoio |
| 🔴 Vermelho Terra | `#8C141E` | Destaques, badges |
| 🔴 Vermelho Vivo | `#F23535` | CTAs, ações importantes |
| 🟢 Verde Água | `#219F8A` | Links, ícones, elementos de tecnologia |
| 🟢 Verde Neon | `#5AF989` | Hover, elementos interativos, destaques |
| ⚪ Branco Neve | `#EFF1F4` | Textos principais, alto contraste |

> A relação de contraste entre as principais combinações de texto/fundo foi verificada segundo os critérios da WCAG — detalhes no documento [`ACESSIBILIDADE.md`](./ACESSIBILIDADE.md).

### Tipografia

| Uso | Fonte | Observação |
|---|---|---|
| Títulos (`--font-title`) | **Orbitron** (Bold) | Fonte carregada localmente (`@font-face`), com visual futurista alinhado à identidade "amazofuturista" |
| Corpo de texto (`--font-text`) | **Oxanium** | Carregada via Google Fonts, boa legibilidade em telas pequenas |

> As fontes originais definidas no moodboard da marca (Catchy Mager e HK Gothic) são comerciais e não estão disponíveis no Google Fonts. Optamos por alternativas com estética "gamer/tech" compatíveis com o clima visual do projeto, evitando problemas de licenciamento em um repositório público.

### Decisões visuais

1. **Efeito "glass" no header e nos cards** — fundo semitransparente (`rgba`) combinado com `backdrop-filter: blur()`, criando sensação de profundidade e camadas sobre o fundo escuro, reforçando a estética "tecnológica" da identidade visual.

2. **Vídeo em loop no Hero** — em vez de uma imagem estática, o hero usa um vídeo de fundo em loop (`autoplay muted loop`), com uma camada de overlay escuro por cima para garantir contraste e legibilidade do texto.

3. **Botão CTA com efeito de preenchimento animado** — o botão "Explorar jogos" nasce apenas com contorno (stroke), e no hover um preenchimento com leve desfoque (`blur`) "varre" da esquerda para a direita, trocando também a cor do texto para manter o contraste. O efeito comunica interatividade sem ser exagerado.

4. **Cards de jogos com opacidade progressiva** — os cards da seção "Jogos em destaque" começam com opacidade reduzida (50%) e ficam totalmente visíveis no hover/foco, convidando à exploração ativa do catálogo (ver justificativa de acessibilidade no documento dedicado).

---

## ♿ UX e Acessibilidade

As decisões de acessibilidade do projeto — paleta com contraste verificado (WCAG), estrutura semântica, formulários acessíveis, navegação por teclado, respeito a `prefers-reduced-motion`, entre outras — estão documentadas em detalhe no arquivo:

📄 **[`ACESSIBILIDADE.md`](./ACESSIBILIDADE.md)**

---

## 🗂️ Estrutura do projeto

```
├── index.html
├── README.md
├── ACESSIBILIDADE.md
├── CSS/
│   └── styles.css
├── Imagens/
│   ├── logo_IARA_GAMES.svg
│   ├── logo_IARA_GAMES.png
│   ├── video.mp4
│   └── img_1.jpg, img_2.jpg, img_3.jpg, img_4.jpg
└── Fonte/
    └── orbitron-master/
        └── Orbitron Bold.otf
```

## 🛠️ Tecnologias

- **HTML5** semântico
- **CSS3** (Flexbox, Grid, variáveis CSS/Custom Properties, `@font-face`)
- Sem JavaScript e sem back-end nesta sprint (conforme escopo definido)

## 🚀 Como visualizar o projeto

1. Clone este repositório:
   ```bash
   git clone [URL_DO_REPOSITORIO]
   ```
2. Abra o arquivo `index.html` diretamente no navegador (duplo clique, ou clique com o botão direito → "Abrir com" → navegador de sua preferência).

> Não é necessário instalar nada — o projeto é 100% estático (HTML + CSS).

## 👥 Equipe

<!-- TODO: adicionar nomes e RMs dos integrantes -->
- Nome — RM
- Nome — RM

---

*Projeto desenvolvido para a disciplina de Web Design — FIAP.*
