---
title: Información general de Live Chat y Meeting Booking
description: Descubra cómo Brand Concierge entrega a un visitante a un ser humano, ya sea como chat en vivo con un representante disponible o como una reunión reservada en el calendario de un representante.
role: User, Admin
level: Beginner
TQID: https://experienceleague.adobe.com/vfX6M2-ts7d2-AxKGjaP1Ygkk3FGSGRl4CHslcKYSXU
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
source-git-commit: 91cbec8d6f4e4800e3bdc8c8f60bfe9ed168a963
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 0%
---
# Descripción general de chat en vivo y reservas de reuniones {#overview}

Un conserje responde a la mayoría de las preguntas por su cuenta. Algunas conversaciones necesitan una persona: una negociación de precios, un cuestionario de compras, una solicitud de demostración. El chat en vivo y la reserva de reuniones son las dos maneras en que Brand Concierge entrega esa conversación a un ser humano sin perder el contexto que el visitante ya proporcionó.

* El chat en vivo conecta al visitante con un representante disponible inmediatamente, en la misma ventana de chat.
* La reserva de reuniones ofrece al visitante espacios abiertos reales del calendario de un representante y reserva la reunión.

Ambos son ofrecidos por la misma aptitud, **[!UICONTROL Entrega a ventas]**, y ambos se dirigen a través de [!DNL Adobe Marketo Qualifier] (anteriormente [!DNL Sales Qualifier]), donde sus representantes conectan sus calendarios, establecen su disponibilidad y toman charlas.

## Cómo funciona un traspaso {#how-it-works}

Cuatro piezas tienen que alinearse antes de que un visitante pueda llegar a una persona.

| Pedazo | Qué hace | Dónde lo configuró. |
| --- | --- | --- |
| Perfil del representante | Conecta un calendario y declara cuándo el representante está disponible para reuniones y para charlas | [!DNL Adobe Marketo Qualifier] > **[!UICONTROL Configuración de perfil]** |
| Enrutamiento | Decide *qué* representante obtiene este visitante | [!DNL Adobe Marketo Qualifier] > **[!UICONTROL Reglas de enrutamiento]** y el tipo de enrutamiento en cada integración |
| Integraciones | La **[!UICONTROL reserva de reuniones]** y el **[!UICONTROL chat en vivo]** le permiten al conserje comprobar la disponibilidad, iniciar una conversación y reservar un espacio | Compositor > **[!UICONTROL Integraciones de exploración]** |
| Habilidad | **[!UICONTROL Envío a ventas]** decide *cuándo* ofrecer un envío, según la intención del visitante | Compositor > **[!UICONTROL aptitudes de exploración]** |

En tiempo de ejecución, el visitante indica algo que coincide con una de las **[!UICONTROL condiciones de uso de la aptitud cuando]**. La aptitud se activa y llama a las integraciones que estén adjuntas. A continuación, el enrutamiento resuelve un representante y se ofrece al visitante una conversación, una reunión o ambas cosas.

>[!NOTE]
>
>Las habilidades e integraciones son los componentes básicos generales de un conserje. Para el modelo subyacente, consulte [Marco de aptitudes e integraciones](../skills-and-integrations.md).

## La experiencia del visitante {#visitor-experience}

Cuando la habilidad se activa, el conserje explica las opciones y las presenta como botones en la conversación.

![La respuesta del conserje ofrece un traspaso, con Chat con un especialista ahora y los botones de Programar reunión debajo](../assets/sales-handoff-visitor-1.png){width="800" zoomable="yes"}

### Chat en vivo {#visitor-live-chat}

Si el visitante decide chatear, el conserje muestra un estado de conexión mientras el enrutamiento encuentra un representante disponible.

![Conserje mostrando una conexión a un estado de especialista después de que el visitante seleccione Chatear con un especialista ahora](../assets/sales-handoff-visitor-2.png){width="800" zoomable="yes"}

Antes de que el representante se una, el visitante completa un breve formulario de conversación previa. Estas respuestas viajan con la conversación y aparecen al representante como **[!UICONTROL Detalles del formulario]** en la bandeja de entrada del chat, de modo que el visitante no tiene que repetir nada.

El visitante puede finalizar el chat en cualquier momento y se le pide que confirme.

![Finalizar cuadro de diálogo de confirmación de chat pidiendo al visitante que confirme la finalización del chat con el especialista](../assets/sales-handoff-visitor-4.png){width="800" zoomable="yes"}

### Reunión reservada {#visitor-meeting-booking}

Si el visitante decide reservar una reunión, el conserje muestra un calendario con las ranuras que están genuinamente abiertas en el calendario del representante enrutado, en el huso horario del visitante.

![Reserva una tarjeta de reunión en la conversación que muestre un calendario mensual y una lista de los espacios de tiempo disponibles](../assets/sales-handoff-visitor-3.png){width="800" zoomable="yes"}

Una vez que el visitante confirma un espacio, recibe el correo electrónico de confirmación del representante, que opcionalmente incluye un vínculo [!DNL Microsoft Teams]. El contexto de conversación se dirige al representante con la invitación.

## Lo que necesita antes de empezar {#prerequisites}

* Acceso a [!DNL Adobe Marketo Qualifier], con sus representantes agregados como usuarios en [!DNL Adobe Admin Console].
* Al menos un representante que haya conectado un calendario. No se puede activar la integración de **[!UICONTROL Meeting Booking]** hasta que se haya activado una.
* Al menos un representante que haya establecido la disponibilidad del chat en vivo. La integración de **[!UICONTROL Live Chat]** no se puede activar hasta que una lo haga.
* Un conserje en Composer al que puedes añadir integraciones y habilidades.

>[!NOTE]
>
>Las reservaciones para reuniones y charlas en vivo no requieren [!DNL Adobe Marketo Engage]. Sin ella, los datos de los representantes, las reuniones y los chats permanecerán en [!DNL Adobe Marketo Qualifier]. Hay dos cosas que requieren [!DNL Marketo Engage]: reglas de enrutamiento personalizadas, que se basan en los atributos de cliente potencial y compañía de [!DNL Marketo], y los tipos de actividades de conserjería que se escriben en el registro de persona de [!DNL Marketo].

## Configurar el chat en vivo y la reserva de reuniones {#setup-path}

Trabaje en estos campos en orden.

1. [Configurar representantes en Adobe Marketo Qualifier](representative-setup.md): conecte un calendario, defina el correo electrónico de confirmación y establezca la disponibilidad del calendario y del chat en vivo.
1. [Enrutar conversaciones a los representantes](routing-rules.md): elija operación por turnos, un agente directo o reglas personalizadas creadas en atributos de [!DNL Marketo].
1. [Activar chat en vivo y reserva de reuniones](configure-in-composer.md) — conecta las dos integraciones y activa la habilidad **[!UICONTROL Entrega a ventas]**.
1. [Bandeja de entrada de chat](chat-inbox.md): lo que los representantes hacen una vez que llega una conversación, incluida la puntuación de la conversación.
1. [Datos de Brand Concierge en Marketo Engage](marketo-activities.md): los campos de posibles clientes y los tipos de actividades escritos en [!DNL Marketo], y cómo usarlos en campañas inteligentes.
1. [Supervise reuniones y charlas en vivo](monitor.md): la lista de reservas y el panel de rendimiento.

## Retención de datos {#retention}

Las conversaciones de chat en vivo se conservan durante 30 días.
