# Convenciones y Estándares de Diseño: Patitas Seguras

## 1. Semántica HTML5 Estricta
Para garantizar accesibilidad (a11y) y estándares web, cada elemento debe cumplir con su función estructural:
- `<header>`: Navbar y encabezados de vistas.
- `<nav>`: Contenedores de enlaces de navegación principal y drawer móvil.
- `<main>`: Contenedor principal de las vistas de la SPA.
- `<section>`: Delimitación de cada vista (Hero, Catálogo, Formulario, Institucional).
- `<article>`: Tarjetas individuales de animales en tránsito.
- `<figure>` y `<figcaption>`: Imágenes de animales con su respectiva descripción.
- `<button>`: **OBLIGATORIO** para todos los disparadores interactivos (abrir modal, cerrar modal, toggle theme, hamburguesa, tabs). Nunca usar `<div>` o `<span>` con handlers de clic.
- `<form>`: Agrupador de campos con etiquetas `<label>` asociadas por `for`/`id`.

---

## 2. Paleta de Colores y Tokens CSS

El sistema cuenta con soporte de **Modo Oscuro (inicial)** y **Modo Claro**:

```css
/* Tokens conceptuales integrados con TailwindCSS */
:root {
  /* Modo Claro */
  --bg-light-ice: #ECFEFF;        /* Ice Teal: fondo principal en modo claro */
  --surface-light: #FFFFFF;       /* Fondo de tarjetas y componentes claros */
  --text-light-main: #0f172a;     /* Texto principal legible */
  --text-light-muted: #475569;    /* Texto secundario */

  /* Modo Oscuro (Default) */
  --bg-dark-deep: #042f2e;        /* Teal oscuro profundo (bg general) */
  --surface-dark: #134e4a;        /* Teal contenedor (cards / modales) */
  --text-dark-main: #f0fdfa;      /* Texto claro de alto contraste */
  --text-dark-muted: #99f6e4;     /* Texto secundario claro */

  /* Colores de Marca y Acción */
  --brand-teal: #0d9488;          /* Teal primario para botones e identidad */
  --brand-teal-hover: #0f766e;    /* Hover primario */
  --accent-amber: #f59e0b;        /* Acento cálido para avisos de rescate */
  --feedback-success: #10b981;    /* Verde para Toast de confirmación */
}
```

### Regla de Contraste Estricto (`.force-text-white`)
Todo botón de llamada a la acción (CTA), badge de estado crítico o elemento sobre fondo saturado debe poseer la clase de contraste forzado para garantizar legibilidad WCAG AAA:
```css
.force-text-white {
  color: #ffffff !important;
}
```

---

## 3. Tipografía y Jerarquía Visual

- **Encabezados (`h1`, `h2`, `h3`, `h4`)**:
  - Familia: `'Plus Jakarta Sans', sans-serif`
  - Peso: `font-semibold` (600) o `font-bold` (700)
  - Tracking: `tracking-tight` (-0.02em)
- **Cuerpo y Párrafos (`p`, `span`, `input`, `label`)**:
  - Familia: `'Noto Sans', sans-serif`
  - Peso: `font-normal` (400) y `font-medium` (500)
  - Line-height: `leading-relaxed` (1.6)

---

## 4. Diseño Responsive y Micro-interacciones

| Dispositivo / Breakpoint | Grilla de Catálogo | Navegación | Área Táctil Mínima |
| :--- | :--- | :--- | :--- |
| **Móviles (`< 768px`)** | 1 columna (`grid-cols-1`) | Menú Drawer Hamburguesa | 44px x 44px (`min-h-[44px] min-w-[44px]`) |
| **Tablets (`768px - 1024px`)** | 2 columnas (`grid-cols-2`) | Navbar colapsable o compacto | 44px x 44px |
| **Desktop (`>= 1024px`)** | 3 columnas (`grid-cols-3`) | Navbar horizontal completo | Estándar de cursor |

### Micro-interacciones & Hover:
- **Tarjetas**: Elevación suave con `transform: translateY(-4px)` y sombra difuminada al pasar el cursor (`transition-all duration-300`).
- **Botones**: Cambio suave de luminosidad/color en 200ms con escala activa leve (`active:scale-95`).
