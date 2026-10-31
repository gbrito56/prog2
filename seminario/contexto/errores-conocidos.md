# Errores Conocidos y Gotchas de Maquetado Web

Este documento registra los problemas comunes de desarrollo frontend ("gotchas") identificados durante la fase de especificación para blindar el código y evitar frustraciones en maquetados para principiantes.

---

## 1. Desborde Horizontal en Celulares (Scroll Horizontal Roto)
- **Problema**: Elementos con anchos fijos en píxeles (`width: 500px`) o márgenes/paddings excesivos empujan el ancho de la página más allá del viewport en teléfonos pequeños (320px - 414px), provocando que la página se desplace lateralmente de forma incómoda y antiestética.
- **Causa Raíz**: Contenedores rígidos que no respetan el modelo de caja fluido o imágenes sin ancho responsivo.
- **Blindaje / Solución**:
  - Declarar `overflow-x: hidden;` en el elemento `body` y `html`.
  - Utilizar siempre clases fluidas de Tailwind (`w-full`, `max-w-screen-xl`, `mx-auto`) y nunca anchos rígidos mayores a `100%`.
  - Asegurar que todas las imágenes lleven `w-full h-auto object-cover` con relaciones de aspecto delimitadas (`aspect-video` o `aspect-square`).

---

## 2. Pérdida de Contraste en Dark/Light Mode
- **Problema**: Al alternar entre modo claro y modo oscuro, textos colocados sobre botones de colores vivos (como Teal o Ámbar) cambian a tonos oscuros o ilegibles por herencia del tema.
- **Causa Raíz**: Clases de color de texto genéricas (`text-slate-800 dark:text-white`) aplicadas sobre botones que siempre deberían conservar el texto blanco para garantizar contraste.
- **Blindaje / Solución**:
  - Implementar y aplicar la regla estricta `.force-text-white { color: #ffffff !important; }` en todos los botones primarios, badges de alerta y barras de navegación destacadas.
  - Verificar manualmente contrastes en ambos modos antes de entregar la UI.

---

## 3. Scroll de Fondo Fantasma con Modal Abierto
- **Problema**: Cuando el usuario abre la ventana modal para ver la ficha técnica de un animal, el scroll de la rueda del mouse o el touch en móviles sigue moviendo la página que está detrás, desorientando al usuario.
- **Causa Raíz**: El overlay del modal intercepta clics pero no bloquea la propiedad `overflow` del elemento `<body>`.
- **Blindaje / Solución**:
  - Al abrir el modal, agregar inmediatamente la clase `overflow-hidden` a `document.body`.
  - Al cerrar el modal (botón cerrar, clic afuera o tecla Escape), remover la clase `overflow-hidden` de `document.body`.

---

## 4. Botones Inaccesibles y "Falsos Botones"
- **Problema**: Usar `<div onclick="...">` o `<span onclick="...">` para botones de tarjetas o el menú hamburguesa. Esto impide que personas que navegan con teclado (tecla Tab / Enter) o lectores de pantalla puedan interactuar.
- **Causa Raíz**: Falta de rigor semántico en el marcado HTML.
- **Blindaje / Solución**:
  - Usar **exclusivamente etiquetas `<button type="button">`** para todo disparador de eventos JavaScript.
  - Asegurar que el área táctil en pantallas móviles tenga como mínimo `min-h-[44px]` y `min-w-[44px]`.
  - Incorporar `aria-label` descriptivo en botones con solo íconos (ej: botón del menú hamburguesa o botón de cerrar modal).

---

## 5. Imágenes Rotas o Sin Atributo Alt
- **Problema**: Imágenes externas que tardan en cargar o URLs rotas dejan espacios vacíos deformados, y los lectores de pantalla no pueden describir la mascota.
- **Causa Raíz**: Omitir atributos de texto alternativo o usar URLs de prueba inestables.
- **Blindaje / Solución**:
  - Obligatorio incluir `alt="Fotografía de [Nombre], [Especie] en tránsito para adopción"` en cada imagen.
  - Utilizar imágenes optimizadas de Unsplash con parámetros de compresión (`?auto=format&fit=crop&w=600&q=80`).
  - Definir un color de fondo de respaldo (`bg-slate-200 dark:bg-slate-700`) en el contenedor de la imagen para evitar saltos de layout (*Cumulative Layout Shift - CLS*).
