# Decisões de Acessibilidade - Iara Games

## Contexto

A Iara Games é uma plataforma de distribuição de jogos independentes brasileiros, com identidade visual amazofuturista (contraste entre elementos orgânicos e tecnológicos). A acessibilidade foi tratada como critério de design desde a escolha da paleta e da estrutura das páginas, e não como ajuste posterior.

Este documento reúne as decisões aplicadas até a **Sprint 3**, em que as páginas foram reconstruídas com **Bootstrap 5.3**. Ele descreve o que foi implementado e verificado (estrutura, contraste, teclado, formulários) e deixa explícito, ao final, o que ainda **não** está resolvido.

---

## 1. Cor e contraste

A paleta está organizada em *tokens semânticos* no CSS (fundo, texto, CTA, link, destaque), em vez de cores soltas. Isso permite conferir e ajustar o contraste em um só lugar.

Os valores abaixo foram **calculados pela fórmula de contraste da WCAG 2.x**. Quando o fundo é semitransparente, o cálculo usa a cor resultante da sobreposição sobre o fundo da página, então os números de fundos translúcidos são aproximados.

| Combinação | Contraste | Uso | AA (4,5:1) | AAA (7:1) |
|---|---|---|---|---|
| Branco Neve sobre Azul Noite | 15,70:1 | texto geral | ✅ | ✅ |
| Branco Neve sobre o painel "vidro" | 13,27:1 | texto dentro dos cards | ✅ | ✅ |
| Verde Neon sobre Azul Noite | 12,98:1 | destaques, títulos | ✅ | ✅ |
| Azul Noite sobre Verde Neon | 12,98:1 | texto de botões e selos | ✅ | ✅ |
| Verde Neon sobre o painel "vidro" | 10,97:1 | preços, ícones | ✅ | ✅ |
| Verde Neon sobre a faixa de cabeçalho dos blocos | 9,06:1 | links no cabeçalho e rodapé dos blocos | ✅ | ✅ |
| Texto secundário sobre o painel | 7,12:1 | nome do estúdio, legendas | ✅ | ✅ |
| Verde Água sobre Azul Noite | 5,41:1 | links em texto corrido | ✅ | ❌ |
| Azul Noite sobre Verde Água | 5,41:1 | botão no estado hover | ✅ | ❌ |
| Placeholder (Branco Neve a 70%) sobre Verde Floresta | 5,79:1 | campos de busca | ✅ | ❌ |
| Verde Água sobre o corpo dos cards | 4,57:1 | links na tabela de compras | ✅ | ❌ |
| Texto de erro dos formulários (`#ea868f`) sobre o card | ≈ 5,9:1 | mensagens de validação | ✅ | ❌ |

### Problemas de contraste encontrados e corrigidos

Esses ajustes vieram de conferir o contraste durante o desenvolvimento, não só ao final:

| Problema | Contraste antes | Correção |
|---|---|---|
| Card inteiro a 50% de opacidade (efeito "apagado") | título 4,40:1, preço 3,78:1, estúdio 2,85:1 | a opacidade passou a valer só para a **imagem**; o texto mantém 13,27:1 |
| Texto branco no selo de fundo Verde Água | 2,90:1 | texto em Azul Noite (5,41:1) |
| Link "← Voltar" em Verde Água sobre Verde Floresta | 3,45:1 | link em Verde Neon (8,28:1) |
| Placeholder em Verde Água sobre Verde Floresta | 3,45:1 | Branco Neve a 70% (5,79:1) |
| Links em Verde Água sobre a faixa de cabeçalho/rodapé dos blocos | 3,77:1 | links em Verde Neon (9,06:1) |
| Texto de erro sobre o card translúcido do cadastro | 4,48:1 | fundo do card quase sólido (≈ 5,9:1) |

### Onde o contraste mais baixo foi mantido de propósito

- **Vermelho Vivo sobre o painel (3,82:1)** e **Verde Água sobre Verde Floresta (3,45:1)** são usados apenas em **bordas e ícones**, que a WCAG exige em 3:1 (componentes de interface). Nenhum texto usa essas combinações.
- O botão "Encerrar sessão" tem texto claro com **borda** vermelha, justamente por isso.
- O Verde Terra (`--text-secondary`) existe como cor de fundo de apoio e **não deve ser usado como texto** sobre fundo escuro.

---

## 2. Estrutura semântica

- Cada página usa `<header>`, `<nav>`, `<main>`, `<section>`, `<aside>` e `<footer>`, em vez de `<div>` genéricas.
- Existe **um único `<h1>` por página**, seguido de `h2` e `h3` em ordem. Quando o tamanho visual difere da hierarquia, o Bootstrap permite usar uma classe (por exemplo `h5`) sem trocar a tag.
- A logo deixou de ser `<h1>` na Sprint 3: o título da página descreve o conteúdo, e a logo é um link para a Home.
- Os dois grupos de links do rodapé são `<nav>` separados, cada um com `aria-label`. O menu de topo é um `<nav>` com `aria-label="Navegação principal"`.
- A página atual é marcada com `aria-current="page"` (menu de topo, menu lateral e *breadcrumb*), de modo que a informação não dependa apenas da cor.
- `<html lang="pt-BR">` em todas as páginas, para pronúncia correta em leitores de tela.
- O título da área do usuário no menu lateral é um `<p>`, e não um `<h2>`, porque aparece antes do `<h1>` no código e bagunçaria a ordem dos títulos.

---

## 3. Navegação por teclado e foco

- **Link "Ir para o conteúdo principal"** (*skip link*) no início de cada página, visível ao receber foco, para pular o menu.
- **Foco visível em tudo**: botões e links próprios usam contorno ou anel em Verde Neon. O Bootstrap remove o contorno dos controles do carrossel, e esse contorno foi **restaurado** no CSS.
- Os botões personalizados (`btn-iara`, `btn-neon`, `btn-outline-iara`) recebem a variável de anel de foco do Bootstrap, que não existe nos botões criados do zero.
- O menu recolhível (hambúrguer), o painel lateral (*offcanvas*) e o carrossel funcionam por teclado (`Tab`, `Enter`, `Esc` e setas, conforme o componente).
- Na Home, o card de jogo inteiro é clicável por um **único link** (`stretched-link`), então cada card tem uma só parada no `Tab`.

---

## 4. Formulários

- Todo campo tem `<label>` associado por `for`/`id`. Nos campos de busca, o rótulo fica escondido visualmente (`visually-hidden`), mas continua disponível para leitores de tela.
- Os formulários de busca têm `role="search"`.
- No cadastro, cada campo liga **a dica e a mensagem de erro** por `aria-describedby`, e o script marca `aria-invalid` conforme a validação.
- Quando há erro ao enviar, o **foco vai para o primeiro campo inválido**. Ao concluir o cadastro, o foco vai para o título da confirmação, para que a mudança seja anunciada.
- Os erros aparecem como **texto e ícone**, não só como mudança de cor.
- `autocomplete` correto (`username`, `email`, `new-password`), que ajuda gerenciadores de senha e quem tem dificuldade para digitar.
- Os filtros da biblioteca são `checkbox` reais (estilizados como botão), agrupados em `fieldset` com `legend`.
- A chave de "Aviso de compatibilidade" é um `checkbox` com `role="switch"` e descrição por `aria-describedby`.
- O cadastro informa, de forma visível, que é uma **demonstração**: nenhum dado é enviado ou armazenado.

---

## 5. Componentes dinâmicos (Bootstrap)

- **Carrossel:** sem autoplay (nada se move sozinho). Tem `aria-roledescription="carousel"`, rótulo em cada slide ("Jogos 1 a 4"), botões anterior/próximo com texto para leitor de tela e indicadores com `aria-label`. A rotação é cíclica (do último volta ao primeiro).
- **Menu lateral (*offcanvas*):** tem `aria-labelledby`, botão de fechar com rótulo e foco gerenciado pelo Bootstrap.
- **Botão do menu (hambúrguer):** `aria-label`, `aria-controls` e `aria-expanded`, que o Bootstrap atualiza sozinho.

---

## 6. Conteúdo não textual

- Todas as capas e a logo têm `alt` descritivo. A logo do rodapé, que também é link, tem um `alt` que descreve a **função** ("Voltar ao topo").
- Ícones decorativos, o vídeo de fundo e os quadrados de capa ainda sem imagem usam `aria-hidden="true"`.
- As barras de progresso (XP e armazenamento) têm `role="progressbar"` com `aria-valuenow`, `aria-valuemin` e `aria-valuemax`. A de armazenamento usa `aria-valuetext` ("220 GB usados de 256 GB"), para o leitor de tela dizer o valor real, não uma porcentagem.

---

## 7. Tabelas, listas e rótulos de botões

- A tabela de compras tem `<caption>` (escondida visualmente), `scope="col"` nos cabeçalhos, `scope="row"` na primeira coluna e datas em `<time>`.
- As especificações de hardware usam lista de definições (`<dl>`).
- Os botões repetidos (Jogar, Instalar, Desinstalar, Baixar PDF) têm `aria-label` com o **nome do jogo**, para que seis botões "Jogar" não sejam todos iguais para o leitor de tela. O texto visível está contido no rótulo, como a WCAG recomenda.

---

## 8. Movimento e animações

- `prefers-reduced-motion` está implementado: para quem pediu movimento reduzido, o **vídeo do hero some**, a rolagem suave vira instantânea e as transições próprias (botão de preenchimento, clareamento de imagem) são desligadas. O Bootstrap já desliga a animação do carrossel nesse caso.
- O efeito de "card apagado" atua só na imagem, e o hover tem equivalente por teclado (`:focus-within`).

---

## 9. Informação que não depende só de cor

- O alerta de pouco espaço no disco é texto com ícone, além da barra vermelha.
- Os status ("Instalado", "Não instalado", "Licença sua") são rótulos de texto.
- Os links dentro de texto corrido são **sublinhados** (WCAG 1.4.1), para não dependerem da cor.
- O menu ativo usa `aria-current`, além da cor.

---

## 10. Responsividade e legibilidade

- `<meta name="viewport">` em todas as páginas e layout pelo grid do Bootstrap (`sm`, `md`, `lg`, `xl`), que reorganiza as colunas em vez de reduzir o conteúdo.
- A tabela de compras rola na horizontal **dentro do próprio bloco** em telas pequenas, sem criar rolagem na página inteira.
- Tipografia em unidades relativas (`rem`), o que respeita o tamanho de fonte escolhido pelo usuário no navegador.

---

## 11. Limitações conhecidas

Para não afirmar mais do que foi feito:

- **O vídeo de fundo do hero não tem botão de pausar.** A WCAG (critério 2.2.2) pede um mecanismo para conteúdo em movimento por mais de 5 segundos. Hoje ele é decorativo, está escondido de leitores de tela e some para quem ativa "reduzir movimento", mas um botão de pausa é uma melhoria futura.
- **Filtros, "Instalar", "Jogar", "Desinstalar" e "Solicitar reembolso" são só interface**, sem JavaScript próprio nem back-end. Quando passarem a funcionar, será preciso anunciar os resultados e as mudanças de estado a leitores de tela (regiões `aria-live`).
- **Algumas páginas ainda não existem** (Explorar, Estúdios, Ofertas, Biblioteca e outras), então os links para elas levam a erro 404.
- **Há um script próprio**, no cadastro, para a validação e a mensagem de sucesso. Todo o resto usa só o JavaScript do Bootstrap.
- Este documento descreve decisões de código e verificações de contraste e estrutura. **Não afirma conformidade completa com a WCAG nem resultados de testes com leitores de tela.**

---

## 12. Como verificar

Qualquer pessoa pode reproduzir as verificações:

1. **Teclado:** abra a página e aperte `Tab` do começo ao fim, sem mouse. Todo item interativo deve mostrar um contorno visível, e o *skip link* deve aparecer no primeiro `Tab`.
2. **Movimento reduzido:** DevTools → `Ctrl+Shift+P` → "Rendering" → "Emulate CSS media feature prefers-reduced-motion" → `reduce`. O vídeo deve sumir.
3. **Contraste:** informe os pares de cor em um verificador como o [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/).
4. **Auditoria automática:** DevTools → aba Lighthouse → categoria Accessibility.
5. **Estrutura:** use um leitor de tela ou uma extensão que liste títulos e regiões da página.

<!--
TODO (equipe): se quiser registrar a nota do Lighthouse de cada página, adicione aqui uma tabela
"Página | Nota de Acessibilidade" com os valores obtidos.
-->
