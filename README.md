# 💳 Pricing Cards - Página de Preços

Uma página de preços moderna e responsiva construída com HTML semântico e CSS puro.

## 🎯 Conceitos Demonstrados

Este projeto demonstra os seguintes conceitos que serão abordados nas aulas:

### Dia 1 - HTML Semântico
- `<header>` - Cabeçalho da página
- `<nav>` - Navegação principal
- `<main>` - Conteúdo principal
- `<section>` - Secções de conteúdo
- `<article>` - Cartões de preço (conteúdo independente)
- `<footer>` - Rodapé da página
- `<ul>` / `<li>` - Listas de funcionalidades
- Atributos de acessibilidade (`aria-label`, `aria-hidden`)

### Dia 2 - CSS Básico
- **CSS Custom Properties** (Variáveis CSS) - Definidas em `:root`
- **Seletores de classe** - Usando BEM naming (Block__Element--Modifier)
- **Cores e gradientes** - `linear-gradient()`, `radial-gradient()`
- **Box model** - `padding`, `margin`, `border`
- **Tipografia** - Google Fonts, `font-size`, `font-weight`, `line-height`
- **Pseudo-classes** - `:hover`, `:focus-visible`, `:checked`
- **Transições** - `transition` para animações suaves
- **Seletor :has()** - Seleciona elementos baseado nos seus filhos/irmãos

### 🔥 Técnica Especial: Toggle CSS-Only (Sem JavaScript!)

O toggle Mensal/Anual funciona **apenas com CSS** usando a técnica do "checkbox hack":

```html
<!-- HTML: Checkbox escondido + Label clicável -->
<input type="checkbox" id="toggle" class="visually-hidden">
<label for="toggle" class="switch">
    <span class="thumb"></span>
</label>
```

```css
/* CSS: Usa :checked e :has() para mudar estilos */

/* Move o thumb quando checkbox está ativo */
.checkbox:checked ~ .switch .thumb {
    transform: translateX(22px);
}

/* Mostra preço anual quando toggle está ativo */
body:has(.checkbox:checked) .price--annual {
    display: inline;
}

body:has(.checkbox:checked) .price--monthly {
    display: none;
}
```

**Como funciona:**
1. O `<input type="checkbox">` está escondido visualmente
2. O `<label for="toggle">` é clicável e controla o checkbox
3. Quando clicado, o checkbox fica `:checked`
4. O CSS usa `:checked` e `:has()` para alterar estilos

### Dia 3 - Flexbox
Exemplos de Flexbox no projeto:
```css
/* Header - alinha logo e navegação */
.header__content {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

/* Cartões - organiza conteúdo verticalmente */
.pricing__card {
    display: flex;
    flex-direction: column;
}

/* Preço - alinha elementos na baseline */
.pricing__card-price {
    display: flex;
    align-items: baseline;
}
```

### Dia 4 - CSS Grid
Exemplos de Grid no projeto:
```css
/* Grid de cartões de preço */
.pricing__grid {
    display: grid;
    grid-template-columns: 1fr;           /* Mobile: 1 coluna */
    gap: var(--spacing-lg);
}

/* Desktop: 3 colunas */
@media (min-width: 1024px) {
    .pricing__grid {
        grid-template-columns: repeat(3, 1fr);
    }
}

/* Footer - grid de 3 colunas para links */
.footer__nav {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}
```

### Dia 5 - Responsividade / Compatibilidade
```css
/* Mobile First - estilos base são para mobile */
.pricing__grid {
    grid-template-columns: 1fr;
    max-width: 400px;
}

/* Tablet: 640px e acima */
@media (min-width: 640px) {
    .pricing__grid {
        grid-template-columns: repeat(2, 1fr);
        max-width: 700px;
    }
}

/* Desktop: 1024px e acima */
@media (min-width: 1024px) {
    .pricing__grid {
        grid-template-columns: repeat(3, 1fr);
        max-width: none;
    }
}
```

## 📁 Estrutura de Ficheiros

```
Pricing Cards/
├── index.html    # Estrutura HTML semântica
├── styles.css    # Estilos CSS (bem comentados!)
└── README.md     # Este ficheiro
```

## 🎨 Características do Design

- **Tema escuro** com acentos em gradiente roxo
- **Cards de preço** com destaque para o plano popular
- **Ícones SVG** inline para o logo
- **Emojis** como ícones dos planos
- **Efeitos hover** suaves nos cartões e botões
- **Fonte Outfit** do Google Fonts

## ♿ Acessibilidade

O projeto inclui boas práticas de acessibilidade:
- HTML semântico apropriado
- Atributos `aria-label` para elementos interativos
- Estados de foco visíveis (`:focus-visible`)
- Respeito por `prefers-reduced-motion`
- Contraste de cores adequado

## 🚀 Como Usar

1. Abre o ficheiro `index.html` no browser
2. Ou usa um servidor local:
   ```bash
   npx serve
   ```

## 📚 Recursos de Aprendizagem

- [Flexbox Froggy](https://flexboxfroggy.com/) - Jogo para aprender Flexbox
- [Grid Garden](https://cssgridgarden.com/) - Jogo para aprender CSS Grid
- [MDN Web Docs](https://developer.mozilla.org/pt-PT/) - Documentação oficial

---

Criado para as aulas de HTML & CSS 🎓

