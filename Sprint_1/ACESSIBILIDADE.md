# Decisões de Acessibilidade - Iara Games

## Contexto

A Iara Games é uma plataforma de distribuição de jogos independentes brasileiros, com identidade visual amazofuturista (contraste entre elementos orgânicos e tecnológicos). Acessibilidade foi tratada como critério de design desde a concepção da paleta de cores e da estrutura da página, não como ajuste posterior.

Este documento descreve as decisões já implementadas na Sprint 1 e os pontos que seguem em alinhamento com o time para as próximas sprints.

---

## Decisões já implementadas

### Paleta de cores pensada para contraste

A paleta da marca (Azul Noite, Verde Floresta, Verde Terra, Vermelho Terra, Vermelho Vivo, Verde Água, Verde Neon, Branco Neve) foi estruturada em *tokens semânticos* no CSS — separando cor de fundo, cor de texto, cor de CTA e cor de link — em vez de cores soltas espalhadas pelo código. Isso permite validar e ajustar contraste de forma centralizada, garantindo consistência em todas as páginas do site.

O texto principal (Branco Neve sobre Azul Noite) e os elementos de destaque (Verde Neon sobre Azul Noite) foram escolhidos por manterem alto contraste. Verificamos os valores com uma ferramenta de contraste WCAG:

| Combinação | Contraste | WCAG AA (4.5:1) | WCAG AAA (7:1) |
|---|---|---|---|
| Branco Neve sobre Azul Noite | ≈ 15.2:1 | ✅ | ✅ |
| Verde Neon sobre Azul Noite | ≈ 12.7:1 | ✅ | ✅ |

### Estrutura semântica do HTML

A página usa marcação semântica ao invés de `<div>`s genéricas:

- `<header>`, `<nav>` (com `aria-label` distinguindo "Navegação principal" de "Conta"), `<section>` e `<article>` para cada card de jogo.
- Hierarquia de headings organizada (`h1` para a logo, `h2` para títulos de seção, `h3` para nome de cada jogo).

Isso permite que leitores de tela naveguem pela página por landmarks e por níveis de título, em vez de precisar ler tudo linearmente.

### Formulário de busca acessível

Os dois campos de busca (header e seção secundária) têm `<label>` associada via `for`/`id`, mesmo estando visualmente oculta (`.visually-hidden`) para manter o layout compacto. Isso garante que leitores de tela anunciem corretamente o campo, em vez de depender só do `placeholder` — que desaparece ao digitar e não é lido de forma confiável por todas as tecnologias assistivas.

Os botões de busca também têm `aria-label="Buscar"`, garantindo que o ícone sozinho não deixe a ação ambígua.

Os campos de busca também contam com um indicador de foco customizado (`:focus-within`), reforçando visualmente qual campo está ativo para quem navega via teclado.

### Idioma declarado

`<html lang="pt-BR">` está definido, garantindo pronúncia correta em leitores de tela e ativação de corretores/tradutores adequados ao conteúdo.

### Textos alternativos em imagens

Todas as capas de jogos e a logo têm atributo `alt` descritivo, evitando texto genérico como "imagem". A logo no rodapé, que também funciona como link de retorno ao topo, tem um `alt` que descreve essa função ("Voltar ao topo"), não só o conteúdo visual.

### Navegação e movimento

- O link de retorno ao topo (logo no rodapé) usa rolagem suave nativa via CSS (`scroll-behavior: smooth`), sem depender de JavaScript.
- O vídeo de fundo do Hero respeita a preferência de sistema `prefers-reduced-motion`: usuários que configuraram essa opção (sensibilidade a movimento) recebem a página com o vídeo desativado automaticamente.

---

## Pontos de atenção documentados

Os cards da seção "Jogos em destaque" usam opacidade reduzida (50%) como recurso estético no estado padrão, o que tecnicamente reduz o contraste do conteúdo. Essa foi uma decisão consciente do grupo — compensada pelo estado de hover e de foco (`:focus-within`), que restauram 100% de opacidade, garantindo que o conteúdo completo esteja acessível tanto para uso com mouse quanto com teclado.
