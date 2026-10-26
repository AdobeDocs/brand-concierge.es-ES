---
title: Datos de Brand Concierge en Marketo Engage
description: Comprenda los campos de origen de los posibles clientes y los tres tipos de actividades de conserjería escritos en Adobe Marketo Engage, y cómo utilizarlos en listas inteligentes y campañas inteligentes.
role: User, Admin
level: Beginner
product_v2:
  - id: b6ee73fe-bdc6-47d9-99a2-80194514dd40
    internal-label: Brand Concierge
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: ec567c798c52edaba7e2cfb41a837d8058bcceb7
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 4%
---
# Datos de Brand Concierge en Marketo Engage {#marketo-activities}

Cuando [!DNL Adobe Marketo Engage] está conectado, todos los visitantes que rellenan un formulario, reservan una reunión o inician una conversación en vivo se convierten en un registro de persona en [!DNL Marketo], y su participación de conserje se escribe en ese registro como tipos de actividades nativas. Esto significa que puede generar listas inteligentes y campañas inteligentes según el comportamiento del conserje exactamente como lo haría en cualquier otra actividad de [!DNL Marketo].

>[!NOTE]
>
>El chat en vivo y la reserva de reuniones no requieren [!DNL Marketo Engage]. Sin ella, los datos descritos en esta página permanecen en [!DNL Adobe Marketo Qualifier]. Ver [descripción general de la reserva de reuniones y chat en vivo](overview.md#prerequisites).

## Creación de posibles clientes y atribución de origen {#lead-creation}

Una persona creada a través de un conserje está etiquetada para que siempre puedas saber de dónde vienen.

| Campo | Valor |
| --- | --- |
| **[!UICONTROL Source de persona]** | `Brand Concierge` |
| **[!UICONTROL Tipo de Source original]** | `Chat` |
| **[!UICONTROL Información original de Source]** | `Concierge` |
| **[!UICONTROL Tipo de registro de Source]** | `Chat` |
| **[!UICONTROL Información de registro de Source]** | `Concierge` |

![Pestaña Información de registro de persona de Marketo que muestra el Source de persona establecido en Brand Concierge y los campos de origen de chat y conserjería](../assets/sales-handoff-marketo-1.png){width="800" zoomable="yes"}

## Tipos de actividades. {#activity-types}

Se insertan tres tipos de actividades nativas en el registro de persona. Los tres están disponibles como déclencheur y filtros.

![Registro de actividades de Marketo de una persona que muestre Participación con el Conserje, Programar reunión en el Conserje y Participación con chat en vivo en las entradas del Conserje](../assets/sales-handoff-marketo-2.png){width="800" zoomable="yes"}

### Interactúe con Concierge {#engage-with-concierge}

Se registra cuando un visitante se involucra con el conserje.

| Atributo | Descripción |
| --- | --- |
| Nombre del conserje | El conserje con el que el visitante se comprometió |
| Identificador de conversación | El identificador de la conversación. Úselo en Compositor para abrir la transcripción completa |
| URL de página | La página donde se produjo el compromiso |
| Creado el | Cuando se creó la conversación |
| Duración | Cuánto duró la conversación |

>[!NOTE]
>
>Algunos atributos de este tipo de actividad, incluidos los temas analizados, el resumen y el idioma, aún no se han rellenado. Están planificados para una versión futura.

### Programar reunión en Concierge {#schedule-meeting}

Se ha registrado **dos veces** para una sola reserva, que es lo que le permite separar la intención del resultado.

**Primero, al iniciarse.** El visitante seleccionó la opción de programar una reunión y apareció el formulario de reserva. El estado de la reunión es `Started`.

| Atributo | Descripción |
| --- | --- |
| Estado de reunión | `Started` |
| URL de página | La página donde el visitante inició la reserva |
| ID de conserje | El conserje con el que el visitante se comprometió |
| ID de persona | El registro de persona [!DNL Marketo] |

**Entonces, al reservar.** El visitante confirmó una ranura. El estado de la reunión es `Scheduled`.

| Atributo | Descripción |
| --- | --- |
| Estado de reunión | `Scheduled` |
| Nombre del representante de ventas | El representante con el que se reservó la reunión |
| Correo electrónico del representante de ventas | La dirección de correo electrónico del representante |
| Programado para | La fecha y hora de la reunión |
| Duración de reunión | Duración de la reunión reservada |
| Tipo de enrutamiento | El enrutamiento que resolvió el calendario de este representante |
| URL de página | La página donde el visitante hizo la reserva |
| ID de conserje | El conserje con el que el visitante se comprometió |
| ID de persona | El registro de persona [!DNL Marketo] |

>[!TIP]
>
>Generar una lista inteligente en `Meeting Status` es `Started`, pero no `Scheduled` para encontrar a todos los que empezaron a reservar una reunión y la abandonaron. Es una audiencia ya preparada para la reorientación.

### Interactúe con el chat en vivo en Concierge {#engage-with-live-chat}

Registrado después de que finalice un chat en vivo.

| Atributo | Descripción |
| --- | --- |
| Estado de conversación | `Ended` si el chat se cerró deliberadamente, `Dropped` si el visitante abandonó el sitio y se agotó el tiempo de espera del chat |
| Agentes notificados | Las direcciones de correo electrónico de todos los agentes a los que se notificó este chat |
| Puntuación de conversación | La calificación de 0 a 3 que el representante dio a la conversación. Ver [Puntuación de la conversación](chat-inbox.md#conversation-score) |
| URL de página | La página donde se inició el chat en vivo |
| ID de conserje | El conserje con el que el visitante se comprometió |
| ID de sesión | El identificador de la sesión de chat en vivo |
| Hora de inicio | Cuando comenzó el chat |

>[!TIP]
>
>La puntuación de conversación es el atributo de mayor valor aquí, porque lo establece un ser humano que realmente habló con el visitante. Utilícelo para la puntuación de posibles clientes, el redireccionamiento, la personalización y el traspaso a ventas y CRM.

## Uso de datos de concierge en una campaña inteligente {#smart-campaign}

En **[!UICONTROL Smart List]** de una campaña inteligente, busque `concierge` para ver todo lo que está disponible.

![Lista inteligente de Marketo que muestra los déclencheur y filtros disponibles para la actividad de Brand Concierge](../assets/sales-handoff-marketo-3.png){width="800" zoomable="yes"}

| Categoría | Elementos disponibles |
| --- | --- |
| **[!UICONTROL Activadores]** | Se involucra con Concierge, Se involucra con Chat en vivo en Concierge, Programa la reunión en Concierge |
| **[!UICONTROL Filtros]** > Historial de actividades | Comprometido con Concierge, Comprometido con Chat en vivo en Concierge, Reunión programada en Concierge |
| **[!UICONTROL Filtros]** > Filtros De Inactividad | No participar con Concierge, No participar con chat en vivo en Concierge, No programado reunión en Concierge |

Arrastre un déclencheur al lienzo y, a continuación, seleccione **[!UICONTROL Agregar restricción]** para reducirlo.

### Restricciones {#constraints}

| Déclencheur o filtro | Restricciones |
| --- | --- |
| Comprometido con Concierge | Nombre del conserje, URL de la página, Creado en, Duración, Fecha de la actividad |
| Reunión programada en Concierge | Nombre del conserje, Nombre del representante de ventas, Estado de la reunión, Programado para, Duración de la reunión, Tipo de enrutamiento, URL de la página, Fecha de la actividad |
| Interactuado con chat en vivo en Concierge | Nombre del conserje, Nombre del representante de ventas, Estado de la conversación, Puntuación de la conversación, Hora de inicio, Hora de aceptación, Hora de finalización, Cerrado por, Duración, Tema tratado, URL de la página, Idioma, Fecha de la actividad |

## Siguiente paso {#next}

Revise el rendimiento de las reuniones y charlas en [Supervisar reuniones y charlas en vivo](monitor.md).
