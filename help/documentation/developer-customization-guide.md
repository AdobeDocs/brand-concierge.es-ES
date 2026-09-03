---
title: Guía para desarrolladores y personalización
description: Obtenga información sobre cómo instalar Brand Concierge Web SDK y el cliente web, personalizar el aspecto y el contenido, controlar los eventos del lado del cliente y exportar los datos de conversación.
role: Developer,Admin
level: Experienced
toc: true
source-git-commit: 13db0491c987a08492820ac216e20feb87f30e44
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 4%

---


# Guía para desarrolladores y personalización {#developer-customization-guide}

Esta guía es para desarrolladores y equipos técnicos que implementan o personalizan una implementación de Brand Concierge. Abarca la instalación de Web SDK y Web Client, la personalización del aspecto y el contenido, la escucha de eventos del lado del cliente a través de funciones de devolución de llamada y la exportación de datos de conversación para la creación de informes.

## Instalación de Web SDK y Web Client {#installation}

### Requisitos previos {#prerequisites}

* La organización es cliente de Adobe Experience Platform (AEP).
* La página está equipada con Adobe Experience Platform Web SDK.
* El ID de flujo de datos utilizado en la página está habilitado para Brand Concierge.

### Paso 1: Inserción de Web SDK {#inject-web-sdk}

Agregue lo siguiente a la sección `<head>` de la página:

```html
<script>
  !(function (n, o) {
    o.forEach(function (o) {
      n[o] ||
        ((n.__alloyNS = n.__alloyNS || []).push(o),
        (n[o] = function () {
          var u = arguments;
          return new Promise(function (i, l) {
            n[o].q.push([i, l, u]);
          });
        }),
        (n[o].q = []));
    });
  })(window, ["alloy"]);
</script>
<script src="https://cdn1.adoberesources.net/alloy/2.31.1/alloy.min.js"></script>
```

### Paso 2: Inyectar el cliente web {#inject-web-client}

Agregue lo siguiente después del script de Web SDK, aún en la sección `<head>`:

```html
<script src="https://experience.adobe.net/solutions/experience-platform-brand-concierge-web-agent/static-assets/main.js"></script>
```

### Paso 3: Configuración de Web SDK {#configure-web-sdk}

Llame a `alloy("configure", ...)` con los valores propios de su organización en lugar de los marcadores de posición siguientes:

```javascript
alloy("configure", {
  defaultConsent: "in",
  edgeDomain: "edge.adobedc.net",
  edgeBasePath: "ee",
  datastreamId: "YOUR_DATASTREAM_ID",
  orgId: "YOUR_IMS_ORG_ID",
  debugEnabled: true,
  idMigrationEnabled: false,
  thirdPartyCookiesEnabled: false,
  prehidingStyle: ".personalization-container { opacity: 0 !important }",
  onBeforeEventSend: (options) => {
    const x = options.xdm;
    const params = new URLSearchParams(window.location.search);
    const titleParam = params.get("title");
    if (titleParam) {
      x.web.webPageDetails.name = titleParam;
    } else {
      x.web.webPageDetails.name = "default-page";
    }
    return true;
  }
});
alloy("sendEvent", {});
```

| Campo | Descripción |
|---|---|
| `datastreamId` | ID de flujo de datos configurado para esta página, habilitado para Brand Concierge. |
| `orgId` | El ID de organización de IMS en el que está configurado el conserje. |
| `debugEnabled` | Se establece en `false` en producción una vez verificada la integración. |
| `prehidingStyle` | CSS aplicado antes de que se cargue el contenido de personalización para evitar un flash de contenido sin estilo. |
| `onBeforeEventSend` | Enlace opcional para modificar la carga útil XDM antes de enviarla; normalmente se utiliza para establecer el nombre de página o el contexto. |

### Paso 4: Inicializar el cliente web {#initialize-web-client}

Después de la llamada de configuración de Web SDK, inicialice el cliente web llamando a la API de arranque:

```javascript
window.adobe.concierge.bootstrap({
  instanceName: "alloy",
  stylingConfigurations: window.styleConfigurations,
  selector: "#brand-concierge-mount"
});
```

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `instanceName` | string | Sí | Nombre de la instancia de Web SDK. |
| `stylingConfigurations` | Objeto JSON | Sí | La configuración de estilo del cliente web (consulte [Personalización de contenido y visual](#customization)). |
| `selector` | string | Sí | Selector de CSS para el elemento de HTML en el que se monta el cliente web. |
| `onEvent` | función | No | Llamada de retorno para eventos del lado del cliente (consulte [Eventos del lado del cliente y funciones de devolución de llamada](#events)). |

## Personalización visual y de contenido {#customization}

El objeto `stylingConfigurations` pasado a `bootstrap()` controla la apariencia, el comportamiento y el texto en todo el cliente web. Está organizado en varias zonas.

### Metadatos {#metadata}

```javascript
"metadata": {
  "brandName": "Your Brand",
  "version": "1.0.0",
  "language": "en-US",
  "namespace": "brand-concierge"
}
```

### Comportamiento {#behavior}

Controla el comportamiento funcional de las funciones de chat individuales.

```javascript
"behavior": {
  "input": {
    "enableVoiceInput": true
  },
  "chat": {
    "messageAlignment": "left",
    "messageWidth": "80%"
  },
  "privacyNotice": {
    "title": "Privacy Notice",
    "text": "By using this automated chatbot, you consent that any personal information you provide in the chat may be collected, used, analyzed, disclosed, and retained by Adobe and its service providers, in accordance with the Adobe Privacy Policy. Please do not enter any sensitive personal information (e.g., financial or health data)."
  },
  "disclaimer": {
    "attachWithInput": true
  },
  "chatTranscript": {
    "enabled": true,
    "maxSessions": 1,
    "maxMessagesPerSession": 20,
    "cleanupInterval": 24
  },
  "meetingForm": {
    "fieldsPerRow": 2,
    "title": { "text": "Schedule meeting", "alignment": "left" },
    "subtitle": { "text": "I'd be happy to help you schedule a meeting! Please fill out the form below, and we'll follow up with a calendar to confirm your day and time.", "alignment": "left" },
    "buttons": {
      "submit": { "text": "Schedule meeting", "alignment": "left" },
      "cancel": { "text": "Cancel", "alignment": "left" }
    }
  },
  "calendarWidget": {
    "title": { "text": "Book a meeting", "alignment": "left" },
    "subtitle": { "text": "Thanks! Here's a calendar where you can choose a time that works best for your schedule:", "alignment": "left" },
    "postTitle": { "text": "Once confirmed, you'll receive a calendar invite with all the details.", "alignment": "left" },
    "buttons": {
      "confirm": { "text": "Schedule a meeting", "alignment": "left" },
      "cancel": { "text": "Cancel", "alignment": "left" }
    }
  }
}
```

### Descargo de responsabilidad {#disclaimer}

```javascript
"disclaimer": {
  "text": "AI responses may be inaccurate or misleading. Be sure to double check answers and sources."
}
```

### Cadenas de texto {#text-strings}

Toda la copia orientada al usuario se puede sobrescribir mediante el objeto `text`. Claves comunes:

| Clave | Objetivo |
|---|---|
| `welcome.heading` / `welcome.subheading` | Titular y subtexto de la pantalla de bienvenida |
| `input.placeholder` | Texto de marcador de posición de campo de entrada |
| `input.messageInput.aria` / `input.send.aria` / `input.mic.aria` | Etiquetas de accesibilidad para los controles de entrada |
| `error.network` / `error.general` | Mensajes de error mostrados al visitante |
| `loading.message` | Texto mostrado mientras se genera una respuesta |
| `feedback.dialog.title.positive` / `.negative` | Títulos del cuadro de diálogo Comentarios |
| `feedback.dialog.question.positive` / `.negative` | Texto del mensaje del cuadro de diálogo Comentarios |
| `feedback.toast.success` | Mensaje de confirmación después de enviar los comentarios |
| `feedback.thumbsUp.aria` / `feedback.thumbsDown.aria` | Etiquetas de accesibilidad para los botones de comentarios |

### Matrices {#arrays}

Listas de contenido configurables:

```javascript
"arrays": {
  "welcome.examples": [
    {
      "text": "I want to edit and enhance my photos",
      "image": "https://example.com/idea-1.png",
      "backgroundColor": "#66BFE7"
    }
  ],
  "feedback.positive.options": [
    "Helpful and relevant recommendations",
    "Clear and easy to understand",
    "Friendly and conversational tone",
    "Visually appealing presentation",
    "Other"
  ],
  "feedback.negative.options": [
    "Not helpful or relevant",
    "Confusing or unclear",
    "Too formal or robotic",
    "Poor visual presentation",
    "Other"
  ]
}
```

### Recursos {#assets}

```javascript
"assets": {
  "icons": {
    "company": "<svg>...</svg>"
  }
}
```

### Tema {#theme}

Propiedades personalizadas de CSS que controlan los colores, las fuentes y el diseño:

```css
"theme": {
  "--color-primary": "#1473e6",
  "--color-primary-hover": "#0056b3",
  "--color-button-primary": "#3B63FB",
  "--color-accent": "#9085ED",
  "--color-button-submit": "#4759e6",
  "--color-button-submit-hover": "#3a4bce",
  "--color-message-user": "#1473e6",
  "--font-family": "'Adobe Clean', adobe-clean, 'Trebuchet MS', sans-serif",
  "--main-container-background": "linear-gradient(135deg, #66ccff, #cc99ff, #ffcc99, #ccff99)",
  "--submit-button-fill-color": "white",
  "--card-text-background": "var(--color-background)",
  "--card-text-border-radius": "var(--border-radius-card)",
  "--message-concierge-link-decoration": "underline",
  "--message-max-width": "100%"
}
```

## Eventos del lado del cliente y funciones de llamada de retorno {#events}

El sistema de llamada de retorno de evento permite que una página observe eventos del ciclo vital del cliente web, interacciones del usuario, respuestas, comentarios y errores en tiempo real, lo cual resulta útil para enviar datos de participación a Adobe Analytics, Google Analytics u otros sistemas de terceros.

### Características principales {#key-characteristics}

* **Devolución de llamada única** — una función `onEvent` recibe todos los tipos de eventos, distinguida por `event.eventType`.
* **Solo lectura**: los datos de evento son una instantánea clonada y no se pueden usar para modificar el comportamiento del cliente.
* **Aisladas por errores**: las excepciones iniciadas dentro de la devolución de llamada se capturan y registran; no rompen el cliente web.
* **Registrado a través de`bootstrap()`** — pasado de la misma manera que `onBeforeEventSend`.

### Inicio rápido {#quick-start}

```javascript
window.adobe.concierge.bootstrap({
  instanceName: "my-instance",
  selector: "#brand-concierge-mount",
  stylingConfigurations: { /* ... */ },
  onEvent: (event) => {
    console.log(event.eventType, event.timestamp, event.data);
  }
});
```

### Filtrado por tipo de evento {#filtering}

```javascript
onEvent: (event) => {
  switch (event.eventType) {
    case "query:submitted":
      console.log("User query:", event.data.query);
      break;
    case "response:completed":
      console.log("Response received:", event.data.conversationId);
      break;
    case "card:clicked":
      console.log("Card clicked:", event.data.element.entity_info.productName);
      break;
    case "error:occurred":
      console.log("Error:", event.data.errorMessage);
      break;
  }
}
```

### Tipos de eventos {#event-types}

| Tipo de evento | Valor | Categoría | Cuando se activa |
|---|---|---|---|
| `WEBCLIENT_INITIALIZED` | `webclient:initialized` | Ciclo de vida | El cliente finaliza la inicialización (DOM montado, contenido cargado) |
| `QUERY_SUBMITTED` | `query:submitted` | Interacción del usuario | El usuario envía un mensaje (escrito o por sugerencia) |
| `PROMPT_SUGGESTION_CLICKED` | `promptSuggestion:clicked` | Interacción del usuario | El usuario hace clic en una píldora de sugerencias |
| `CARD_CLICKED` | `card:clicked` | Interacción del usuario | El usuario hace clic en una tarjeta |
| `HISTORY_CLEARED` | `history:cleared` | Interacción del usuario | El usuario borra el historial de chat |
| `RESPONSE_STARTED` | `response:started` | Respuesta | El primer fragmento de flujo llega desde la API |
| `RESPONSE_COMPLETED` | `response:completed` | Respuesta | Se recibe y se representa la respuesta completa |
| `CARDS_RENDERED` | `cards:rendered` | Respuesta | Las tarjetas (de una sola imagen o carrusel) finalizan la renderización |
| `FEEDBACK_SUBMITTED` | `feedback:submitted` | Comentarios | El usuario envía un formulario de comentarios (miniaturas arriba/abajo con detalles) |
| `ERROR_OCCURRED` | `error:occurred` | Error | Se produce un error (red, API o tiempo de ejecución) |

### Eventos de ciclo vital {#lifecycle-events}

`webclient:initialized` se activa después de que el cliente se haya inicializado completamente: contenido cargado, CSS insertado, IU de chat representada en el DOM.

```json
{
  "eventType": "webclient:initialized",
  "timestamp": 1741638123789,
  "data": {
    "instanceName": "my-instance"
  }
}
```

### Eventos de interacción del usuario {#user-interaction-events}

`query:submitted` se activa cuando el usuario envía un mensaje, independientemente de si ha escrito, desde una sugerencia o desde una opción de widget.

```json
{
  "eventType": "query:submitted",
  "timestamp": 1741638124000,
  "data": {
    "query": "What photo editing tools do you offer?"
  }
}
```

`promptSuggestion:clicked` se activa cuando el usuario hace clic en una píldora de sugerencias de mensajes. Se activa *antes de* el evento `query:submitted` subsiguiente.

```json
{
  "eventType": "promptSuggestion:clicked",
  "timestamp": 1741638124100,
  "data": {
    "suggestion": "Tell me more about Photoshop"
  }
}
```

`card:clicked` se activa cuando el usuario hace clic en una tarjeta.

```json
{
  "eventType": "card:clicked",
  "timestamp": 1741638124200,
  "data": {
    "element": {
      "entity_info": {
        "productName": "Adobe Photoshop",
        "productDescription": "Photo editing software",
        "productPageURL": "https://www.adobe.com/es/products/photoshop.html",
        "productImageURL": "https://example.com/photoshop.png"
      }
    }
  }
}
```

`history:cleared` se activa cuando el usuario hace clic en el botón borrar historial de chat.

```json
{
  "eventType": "history:cleared",
  "timestamp": 1741638124400,
  "data": {}
}
```

### Eventos de respuesta {#response-events}

`response:started` se activa cuando llega el primer fragmento de flujo continuo desde la API.

```json
{
  "eventType": "response:started",
  "timestamp": 1741638125000,
  "data": {
    "conversationId": "conv-abc-123",
    "interactionId": "int-xyz-456"
  }
}
```

`response:completed` se activa cuando se recibe la respuesta completa.

```json
{
  "eventType": "response:completed",
  "timestamp": 1741638126000,
  "data": {
    "conversationId": "conv-abc-123",
    "interactionId": "int-xyz-456"
  }
}
```

`cards:rendered` se activa después de que las tarjetas se representen en el DOM. Se activa por separado de `response:completed` e indica el modo de visualización utilizado.

```json
{
  "eventType": "cards:rendered",
  "timestamp": 1741638126100,
  "data": {
    "element": [
      { "entity_info": { "productName": "Adobe Photoshop" } },
      { "entity_info": { "productName": "Adobe Illustrator" } }
    ],
    "displayMode": "carousel"
  }
}
```

### Eventos de comentarios {#feedback-events}

`feedback:submitted` se activa cuando el usuario completa y envía un formulario de comentarios (después de reducir/reducir los miniaturas).

```json
{
  "eventType": "feedback:submitted",
  "timestamp": 1741638127000,
  "data": {
    "conversationId": "conv-abc-123",
    "interactionId": "int-xyz-456",
    "feedbackType": "negative",
    "selectedOptions": ["Incorrect information", "Not relevant"],
    "notes": "The response did not address my question about pricing."
  }
}
```

### Eventos de error {#error-events}

`error:occurred` se activa cuando el cliente encuentra un error de red, API o tiempo de ejecución.

```json
{
  "eventType": "error:occurred",
  "timestamp": 1741638128000,
  "data": {
    "errorMessage": "Something went wrong. Please try again."
  }
}
```

### Estructura del objeto de evento {#event-object-structure}

Todos los eventos comparten la misma forma de nivel superior:

```typescript
interface BrandConciergeEvent {
  eventType: string;  // e.g. "query:submitted"
  timestamp: number;  // Unix epoch, milliseconds
  data: object;       // Event-specific payload
}
```

### Referencia de tipo de datos: Elemento (tarjeta de producto) {#element-reference}

```typescript
interface Element {
  id?: string;
  type?: string;
  entity_info: {
    productName: string;
    productDescription: string;
    description: string;
    productPageURL: string;
    details: string;
    backgroundColor: string;
    learningResource: string;
    productImageURL: string;
    logo: string;
    variants?: Record<string, ElementVariant>;
    primary: ElementAction;
    secondary: ElementAction;
  };
}

interface ElementAction {
  label: string;
  url: string;
}
```

### Prácticas recomendadas {#best-practices}

* **Usar para análisis y supervisión.** Rastrear participación, patrones de consulta e interés del producto; reenviar `error:occurred` a un servicio de seguimiento de errores; rastrear clics de tarjetas para el análisis de conversión.
* **Mantenga la llamada de retorno rápida.** Se ejecuta sincrónicamente en el subproceso principal, por lo que evite bloquear las llamadas de red:

```javascript
// Good — fire and forget
onEvent: (event) => {
  navigator.sendBeacon("/analytics", JSON.stringify(event));
}

// Avoid — blocking network call
onEvent: async (event) => {
  await fetch("/analytics", { body: JSON.stringify(event) });
}
```

* **No confíe en el orden de eventos estricto** para las máquinas de estado. Los eventos se desencadenan en una secuencia lógica, pero se utilizan `conversationId` y `interactionId` para correlacionar eventos relacionados en lugar de asumir el orden.
* **Gestionar errores dentro de su propia devolución de llamada.** El cliente aísla y registra los errores de devolución de llamada, pero los errores no controlados dentro de la devolución de llamada pueden perder datos de análisis:

```javascript
onEvent: (event) => {
  try {
    myAnalytics.track(event);
  } catch (e) {
    console.warn("Analytics tracking failed", e);
  }
}
```

## Exportar conversaciones mediante el servicio de consultas de AEP {#export-conversations}

Brand Concierge escribe datos de conversación (preguntas, respuestas y comentarios) en conjuntos de datos de Adobe Experience Platform (AEP). Puede consultarlos directamente con el servicio de consultas (SQL) para crear informes personalizados.

### Buscar el conjunto de datos y el nombre de tabla {#find-dataset}

1. Abra Adobe Experience Platform.

1. Ir a **[!UICONTROL Conjuntos de datos]**.

1. Busque `cja_brand_concierge` para ver una lista de los conjuntos de datos relacionados con Brand Concierge.

1. Abra el conjunto de datos que necesite (por ejemplo, respuestas en comparación con otros flujos, si existe más de uno).

1. En la vista de detalles del conjunto de datos, busque el **[!UICONTROL nombre de tabla]** que usa el servicio de consultas e inspeccione los datos de ejemplo o de vista previa para confirmar las columnas (avisos, respuestas, comentarios, marcas de tiempo, etc.).

>[!NOTE]
>
>Los nombres de las tablas están vinculados a cada conjunto de datos y difieren según el entorno y la zona protegida. Si tiene varios entornos limitados o implementaciones, repita estos pasos en el entorno limitado correcto para que el nombre de la tabla coincida con el lugar en el que se escriben los datos.

### Consulta de ejemplo {#example-query}

```sql
SELECT *
FROM cja_brand_concierge_responses_dataset_5f5105bd_1c38_4ebc_8505_bd
WHERE timestamp >= TIMESTAMP '2026-03-16 00:00:00'
  AND timestamp <= NOW()
ORDER BY timestamp ASC;
```

>[!IMPORTANT]
>
>El nombre de la tabla anterior es solo una ilustración; no la codifique. Confirme primero el nombre real de la tabla para el conjunto de datos en AEP (consulte [Buscar el conjunto de datos y el nombre de la tabla](#find-dataset)) y ajuste el filtro de tiempo, el criterio de ordenación u otras cláusulas para que coincidan con sus necesidades de creación de informes. Ejecute la consulta desde el flujo de trabajo del servicio de consulta de su organización (interfaz de usuario, API o cliente conectado), utilizando la misma zona protegida que el conjunto de datos.

### Ejecute una consulta en la interfaz de usuario del servicio de consultas {#run-query-ui}

Si necesita una extracción manual de datos para la creación de informes, la interfaz de usuario del servicio de consultas proporciona una forma de ejecutar y descargar los resultados directamente:

1. En Adobe Experience Platform, vaya a **[!UICONTROL Consultas]**.

1. Escriba la consulta en el editor y haga clic en **[!UICONTROL Ejecutar consulta]**.

1. Los resultados aparecen en la ficha **[!UICONTROL Resultados]** debajo del editor una vez que se completa la consulta. A partir de ahí, puede descargar los resultados.

### Lectura adicional {#further-reading}

* [Documentación de la API del servicio de consultas](https://experienceleague.adobe.com/es/docs/experience-platform/query/home){target="_blank"}: la referencia oficial de Adobe para el comportamiento, los límites, la autenticación y las rutas de API del servicio de consultas, que cambian con el tiempo independientemente de esta guía.
