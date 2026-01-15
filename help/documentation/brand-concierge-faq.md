---
title: Preguntas frecuentes
description: Obtenga respuestas a las preguntas frecuentes sobre Adobe Brand Concierge.
role: User,Admin
level: Beginner
source-git-commit: 0f010472e3f49c5d84e9875a33215d56e020bef8
workflow-type: tm+mt
source-wordcount: '1091'
ht-degree: 1%

---

# Preguntas frecuentes

Lea esta sección para obtener respuestas a las preguntas frecuentes sobre Brand Concierge.

## General

### ¿En qué se diferencia Brand Concierge de los bots de chat?

Brand Concierge se diferencia de los bots de chat tradicionales por aprovechar la IA generativa que está específicamente entrenada en el contenido de su organización y los datos de los clientes, en lugar de depender de respuestas con scripts o resultados web genéricos. Esto permite al asistente proporcionar respuestas personalizadas basadas en el comportamiento individual de los clientes, integrarse profundamente con las herramientas y los datos de Adobe, aprender continuamente de cada interacción e interpretar con precisión la intención del cliente más allá de la coincidencia de palabras clave básicas.

### ¿Puedo utilizar Brand Concierge tanto para B2C como para B2B?

Sí. Los casos de uso incluyen:

* **B2C:** descubrimiento de productos, asistencia para compras, atención al cliente, recomendaciones personalizadas.
* **B2B:** evaluaciones guiadas, comparaciones de características, programación de reuniones, enrutamiento de representantes de ventas, reserva de consultas.

### ¿Qué industrias pueden utilizar Brand Concierge?

Brand Concierge se puede utilizar en una amplia gama de sectores, incluidos el comercio minorista y electrónico, los viajes y la hospitalidad, los servicios financieros, la sanidad (con controles de conformidad), los medios de comunicación y el entretenimiento, y la tecnología y el software. Básicamente, cualquier sector que ayude a los clientes a encontrar información y tomar decisiones puede beneficiarse de la implementación de Brand Concierge.

## Datos y privacidad

### ¿Son seguros los datos del cliente?

Sí. Brand Concierge garantiza la seguridad de los datos de los clientes cumpliendo con el RGPD y la CCPA, procesando datos en la infraestructura segura de Adobe, proporcionándole control sobre el uso de los datos y salvaguardando las conversaciones mediante el cifrado y el registro de auditoría.

Todas las conversaciones se producen en sus propiedades, no en servidores de terceros.

### ¿Qué fuentes de datos puedo conectar?

Puede conectar los siguientes tipos de fuentes de datos a Brand Concierge:

| Tipo de Source de datos | Orígenes/detalles disponibles |
|------------------|---------------------------|
| **Producto y contenido** | Catálogos de productos<br>Sistemas de inventario<br>Bases de conocimiento y documentación<br>Contenido del sitio web a través de la carga de URL CSV<br>Contenido de Adobe Experience Manager<br>Datos de Adobe Commerce |
| **Datos del cliente** | Perfiles de Adobe Experience Platform<br>Datos de comportamiento de Adobe Analytics<br>Atributos de cliente de origen<br>API de terceros (configuradas) |
| **Formato de archivo CSV** | Una columna que contiene las direcciones URL del sitio web<br>Brand Concierge rastrea las direcciones URL y extrae el contenido automáticamente<br>Se pueden cargar varios archivos CSV para diferentes áreas de contenido durante el procesamiento de actualizaciones de estado en tiempo real<br>2 |

Todos los datos siguen sus reglas de gobernanza.

### ¿Pueden los clientes excluirse de la personalización?

Sí. Los clientes que no desean participar reciben respuestas útiles sin personalización de comportamiento. Puede configurar la administración de la exclusión para que coincida con sus políticas de privacidad.

## Configuración y control

### ¿Cómo controlo la voz de la marca?

Puede controlar la voz de su marca directamente en la interfaz de usuario configurando elementos como el tono (que va desde formal a casual), el idioma (desde simple a técnico) y la personalidad (por ejemplo, útil, entusiasta o profesional). Además, puede definir patrones de respuesta mediante plantillas y ejemplos, y establecer protecciones para aplicar reglas de conformidad y límites. Comience con las instrucciones de referencia de Adobe y adapte esta configuración para reflejar la identidad única de su marca.

### ¿Qué sucede cuando Brand Concierge no puede responder a una pregunta?

Puede configurar comportamientos de reserva para determinar cómo responde Brand Concierge cuando no puede responder a una pregunta. Las opciones incluyen mostrar un mensaje &quot;No puedo ayudar con eso&quot;, sugerir preguntas alternativas, vincular a recursos de autoservicio o escalar automáticamente la consulta a un agente humano. Elija lo que mejor funcione para su marca.

### ¿Puedo personalizar el diseño visual?

Sí. Personalice todos los elementos visuales, incluidos:

* Colores y marca
* Fuentes y tipografía
* Estilos de botón
* Posición del widget
* Diseños de tarjeta
* Formato de respuesta

Los SDK proporcionan componentes predeterminados y opciones de personalización completas.

### ¿Cuánto tiempo tarda la instalación?

La duración de la configuración puede depender del tipo de implementación. Una implementación básica que incluye un catálogo de productos existente, contenido de preguntas más frecuentes estándar y configuración predeterminada puede tardar entre 3 y 5 días en configurarse. Por otro lado, las implementaciones avanzadas con integraciones personalizadas, una personalización extensa, flujos de trabajo complejos y reglas de conformidad personalizadas pueden tardar entre 2 y 4 semanas en completarse.

### ¿Cómo funcionan la previsualización y las pruebas?

Brand Concierge incluye herramientas de prueba integradas:

| Herramienta de prueba | Funcionalidades |
|--------------|----------|
| **Modo de vista previa** | Simular las conversaciones con los clientes<br>Ajustar la configuración en tiempo real<br>Ver los cambios al instante<br>Compartir los vínculos de vista previa con su equipo |
| **Vista de comprobador** | Valorar las respuestas con los pulgares arriba/abajo<br>Proporcionar comentarios estructurados en 4 categorías<br>Agregar comentarios detallados<br>Rastrear comentarios en el panel |

Todas las pruebas se realizan antes de realizar la implementación en los clientes.

### ¿Pueden los clientes programar reuniones con nuestro equipo?

Sí, los clientes pueden programar reuniones con su equipo utilizando la habilidad de reserva de reuniones. Para activar esta función, active la aptitud en Configuración de aptitudes, defina intenciones de activación (como &quot;hablar con ventas&quot;), conecte el calendario o el sistema de programación y establezca la disponibilidad y los tipos de reunión. Una vez configuradas, los clientes pueden solicitar reuniones durante las conversaciones, y Brand Concierge facilitará el proceso de programación sin que sea necesario que abandonen el chat.

### ¿Quién se encarga de la rápida ingeniería?

Los consultores de Adobe se encargan de la ingeniería rápida en segundo plano:

1. Puede responder a preguntas de configuración en la página Habilidades.
1. Proporcione conocimientos del producto, reglas empresariales y evite las palabras clave.
1. Envíe sus entradas.
1. Los consultores de Adobe utilizan sus respuestas para diseñar preguntas optimizadas.
1. Los cambios se reflejarán automáticamente en su conserje.

Esto garantiza que su conserje utilice patrones de mensajes de IA de prácticas recomendadas mientras mantiene los requisitos específicos de su marca.

## Rendimiento y análisis

### ¿Cómo se mide el éxito?

Puede medir la eficacia mediante el tablero de Brand Concierge. Utilice el tablero para realizar un seguimiento de métricas como:

| Métrica | Qué Rastrea |
|--------|----------------|
| **Participación** | Volumen de conversación, duración de la sesión |
| **Satisfacción** | Puntuaciones de opiniones, clasificaciones de comentarios |
| **Conversión** | Tasas de compra para asistencia frente a para asistencia |
| **Temas** | Preguntas y solicitudes más comunes |
| **Entrega** | Tasas y motivos de escalación |
| **Rendimiento** | Precisión de respuesta, tiempo de resolución |

También se puede integrar con Adobe Analytics para un análisis más profundo.

### ¿Qué debo hacer si los sentimientos caen?

Si nota una caída en la percepción, investigue las causas subyacentes revisando las consultas fallidas recientes, comprobando si hay huecos en el contenido, analizando los comentarios negativos, probando el tono adecuado y verificando cualquier problema técnico. Una vez identificadas las causas básicas, aborde de inmediato las mismas y continúe monitoreando la mejoría.

## Integración y asistencia técnica

### ¿Necesito otros productos de Adobe?

No, pero mejoran el rendimiento:

| Opción de integración | Competencias |
|-------------------|--------------|
| **Independiente** | Funciona con el catálogo de productos y el contenido |
| **Con Adobe Experience Platform** | Perfiles de cliente unificados<br>Personalización avanzada<br>Consistencia en canales múltiples |
| **Con Adobe Commerce** | Inventario en tiempo real<br>Historial de pedidos<br>Integración del carro de compras |
| **Con Adobe Experience Manager** | Administración de contenido<br>Actualizaciones dinámicas<br>Compatibilidad con varios sitios |

### ¿Qué sucede si mi sitio no está en Adobe?

Brand Concierge funciona con cualquier plataforma. JavaScript SDK se integra con cualquier sitio web y los SDK móviles funcionan con cualquier back-end de la aplicación.

### ¿Cómo funciona el traspaso de agentes?

Cuando se activa el traspaso de agentes, Brand Concierge transfiere al agente el historial de conversaciones completo, el perfil y el ID del cliente, la intención identificada, los detalles de los productos analizados y cualquier intento de resolución. Esto garantiza que los agentes tengan un contexto completo y puedan continuar la conversación sin problemas, sin que sea necesario que los clientes repitan la información.

### ¿Puedo utilizar varios idiomas?

Sí. Configure el soporte de idioma por asistente en función de su base de clientes. Brand Concierge detecta el idioma del cliente y responde en consecuencia.
