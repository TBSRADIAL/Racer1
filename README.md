# Racer 1 🏎️

Sitio informativo sobre el mundo de la Fórmula 1: escuderías, reglamento, calendario y curiosidades para quienes se inician en el deporte.

## Demo

Una vez publicado con GitHub Pages, el sitio queda disponible en:
https://tbsradial.github.io/Racer1/

## Tecnologías utilizadas

- **HTML5** — estructura semántica (`header`, `nav`, `main`, `section`, `article`, `footer`)
- **Sass / SCSS** — arquitectura de partials, variables, mixins con parámetros, `@extend`, operadores, nesting y el operador `&`; se compila a un único `css/style.css`
- **CSS3** — Flexbox, CSS Grid con `grid-template-areas`, transiciones y `@keyframes`
- **Bootstrap 5.3.3** (vía CDN) — navbar responsiva con menú hamburguesa, carousel y grid system (`row` / `col-*`)
- **AOS 2.3.4** (vía CDN) — animaciones de entrada al hacer scroll
- **Google Fonts** — `Titillium Web` (títulos) y `Source Sans 3` (texto)

## Estructura del proyecto

```
racer1/
├── index.html                   # Página de inicio
├── scss/                        # Código fuente de los estilos (no se enlaza directo)
│   ├── main.scss                 # Punto de entrada único (@use)
│   ├── utilities/
│   │   ├── _variables.scss        # Colores, tipografía, escala de espaciado, tiempos y breakpoints
│   │   └── _mixins.scss           # transicion(), flex(), desde(), animar(), elevar()
│   ├── base/
│   │   ├── _base.scss             # Reset, estilos globales y placeholder %lista-limpia
│   │   └── _tipografia.scss       # Clases de títulos y texto
│   ├── layout/
│   │   ├── _header.scss           # Marca / logo
│   │   ├── _nav.scss              # Navbar de Bootstrap personalizada
│   │   ├── _footer.scss           # Pie de página y redes sociales
│   │   └── _contenido.scss        # Contenedor principal, CSS Grid y animación de entrada
│   └── components/
│       ├── _buttons.scss
│       ├── _cards.scss
│       ├── _lists.scss
│       ├── _gallery.scss
│       └── _carousel.scss
├── css/
│   └── style.css                 # CSS compilado (el que enlazan los HTML)
├── Pages/
│   ├── sobre.html
│   ├── escuderias.html            # Con carousel
│   ├── faq.html
│   └── contacto.html
└── Assets/
    ├── miniatura-coche.png        # Favicon
    └── ...                        # Imágenes del sitio
```

## Características

- **Responsive mobile-first** en las 5 páginas, con tres medidas:
  - Base (celular), sin media query.
  - `@media (min-width: 768px)` — tablet.
  - `@media (min-width: 1024px)` — escritorio, donde el grid pasa de 1 a 2 columnas.
- **Navbar de Bootstrap** con menú hamburguesa, presente en las 5 páginas.
- **Carousel de Bootstrap** en `index.html` y `Pages/escuderias.html`, con proporción fija por medida (4:3, 3:2 y 16:9).
- **CSS Grid con áreas con nombre** (`.layout-grid`), con una variante (`.layout-grid--equipos`) para que las tarjetas de escuderías ocupen todo el ancho en escritorio.
- **Paleta de colores propia** (asfalto, morado "vuelta rápida" y ámbar de bandera de precaución), definida como variables de Sass y aplicada por encima de los estilos por defecto de Bootstrap.
- **Estados interactivos** (`:hover`, `:focus`, `:active`) con `transition` en enlaces, botones y tarjetas.
- Sin IDs usados para estilos (solo clases), sin `!important` y sin estilos en línea.
- **Cero CSS escrito a mano**: todo el estilo propio nace en `.scss` y se compila a `css/style.css`.

## Animaciones

**Nativas (desde SCSS):**
- Entrada suave del primer bloque de cada página al cargar (`@keyframes aparecer`).
- Subrayado animado en los links del navbar.
- Zoom sutil de las fotos al pasar el mouse.
- Tarjetas que se elevan en `:hover` y `:focus`.

**Con librería (AOS):** las secciones y tarjetas aparecen con `fade-up` al hacer scroll. Se respeta la preferencia de sistema "reducir movimiento" (`prefers-reduced-motion`), tanto en AOS como en la animación de entrada.

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
