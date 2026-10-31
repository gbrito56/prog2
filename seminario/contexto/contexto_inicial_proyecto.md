# Resumen de Entrevista y Contexto Inicial del Proyecto

## 1. Identidad y Propósito
- **Nombre**: "Patitas Seguras - Refugio & Rescate"
- **Propósito**: Conectar animales rescatados en tránsito con familias adoptantes, gestionar reportes de rescates y dar visibilidad al equipo y sede física del refugio.

## 2. Glosario de Términos (Vocabulario Ubicuo)
- **Refugio**: Espacio físico y organización dedicada a la protección animal.
- **Hogar de tránsito**: Espacio temporal familiar para rehabilitación antes de adopción definitiva.
- **Pedido / Reporte de rescate**: Formulario de alerta ciudadana sobre animales en riesgo.
- **Ficha de adopción**: Información clínica, temperamental y datos del animal.
- **Castrado / Esterilizado**: Estado quirúrgico para control poblacional y salud.
- **Adopción responsable**: Compromiso formal de cuidado integral a largo plazo.
- **Vacunación**: Registro de esquema inmunológico al día.
- **Donaciones**: Aporte económico o de insumos materiales para el refugio.

## 3. Estructura y Navegación SPA
- **Navbar fijo superior**: Logo, selector Dark/Light mode y enlaces de navegación entre vistas.
- **Menú Drawer**: Menú móvil táctil tipo hamburguesa accesible (botones min 44px).
- **Vista 1 (Hero Portada)**: Presentación emotiva, llamado a la acción (CTA) con redirección al catálogo o reporte.
- **Vista 2 (Catálogo de Tarjetas)**: Grilla de animales en tránsito con modal dinámico de detalle.
- **Vista 3 (Formulario de Contacto / Reserva / Rescate)**: Captura de datos con Toast verde de confirmación.
- **Información Institucional del Refugio**: Detalle de sede física, voluntarios, horarios y donaciones por debajo del formulario.
- **Footer**: Enlaces, redes sociales y contacto de emergencia.

## 4. Componente de Tarjeta (Cards)
- 6 tarjetas completas de animales.
- Atributos por tarjeta: Imagen optimizada con `alt` descriptivo, badge de categoría, nombre del animal, datos clave (especie, edad, sexo, estado de salud, descripción breve de personalidad) y botón semántico `<button>` "Ver ficha".
- Comportamiento: Apertura de ventana modal emergente con detalles completos y bloqueo de scroll de fondo.

## 5. Formulario Interactivo y Feedback
- Campos: Nombre completo, Email, Teléfono/WhatsApp, Motivo (Postulación de Adopción, Ofrecer Tránsito, Reporte de Rescate, Donación/Voluntariado), Mensaje.
- Validación y Feedback: Notificación Toast visual verde de confirmación al enviar.

## 6. Sistema de Diseño y Tokens Visuales
- **Modo inicial**: Modo Oscuro (Dark Mode).
- **Fondo Dark**: Teal oscuro profundo.
- **Fondo Light (Ice Teal)**: `#ECFEFF`.
- **Color Principal**: Teal vibrante con contraste verificado.
- **Regla de contraste**: Clase utilitaria `.force-text-white` para botones de acción y badges.
- **Colores secundarios**: Acentos armónicos (cálidos/ámbar para alertas y rescates).

## 7. Tipografía
- **Encabezados**: Plus Jakarta Sans (semibold, Google Fonts).
- **Párrafos y cuerpo**: Noto Sans (Google Fonts).

## 8. Diseño Responsive y Micro-interacciones
- **Grilla**: 1 columna en móviles, 3 columnas en desktop.
- **Móvil**: Menú drawer táctil y botones con área de toque mínima de 44px.
- **Hover**: Elevación sutil de tarjetas (`transform: translateY(-4px)`), sombras difuminadas fluidas y transiciones suaves en botones.

## 9. Decisiones Técnicas y Guardarraíles
- **Framework CSS**: TailwindCSS v3 oficial vía CDN (script en `<head>`).
- **Arquitectura**: Single Page Application (SPA) liviana en un solo archivo `index.html`.
- **Lógica**: JavaScript Vanilla limpio en el navegador.
- **Límites estrictos**: CERO React/Vue/Angular, CERO backend Node/Python/PHP, CERO bases de datos externas SQL/Firebase.

## 10. Flujo de Trabajo, DoD y Prevención de Gotchas
- **Construcción por capas**: HTML semántico ➔ TailwindCSS ➔ JS dinámico.
- **Definition of Done (DoD)**: Verificación y documentación de los 4 estados UI (Loading, Empty, Error, Success) en `REPORTE_VERIFICACION_SDD.md`.
- **Blindaje anti-gotchas**:
  - `overflow-x: hidden` para prevenir scroll horizontal accidental en celulares.
  - Atributos `alt` obligatorios en todas las imágenes.
  - Uso exclusivo de etiquetas semánticas `<button>` para elementos interactivos.
