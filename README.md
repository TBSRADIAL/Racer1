# Racer 1 🏎️

Sitio informativo sobre el mundo de la Fórmula 1: escuderías, reglamento, calendario y curiosidades para quienes se inician en el deporte.

## Demo

Una vez publicado con GitHub Pages, el sitio queda disponible en:
`https://<tu-usuario>.github.io/<nombre-del-repo>/`

## Tecnologías utilizadas

- **HTML5** — estructura semántica (`header`, `nav`, `main`, `section`, `article`, `footer`)
- **CSS3** — variables personalizadas, Flexbox, CSS Grid y Media Queries (mobile-first)
- **Bootstrap 5.3.3** (vía CDN) — navbar responsiva con menú hamburguesa y carousel de imágenes
- **Bootstrap Icons** — iconografía de la interfaz
- **Google Fonts** — `Titillium Web` (títulos) y `Source Sans 3` (texto)

## Estructura del proyecto

```
racer1/
├── index.html              # Página de inicio
├── Estilos/
│   └── estilos.css         # Hoja de estilos del sitio completo
├── Pages/
│   ├── sobre.html           # Sobre el sitio
│   ├── escuderias.html      # Escuderías destacadas (con carousel)
│   ├── faq.html              # Preguntas frecuentes
│   └── contacto.html         # Datos de contacto
└── Assets/
    ├── miniatura-coche.png   # Favicon
    └── ...                   # Imágenes del sitio
```

## Características

- **Diseño responsive**, desarrollado mobile-first: una sola columna en móvil, layout en Grid/Flexbox a partir de tablet y escritorio (`min-width: 1024px`).
- **Navbar de Bootstrap** con menú hamburguesa, presente en las 5 páginas.
- **Carousel de Bootstrap** como galería de imágenes en `index.html` y `Pages/escuderias.html`.
- **Paleta de colores propia** (asfalto, morado "vuelta rápida" y ámbar de bandera de precaución), aplicada por encima de los estilos por defecto de Bootstrap.
- **Estados interactivos** (`:hover`, `:focus`, `:active`) con `transition` en enlaces, botones y tarjetas.
- Sin IDs usados para estilos (solo clases); sin `!important`; sin estilos en línea.

## Cómo correrlo localmente

1. Clona este repositorio.
2. Abre la carpeta en Visual Studio Code.
3. Instala la extensión **Live Server**.
4. Clic derecho sobre `index.html` → **Open with Live Server**.

No requiere instalación de dependencias: Bootstrap y las fuentes se cargan vía CDN.

## Autor

Alejandro Sebastian De la Barrera Alvarado
