# Decisões de Acessibilidade — Iara Games (Sprint 02)

## Contexto

A acessibilidade na Iara Games é um pilar estrutural desde a concepção do design visual (amazofuturismo) e da arquitetura de código, abrangendo tanto a home quanto os novos formulários e páginas desenvolvidos na Sprint 02.

---

## Diretrizes Implementadas

### 1. Contraste de Cores (WCAG AA e AAA)
A paleta baseada em *tokens semânticos* garante separação clara entre fundo, texto e elementos interativos. As principais combinações mantêm altos índices de contraste testados:
- **Branco Neve (`#EFF1F4`) sobre Azul Noite (`#0F172E`):** Contraste de aprox. **15.2:1** (Aprovado em WCAG AA e AAA).
- **Verde Neon (`#5AF989`) sobre Azul Noite (`#0F172E`):** Contraste de aprox. **12.7:1** (Aprovado em WCAG AA e AAA).

### 2. Acessibilidade em Formulários (Novidade da Sprint 2)
- **Associação Rótulo-Campo:** Todos os campos de entrada de dados nos formulários possuem tags `<label>` explicitamente vinculadas via atributos `for` e `id`.
- **Estados de Foco Visíveis:** Os elementos interativos e campos de formulário contam com estilos de foco customizados (`:focus` e `:focus-within`), permitindo que usuários que navegam exclusivamente via teclado identifiquem com precisão onde estão na página.
- **Mensagens e Rótulos Claros:** Instruções de preenchimento e botões de ação possuem descrições diretas e atributos `aria-label` onde há uso de ícones visuais.

### 3. Marcação Semântica e Hierarquia de Títulos
- O código utiliza elementos HTML5 semânticos (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<form>`, `<footer>`), permitindo navegação estruturada por tecnologias assistivas (leitores de tela).
- A hierarquia de títulos (`<h1>`, `<h2>`, `<h3>`) segue uma progressão lógica sem saltos de níveis.

### 4. Gestão de Movimento e Mídia
- O vídeo de fundo da seção principal (*Hero*) respeita a preferência de sistema do usuário (`prefers-reduced-motion`), desativando animações pesadas caso o sistema operacional esteja configurado para reduzir o movimento.

### 5. Atributos Alternativos e Idioma
- O documento está configurado com o idioma correto (`<html lang="pt-BR">`).
- Todas as imagens informativas e ilustrativas contam com textos descritivos no atributo `alt`.