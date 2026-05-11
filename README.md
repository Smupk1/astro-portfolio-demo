# astro-portfolio-demo

Portfolio de desarrollador construido con **Astro puro** (sin React, sin frameworks adicionales), inspirado en la paleta de la **Universidad Central de Colombia**: verde oliva profundo, granate, crema cálida y negro tinta.

Este proyecto fue creado como **material de apoyo para una presentación a estudiantes universitarios** sobre cómo construir sitios web modernos, performantes y mantenibles usando Astro y conceptos fundamentales del desarrollo web — sin abusar de frameworks pesados.

---

## Para qué sirve

- **Demostrar Astro** como alternativa a React/Next.js para sitios estáticos y portfolios.
- **Mostrar que se puede tener interactividad sin un framework pesado**: clock en vivo, filtros, tabs, copy-to-clipboard, formularios con floating labels — todo con JavaScript vanilla.
- **Ejemplo de design tokens y CSS variables** aplicados a una paleta institucional real.
- **Plantilla pedagógica**: el código está pensado para ser leído, no solo ejecutado. Cada componente vive en su propio archivo y la lógica está separada de la presentación.

---

## Stack

- [Astro 4](https://astro.build) — generador de sitios estáticos basado en componentes
- HTML / CSS / JavaScript vanilla
- Tres fuentes de Google Fonts: Libre Caslon Text (serif display), DM Sans (sans body), JetBrains Mono (meta/labels)

**Sin** React, Vue, Tailwind, ni librerías de UI. Todo CSS está escrito a mano usando custom properties.

---

## Estructura del proyecto

```
src/
├── pages/
│   └── index.astro          # Página principal que compone todo
├── layouts/
│   └── Layout.astro         # HTML base, fuentes, meta tags
├── components/
│   ├── Nav.astro            # Navegación sticky con scroll state
│   ├── Hero.astro           # Hero con reloj en vivo de Bogotá
│   ├── Marquee.astro        # Marquee de áreas de interés
│   ├── Work.astro           # Lista filtrable de proyectos
│   ├── About.astro          # Sección "Sobre mí"
│   ├── Stack.astro          # Toolkit con tabs y barras de progreso
│   ├── Experience.astro     # Timeline de trayectoria
│   ├── Writing.astro        # Índice de escritura
│   ├── Contact.astro        # Formulario + copy email
│   ├── Footer.astro
│   ├── Monogram.astro       # SVG del logo
│   ├── Sigil.astro          # SVG decorativo
│   └── SectionTitle.astro   # Título de sección reutilizable
└── styles/
    └── global.css           # Design tokens + estilos globales
```

---

## Cómo clonar y correr el proyecto

### Requisitos previos

- [Node.js](https://nodejs.org/) versión 18.17.1 o superior
- [pnpm](https://pnpm.io/installation) (recomendado) o npm

### Paso a paso

**1. Clonar el repositorio**

```bash
git clone https://github.com/Smupk1/astro-portfolio-demo.git
cd astro-portfolio-demo
```

**2. Instalar dependencias**

```bash
pnpm install
```

> Si no tenés pnpm, podés instalarlo con `npm install -g pnpm` o usar `npm install`.

**3. Levantar el servidor de desarrollo**

```bash
pnpm dev
```

Abrí [http://localhost:4321](http://localhost:4321) en el navegador. Cualquier cambio que hagas en los archivos se va a reflejar al instante (hot module reload).

**4. Build de producción**

```bash
pnpm build
```

Esto genera el sitio estático en la carpeta `dist/`. Son archivos HTML, CSS y JS listos para subir a cualquier hosting estático (Netlify, Vercel, GitHub Pages, Cloudflare Pages, etc.).

**5. Preview del build**

```bash
pnpm preview
```

Sirve la carpeta `dist/` localmente para verificar cómo se ve el build final.

---

## Cómo personalizarlo

- **Cambiar los colores**: editá las CSS variables en `src/styles/global.css` (sección `:root`).
- **Cambiar los proyectos**: editá el array `PROJECTS` en `src/components/Work.astro`.
- **Cambiar el stack**: editá el objeto `STACK_DATA` en `src/components/Stack.astro`.
- **Cambiar la trayectoria**: editá el array `EXPERIENCE` en `src/components/Experience.astro`.
- **Cambiar los posts**: editá `POSTS` en `src/components/Writing.astro`.
- **Cambiar el email y redes**: en `src/components/Contact.astro`.

---

## Conceptos clave para discutir en la presentación

1. **Component Islands**: Astro renderiza HTML estático por defecto y solo hidrata JavaScript donde realmente lo necesitás.
2. **Zero JS by default**: la página carga sin JS innecesario; los scripts `<script>` de cada componente se procesan y optimizan en el build.
3. **CSS variables como design system**: una paleta institucional aplicada con custom properties — escalable y temable.
4. **Separación de responsabilidades**: cada componente tiene su markup, sus estilos (vía clases) y su comportamiento (vía `<script>` local).
5. **Progressive enhancement**: el sitio funciona sin JavaScript; las interacciones lo enriquecen.

---

## Licencia

MIT — ver [LICENSE](./LICENSE).

Sentite libre de clonarlo, modificarlo y usarlo como base para tu propio portfolio o como material docente.
