---
description: Notas de la versión actuales de Adobe Brand Concierge.
title: Notas de la versión actual
feature: Release Information
source-git-commit: 35ce8a7b460e97336246293ad5e53ee83ead5108
workflow-type: tm+mt
source-wordcount: '1046'
ht-degree: 0%

---

# Información de la versión actual {#current-release-notes}

Adobe Brand Concierge sigue un modelo de entrega continua, lo que permite a Adobe ofrecer nuevas funciones, mejoras y correcciones de forma continua.

Todas las funciones están disponibles generalmente a menos que se indique lo contrario.

## Agosto de 2026 {#august-2026}

* **Compositor 2.0**: la creación de un conserje se rediseña en torno a una sola dirección URL del sitio web. Composer redacta automáticamente un punto de partida alineado con la marca, que incluye la expresión de marca, el perfil de la marca, las instrucciones, las protecciones, una fuente de conocimiento y una aptitud de línea de base, listos para revisar y publicar en minutos sin necesidad de configuración manual para comenzar.

* **Marco de habilidades e integraciones**: los conserjes se crean a partir de un catálogo de habilidades e integraciones de autoservicio, que se pueden descubrir y configurar a través de las habilidades de exploración y las integraciones de exploración. Esto incluye funciones nuevas y lanzadas anteriormente, como asesoramiento del sitio, asesoramiento de productos y detección y comparación de catálogos de Commerce.

* **Personalización de componentes de chat y estilo visual**: personalice los colores, las fuentes, el mensaje de bienvenida y los componentes de chat individuales de un conserje, incluidas las burbujas de chat, las sugerencias de mensajes, las citas, los controles de comentarios y las tarjetas de producto, con los cambios que se previsualizan en directo.

* **Múltiples conserjes por espacio aislado**: Cree y administre varios conserjes en un solo espacio aislado, cada uno con una configuración independiente.

* **Eventos del lado del cliente y funciones de devolución de llamada**: registre una sola devolución de llamada para observar eventos del ciclo de vida del cliente web, interacciones del usuario, respuestas, comentarios y errores en tiempo real, para usarla para enviar datos de participación a Adobe Analytics, Google Analytics u otros sistemas de terceros.

* **Soporte de Conserjería Multilingüe (Disponibilidad Limitada)**: Implemente un Conserjería en otros idiomas además del inglés, con soporte validado para español y francés. Cada idioma de destino se ejecuta como su propio conserje en la misma zona protegida y se enruta automáticamente mediante el idioma de solicitud.

* **Implementación: Configuración de flujo de datos y superficie**: configure un flujo de datos para rastrear la participación del visitante y, a continuación, defina reglas de superficie para controlar en qué páginas y dominios aparece el conserje, usando coincidencia de dominios y rutas (cualquiera, empieza por, termina por o coincidencia exacta).

## Junio de 2026 {#june-2026}

* **Integración de Marketo**: Las conversaciones de los visitantes, incluida la captura de posibles clientes en el chat, fluyen automáticamente a Marketo Engage como datos de actividad nativos, disponibles para su uso en campañas inteligentes en déclencheur y por lotes.

## Abril de 2026 {#april-2026}

* **Integración de Brand Concierge con Real-Time CDP (disponibilidad limitada)**: mejore la calidad y la relevancia de las respuestas conversacionales incorporando el contexto de Real-Time CDP, como los atributos del usuario, las señales de comportamiento y las interacciones anteriores para alinear mejor las respuestas con la intención del usuario.

* **Mejora de ajuste de autoservicio**: Brand Concierge Composer evalúa automáticamente el rendimiento de la conversación y actualiza las configuraciones de solicitud para mejorar la calidad de la respuesta. Estas optimizaciones se aplican continuamente en función de los resultados de la evaluación automatizada, lo que reduce la necesidad de un ajuste manual.

* **Recomendación de producto según el contexto**: Brand Concierge ofrece recomendaciones de producto basadas en la intención inferida del usuario, aprovechando los datos estructurados del catálogo de productos y la capacidad de integrarse con los sistemas de registro de búsqueda de productos y recomendaciones para mejorar la relevancia y la precisión. Las tarjetas de producto se presentan cuando corresponde, admiten recomendaciones de varios productos y se alinean con la intención de descubrimiento o compra.

* **Comparación en paralelo**: Habilite la comparación en paralelo de varios productos dentro de la conversación a través de una vista de tabla estructurada, en la que se resalten los atributos, características y diferencias clave. La comparación se genera dinámicamente en función de la intención del usuario y los productos seleccionados, lo que permite una evaluación y una toma de decisiones más informadas.

* **Agente de soporte (Guía de solución de problemas y procedimientos)**: habilite soporte guiado dentro de la conversación ayudando a los usuarios a solucionar problemas y completar tareas de procedimientos mediante asistencia según el contexto. El agente adapta las respuestas en función de los datos introducidos por el usuario para lograr una resolución eficaz del problema sin necesidad de escalación.

## Marzo de 2026 {#march-2026}

* **Configuración de AEM de Site Advisor en el Compositor**: La configuración de AEM de Site Advisor en el Compositor permite a los clientes de AEM configurar fácilmente la ingesta de fuentes de conocimiento directamente en el Compositor, con el contenido del sitio web de AEM como fuente de conocimiento principal. Esto reduce la fricción de incorporación y, al mismo tiempo, garantiza respuestas precisas, compatibles y predecibles basadas en el contenido AEM del cliente.

* **Ingesta de sitios completos**: la ingesta de sitios completos permite a los clientes ingerir automáticamente todo el sitio web mediante un solo mapa del sitio, lo que elimina la necesidad de cargar manualmente las direcciones URL. Esto garantiza una cobertura de contenido completa y actualizada con una incorporación escalable, de bajo esfuerzo y una actualización de contenido continua.

* **Creación automatizada de mensajes (disponibilidad limitada)**: la creación automatizada de mensajes permite a los clientes crear una experiencia de Brand Concierge de alta calidad mediante un flujo de autoservicio sencillo. Brand Concierge genera automáticamente mensajes de concierge a partir de entradas mínimas del usuario sin exponer ni requerir ingeniería rápida. Los usuarios no técnicos pueden obtener rápidamente un conserje funcional y validado con calidad a través de la validación guiada del perfil de marca y la configuración controlada por IA.

* **BYOA: agente de Firefly en Adobe.com Brand Concierge**: la generación de imágenes de Firefly ahora está integrada en Adobe.com Brand Concierge, lo que permite a los usuarios crear, descargar y seguir editando imágenes o paneles de HUMOR en Firefly. Este es nuestro primer lanzamiento de la integración &quot;Traer su propio agente&quot;, que permite a los agentes de clientes y terceros dentro de Brand Concierge a través de Agent Orchestrator.

## Febrero de 2026 {#february-2026}

* **Generación automatizada de conjuntos de datos de evaluación**: genere automáticamente conjuntos de datos de evaluación de alta calidad para evaluaciones funcionales, fuera de ámbito y de salvaguardia. El conjunto de datos eval se basa directamente en la base de conocimientos de la marca, lo que garantiza pruebas fiables y de alta confianza.

* **Evaluación automatizada y bucle de calidad basado en LLM**: valide el rendimiento de Concierge con un solo clic utilizando una puntuación basada en LLM en dimensiones de calidad, incluida la corrección, la utilidad y el cumplimiento de la marca. Esto ofrece evaluaciones de calidad objetivas y repetibles que dan confianza a los clientes antes de cada lanzamiento.

* **Automatización para tareas de creación y lanzamiento de Concierge (interfaz de usuario del desarrollador)**: se trata de una característica interna orientada al desarrollador que permite a los equipos girar e iniciar una experiencia de Concierge rápidamente, con opciones para administrar la zona protegida y la configuración de Concierge, la configuración de la interfaz de usuario/estilo y el ajuste rápido. Esto acelera el tiempo de lanzamiento y permite a los equipos crear instancias de Concierge personalizadas y de alta calidad a escala.

* **Mejora de Knowledge Source: Carga/actualización incremental de URL y compatibilidad con tipos de archivo adicionales**: La característica de administración incremental de URL permite a los clientes actualizar (agregar/eliminar/actualizar) fácilmente solo las páginas que han cambiado, sin volver a procesar toda la fuente de conocimiento. Esto reduce el tiempo de actualización y la sobrecarga operativa. Además, Brand Concierge ahora admite la carga de archivos PDF/DOCX.

* **Compatibilidad con esquemas de productos personalizados**: La característica de compatibilidad con esquemas personalizados permite a los clientes cargar y administrar catálogos de productos que siguen su propia estructura de datos en lugar de un formato fijo. Esto permite la validación adecuada, la asignación de campos y la generación precisa de tarjetas de producto en todas las marcas con diferentes modelos de catálogo.

* **SDK móvil**: Brand Concierge Mobile SDK (para aplicaciones móviles) permite a las marcas incrustar Brand Concierge directamente en sus aplicaciones móviles y admitir interacciones de texto, voz e imagen. Proporciona una interfaz y una integración back-end predeterminadas para que los consumidores puedan acceder fácilmente a Brand Concierge dentro de la aplicación de la marca.
