# Registro de Decisiones de Arquitectura (ADR)

Este registro documenta de forma cronológica e inmutable las decisiones arquitectónicas del proyecto **Patitas Seguras**.
Cualquier modificación o adición estructural requiere **autorización previa obligatoria** antes de su ejecución.

---

## [ADR-001] Adopción de Arquitectura SPA Client-Side en un Único Archivo
- **Fecha / Hora**: 2026-10-19 23:52:31 (-03:00)
- **Estado**: Aceptado / En vigor
- **Contexto**: Se requiere una plataforma web rápida, moderna y didáctica para un refugio de animales, evitando dependencias de empaquetadores complejos o servidores para estudiantes de programación web.
- **Decisión**: Construir la aplicación como una SPA en un solo archivo [`index.html`](file:///c:/Users/G/Documents/itec/segundo/prog2/seminario_antigravity/index.html) mediante HTML5 semántico, TailwindCSS por CDN y JavaScript Vanilla.
- **Consecuencias**:
  - *Positivas*: Cero configuración de build tools, carga inmediata en navegador, fácil despliegue y máxima portabilidad.
  - *Mitigaciones*: Se organizará el código en secciones claramente delimitadas para evitar desorden.

---

## [ADR-002] Sistema de Diseño con TailwindCSS CDN y Paleta Teal / Ice Teal
- **Fecha / Hora**: 2026-10-19 23:52:31 (-03:00)
- **Estado**: Aceptado / En vigor
- **Contexto**: El proyecto requiere un estilo visual empático y moderno que soporte Modo Oscuro y Modo Claro sin hojas de estilo infladas ni CSS monolítico.
- **Decisión**: Utilizar TailwindCSS v3 vía CDN configurando modo de inicio Oscuro (fondo Teal oscuro profundo), fondo Claro Ice Teal (`#ECFEFF`), y regla estricta `.force-text-white` para elementos interactivos.
- **Consecuencias**:
  - *Positivas*: Consistencia de diseño, alternancia ágil entre temas, alto contraste visual garantizado.

---

## [ADR-003] Prohibición Estricta de Backend, Frameworks SPA y Bases de Datos
- **Fecha / Hora**: 2026-10-19 23:52:31 (-03:00)
- **Estado**: Aceptado / En vigor
- **Contexto**: Evitar sobreingeniería (over-engineering) y asegurar que el código se mantenga alineado al alcance pedagógico del seminario.
- **Decisión**: Prohibir expresamente Node.js, Express, Python, PHP, React, Vue, Angular, Firebase y SQL.
- **Consecuencias**:
  - *Positivas*: El código es 100% testeable directamente en el cliente, seguro y sin costos de infraestructura.

---

## [ADR-004] Interacciones Críticas: Modal, Drawer Móvil y Notificaciones Toast
- **Fecha / Hora**: 2026-10-19 23:52:31 (-03:00)
- **Estado**: Aceptado / En vigor
- **Contexto**: Se requiere visualización profunda de la ficha de animales y confirmación inmediata tras enviar formularios sin recargar la página.
- **Decisión**: Implementar una ventana modal emergente con bloqueo de scroll (`overflow: hidden` en body), un menú drawer táctil móvil y un toast visual verde para confirmación de solicitudes.
- **Consecuencias**:
  - *Positivas*: Experiencia de usuario (UX) rica y profesional sin salir de la vista actual.

---

## [ADR-005] Protocolo de Modificación y Control de Guardas
- **Fecha / Hora**: 2026-10-28 17:48:00 (-03:00)
- **Estado**: Aceptado / En vigor
- **Contexto**: Mantener la integridad de los requerimientos acordados en la entrevista inicial.
- **Decisión**: Ningún cambio que altere el stack, las secciones acordadas o las tecnologías prohibidas podrá implementarse sin autorización previa del usuario y la emisión del ADR correspondiente.
