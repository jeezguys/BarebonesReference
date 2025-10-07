# Modern CSS Barebones Guide (.md)

## Core Concepts
- **Cascade & Specificity:** Inline > ID > Class/Attr/Pseudo-class > Element. Later wins at same specificity.
- **Box Model:** content + padding + border + margin. Use `box-sizing: border-box;`.
- **Units:** `rem`, `em`, `px`, `%`, `vw`/`vh`, `svh`/`dvh`, `ch`, `fr` (Grid).
- **Color:** `#hex`, `rgb()`, `hsl()`, `lab()`, `lch()`, alpha via `/` or `rgba()`/`hsla()`.

## Selectors
- **Basic:** `*`, `element`, `.class`, `#id`, `[attr]`, `[attr="v"]`.
- **Combinators:** `A B` (desc), `A > B` (child), `A + B` (adjacent), `A ~ B` (siblings).
- **Pseudo-classes:** `:hover`, `:focus`, `:focus-visible`, `:active`, `:disabled`, `:checked`, `:not()`, `:is()`, `:where()`, `:has()`.
- **Pseudo-elements:** `::before`, `::after`, `::placeholder`, `::selection`.

## Reset / Base
```css
/* Reset-ish */
*, *::before, *::after { box-sizing: border-box; }
* { margin: 0; }
:root { color-scheme: light dark; }
html { hanging-punctuation: first last; }
body { font-family: system-ui, sans-serif; line-height: 1.5; }
img, svg, video, canvas { max-width: 100%; height: auto; }
```

## Custom Properties (Variables)
```css
:root {
  --space: 1rem;
  --brand: hsl(220 90% 56%);
}
.button {
  padding: var(--space);
  background: var(--brand);
}
```

## Layout
### Flexbox (1D)
```css
.container {
  display: flex;
  gap: 1rem;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
}
.item { flex: 1 1 200px; } /* grow shrink basis */
```

### Grid (2D)
```css
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(16rem, 1fr));
  gap: 1rem;
}
.header { grid-column: 1 / -1; }
```

### Positioning
```css
.wrap { position: relative; }
.badge { position: absolute; inset: 0.5rem auto auto 0.5rem; }
.sticky { position: sticky; top: 0; }
```

## Spacing & Sizing
- **Logical props:** `margin-inline`, `padding-block`, `inset`, `border-block`.
- **Min/Max/Clamp:** `width: clamp(16rem, 50vw, 60rem);`
- **Gap:** prefer `gap` in Flex/Grid over margins between items.

## Typography
```css
:root { font-size: 16px; }
h1 { font-size: clamp(2rem, 4vw, 3rem); }
p { max-width: 65ch; }
```

## Modern Color & Gradients
```css
.card {
  background: linear-gradient(180deg, hsl(210 30% 98%), hsl(210 30% 94%));
}
.btn {
  color: white;
  background: color-mix(in oklch, var(--brand), black 10%);
}
```

## State & Interactions
```css
a {
  color: var(--brand);
  text-decoration: underline;
  text-underline-offset: 0.15em;
}
a:hover { text-decoration-thickness: 0.15em; }
button:focus-visible { outline: 2px solid var(--brand); outline-offset: 2px; }
```

## Responsive Design
```css
/* Mobile-first breakpoints */
@media (min-width: 40rem) { /* tablet */ }
@media (min-width: 64rem) { /* desktop */ }

/* Container queries */
.card { container-type: inline-size; }
@container (min-width: 30rem) {
  .card .meta {
    display: grid;
    grid-template-columns: 1fr auto;
  }
}

/* User preferences */
@media (prefers-reduced-motion: reduce) {
  * { animation: none; transition: none; }
}
@media (prefers-color-scheme: dark) {
  :root { color-scheme: dark; }
}
```

## Transitions & Animations
```css
.box { transition: transform 150ms ease, opacity 150ms ease; }
.box:hover { transform: translateY(-2px); }

@keyframes fade-in {
  from { opacity: 0; }
  to { opacity: 1; }
}
.toast { animation: fade-in 300ms ease-out; }
```

## Borders, Shadows, Filters
```css
.panel {
  border: 1px solid hsl(0 0% 90%);
  border-radius: 0.5rem;
  box-shadow:
    0 1px 2px hsl(0 0% 0% / 0.07),
    0 8px 24px hsl(0 0% 0% / 0.08);
  backdrop-filter: blur(8px);
}
```

## Forms (modern)
```css
input, button, select, textarea { font: inherit; }
input, select, textarea {
  border: 1px solid hsl(0 0% 80%);
  border-radius: 0.375rem;
  padding: 0.5rem 0.75rem;
}
input:focus-visible { outline: 2px solid var(--brand); outline-offset: 2px; }
::placeholder { color: hsl(0 0% 50%); }
```

## Grid/Flex Utilities (examples)
```css
.stack { display: grid; gap: var(--space); }
.center { display: grid; place-items: center; }
.cluster {
  display: flex;
  flex-wrap: wrap;
  gap: var(--space);
  align-items: center;
}
```

## Layers & Scopes
```css
@layer reset, base, components, utilities;
/* later layers override earlier */
@scope (.card) {
  :scope { padding: 1rem; }
  .title { font-weight: 600; }
}
```

## Performance & Best Practices
- Prefer `transform` and `opacity` for animations.
- Use `content-visibility: auto;` on large, below-the-fold sections.
- Use `will-change` sparingly.

## Debugging
```css
* { outline: 1px solid rgba(0,0,0,.05); } /* temporary layout debug */
```

## Minimal Starter
```css
:root { --space: 1rem; --brand: hsl(220 90% 56%); }
*,
*::before,
*::after { box-sizing: border-box; }
body { margin: 0; font-family: system-ui, sans-serif; line-height: 1.5; }
```
