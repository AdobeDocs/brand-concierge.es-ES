---
title: Activar chat en directo y reserva de reunión
description: Conecte las integraciones de Live Chat y Meeting Booking en Composer y, a continuación, active la entrega a la habilidad de ventas para que su conserje sepa cuándo ofrecer un humano.
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
source-git-commit: 4751ce408fb2aa6d1affae4dd7a5d81ca43ffc8a
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 0%
---
# Activar Live Chat y reserva de reunión {#configure-in-composer}

Hay dos cosas que deben estar en su lugar en Composer. Las integraciones de **[!UICONTROL Meeting Booking]** y **[!UICONTROL Live Chat]** le dan al conserje la *capacidad* de comprobar la disponibilidad, iniciar una conversación y reservar un espacio. La habilidad **[!UICONTROL Entrega a ventas]** le indica *cuándo* usar esa habilidad.

>[!NOTE]
>
>Complete [Primero configure representantes en Adobe Marketo Qualifier](representative-setup.md). Las integraciones buscan calendarios conectados y disponibilidad de chat en vivo, y no se activarán sin ellos.

## Conectar la integración de Meeting Booking {#connect-meeting-booking}

1. En Compositor, abre tu conserje y selecciona **[!UICONTROL Integraciones]** > **[!UICONTROL Integraciones de exploración]**.

   **[!UICONTROL Las reservas para reuniones]** y **[!UICONTROL Live Chat]** aparecen en **[!UICONTROL Integraciones integradas]**.

   ![Examinar el panel de integraciones en Compositor que muestra las tarjetas de Live Chat y Meeting Booking en Integraciones integradas](../assets/sales-handoff-composer-1.png){width="800" zoomable="yes"}

1. Seleccione **[!UICONTROL reserva de reunión]** y, a continuación, seleccione **[!UICONTROL Configurar]**.

1. Introduzca un nombre y una descripción.

   Asigne un nombre a la integración para lo que hace en este conserje, como `Meeting booking - US region` o `Meeting booking - round robin`. Puede conectar más de uno, por lo que el nombre es cómo se diferencian más adelante.

1. Compruebe el estado de conexión del calendario.

   La integración comprueba que al menos un representante de su organización ha conectado un calendario.

   * Si ninguno tiene, un error le indica que conecte al menos un calendario antes de activar la reserva de reunión. Regresa a [!DNL Adobe Marketo Qualifier] y completa [Conecta tu calendario](representative-setup.md#connect).
   * Si al menos uno tiene, una confirmación muestra que los representantes están disponibles.

1. Seleccione un tipo de enrutamiento: **[!UICONTROL Round robin]**, **[!UICONTROL agente directo]** o **[!UICONTROL enrutamiento personalizado]**.

   Si selecciona **[!UICONTROL Agente directo]**, elija el representante que recibirá todas las reuniones reservadas a través de este conserje. Si selecciona **[!UICONTROL enrutamiento personalizado]**, se aplican las reglas de enrutamiento que creó en [!DNL Adobe Marketo Qualifier]. Para ver cómo se comporta cada uno, consulte [Enrutar conversaciones a los representantes](routing-rules.md).

1. Seleccione **[!UICONTROL Conectar]**.

## Conexión de la integración de Live Chat {#connect-live-chat}

1. En **[!UICONTROL Integraciones de exploración]**, seleccione **[!UICONTROL Chat en vivo]** y luego seleccione **[!UICONTROL Configurar]**.

1. Escriba un nombre y una descripción, por ejemplo `Live chat - round robin`.

1. Compruebe el estado de disponibilidad del chat en vivo.

   La integración comprueba que al menos un representante ha establecido la disponibilidad del chat en vivo.

   * Si ninguno tiene, un mensaje le indica que agregue representantes que hayan configurado su disponibilidad de chat en vivo. Regresa a [!DNL Adobe Marketo Qualifier] y completa [Establecer disponibilidad de chat en vivo](representative-setup.md#chat-availability).
   * Si al menos uno tiene, una confirmación muestra que los representantes están disponibles.

1. Seleccione un tipo de enrutamiento.

   El chat en vivo admite los mismos tres tipos de enrutamiento que la reserva de reuniones. Con **[!UICONTROL Round robin]**, todos los representantes elegibles reciben una notificación a la vez y el primero en aceptar toma el chat.

1. Seleccione **[!UICONTROL Conectar]**.

## Activar el traspaso a la aptitud de ventas {#activate-skill}

Las integraciones ya están conectadas, pero el conserje todavía necesita saber cuándo ofrecerlas. Ese es el trabajo de la habilidad.

1. En Compositor, seleccione **[!UICONTROL Aptitudes]** > **[!UICONTROL Aptitudes de exploración]** y, a continuación, seleccione **[!UICONTROL Transferencia a ventas]**.

   El panel de detalles muestra la descripción de la aptitud, su **[!UICONTROL uso cuando]** condiciones, las **[!UICONTROL integraciones]** recomendadas y las **[!UICONTROL instrucciones de aptitud]**.

   ![Examine el panel de aptitudes con la opción Entregar a la aptitud de ventas seleccionada, en el que se muestra Condiciones de uso, integraciones recomendadas e instrucciones de aptitudes](../assets/sales-handoff-composer-2.png){width="800" zoomable="yes"}

1. Seleccione **[!UICONTROL Modificar]**.

   ![Transferencia a la aptitud de ventas en modo de modificación con nombre de aptitud editable, descripción y uso cuando las condiciones](../assets/sales-handoff-composer-3.png){width="800" zoomable="yes"}

1. Revise el nombre y la descripción de la aptitud y edítelos si lo desea.

1. Revisar las condiciones de **[!UICONTROL Uso cuando]**.

   Estas son las intenciones que déclencheur un traspaso. La aptitud se enviará con un conjunto predeterminado:

   | Condición | Déclencheur en |
   | --- | --- |
   | Acceso de consultor | Reservar o programar una reunión, iniciar una conversación en directo o solicitar conectarse con un representante de la empresa |
   | Ventas y compras | Precios, presupuestos, descuentos, asistencia para compras o licencias empresariales |
   | Comparación competitiva | Comparación de las soluciones con alternativas, diferenciación o migración de la competencia desde una plataforma de la competencia |
   | Acceso de prueba y POC | Configuraciones de prueba, acceso al patio de recreo, pruebas de concepto o pilotos |
   | Cambios en contratos y licencias | Renovaciones de contratos, extensiones de plazos o actualizaciones de planes |
   | RFP o RFI de compras | Envíos, respuestas, cuestionarios a proveedores, formularios de compras o documentación de cumplimiento |
   | Demostraciones | Demostraciones o tutoriales de productos |

   Seleccione **[!UICONTROL Agregar condición]** para agregar una intención propia o eliminar cualquier condición que no se aplique a su negocio.

1. Añada las integraciones que ha conectado.

   Agregue **[!UICONTROL Chat en vivo]**, **[!UICONTROL Reserva de reunión]** o ambos, según lo que desee que ofrezca este conserje.

1. Revise las **[!UICONTROL instrucciones de aptitudes]**.

   Las instrucciones se generan a partir de las condiciones e integraciones seleccionadas, por lo que en la mayoría de los casos no es necesario realizar ninguna edición.

   Edítelos en un lenguaje sencillo cuando desee tener un control más preciso sobre qué intención lleva a qué opción. Por ejemplo, puede indicar al conserje que ofrezca chat en vivo para preguntas sobre precios, que ofrezca una reunión para solicitudes de demostración y que ofrezca ambas cosas para preguntas sobre compras.

1. Seleccione **[!UICONTROL Guardar]**.

## Prueba y publicación {#test-and-publish}

Abra la vista previa y pídale al conserje algo que coincida con una de las condiciones de **[!UICONTROL Usar cuando]**, como solicitar una demostración. El conserje debe ofrecerle conectarse con un especialista, mostrar la opción de chat, la opción de reunión, o ambos, y presentar disponibilidad real.

Cuando el comportamiento sea correcto, publique su conserje para que el traspaso esté activo en su sitio.

## Siguiente paso {#next}

Sus representantes ahora pueden recibir charlas. Ver [Bandeja de entrada de chat](chat-inbox.md).
