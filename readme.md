# AlexBanexx Soluciones IT

Portafolio web de servicios IT con estética neón, desarrollado con **HTML5, Bootstrap 5 y SCSS modular**.
Entrega final del **Módulo 8: Animaciones y full-responsive**.

**Repositorio:** 
`https://github.com/ingalexbanexx/Mod8_Animaciones_Corregido.git`

## Descripción

Correccion del Sitio de 5 páginas que presenta los servicios, proyectos y datos de contacto de **AlexBanexx Soluciones IT**.
En esta última etapa se sumaron animaciones (nativas y con librería), herramientas avanzadas de SCSS y el cierre del diseño responsive mobile-first.

| Página | Archivo |
|---|---|
| Inicio | `index.html` |
| Sobre mí | `pages/sobre-mi.html` |
| Servicios | `pages/servicios.html` |
| Proyectos | `pages/proyectos.html` |
| Contacto | `pages/contacto.html` |

## Tecnologías

- HTML5 semántico
- CSS3 compilado desde **SCSS** (Dart Sass)
- **Bootstrap 5.3.3** y **Bootstrap Icons 1.11.3** (CDN)
- **AOS 2.3.4** (animaciones al hacer scroll)
- Tipografías Google Fonts: *Orbitron* y *Rajdhani*
- Git y GitHub

## Arquitectura SCSS

Todos los estilos viven en partials y se cargan solo desde `main.scss` con `@use`.
Orden de carga: **utilities → base → components → layout**.
No existe ningún `.css` escrito a mano: `styles/styles.css` se genera con Sass.

## Animaciones

### Animaciones nativas (SCSS)

- **`transition` + `transform`** en estados `:hover`, `:focus` y `:active` de botones, tarjetas, enlaces sociales, navegación y botón hamburguesa.
- **`@keyframes`** propios definidos en los partials de componentes (por ejemplo `entrada-arriba`, `flotar` y `pulso-neon`), aplicados con un mixin parametrizable.
- Respeto por la accesibilidad con `@media (prefers-reduced-motion: reduce)`.

### Animaciones con librería: AOS

AOS se carga por CDN en las **5 páginas** y se inicializa con duración, `once: true` y desactivación automática si el usuario prefiere menos movimiento.
Se usa mediante atributos `data-aos` (`fade-up`, `fade-right`, `zoom-in`) con retrasos escalonados en tarjetas.

### Animaciones de Bootstrap (ya incluidas)

Carrusel automático, modales con `fade` y menú colapsable.

## SCSS avanzado

| Herramienta | Aplicación |
|---|---|
| **Mixins con parámetros** | `respond-up($key)`, `neon-glow($size, $alpha, $color)`, `focus-ring(...)`, `flex-align($gap)` y mixins de animación |
| **`@extend` + placeholders** | Estilos base compartidos entre tarjetas y botones |
| **`@each`** | Generación de clases de retraso de animación |
| **`@if`** | Lógica condicional dentro del mixin de animación |
| **Operadores y `calc()`** | Espaciados y tamaños calculados |
| **Variables y mapas** | Paleta, tipografías, transición y `$breakpoints` |
| **Nesting y módulos** | `&:hover`, `&:focus` y `@use ... as` |

## Diseño responsive

Estrategia **mobile-first** con el mixin `respond-up`:

| Medida | Breakpoint | Uso |
|---|---|---|
| Mobile | Base (sin media query) | Una columna, menú hamburguesa |
| Tablet | `min-width: 768px` | Grillas de 2 columnas |
| Escritorio | `min-width: 1024px` | Grillas de 3 columnas y layouts con `grid-template-areas` |

## Validación

Se revisó cada página reduciendo la ventana de 1400 px a 375 px, sin scroll horizontal, superposiciones ni textos cortados.

| Página | 1400 px | 1024 px | 768 px | 375 px |
|---|:---:|:---:|:---:|:---:|
| `index.html` | ✅ | ✅ | ✅ | ✅ |
| `pages/sobre-mi.html` | ✅ | ✅ | ✅ | ✅ |
| `pages/servicios.html` | ✅ | ✅ | ✅ | ✅ |
| `pages/proyectos.html` | ✅ | ✅ | ✅ | ✅ |
| `pages/contacto.html` | ✅ | ✅ | ✅ | ✅ |

## Instalación y compilación

# 1. Instalar dependencias
npm install

# 2. Compilar SCSS a CSS
npm run sass

# 2. Modo desarrollo (recompila al guardar)
npm run sass:watch

# 5. Compilación para producción (minificado)
npm run build

Luego abrí `index.html` en el navegador (o con la extensión *Live Server* de VSCode).

**Alejandro** — [@ingalexbanexx](https://github.com/ingalexbanexx)
Curso Full Stack Development · Coderhouse