# Racer 1 🏎️

Guía de Fórmula 1 en español: escuderías, reglamento, Grandes Premios y preguntas frecuentes para quienes se inician en el deporte.

## 🔗 Sitio publicado

**Link del sitio:** https://proyecto-self-ten.vercel.app

Repositorio: https://github.com/TBSRADIAL/Racer1

## Tecnologías utilizadas

- **HTML5**: estructura semántica (`header`, `nav`, `main`, `section`, `article`, `figure`, `figcaption`, `address`, `footer`)
- **Sass / SCSS**: partials, variables, mixins con parámetros, `@extend`, operadores, nesting y el operador `&`; se compila a un único `styles/main.css`
- **CSS3**: Flexbox, CSS Grid con `grid-template-areas`, media queries mobile-first, transiciones y `@keyframes`
- **Bootstrap 5.3.3** (vía CDN): navbar responsiva con menú hamburguesa y carousel
- **AOS 2.3.4** (vía CDN): animaciones de entrada al hacer scroll
- **Google Fonts**: `Titillium Web` (títulos) y `Source Sans 3` (texto)

## Estructura del proyecto

```
racer1/
├── index.html                           # Página de inicio (raíz)
├── pages/
│   ├── sobre-nosotros.html
│   ├── escuderias-formula-1.html         # Con carousel
│   ├── preguntas-frecuentes-f1.html
│   └── contacto.html
├── scss/                                # Código fuente de los estilos
│   ├── main.scss                         # Solo importa los partials con @use (no tiene estilos)
│   ├── utilities/
│   │   ├── _variables.scss                # Colores, tipografía, espaciado, tiempos y breakpoints
│   │   └── _mixins.scss                   # transicion(), flex(), desde(), animar(), elevar()
│   ├── base/
│   │   ├── _base.scss                     # Reset, estilos globales, foco visible, placeholder %lista-limpia
│   │   └── _tipografia.scss               # Clases de títulos y texto
│   ├── layout/
│   │   ├── _header.scss                   # Marca / logo
│   │   ├── _nav.scss                      # Navbar de Bootstrap personalizada
│   │   ├── _footer.scss                   # Pie de página y redes sociales
│   │   └── _contenido.scss                # Contenedor principal, CSS Grid y animación de entrada
│   └── components/
│       ├── _buttons.scss
│       ├── _cards.scss                    # Tarjetas + secciones de tarjetas en CSS Grid
│       ├── _lists.scss
│       ├── _gallery.scss
│       └── _carousel.scss
├── styles/
│   └── main.css                          # CSS compilado (el que enlazan los HTML)
├── assets/                              # Imágenes e íconos con nombres descriptivos
│   ├── favicon-racer1.png
│   ├── scuderia-ferrari-escudo-cavallino.jpg
│   ├── pit-lane-vista-aerea-paradas-boxes.jpg
│   └── ...
└── .vscode/
    └── settings.json                     # Live Sass Compiler: compila a /styles
```

## SEO on-page

Cada página tiene un `<title>`, una `meta description` y unas `meta keywords` únicas, escritas según su contenido. Las keywords también aparecen en el `<h1>`, los `<h2>` y el texto, sin repetirse de más.

| Página | `<title>` | Keywords principales |
|---|---|---|
| `index.html` | Guía de Fórmula 1 en español: escuderías y pilotos | Fórmula 1, F1, guía de Fórmula 1 en español, escuderías, pilotos, reglamento |
| `sobre-nosotros.html` | Quiénes somos: aprende Fórmula 1 desde cero con Racer 1 | aprender Fórmula 1 desde cero, Fórmula 1 para principiantes, historia de la F1 |
| `escuderias-formula-1.html` | Escuderías de F1: historia de Ferrari, Mercedes y Red Bull | escuderías de Fórmula 1, Ferrari, Mercedes-AMG, Red Bull Racing, McLaren, Audi, Cadillac |
| `preguntas-frecuentes-f1.html` | Preguntas frecuentes de F1: puntos y paradas en boxes | vueltas de una carrera, parrilla de salida, puntos del campeonato, paradas en boxes |
| `contacto.html` | Contacto: Racer 1, guía de Fórmula 1 desde Ciudad de México | contacto Racer 1, Fórmula 1 en Ciudad de México, F1 México |

- **Encabezados específicos:** un solo `<h1>` por página y jerarquía `h1 → h2 → h3`. Ningún título es genérico: en lugar de "Galería" o "Datos de contacto", se usan títulos como "McLaren, Audi y Cadillac en la parrilla de la F1 2026" o "Correo y ubicación de Racer 1 en Ciudad de México".
- **SEO local:** la página de contacto incluye Ciudad de México en el título, la descripción, el `<h1>` y los datos de `<address>`.
- **HTML semántico, sin contenedores genéricos innecesarios:** las tarjetas son `<article>` hijas directas de su `<section>`, cada diapositiva del carousel es un `<figure>` con `<figcaption>` y los datos de contacto usan `<address>`. Los únicos `<div>` que quedan son los que Bootstrap necesita para la navbar y el carousel.
- **Enlaces internos** entre páginas con textos descriptivos ("Historia de las escuderías de Fórmula 1").
- **Nombres de archivo descriptivos** en minúsculas, con guiones y sin espacios.
- **Imágenes optimizadas:** de máximo 1600 px de ancho, con `width`/`height` para evitar saltos de diseño y `loading="lazy"` en las que no se ven al cargar.

## Accesibilidad

- **`alt` descriptivo en todas las imágenes**, distinto del `figcaption` para no repetir información.
- **Contraste WCAG 2.1 AA** (mínimo 4.5:1 para texto). Todo texto morado usa `#A78BFA`; el morado original `#8B5CF6` queda solo para bordes decorativos.

  | Combinación | Contraste |
  |---|---|
  | Texto claro `#F1EFEA` sobre fondo `#1B1E24` | 14.5:1 |
  | Texto claro sobre tarjeta `#24272E` | 13.0:1 |
  | Pie de foto `#ABAEB8` sobre tarjeta | 6.8:1 |
  | Morado de texto `#A78BFA` sobre fondo / tarjeta | 6.1:1 / 5.5:1 |
  | Texto oscuro `#14161A` sobre botón `#A78BFA` | 6.7:1 |

- Enlace **"Saltar al contenido principal"**, visible al navegar con Tab.
- **Foco visible** (`:focus-visible`) en todos los elementos interactivos.
- **`aria-label`** en la navegación principal, la de redes sociales y los carruseles.
- Los enlaces externos avisan a los lectores de pantalla que se abren en una pestaña nueva.

## Responsive

El sitio es mobile-first y se adapta con media queries generadas por el mixin `desde()`:

| Breakpoint | Qué cambia |
|---|---|
| Base (celular, sin media query) | Una columna, menú hamburguesa, carousel en 4:3 |
| `tablet` (768 px) | Tarjetas en 2 columnas, carousel en 3:2, más espaciado |
| `menu-horizontal` (992 px) | La navbar de Bootstrap pasa de hamburguesa a menú horizontal |
| `desktop` (1024 px) | Grid de 2 columnas, tarjetas de escuderías en 3 columnas, carousel en 16:9 |

Probado a 360, 768, 1024 y 1440 px en las 5 páginas, sin scroll horizontal.

## Animaciones

**Nativas (SCSS):**
- `@keyframes aparecer`: entrada suave del primer bloque de cada página.
- `transition`: subrayado animado en los links del navbar, zoom de las fotos al pasar el mouse y tarjetas que se elevan en `:hover` y `:focus`.

**Con librería (AOS):** secciones y tarjetas aparecen con `fade-up` al hacer scroll.

Las dos respetan la preferencia del sistema "reducir movimiento" (`prefers-reduced-motion`).

## SCSS

| Herramienta | Dónde |
|---|---|
| Partials | `utilities/`, `base/`, `layout/` y `components/`, importados en `main.scss` solo con `@use` |
| Variables | `utilities/_variables.scss` (colores, fuentes, espaciado, tiempos y mapa de breakpoints) |
| Operadores | Escala de espaciado (`$espacio-base * 1.5`, etc.); el mixin `elevar()` usa `*` y `math.div` |
| Mixin `desde($punto)` | Media queries mobile-first: `@include desde(tablet) { ... }` |
| Mixin `animar($nombre, $duracion, $retraso, $timing)` | Aplica una animación respetando `prefers-reduced-motion` |
| Mixin `elevar($distancia, $color-borde-hover)` | Efecto de elevación en `:hover`, `:focus` y `:active` |
| Mixins `transicion($propiedad, $duracion)` y `flex($direccion, $justificar, $alinear, $espacio)` | Transiciones y contenedores flex reutilizables |
| `@extend` | El placeholder `%lista-limpia` lo extienden `.menu`, `.redes` y `.lista-destacados` |
| Nesting y `&` | En todos los partials (estados, variantes `&--vertical`, `&--equipos`, pseudo-elementos) |

## Cómo correrlo localmente

1. Clona este repositorio.
2. Abre la carpeta en Visual Studio Code.
3. Instala las extensiones **Live Server** (para ver el sitio) y **Live Sass Compiler** (para editar los estilos).
4. Clic derecho sobre `index.html` → **Open with Live Server**.

No requiere instalar dependencias: Bootstrap, AOS y las fuentes se cargan vía CDN.

## Cómo editar los estilos

El `styles/main.css` **no se edita a mano**: es el resultado de compilar `scss/main.scss`.

**Opción A: VS Code (recomendada).** El archivo `.vscode/settings.json` ya configura Live Sass Compiler para guardar el CSS en `/styles`. Haz clic en "Watch Sass" en la barra inferior y, cada vez que guardes un `.scss`, se regenera `styles/main.css`.

**Opción B: terminal.**
```bash
npm install -g sass
sass scss/main.scss styles/main.css --no-source-map
```

⚠️ El `styles/main.css` compilado se sube al repositorio junto con los `.scss`, porque Netlify y Vercel sirven archivos estáticos y no compilan Sass por sí solos.

## Cómo desplegarlo

**Netlify:** en app.netlify.com → *Add new site* → *Import an existing project* → GitHub → elegir `Racer1`. Dejar vacíos el *Build command* y el *Publish directory* y hacer clic en *Deploy*.

**Vercel:** en vercel.com → *Add New…* → *Project* → importar `Racer1` desde GitHub. En *Framework Preset* elegir *Other*, sin comando de build, y hacer clic en *Deploy*.

## Autor

Alejandro Sebastian De la Barrera Alvarado
