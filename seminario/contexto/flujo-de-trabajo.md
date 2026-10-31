# Flujo de Trabajo y Definition of Done (DoD)

Este documento describe la metodología de maquetado progresivo bajo el estándar **Spec-Driven Development (SDD)** y los criterios de aceptación rigurosos para dar por finalizada la interfaz.

---

## 1. Pasos de Maquetado Progresivo SDD

El desarrollo del sitio sigue un orden secuencial por capas desacopladas:

```
[Paso 1: Estructura HTML5 Semántica] 
         │
         ▼
[Paso 2: Sistema de Diseño con TailwindCSS] 
         │
         ▼
[Paso 3: Interactividad y Comportamiento con Vanilla JS] 
         │
         ▼
[Paso 4: Auditoría de Calidad y Verificación de los 4 Estados UI]
```

### Paso 1: Estructura HTML5 Semántica (Wireframe Limpio)
- Configurar el esqueleto base en [`index.html`](file:///c:/Users/G/Documents/itec/segundo/prog2/seminario_antigravity/index.html) con metadatos de viewport, accesibilidad y fuentes de Google Fonts.
- Maquetar las regiones principales: `<header>`, `<nav>`, `<main>`, `<section id="view-hero">`, `<section id="view-catalog">`, `<section id="view-contact">`, `<section id="institutional">` y `<footer>`.
- Insertar etiquetas nativas `<button>` para todas las acciones interactivas y atributos `alt` descriptivos en imágenes.

### Paso 2: Sistema de Diseño y Estilos (TailwindCSS v3 CDN)
- Inyectar el script de TailwindCDN en `<head>` con su bloque de configuración (`tailwind.config`) definiendo la paleta Teal / Ice Teal y modo oscuro.
- Aplicar clases utilitarias para la grilla responsive (1 col móvil, 3 col desktop), tipografía (`Plus Jakarta Sans` y `Noto Sans`), elevaciones de hover y reglas de contraste `.force-text-white`.

### Paso 3: Interactividad Dinámica (JavaScript Vanilla)
- Programar el enrutador SPA básico (mostrar/ocultar secciones mediante cambio de clases `hidden`/`block`).
- Implementar la apertura y cierre del Modal de Ficha Técnica, vinculando los datos de la mascota y bloqueando el scroll del body (`overflow-hidden`).
- Programar el alternador Dark/Light mode con persistencia en `localStorage`.
- Controlar el menú Drawer móvil y programar la validación del formulario con disparo del Toast verde.

### Paso 4: Auditoría de Calidad y Reporte SDD
- Evaluar la interfaz contra el Definition of Done y generar el archivo `REPORTE_VERIFICACION_SDD.md`.

---

## 2. Definition of Done (DoD) Rigurosa

Ninguna entrega se considera terminada si no cumple con el 100% de los siguientes criterios:

1. **Estructura y Semántica**: Cero elementos `<div>` utilizados como botones; todas las imágenes cuentan con atributo `alt` coherente.
2. **Control de Desbordes**: La propiedad `overflow-x: hidden` está aplicada en el body o contenedor raíz impidiendo cualquier scroll horizontal en pantallas móviles (320px a 480px).
3. **Consola Limpia**: Cero errores o advertencias rojas en la consola de herramientas de desarrollo (`F12`).
4. **Accesibilidad Táctil**: Todo botón o elemento interactivo móvil posee un área táctil mínima de 44px x 44px.
5. **Verificación Visual de los 4 Estados UI**:
   - ⏳ **Loading State**: Indicador o estado de procesamiento al simular envío del formulario.
   - 📭 **Empty State**: Mensaje claro cuando no hay resultados de búsqueda o filtros.
   - ⚠️ **Error State**: Resaltado visual en campos inválidos del formulario y mensaje de advertencia.
   - ✅ **Success State**: Renderizado accesible, modal completo y Toast verde de confirmación tras el envío exitoso.
