# Racer 1 🏎️

Sitio informativo sobre el mundo de la Fórmula 1: escuderías, reglamento, calendario y curiosidades para quienes se inician en el deporte.

## Demo

Una vez publicado con GitHub Pages, el sitio queda disponible en:
https://tbsradial.github.io/Racer1/

## Tecnologías utilizadas

- **HTML5** — estructura semántica (`header`, `nav`, `main`, `section`, `article`, `footer`)
- **Sass / SCSS** — arquitectura de partials, variables, mixins, nesting y el operador `&`, compilado a un único `css/style.css`
- **CSS3** — Flexbox y CSS Grid con Media Queries (mobile-first)
- **Bootstrap 5.3.3** (vía CDN) — navbar responsiva con menú hamburguesa, carousel de imágenes y grid system (`row`/`col-*`)
- **Bootstrap Icons** — iconografía de la interfaz
- **Google Fonts** — `Titillium Web` (títulos) y `Source Sans 3` (texto)

## Estructura del proyecto

```
racer1/
├── index.html                   # Página de inicio
├── scss/                        # Código fuente de los estilos (no se linkea directo)
│   ├── main.scss                 # Punto de entrada único (@use)
│   ├── utilities/
│   │   ├── _variables.scss        # Paleta de colores y tipografía
│   │   └── _mixins.scss           # transicion() y flex()
│   ├── base/
│   │   ├── _base.scss             # Reset + estilos globales a etiquetas
│   │   └── _tipografia.scss       # Clases de títulos y texto
│   ├── layout/
│   │   ├── _header.scss           # Marca / logo
│   │   ├── _nav.scss              # Navbar de Bootstrap personalizada
│   │   ├── _footer.scss           # Pie de página y redes sociales
│   │   └── _contenido.scss        # Contenedor principal + CSS Grid
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

- **Diseño responsive**, desarrollado mobile-first: una sola columna en móvil, layout en Grid/Flexbox a partir de tablet y escritorio (`min-width: 1024px`).
- **Navbar de Bootstrap** con menú hamburguesa, presente en las 5 páginas.
- **Carousel de Bootstrap** como galería de imágenes en `index.html` y `Pages/escuderias.html`.
- **Paleta de colores propia** (asfalto, morado "vuelta rápida" y ámbar de bandera de precaución), definida como variables de Sass y aplicada por encima de los estilos por defecto de Bootstrap.
- **Estados interactivos** (`:hover`, `:focus`, `:active`) con `transition` en enlaces, botones y tarjetas.
- Sin IDs usados para estilos (solo clases); sin `!important`; sin estilos en línea.
- **Cero CSS escrito a mano**: todo el estilo propio nace en `.scss` y se compila a `css/style.css`.

## Cómo correrlo localmente

1. Clona este repositorio.
2. Abre la carpeta en Visual Studio Code.
3. Instala la extensión **Live Server** (para ver el sitio) y **Live Sass Compiler** (para editar los estilos).
4. Clic derecho sobre `index.html` → **Open with Live Server**.

No requiere instalación de dependencias: Bootstrap y las fuentes se cargan vía CDN.

## Cómo editar los estilos

El `css/style.css` **no se edita a mano** — es el resultado de compilar `scss/main.scss`.

**Opción A — VS Code (recomendada):**
Con la extensión Live Sass Compiler instalada, clic en "Watch Sass" en la barra inferior. Cada vez que guardes un archivo `.scss`, se regenera `css/style.css` automáticamente.

**Opción B — Terminal:**
```bash
npm install -g sass
sass scss/main.scss css/style.css --no-source-map
```

⚠️ El `css/style.css` compilado se sube al repositorio junto con los `.scss` — GitHub Pages no compila Sass por sí solo, solo sirve archivos estáticos.

## Autor

Alejandro Sebastian De la Barrera Alvarado
