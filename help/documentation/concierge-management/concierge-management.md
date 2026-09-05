---
title: Administrar un conserje
description: Aprenda a crear una Brand Concierge a partir de un sitio web, a configurar sus integraciones, habilidades, instrucciones, tono y estilo visual, y a probarla antes de la implementación.
toc: true
source-git-commit: 3f05cb0dd8c11620b0ed7e254d0f4f9b24408b08
workflow-type: tm+mt
source-wordcount: '1761'
ht-degree: 1%

---


# Administrar un conserje

Un conserje se crea a partir de un sitio web de marca y se puede refinar con integraciones, habilidades, instrucciones, ajustes de tono y voz, estilos visuales y componentes de chat. Utilice la vista previa para probar los cambios antes de implementar deliberadamente el servicio de conserjería para los visitantes.

## Información general

| Elemento | Detalles |
|---|---|
| Usuario principal | Especialista en marketing que utiliza la configuración de autoservicio |
| Asistencia adicional | Las integraciones de Commerce y B2B pueden requerir códigos, claves o configuración de un equipo de TI, comercial o de ventas |
| Hora típica | Unos 5 minutos para crear un conserje de línea de base; se requiere tiempo en curso para el refinamiento y las pruebas |
| Implementación | Independiente de la creación; la creación de un conserje no lo hace visible para los visitantes del sitio web |

>[!NOTE]
>
>Una zona protegida puede contener varios conserjes. Cada conserje tiene su propia configuración, y los conserjes se pueden eliminar de la lista de conserjes.

## Crear un conserje

La creación de un conserje a partir de una sola URL de sitio web es el punto de partida recomendado para un usuario que accede por primera vez. El sistema crea una línea base de trabajo sin necesidad de configuración manual.

1. Escriba la URL del sitio web de la marca y seleccione **Crear**.

1. Revise la expresión de marca generada. El sistema analiza el tono del sitio web y propone atributos como la formalidad, la calidez, el juego y la energía. Ajuste los valores según sea necesario y seleccione **Continuar**.

1. Revise el perfil de marca generado. El perfil puede incluir el objetivo de la marca, productos y servicios, público objetivo, valores de marca, diferenciadores clave y casos de uso comunes. Edite el perfil según sea necesario y seleccione **Continuar**.

1. Revise las instrucciones de inicio, protecciones y sugerencias generadas. Por ejemplo, las protecciones pueden excluir temas legales, temas de cumplimiento o discusiones de competidores, mientras que las sugerencias pueden proporcionar ideas rápidas de seguimiento. Edite el contenido según sea necesario y seleccione **Guardar**.

1. Espere a que el sistema aplique la configuración de línea base. El sistema también crea un estilo visual predeterminado con colores y fuentes extraídas del sitio web y activa habilidades de línea de base e integraciones, como una habilidad general de pregunta y respuesta conectada al contenido del sitio web.

1. Pruebe el conserje en la vista previa. Las vistas para escritorio y móvil están disponibles. Seleccione **Nuevo** para reiniciar una conversación de prueba.

>[!IMPORTANT]
>
>La creación de un conserje no lo hace visible para los visitantes. La implementación es un paso independiente y deliberado. Puede revisar la configuración en cualquier momento antes de la implementación.

## Comprender lo que se configura automáticamente

Los siguientes elementos se configuran automáticamente al crear un conserje:

| Elemento | Configuración |
|---|---|
| Contenido de Knowledge Base | Creado a partir de las páginas principales del sitio mediante un rastree en segundo plano que se inicia automáticamente |
| Integración de búsqueda de Knowledge Base | Señala automáticamente al contenido rastreado |
| Aptitud de Site Advisory | Activo de forma predeterminada para que el conserje pueda responder preguntas generales inmediatamente |

## Comprender las habilidades e integraciones

Compositor, la interfaz utilizada para construir y configurar un conserje, utiliza dos conceptos relacionados:

- **Integración:** Conexión a un origen de datos, como contenido de un sitio web o un catálogo de productos activo. Una integración recupera información, pero no toma decisiones por sí misma.
- **Habilidad:** Comportamiento que determina qué hace el conserje, cuándo lo hace y qué integraciones puede utilizar.

Una integración puede servir para varias habilidades, y una habilidad puede utilizar varias integraciones. Por ejemplo, una sola conexión del catálogo de productos puede admitir varios casos de uso relacionados con el producto sin que se vuelva a crear para cada aptitud.

## Configuración de integraciones

Seleccione **Examinar integraciones** para ver el catálogo de integraciones disponible.

| Integración | Objetivo | Notas |
|---|---|---|
| Búsqueda en base de conocimientos | Busca contenido del sitio web | Se configura automáticamente cuando se crea el conserje |
| Búsqueda por IA de contenido | Busca contenido de AEM Sites | Relevante para los clientes de AEM Sites as a Cloud Service |
| Vinculación de entidades | Resuelve productos o menciones de la marca en un mensaje del visitante para entidades de catálogo específicas | Integración de soporte, que generalmente se utiliza junto con una integración de búsqueda en lugar de solo |
| MCP de Commerce | Se conecta a un catálogo de Adobe Commerce activo para buscar productos, detalles de productos y comparaciones | No está habilitado de forma predeterminada; requiere códigos o claves del equipo de comercio o TI |
| Convocatoria de reunión | Permite a los visitantes reservar una reunión con un representante de ventas | Requiere configuración con el calendario de un vendedor |
| Chat en vivo | Conecta a los visitantes con un representante de ventas en directo | Requiere configuración con disponibilidad de representante de ventas |

### Activar y configurar una integración

1. Abra el mosaico de integración y seleccione **Editar**.

1. Para **Búsqueda en la base de conocimiento**, seleccione el origen de conocimiento que desea buscar. Puede cambiar el nombre de la conexión, por ejemplo `Website content`.

1. Para **Commerce MCP**, introduzca los siguientes valores proporcionados por el equipo de Adobe Commerce o de TI y conéctese:
   - ID de entorno
   - Código del sitio web
   - Código de tienda
   - Código de vista de tienda
   - Clave de API

1. Seleccione **Guardar**. La integración se muestra como conectada y se puede previsualizar, editar o eliminar.

Puede agregar más de una instancia de la misma integración, como instancias que apunten a diferentes fuentes de conocimiento. Se puede configurar una aptitud para utilizar una instancia de integración específica.

## Configurar aptitudes

Las habilidades determinan lo que un conserje puede hacer por los visitantes. Seleccione **Examinar aptitudes** para ver el catálogo de aptitudes disponible.

| Habilidad | Objetivo | Integración o configuración requeridas |
|---|---|---|
| Site Advisory | Responde preguntas generales de marca, incluidas preguntas frecuentes, políticas, precios, instrucciones y temas de asistencia | Contenido del sitio web; activo de forma predeterminada |
| Asesoramiento de productos | Ayuda a los visitantes a descubrir e investigar productos a través de tarjetas de productos basadas en nombres y preguntas de productos en prosa | Búsqueda en la base de conocimiento, vinculación de entidades |
| Descubrimiento del catálogo Adobe Commerce | Busca, explora, filtra y recupera detalles sobre productos de un catálogo en vivo | Integración de Commerce MCP |
| Comparación de productos de Adobe Commerce | Proporciona una comparación en paralelo de productos con nombre | Integración de Commerce MCP |
| Encuentro de Libros con Ventas | Sugiere y facilita la reserva de una reunión | Integración de Meeting Booking |
| Chat en vivo con Ventas | Sugiere y facilita un traspaso de chat en vivo | Integración de Live Chat |

### Activar y configurar una aptitud

1. Abra el mosaico de aptitudes y seleccione **Modificar**.

1. Defina el nombre, la descripción y las intenciones de la aptitud. Las intenciones son frases o temas que deben poner en déclencheur la aptitud, como `pricing` o `compare products`. Puede añadir varias intenciones.

1. Si la aptitud requiere una integración, adjunte la integración requerida. Por ejemplo, una aptitud comercial requiere MCP de Commerce. También puede seleccionar **Usar recomendado** para que el Compositor seleccione automáticamente una integración apropiada.

1. Revise y edite las instrucciones de inicio de la aptitud según sea necesario.

1. Seleccione **Guardar** y pruebe el cambio en la vista previa activa.

>[!TIP]
>
>Si dos aptitudes pueden responder a la misma pregunta, el enrutamiento puede llegar a ser incoherente. Mantenga los déclencheur de aptitudes distintos y específicos en lugar de utilizar intenciones superpuestas.

## Añadir instrucciones de conserjería

Utilice el campo de instrucciones del conserje para mantener las respuestas alineadas con las directrices de marca. Las instrucciones pueden definir:

- Uso de marcas
- Estructura de respuesta
- Temas que se deben evitar

Escriba instrucciones directamente en el campo de texto. Al guardar las instrucciones, el conserje actualiza automáticamente su comportamiento. Pruebe el resultado inmediatamente en la vista previa en directo.

La misma área también incluye el siguiente contenido editable:

- **Protecciones:** Comportamientos o temas que el conserje debería evitar.
- **Sugerencias:** ideas de mensajes de seguimiento que se pueden mostrar después de una respuesta.

## Configuración del tono y la voz

Los ajustes de tono y voz controlan la longitud de respuesta y los atributos de tono, incluyendo:

- Formal o casual
- Caliente o neutro
- Juguetón o serio

Las selecciones se guardan automáticamente. Pruebe el resultado en la vista previa en directo después de realizar cambios.

## Configuración del estilo visual

La configuración de estilo visual controla el aspecto del conserje, lo que incluye, entre otras cosas:

- Colores
- Fuentes
- Texto del mensaje de bienvenida
- Texto de exención de responsabilidad legal
- Colores de tarjeta

Edite la configuración en la interfaz de usuario y utilice la vista previa en directo para revisar los cambios. Seleccione **Guardar** para que los cambios sean permanentes.

## Configuración de componentes de chat

Los componentes de chat controlan los elementos individuales que los visitantes ven en la ventana de chat. Seleccione un componente en la interfaz de usuario para abrir su configuración en un panel lateral.

| Componente | Qué controla |
|---|---|
| Burbuja de chat | El aspecto de los mensajes del visitante y de los mensajes del conserje |
| Iniciar píldoras de solicitud o petición de datos | Preguntas de apertura sugeridas, especialmente las que se muestran en dispositivos móviles |
| Sugerencias de seguimiento | Preguntas siguientes sugeridas después de una respuesta |
| Barra de entrada | El cuadro de mensaje que los visitantes utilizan para introducir una pregunta |
| Citas | Si las referencias de origen aparecen en una respuesta y cómo aparecen |
| Comentarios | El control de clasificación de pulgares hacia arriba o hacia abajo mostrado después de cada respuesta |
| Tarjeta de producto | Diseño y estilo de las tarjetas de producto, incluidos los colores y los botones |

## Configurar la reserva de reuniones y el chat en vivo

Meeting Booking y Live Chat permiten a los visitantes reservar reuniones con representantes de ventas o iniciar una conversación en directo con un representante. Estas funciones están impulsadas por un producto complementario llamado Sales Qualifier.

### Funciones y responsabilidades

- **Especialista en marketing:** configura la aptitud y la integración en Brand Concierge.
- **Representante de ventas:** Conecta su propio calendario y configura la disponibilidad.

### Configurar la reserva de reunión o el chat en vivo

1. En **Integraciones de exploración**, abra **Reserva de reuniones** o **Chat en vivo**. De forma predeterminada, todos los miembros de la organización están disponibles como miembros potenciales del equipo; no se requiere ningún paso por separado para agregar miembros del equipo en esta fase.

1. Haga que cada representante de ventas inicie sesión en `experienceplatform.adobe.com`, abra **Sales Qualifier** y vaya a **Configuración del perfil**.

1. Pida a cada representante que conecte un calendario, como Outlook. Microsoft Teams se puede incluir de forma opcional. El representante también puede establecer el asunto de la invitación a la reunión y el texto del correo electrónico.

1. Configure la disponibilidad. La disponibilidad se extrae del calendario de forma predeterminada y se puede limitar aún más mediante:
   - Duración de la reunión
   - Tiempo de almacenamiento en búfer entre reuniones
   - Aviso mínimo requerido
   - Ventanas horarias disponibles específicas

1. Configure la disponibilidad de Live Chat de forma independiente mediante un proceso similar.

1. En Brand Concierge, abra **Miembros administrados** y confirme que los representantes se muestran como disponibles.

1. Active la integración de **Meeting Booking** o **Live Chat**.

1. Vaya a **Examinar aptitudes** y seleccione **Reservar reunión con ventas** y/o **Chat en vivo con ventas**. Defina los déclencheur, adjunte la integración correspondiente y guarde la aptitud.

1. Seleccione **Simular** para probar la experiencia de extremo a extremo. Introduzca una pregunta de ejemplo y confirme que se dirige al flujo de aptitud y participación correcto.

### Comportamiento después de la implementación

Cuando las funcionalidades están activas:

- Los chats entrantes en directo aparecen a los representantes disponibles en tiempo real.
- Las reuniones reservadas aparecen en una vista de reuniones.
- Hay disponible en Analytics un informe de rendimiento de la reunión.
- Las reuniones y los encuentros de chat se envían a Marketo como actividades, junto con los datos de actividades existentes.

## Compartir un vínculo de vista previa

Un vínculo de vista previa que se puede compartir permite que las partes interesadas revisen e interactúen con un conserje sin acceso de Compositor y sin implementar el conserje en un sitio web activo.

1. Desde la pantalla de vista previa del conserje, genere un vínculo de vista previa que se pueda compartir.

1. Comparta el vínculo con los revisores.

1. Los revisores pueden interactuar con el conserje a través del vínculo sin iniciar sesión en Composer.

## Prueba antes de la implementación

Utilice la experiencia de previsualización o simulación después de cada cambio de configuración significativo. Como mínimo, compruebe lo siguiente:

- El conserje responde a preguntas generales del contenido del sitio web previsto.
- Cada aptitud responde únicamente a los déclencheur perseguidos.
- Las integraciones necesarias están conectadas y apuntan a la fuente de datos correcta.
- Las búsquedas y comparaciones de productos utilizan la instancia de MCP o Catálogo de productos de Commerce deseada.
- Ruta de Meeting Booking y Live Chat a los representantes previstos.
- El tono, la voz, las instrucciones, las barreras y las sugerencias producen las respuestas esperadas.
- Los estilos visuales y los componentes de chat se muestran correctamente en las vistas de escritorio y móvil.
- Las partes interesadas pueden revisar la experiencia a través del vínculo de vista previa compartible, si se utiliza alguno.
