# Glosario del Proyecto: Patitas Seguras

Este glosario define el vocabulario ubicuo del dominio del negocio y los componentes de la interfaz de usuario para garantizar coherencia en textos, etiquetas, variables y mensajes.

---

## 1. Términos del Dominio (Negocio de Protección Animal)

- **Refugio**: Organización y sede física dedicada al rescate, rehabilitación médica, contención y reubicación de animales domésticos en situación de vulnerabilidad o abandono.
- **Hogar de Tránsito**: Familia o cuidador voluntario que hospeda temporalmente a un rescatado en su casa mientras completa tratamientos médicos o hasta concretar su adopción definitiva.
- **Pedido / Reporte de Rescate**: Alerta comunitaria enviada a través de la web para reportar a un animal accidentado, perdido o en situación de calle para coordinar auxilio.
- **Ficha de Adopción**: Registro estructurado de cada rescatado que resume sus datos biológicos (nombre, especie, sexo, edad aproximada, temperamento y estado veterinario).
- **Adopción Responsable**: Proceso formal y ético mediante el cual una familia asume el compromiso legal, afectivo y económico de cuidar al animal durante toda su vida.
- **Castrado / Esterilizado**: Procedimiento quirúrgico veterinario realizado al animal para control poblacional y prevención de enfermedades.
- **Vacunación al Día**: Constancia médica de que el animal cuenta con su plan sanitario completo (quíntuple, séxtuple, antirrábica).
- **Padrinazgo / Donación**: Contribución monetaria o en especie (alimento balanceado, pipetas, mantas) realizada por simpatizantes para costear insumos médicos y alimentación.

---

## 2. Componentes de Interfaz de Usuario (UI & UX)

- **SPA (Single Page Application)**: Arquitectura web que carga una sola página HTML y actualiza la vista dinámicamente mediante JavaScript sin refrescar el navegador.
- **Navbar Fijo**: Barra de navegación superior anclada en la parte alta de la pantalla (`sticky` o `fixed`) con acceso permanente al menú y al conmutador de temas.
- **Drawer Hamburguesa**: Menú lateral desplegable optimizado para teléfonos inteligentes activado por un botón táctil con área de toque mínima de 44px.
- **Hero Section**: Portada principal de alto impacto visual con mensaje emotivo y botón de llamada a la acción principal (CTA).
- **Card (Tarjeta de Animal)**: Contenedor visual atómico que sintetiza los datos de un rescatado (foto, badges, datos y botón de acción).
- **Badge de Categoría**: Etiqueta compacta con color temático que destaca atributos esenciales (ej: *"En Adopción"*, *"Urgente"*, *"Cachorro"*, *"Senior"*).
- **Modal Emergente**: Ventana en capa superior (*overlay*) que se superpone a la pantalla al presionar `"Ver ficha"`, bloqueando el scroll de fondo y mostrando la ficha técnica detallada.
- **Toast Verde**: Notificación visual flotante no intrusiva que aparece tras enviar el formulario confirmando el éxito del trámite.
- **Theme Toggle**: Selector interactivo para alternar entre Modo Oscuro (Teal Profundo) y Modo Claro (Ice Teal `#ECFEFF`).
