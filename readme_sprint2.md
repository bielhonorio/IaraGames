# IARA GAMES 🎮

> Jogos 100% brasileiros — Sprint 02: Evolução e UX (Desenvolvimento Centrado no Usuário)

Plataforma de distribuição de jogos independentes brasileiros. Este repositório contém a versão evoluída do projeto **Iara Games**, desenvolvida para a Sprint 02 da disciplina de Web Design (FIAP).

**Empresa desenvolvedora:** Masters  
**Fase:** Sprint 2 (Evolução e UX)

---

## 📖 Contexto e Proposta do Projeto

A Iara Games conecta jogadores a jogos independentes brasileiros, transformando a descoberta, a compra e a distribuição de jogos em uma experiência de pertencimento, visibilidade e valorização da produção nacional. Na **Sprint 02**, a plataforma evoluiu com foco em **UX, UI, organização estrutural com grids e HTML semântico, formulários interativos e refinamento centrado no usuário**, respondendo aos desafios reais identificados em pesquisas de mercado.

### Visão, Missão e Posicionamento

- **Visão:** ser a principal porta de entrada para descobrir, valorizar e jogar criações independentes brasileiras, ajudando a formar um ecossistema digital mais diverso, próximo e sustentável.
- **Missão:** distribuir jogos independentes brasileiros com qualidade, visibilidade e respeito às pessoas, aos territórios e às referências culturais que dão origem a cada criação.
- **Posicionamento:** uma plataforma especializada em jogos independentes nacionais, combinando comercialização com curadoria, contexto e proximidade.

### Referência conceitual: Amazofuturismo

O projeto mantém como essência o **Amazofuturismo** — gênero que une a estética indígena do bioma Amazônia a tecnologias e conceitos futuristas. Na Sprint 02, essa identidade se reflete em seis pilares integrados à experiência digital:
1. **Futuro com raízes**
2. **Protagonismo de quem cria sua própria história**
3. **Tecnologia em harmonia com a vida**
4. **Vida como rede**
5. **Estética como conhecimento**
6. **Futuro plural**

---

## 🎯 Usuário e Contexto (Persona)

A partir de pesquisas de experiência (*Desk Research* e questionário com 44 respostas), identificamos as principais dores dos jogadores: **custo elevado, limitações de hardware/espaço e dificuldade de encontrar jogos nacionais**. 

Para guiar o design da Sprint 02, consolidamos a seguinte persona principal:
- **Lucas Martins, 18 anos (Geração Z)** — Jogador frequente e estudante.
- **Objetivos:** Encontrar jogos independentes brasileiros acessíveis, verificar a compatibilidade técnica com seu PC antes de comprar e gerenciar sua biblioteca de forma prática.
- **Dores:** Preços elevados em lançamentos, medo de comprar jogos incompatíveis com seu hardware e fragmentação de launchers.
- **Como a Iara Games ajuda:** Oferecendo filtros avançados por preço, gênero e requisitos técnicos, além de transparência sobre os estúdios nacionais.

---

## ♻️ Alinhamento com os Valores ESG

A estratégia ESG da Iara Games orienta o desenvolvimento da plataforma por meio dos pilares:
- **Ambiental:** Eficiência de recursos digitais, otimização de mídias e escolha de uma arquitetura leve (tecnologia em harmonia com a vida).
- **Social:** Valorização de desenvolvedores brasileiros, fomento à diversidade de narrativas regionais e inclusão digital acessível.
- **Governança:** Critérios transparentes de curadoria, respeito aos direitos autorais e valorização ética de referências culturais.

---

## 🏗️ Estrutura e Layout

- **HTML Semântico:** Utilização rigorosa de tags semânticas (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`) para garantir acessibilidade e SEO.
- **Organização com Grids e Flexbox:** Layout estruturado com CSS Grid para vitrines de jogos e painéis, garantindo responsividade fluida entre dispositivos.
- **Evolução das Páginas:** Além da evolução da Home (agora com carrossel dinâmico e vitrine expandida de destaques), foi estruturada a **página de cadastro/formulário** e a organização de áreas interativas.

---

## 📝 Formulários

Na Sprint 02, desenvolvemos formulários estruturados (como o de cadastro de usuário / perfil de hardware) aplicando rigorosos padrões de usabilidade e acessibilidade:
- **Sem Back-end:** Foco na interface, organização de campos, rótulos claros (`<label>`) associados via `for`/`id`.
- **Validação e Cuidados de UX:** Mensagens de instrução claras, estados de foco evidentes (`:focus-within`) e design responsivo para facilitar o preenchimento sem atritos.

---

## 🎨 UI e UX (Evolução em relação à Sprint 1)

1. **Refinamento Visual:** Evolução da identidade visual, transições suaves e hierarquia tipográfica com *Orbitron* e *Oxanium*.
2. **Carrossel Interativo:** A seção de destaques passou de um modelo estático de 4 jogos para um carrossel dinâmico com vitrine ampliada e indicadores visuais.
3. **Decisões de UX:** Redução da carga cognitiva com camadas de informação progressiva (imagem/nome em primeiro plano, seguidos de estúdio, preço e requisitos técnicos).

---

## ♿ Acessibilidade

As diretrizes de contraste (verificadas via WCAG), suporte a leitores de tela, navegação por teclado e respeito à preferência `prefers-reduced-motion` continuam integradas de forma nativa. Para detalhes técnicos, consulte o arquivo [`ACESSIBILIDADE.md`](./ACESSIBILIDADE.md).

---

## 🗂️ Estrutura do Projeto

```
├── index.html
├── cadastro.html
├── README.md
├── ACESSIBILIDADE.md
├── CSS/
│   └── styles.css
├── Imagens/
│   ├── logo_IARA_GAMES.svg
│   ├── video.mp4
│   └── ...
└── Fonte/
    └── orbitron-master/
```

## 🚀 Como Visualizar

1. Clone o repositório:
   ```bash
   git clone https://github.com/bielhonorio/IaraGames.git
   ```
2. Abra o arquivo `index.html` em seu navegador de preferência.

---

## 👥 Equipe

- André Guima Gonçalves — RM576031
- Stéfany Binelo da Rosa — RM576326
- Daniely Bittencourt Grutzmann Muzeka — RM575991
- Gabriel Honorio Queiroz — RM574855
- Nicole Toscano — RM574909

---
*Projeto desenvolvido para a disciplina de Web Design — FIAP.*