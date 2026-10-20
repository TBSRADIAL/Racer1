# Racer 1 🏎️

Sitio informativo sobre el mundo de la Fórmula 1: escuderías, reglamento, calendario y curiosidades para quienes se inician en el deporte.

## Demo

Una vez publicado con GitHub Pages, el sitio queda disponible en:
https://tbsradial.github.io/Racer1/

## Tecnologías utilizadas

- **HTML5** — estructura semántica (`header`, `nav`, `main`, `section`, `article`, `figure`, `address`, `footer`)
- **Sass / SCSS** — arquitectura de partials, variables, mixins con parámetros, `@extend`, operadores, nesting y el operador `&`; se compila a un único `css/style.css`
- **CSS3** — Flexbox, CSS Grid con `grid-template-areas`, transiciones y `@keyframes`, mobile-first
- **Bootstrap 5.3.3** (vía CDN) — navbar responsiva con menú hamburguesa y carousel
- **AOS 2.3.4** (vía CDN) — animaciones de entrada al hacer scroll
- **Google Fonts** — `Titillium Web` (títulos) y `Source Sans 3` (texto)

## Estructura del proyecto

```
racer1/
├── index.html                          # Página de inicio
├── paginas/
│   ├── sobre-nosotros.html
│   ├── escuderias-formula-1.html        # Con carousel
│   ├── preguntas-frecuentes-f1.html
│   └── contacto.html
├── scss/                               # Código fuente de los estilos (no se enlaza directo)
│   ├── main.scss                        # Punto de entrada único (@use)
│   ├── utilities/
│   │   ├── _variables.scss               # Colores (incluye tonos accesibles), tipografía, espaciado, tiempos y breakpoints
│   │   └── _mixins.scss                  # transicion(), flex(), desde(), animar(), elevar()
│   ├── base/
│   │   ├── _base.scss                    # Reset, estilos globales, foco visible, enlace "saltar al contenido"
│   │   └── _tipografia.scss              # Clases de títulos y texto
│   ├── layout/
│   │   ├── _header.scss                  # Marca / logo
│   │   ├── _nav.scss                     # Navbar de Bootstrap personalizada
│   │   ├── _footer.scss                  # Pie de página y redes sociales
│   │   └── _contenido.scss               # Contenedor principal, CSS Grid y animación de entrada
│   └── components/
│       ├── _buttons.scss
│       ├── _cards.scss                   # Tarjetas + sección de tarjetas en CSS Grid
│       ├── _lists.scss
│       ├── _gallery.scss
│       └── _carousel.scss
├── css/
│   └── style.css                        # CSS compilado (el que enlazan los HTML)
└── img/                                # Imágenes con nombres descriptivos
    ├── favicon-racer1.png
    ├── scuderia-ferrari-escudo-cavallino.jpg
    ├── red-bull-racing-monoplaza-en-pista.jpg
    └── ...
```

## SEO on-page

| Página | `<title>` | Keywords principales |
|---|---|---|
| `index.html` | Fórmula 1: escuderías, pilotos y reglamento explicados | Fórmula 1, F1, escuderías, pilotos, Gran Premio, reglamento |
| `sobre-nosotros.html` | Sobre nosotros: una guía de Fórmula 1 para principiantes | guía de Fórmula 1, principiantes, aprender F1 |
| `escuderias-formula-1.html` | Escuderías de Fórmula 1: Ferrari, Mercedes, Red Bull y más | escuderías de Fórmula 1, equipos de F1, Ferrari, Mercedes, Red Bull, McLaren, Audi, Cadillac |
| `preguntas-frecuentes-f1.html` | Preguntas frecuentes sobre la Fórmula 1 y su reglamento | preguntas frecuentes F1, reglamento, parrilla de salida, paradas en boxes, puntos |
| `contacto.html` | Contacto: escribe a Racer 1, tu guía de Fórmula 1 | contacto Racer 1, Fórmula 1 |

- **`meta description` propia en cada página**, escrita según su contenido (entre 140 y 180 caracteres).
- **Keywords integradas** en el `<title>`, el `<h1>`, los `<h2>` y el texto, sin repetirlas de más. No se usa `meta keywords` porque Google no la tiene en cuenta.
- **Un solo `<h1>` por página** y jerarquía ordenada `h1 → h2 → h3`. Los títulos genéricos ("Galería", "Garaje", "Paddock") se reemplazaron por títulos descriptivos.
- **HTML semántico, sin contenedores genéricos innecesarios:** las tarjetas son `<article>` hijas directas de su `<section>` (se quitaron los `<div class="row">` y `<div class="col">`), los datos de contacto usan `<address>` y los párrafos sueltos ya no van envueltos en `<article>`.
- **Nombres de archivo descriptivos** en minúsculas, con guiones y sin espacios: carpetas `img/` y `paginas/`, páginas como `escuderias-formula-1.html` e imágenes como `pit-lane-vista-aerea-paradas-boxes.jpg`.
- **Imágenes optimizadas:** redimensionadas a 1600 px como máximo (de ~31 MB a ~2 MB en total), con `width`/`height` para evitar saltos de diseño y `loading="lazy"` en las que no se ven al cargar.
- **Textos de enlace descriptivos** ("Conoce más sobre Racer 1" en lugar de "Conoce más").

## Accesibilidad

- **`alt` descriptivo en todas las imágenes**, distinto del `figcaption` para no repetir información.
- **Contraste WCAG 2.1 AA (mínimo 4.5:1 para texto):** el morado original `#8B5CF6` solo llegaba a 3.9:1 sobre el fondo y 3.5:1 sobre las tarjetas. Ahora todo texto morado (enlaces, títulos de tarjeta, menú activo, botón) usa `#A78BFA` (6.1:1 y 5.5:1) y `#C4B5FD` en `:hover`; el morado original queda solo para bordes decorativos.

  | Combinación | Contraste |
  |---|---|
  | Texto claro `#F1EFEA` sobre fondo `#1B1E24` | 14.5:1 |
  | Texto claro sobre tarjeta `#24272E` | 13.0:1 |
  | Pie de foto `#ABAEB8` sobre tarjeta | 6.8:1 |
  | Morado de texto `#A78BFA` sobre fondo / tarjeta | 6.1:1 / 5.5:1 |
  | Texto oscuro `#14161A` sobre botón `#A78BFA` | 6.7:1 |

- **Enlace "Saltar al contenido principal"**, visible al navegar con Tab.
- **Foco visible** (`:focus-visible`) en todos los elementos interactivos.
- **`aria-label`** en la navegación principal, la de redes sociales y los carruseles; los botones de los carruseles indican qué foto muestran.
- Los enlaces externos avisan a los lectores de pantalla que se abren en una pestaña nueva.
- Se quitó `tabindex="0"` de las tarjetas: no son interactivas, así que no deben recibir el foco.
- Se respeta "reducir movimiento" (`prefers-reduced-motion`) en AOS y en la animación de entrada.

## SCSS avanzado

| Herramienta | Dónde |
|---|---|
| Variables | `utilities/_variables.scss` (colores, fuentes, espaciado, tiempos, breakpoints) |
| Operadores | La escala de espaciado se calcula con `$espacio-base * 1.5`, etc.; el mixin `elevar()` usa `*` y `math.div` |
| Mixin `desde($punto)` | Media queries mobile-first: `@include desde(tablet) { ... }` |
| Mixin `animar($nombre, $duracion, $retraso, $timing)` | Aplica una animación respetando `prefers-reduced-motion` |
| Mixin `elevar($distancia, $color-borde-hover)` | Efecto de elevación en `:hover`, `:focus` y `:active` |
| Mixins `transicion()` y `flex()` | Transiciones y contenedores flex reutilizables |
| `@extend` | El placeholder `%lista-limpia` lo extienden `.menu`, `.redes` y `.lista-destacados` |
| Nesting y `&` | En todos los partials (estados, variantes `&--equipos`, pseudo-elementos) |

## Cómo correrlo localmente

1. Clona este repositorio.
2. Abre la carpeta en Visual Studio Code.
3. Instala la extensión **Live Server** (para ver el sitio) y **Live Sass Compiler** (para editar los estilos).
4. Clic derecho sobre `index.html` → **Open with Live Server**.

No requiere instalar dependencias: Bootstrap, AOS y las fuentes se cargan vía CDN.

## Cómo editar los estilos

El `css/style.css` **no se edita a mano**: es el resultado de compilar `scss/main.scss`.

**Opción A — VS Code (recomendada):**
Con la extensión Live Sass Compiler instalada, clic en "Watch Sass" en la barra inferior. Cada vez que guardes un archivo `.scss`, se regenera `css/style.css` automáticamente.

**Opción B — Terminal:**
```bash
npm install -g sass
sass scss/main.scss css/style.css --no-source-map
```

⚠️ El `css/style.css` compilado se sube al repositorio junto con los `.scss`: GitHub Pages no compila Sass por sí solo, solo sirve archivos estáticos.

## Autor

Alejandro Sebastian De la Barrera Alvarado
