# IARA GAMES 🎮

> Jogos 100% brasileiros

Plataforma de distribuição de jogos independentes brasileiros, desenvolvida pela equipe de desenvolvimento da **Master3** para a disciplina de Web Design (FIAP). Este repositório reúne a evolução do projeto, sprint a sprint.

**Cliente:** Iara Silva, 28 anos, ilustradora e designer

🔗 **Repositório:** https://github.com/bielhonorio/IaraGames

<!-- TODO (equipe): se o GitHub Pages estiver ativo, adicione aqui o link do site publicado. -->

---

## 📌 Evolução do projeto

| Sprint | Foco | O que foi entregue |
|---|---|---|
| **1 · Uma nova jornada** | Conceito, identidade e visão inicial | Proposta, pesquisa de mercado, paleta, tipografia e uma Home estática em HTML e CSS |
| **2 · Usuário e estrutura** | Entender quem usa a plataforma | Desk research, questionário, personas, jornadas, ESG, carrossel, responsividade e a página de cadastro |
| **3 · Bootstrap** *(atual)* | Aplicar a identidade com um framework moderno | Home e área do usuário reconstruídas com Bootstrap 5.3, mais o cadastro, com foco em responsividade e acessibilidade |

---

# Sprint 3: identidade visual com Bootstrap

## Páginas desenvolvidas

| Página | Arquivo | Papel na entrega |
|---|---|---|
| Home | `Sprint_3/index.html` | Página principal (obrigatória) |
| Área do usuário | `Sprint_3/area-usuario.html` | Página extra, de escolha livre (obrigatória) |
| Cadastro | `Sprint_3/cadastro.html` | Página adicional, também convertida para Bootstrap |

**Por que a área do usuário como página extra?** A jornada da persona Matheus (18 anos, SSD de 256 GB, esquece os jogos que já comprou) mostrou que ele precisa **ver o espaço do disco, filtrar a biblioteca e instalar ou jogar sem demora**. A página reúne o menu do jogador, a biblioteca com barra de armazenamento e filtros, o perfil de hardware (com aviso de compatibilidade) e o histórico de compras e licenças.

<!-- TODO (equipe): se quiser, adicione aqui os prints das páginas (por exemplo, em docs/prints/). -->

## Identidade visual aplicada

### Logotipo
A logo da marca (**IARA GAMES · Jogos 100% brasileiros**) é usada no topo de todas as páginas, como link para a Home, e no rodapé, onde também leva de volta ao topo. É um arquivo SVG, que se mantém nítido em qualquer tamanho.

### Paleta de cores
A paleta conecta **natureza e tecnologia**: tons profundos, inspirados na floresta amazônica, com cores vibrantes de contraste. No CSS ela está em duas camadas: os **tokens crus** (a cor em si) e as **variáveis semânticas** (o papel da cor na interface). Para o Bootstrap, as variáveis `--bs-*` do tema escuro apontam para essa paleta, então os componentes já nascem com a identidade, sem brigar com o framework.

| Cor | Hex | Uso na interface |
|---|---|---|
| 🔵 Azul Noite | `#0F172E` | Fundo principal |
| 🟢 Verde Floresta | `#1B4034` | Cards, menus, áreas secundárias |
| 🟢 Verde Terra | `#283415` | Fundos de apoio |
| 🔴 Vermelho Terra | `#8C141E` | Destaques, hover do botão de sair |
| 🔴 Vermelho Vivo | `#F23535` | CTAs, alertas (barra de disco cheio) |
| 🟢 Verde Água | `#219F8A` | Links, bordas, ícones |
| 🟢 Verde Neon | `#5AF989` | Destaques, hover, ações principais |
| ⚪ Branco Neve | `#EFF1F4` | Textos principais |

### Tipografia
| Uso | Fonte | Origem |
|---|---|---|
| Títulos | **Orbitron** (Bold) | Arquivo local (`@font-face`) |
| Texto | **Oxanium** | Google Fonts |

As fontes do moodboard original (Catchy Mager e HK Gothic) são comerciais e não estão no Google Fonts. Escolhemos alternativas com estética "gamer/tech", compatíveis com o clima visual do projeto e sem problema de licença em um repositório público.

### Justificativas de aplicação
- **Fundo Azul Noite com texto Branco Neve:** cria a atmosfera noturna da floresta e entrega o maior contraste da paleta.
- **Verde Neon só onde há ação ou destaque** (botões principais, hover, preços, item ativo): guia o olhar para o que a pessoa pode fazer.
- **Vermelho Vivo reservado a alertas e CTAs:** a barra do disco quase cheio e o botão de destaque da Home usam a cor que "chama atenção", e nada mais.
- **Efeito "vidro" nos cards e painéis** (verde translúcido): dá profundidade e reforça o visual tecnológico.
- **Vídeo em loop no hero**, com uma camada escura por cima para garantir a legibilidade do texto.
- **Botão de chamada com contorno que se preenche de vermelho no hover:** comunica interatividade sem exagero.
- **Orbitron nos títulos** traz o ar futurista, e **Oxanium no corpo** mantém a leitura confortável.

## Recursos do Bootstrap utilizados

Versão **5.3.8** e **Bootstrap Icons 1.13.1**, ambos por CDN. A personalização foi feita por **variáveis CSS** (`--bs-*`) e por classes próprias com prefixo da marca (`btn-iara`, `card-iara`...), sem reescrever o framework.

| Recurso | Onde aparece |
|---|---|
| **Navbar responsiva** (`navbar`, `navbar-expand-lg`, `navbar-toggler`, `collapse`, `sticky-top`) | Header de todas as páginas, com menu hambúrguer abaixo de 992px |
| **Grid** (`container`, `row`, `col-*`, `row-cols-*`, `g-*`) | Hero, jogos em destaque, rodapé, área do usuário, cadastro |
| **Carousel** (`carousel`, `carousel-item`, controles e indicadores) | Jogos em destaque da Home, com rotação cíclica e sem autoplay |
| **Cards** (`card`, `card-body`, `card-header`, `card-footer`, `stretched-link`, `ratio`) | Jogos da Home e blocos da área do usuário |
| **Offcanvas responsivo** (`offcanvas-lg`) | Menu do jogador: fixo na lateral no desktop, painel deslizante no celular |
| **Nav pills, badge, breadcrumb, progress** | Menu lateral, etiquetas de status, caminho da página, barras de XP e de armazenamento |
| **List group** | Lista de jogos da biblioteca |
| **Tabela responsiva** (`table`, `table-responsive`) | Histórico de compras e licenças |
| **Formulários** (`form-label`, `form-control`, `form-select`, `input-group`, `form-text`, `form-check`, `form-switch`, `btn-check`) | Busca, filtros da biblioteca, aviso de compatibilidade e cadastro |
| **Validação de formulário** (`needs-validation`, `invalid-feedback`) | Cadastro, com mensagens de erro por campo |
| **Botões** (`btn`, `btn-sm`, `btn-lg` + variantes próprias via `--bs-btn-*`) | Todas as páginas |
| **Utilitários** (`d-flex`, `d-none`/`d-md-*`, `gap-*`, `p-*`, `m-*`, `text-*`, `position-*`, `object-fit-*`, `visually-hidden`, `visually-hidden-focusable`) | Layout, espaçamento, responsividade e acessibilidade |
| **Tema escuro** (`data-bs-theme="dark"`) | Base de cores de todo o site |

**Pontos de quebra usados:** `sm` (576px), `md` (768px), `lg` (992px) e `xl` (1200px).

## Acessibilidade

Resumo dos recursos aplicados (o detalhamento, com os **cálculos de contraste** e as **limitações conhecidas**, está em 📄 **[`ACESSIBILIDADE.md`](./ACESSIBILIDADE.md)**):

- Tags semânticas (`header`, `nav`, `main`, `aside`, `section`, `footer`), um `<h1>` por página e *skip link*.
- Contraste conferido pela fórmula da WCAG: texto principal em **15,70:1** e destaque em neon em **12,98:1**; os pares abaixo de 4,5:1 foram corrigidos ou limitados a bordas e ícones.
- Foco visível em todos os controles e navegação completa por teclado.
- Formulários com rótulos, dicas e erros ligados ao campo, e foco levado ao primeiro erro.
- Texto alternativo nas imagens, rótulos de texto nos botões de ícone e tabela com título e cabeçalhos.
- `prefers-reduced-motion`: o vídeo do hero some para quem pede movimento reduzido.
- Informação nunca só por cor (ícone e texto nos alertas e status, links sublinhados no texto corrido).

## Estrutura do repositório

```
IaraGames/
├── README.md
├── ACESSIBILIDADE.md
├── Sprint_1/
├── Sprint_2/
└── Sprint_3/
    ├── index.html
    ├── area-usuario.html
    ├── cadastro.html
    ├── CSS/
    │   └── styles.css
    ├── Imagens/
    │   ├── logo_IARA_GAMES.svg
    │   ├── video.mp4
    │   └── (capas dos jogos)
    └── Fonte/
        └── orbitron-master/
            └── Orbitron Bold.otf
```

## Tecnologias

- HTML5 semântico e CSS3 (variáveis, `@font-face`, `@media`)
- Bootstrap 5.3.8 e Bootstrap Icons (por CDN)
- JavaScript: apenas o do Bootstrap, mais um pequeno script próprio de validação no cadastro

## Como visualizar

1. Clone o repositório:
   ```bash
   git clone https://github.com/bielhonorio/IaraGames.git
   ```
2. Abra `Sprint_3/index.html` no navegador (duplo clique).

> O Bootstrap, os ícones e a fonte Oxanium vêm de CDN, então é necessário ter **conexão com a internet** para ver o visual completo.

## Limitações desta etapa

- Filtros, botões de instalar/jogar/desinstalar e de reembolso são **apenas interface**, ainda sem back-end.
- Alguns links do menu (Explorar, Estúdios, Ofertas, Biblioteca) apontam para páginas **ainda não criadas**, que devem entrar nas próximas etapas.
- O cadastro é uma **demonstração**: nenhum dado é enviado ou armazenado.
- As páginas poderão evoluir nas próximas atividades, compondo o portfólio completo da plataforma.

---

# Sprint 2: usuário, estrutura e formulários

<details>
<summary><strong>Ver conteúdo da Sprint 2</strong></summary>

## Pesquisa e usuários

**Desk research** em cinco referências: Steam, Epic Games Store, Nuuvem, itch.io e MobyGames, comparando proposta de valor, organização das informações, descoberta de jogos, catálogos, ofertas e avaliações. Também foi estudada a **Pesquisa Game Brasil 2025**, que registrou que 82,8% dos entrevistados têm o hábito de consumir jogos digitais.

**Questionário:** 44 respostas, que indicaram que a Iara Games pode se diferenciar ao facilitar a descoberta de jogos, oferecer informações claras para decisões mais seguras e valorizar a produção independente brasileira.

**Padrões identificados:**
- *Sensibilidade a preço e barreiras técnicas*: o custo elevado dos jogos (34 de 41 respostas), limitações de hardware (13 de 41) e falta de armazenamento (12 de 41).
- *Descoberta visual e valorização cultural*: a descoberta se dá por vídeos e transmissões ao vivo (31 de 41) e recomendações de amigos (17 de 41).

## Personas

| | **Lucas Martins, 18 anos** | **Marina Oliveira, 31 anos** |
|---|---|---|
| Perfil | Jogador frequente, busca custo-benefício | Jogadora exploradora, interessada em jogos independentes |
| Frase | "Quero encontrar um jogo que combine comigo sem gastar dinheiro à toa." | "Quero descobrir jogos que tenham algo diferente para contar, principalmente histórias que me representem." |
| Dores | Preços altos, medo de se arrepender, limitação de hardware e armazenamento, jogos espalhados em vários launchers | Pouca visibilidade dos independentes, falta de contexto sobre quem criou o jogo, insegurança ao escolher um título desconhecido |
| Como a Iara ajuda | Filtros por preço, gênero e requisitos técnicos; comparação de jogos; informação clara para decidir | Curadoria de independentes brasileiros, histórias dos jogos e dos desenvolvedores, descoberta por interesse |

**Jornadas por área da plataforma:** Loja (Lucas, 21 anos), Área do usuário (Matheus, 18 anos), Biblioteca (Camila, 26 anos), Fórum (Lucas, 24 anos) e Suporte (Beatriz, 29 anos).

## ESG

A estratégia ESG está ligada aos seis pilares amazofuturistas do projeto:
- **Social:** valorizar desenvolvedores brasileiros, ampliar a descoberta de produções independentes e reconhecer a diversidade de territórios e trajetórias.
- **Governança:** critérios transparentes de curadoria, reconhecimento de autoria, respeito aos direitos e contextualização de referências culturais.
- **Ambiental:** eficiência dos recursos digitais, otimização de conteúdos e uma experiência tecnológica responsável.

## Decisões de UX e UI

Descoberta orientada · Navegação objetiva · Informações em camadas · Confiança e contexto · Acessibilidade · Linguagem local. A diretriz central: *a camada poética da marca enriquece a experiência, nunca substitui informação funcional nem dificulta a navegação.*

## O que mudou no código

- Home com **carrossel de até 8 jogos** (4 visíveis), setas de navegação e layout responsivo.
- **Página de cadastro** com formulário acessível (rótulos, tipos de campo, validação nativa e mensagem de confirmação).
- Correções de contraste e de acessibilidade, documentadas em `ACESSIBILIDADE.md`.

</details>

---

# Sprint 1: conceito e visão inicial

<details>
<summary><strong>Ver conteúdo da Sprint 1</strong></summary>

## Proposta

A Iara Games conecta jogadores a jogos independentes brasileiros, transformando a descoberta, a compra e a distribuição de jogos em uma experiência de pertencimento, visibilidade e valorização da produção nacional. A plataforma é dedicada exclusivamente à produção brasileira de games, criando um espaço onde jogadores podem descobrir novos títulos, conhecer seus criadores e apoiar diretamente desenvolvedores e estúdios que contribuem para a construção de uma indústria brasileira de jogos com identidade própria.

Mais do que uma plataforma de distribuição, a Iara Games busca fortalecer a relação entre os jogos, seus criadores e o público, dando visibilidade a diferentes histórias, perspectivas, culturas e expressões presentes no Brasil. A plataforma também pretende estabelecer parcerias com instituições educacionais, ampliando o acesso à cultura local por meio dos jogos digitais.

### Visão, missão e posicionamento
- **Visão:** ser a principal porta de entrada para descobrir, valorizar e jogar criações independentes brasileiras, ajudando a formar um ecossistema digital mais diverso, próximo e sustentável.
- **Missão:** distribuir jogos independentes brasileiros com qualidade, visibilidade e respeito às pessoas, aos territórios e às referências culturais que dão origem a cada criação.
- **Posicionamento:** uma plataforma brasileira especializada em jogos independentes nacionais. Diferentemente de lojas globais com catálogos extensos e generalistas, a Iara combina comercialização com curadoria, contexto e proximidade.

## Referência conceitual: Amazofuturismo

Gênero que une a estética indígena do bioma Amazônia a tecnologias e conceitos futuristas, colocando povos indígenas amazônicos como protagonistas de sua própria história, projetados para o futuro sem ignorar sua ancestralidade. O futuro é imaginado a partir de conhecimentos, cosmologias e relações comunitárias, e a tecnologia é pensada como inovadora, limpa e orientada ao bem-estar.

**Seis pilares adaptados à Iara Games:**
1. **Futuro com raízes:** valorizar trajetórias, referências e conhecimentos de cada estúdio brasileiro.
2. **Protagonismo de quem cria sua própria história:** dar visibilidade a desenvolvedores e equipes, não apenas aos produtos.
3. **Tecnologia em harmonia com a vida:** experiência digital funcional, acessível, responsável e não predatória.
4. **Vida como rede:** comunidade, suporte, criadores, jogadores e território como partes do mesmo ecossistema.
5. **Estética como conhecimento:** elementos visuais com significado, pesquisa e contexto, sem ornamento superficial.
6. **Futuro plural:** o Brasil como conjunto de territórios, vozes e culturas, não como uma identidade única.

## Pesquisa de plataformas de distribuição

| Critério | Steam | Nuuvem | Epic Games Store | Direção para a Iara Games |
|---|---|---|---|---|
| **Alcance** | Global e muito amplo | Regional, com foco latino-americano | Global e muito amplo | Começar por relevância, confiança e densidade de catálogo |
| **Descoberta** | Wishlists, tags, avaliações, páginas e comunidade | Campanhas, marketing regional e rede de parceiros | Wishlists, promoções e recursos de loja | Curadoria brasileira, contexto e distribuição de destaque |
| **Relacionamento c/ desenvolvedor** | Ferramentas e documentação estruturadas | Suporte regional, marketing e dados | Portal, incentivos e ferramentas | Onboarding próximo, critérios claros e painel simples |
| **Localização** | Generalista e internacional | Forte domínio regional | Global, com múltiplos idiomas e moedas | Português brasileiro, reais, atendimento local e linguagem acessível |
| **Prova social** | Avaliações e comunidade | Confiança regional e comunicação | Avaliações, wishlists e promoções | Avaliações verificadas, notas, relatos e perfil de estúdio |
| **Distribuição** | Cliente próprio e download local | Chaves, DRM-Free e integrações | Distribuição digital e serviços do ecossistema | Biblioteca e instalação local transparentes |
| **Diferencial** | Escala e ecossistema | Proximidade latino-americana | Incentivos econômicos e alcance | Futuro enraizado, pertencimento e valorização do criador |
| **Risco para a Iara** | Catálogo pequeno pode parecer limitado | Confundir regionalidade com exclusividade nacional | Competir apenas por preço ou percentual | Ser uma loja vazia ou uma estética sem operação correspondente |

## O que foi entregue

Home estática em HTML e CSS (header, hero, jogos em destaque e busca), com a identidade visual definida (paleta, tipografia e decisões de design) e as primeiras decisões de UX e acessibilidade.

</details>

---

## 👥 Equipe

- André Guima Gonçalves — RM576031
- Stéfany Binelo da Rosa — RM576326
- Daniely Bittencourt Grutzmann Muzeka — RM575991
- Gabriel Honorio Queiroz — RM574855
- Nicole Toscano — RM574909

*Projeto desenvolvido para a disciplina de Web Design, FIAP.*
