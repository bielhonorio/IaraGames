## Google Fonts
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;500;600;700&family=Space+Grotesk:wght@300;400;500;700&display=swap" rel="stylesheet">


## Variables

:root {
    /* Fontes */
    --font-title: "Cormorant Garamond", serif;
    --font-text: "Space Grotesk", sans-serif;

    /* ===== Paleta base (tokens crus) ===== */
    --color-blue-night: #0F172E;     /* Azul Noite */
    --color-forest-green: #1B4034;   /* Verde Floresta */
    --color-earth-green: #283415;    /* Verde Terra */
    --color-earth-red: #8C141E;      /* Vermelho Terra */
    --color-vivid-red: #F23535;      /* Vermelho Vivo */
    --color-water-green: #219F8A;    /* Verde Água */
    --color-neon-green: #5AF989;     /* Verde Neon */
    --color-snow-white: #EFF1F4;     /* Branco Neve */

    /* ===== Cores semânticas (uso na interface) ===== */
    --bg-primary: var(--color-blue-night);        /* fundo principal */
    --bg-secondary: var(--color-forest-green);    /* cards, menus, áreas secundárias */
    --bg-support: var(--color-earth-green);       /* fundos de apoio */

    --text-primary: var(--color-snow-white);      /* textos principais, alto contraste */
    --text-secondary: var(--color-earth-green);   /* textos secundários */

    --color-badge: var(--color-earth-red);        /* destaques, badges, elementos especiais */
    --color-cta: var(--color-vivid-red);          /* CTAs, promoções, infos importantes */
    --color-link: var(--color-water-green);       /* links, ícones, tecnologia ativa */
    --color-hover: var(--color-neon-green);       /* hover, destaques interativos */

    /* ===== Gradientes da marca ===== */
    --gradient-tech-life: linear-gradient(90deg, var(--color-water-green), var(--color-neon-green));
    --gradient-tradition-action: linear-gradient(90deg, var(--color-earth-red), var(--color-vivid-red));
    --gradient-amazon-depth: linear-gradient(90deg, var(--color-blue-night), var(--color-forest-green));

    /* Espaçamentos */
    --spacing-xs: 8px;
    --spacing-sm: 10px;
    --spacing-md: 20px;
    --spacing-lg: 30px;
    --spacing-xl: 50px;
    --spacing-2xl: 60px;
    --spacing-3xl: 80px;

    /* Tamanhos */
    --btn-min-width: 180px;
    --hero-max-width: 900px;

    /* Bordas */
    --radius-sm: 8px;
    --radius-pill: 80px;
    --border-width: 2px;

    /* Efeitos */
    --transition-fast: .5s;
    --blur-sm: 7px;
}