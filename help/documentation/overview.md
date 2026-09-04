---
title: Documentación del producto
description: Aprenda a configurar y utilizar las funciones clave de Brand Concierge.
role: User,Admin
level: Beginner
TQID: https://experienceleague.adobe.com/Ob3NAKyD929Ije-Y7UPO1hMfDYDi-UJ0gINpGlxiYGM
product_v2: id: b6ee73fe-bdc6-47d9-99a2-80194514dd40
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: b5520579-b31f-4df7-9281-f0d9f91e2edcid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: df401a2a-327d-468c-a5e4-b7b7ccd071a0id: e1e0219c-f879-479f-8427-888ed2a6e9c2id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 60835c7971d86341194d773f9cf487c4cb6f171a
workflow-type: tm+mt
source-wordcount: 2047
ht-degree: 1%

---

# Ayuda de Brand Concierge

Aprenda a configurar y utilizar las funciones clave de Brand Concierge. Encuentre respuestas a preguntas comunes sobre configuración, integración de datos, privacidad, personalización, medición de rendimiento y requisitos técnicos.

## Funciones principales {#key-features}

Brand Concierge tiene varias funciones clave, entre ellas:

* **Incorporación guiada:** Siga una configuración paso a paso para obtener conocimientos, habilidades y expresión de marca.
* **Integración de conocimientos:** Cargue y administre orígenes como archivos CSV con vínculos a sitios web.
* **Configurar aptitudes** Integrar aptitudes como el asesoramiento de productos.
* **Controlar la marca:** Ajustar la voz, el tono y la duración de la respuesta para cumplir con el estándar y el enfoque de tu marca en particular.
* **Vista previa e iteración:** Utilice una interfaz de vista previa completa para simular conversaciones y realizar ajustes en directo.
* **Sistema de comentarios:** Usa un sistema de comentarios que permita a los usuarios proporcionar calificaciones de pulgares hacia arriba o hacia abajo, junto con formularios de comentarios detallados que cubran la cobertura de respuesta, el tono, la calidad y las características.
* **Panel de Analytics:** Aproveche un panel de análisis con tecnología Customer Journey Analytics para métricas como conversaciones, opinión y participación.

## Introducción {#getting-started}

Puede acceder a Brand Concierge desde el panel de Adobe Experience Cloud. En un nivel superior, se realizan las siguientes tareas:

1. [Crear un conserje](#homepage) a partir de la dirección URL de un sitio web. Se genera automáticamente una fuente de conocimiento inicial, una expresión de marca y una aptitud de línea de base.
1. [Revise y perfeccione las fuentes de conocimientos](#knowledge-sources) según sea necesario.
1. [Configurar aptitudes adicionales](#skills-configuration) más allá de la aptitud de línea de base.
1. [Ajuste la expresión de marca](#brand-expression) si los valores predeterminados generados necesitan cambios.

Para ver un tutorial en vídeo, consulta [Crear tu primer conserje](../getting-started/create-first-concierge.md)

Las secciones siguientes describen en detalle cada tarea y las opciones de la interfaz.

## Crear un conserje {#homepage}

La creación de un conserje a partir de una sola URL de sitio web es el punto de partida recomendado para un usuario que accede por primera vez. La página principal de Brand Concierge lee el sitio y crea una línea de base de trabajo automáticamente: no se requiere configuración manual para comenzar.

A medida que se completa la instalación, un resumen de la configuración proporciona una vista completa de sus detalles, organizados con pestañas para facilitar los ajustes y refinamientos continuos. La página de inicio también incluye una sección inspiradora con vídeos y demostraciones de funciones de conserjería, como recomendaciones de productos, y un acceso rápido a la documentación de Experience League para obtener perspectivas técnicas más detalladas.

**Elementos clave**

* **Creación con un solo clic**: escribe la dirección URL de un sitio web para generar automáticamente una expresión de marca inicial, un perfil de marca, instrucciones, protecciones, una fuente de conocimiento y una aptitud básica.
* **Revisión guiada**: Cada elemento generado se presenta para su revisión antes de guardarse, por lo que no se activará nada sin tener la oportunidad de ajustarlo primero.
* **Sección inspiradora**: vídeos y demostraciones que muestran las funciones de conserjería (por ejemplo, recomendaciones de productos).
* **Vínculos de documentación**: Acceso rápido a los recursos de Experience League para obtener información técnica más detallada.
* **Resumen de configuración**: vista posterior a la instalación de todos los detalles, con fichas para refinar.

**Para crear un conserje**

1. Escriba la URL del sitio web de la marca y seleccione **[!UICONTROL Crear]**.
1. Revise la expresión de marca generada (como la formalidad, la calidez, el juego y la energía) y ajústela según sea necesario.
1. Revise el perfil de marca generado, incluidos los objetivos, productos y servicios, la audiencia de destino y los diferenciadores, y ajústelo según sea necesario.
1. Revise las instrucciones, protecciones y sugerencias generadas y ajústelas según sea necesario.
1. Seleccione **[!UICONTROL Guardar]**. El conserje está listo para probar en la vista previa.

Para obtener información detallada sobre este flujo, incluido lo que se configura automáticamente, consulte [Administrar un conserje](./concierge-management/concierge-management.md).

>[!TIP]
>
>Brand Concierge guarda automáticamente su progreso. Una configuración incompleta puede limitar la funcionalidad, pero no bloqueará ningún intento de previsualización.

### Fuentes de conocimiento {#knowledge-sources}

[!UICONTROL Fuentes de conocimientos] le ayudan a administrar las fuentes de datos que alimentan las respuestas de su conserje. Se crea automáticamente una fuente de conocimientos inicial cuando crea un conserje a partir de una dirección URL de un sitio web; utilice esta área para revisarla o agregar más. [!UICONTROL Fuentes de conocimiento] tiene varios elementos clave que considerar, como:

* **Lista de Source:** Muestra todos los elementos cargados, como archivos CSV con vínculos a sitios web, e indica su estado como procesados o pendientes.
* **Interfaz de carga:** Permite arrastrar y soltar o examinar archivos CSV que contienen direcciones URL, que el sistema rastreará para extraer información.
* **Opciones de conexión:** Le permiten vincular orígenes de conocimientos específicos a aptitudes relevantes para un uso más específico.

**Para agregar un origen de conocimientos**

1. En la página principal, haga clic en **[!UICONTROL Fuentes de conocimientos]**.

1. Asigne un nombre a la fuente de conocimiento.

1. Haga clic en **[!UICONTROL Agregar]** para cargar un archivo CSV.

   Asegúrese de que incluye una columna para las direcciones URL del sitio web.

1. Espere unos minutos para que se procese.

   Este paso se resuelve con bastante rapidez como actualizaciones de estado en tiempo real.

1. Una vez añadido, vuelva a la página principal.

   En este punto, debería ver la nueva fuente añadida a la página principal.

   Utilice la página principal para editar o eliminar las fuentes de conocimientos según sea necesario. También puede volver a conectar una fuente de conocimiento si se producen cambios.

Para ver el conjunto completo de tipos de fuentes de conocimientos y los pasos para solucionar problemas, consulte [Crear y administrar fuentes de conocimientos para Brand Concierge](./knowledge-sources/knowledge-sources.md).

### Configurar aptitudes {#skills-configuration}

Las habilidades determinan lo que un conserje puede hacer por los visitantes, como **Asesoramiento de productos** para recomendaciones de productos o **Asesoramiento de sitios** para preguntas generales de marca. Seleccione **[!UICONTROL Examinar aptitudes]** para ver el catálogo de aptitudes disponible y activar las aptitudes que necesita el conserje.

* **Catálogo de habilidades:** Elija entre las habilidades disponibles, como Asesoramiento del sitio, Asesoramiento de productos y habilidades que respaldan la reserva de reuniones o el chat en vivo con un representante de ventas.
* **Configuración:** Para cada aptitud, establezca su nombre, descripción y las intenciones (frases o temas de déclencheur) que deben invocarla.
* **Integraciones:** Adjunta la integración que una habilidad necesita para hacer su trabajo, o selecciona **[!UICONTROL Usar recomendado]** para que el Compositor seleccione una automáticamente.
* **Vista previa:** La prueba cambia inmediatamente en la vista previa activa.

**Para configurar habilidades**

1. En el conserje, selecciona **[!UICONTROL Examinar aptitudes]**.
1. Seleccione una aptitud para activarla (por ejemplo, Asesoramiento de productos).
1. Defina el nombre, la descripción y las intenciones de la aptitud.
1. Adjunte la integración requerida o seleccione **[!UICONTROL Usar recomendado]**.
1. Seleccione **[!UICONTROL Guardar]** y pruebe el cambio en la vista previa activa.

Para ver el catálogo completo de aptitudes e integración, consulte [Marco de aptitudes e integraciones](./skills-and-integrations.md).

### Expresión de marca {#brand-expression}

La expresión de marca controla la personalidad y el estilo de las respuestas de su conserje. Se redacta automáticamente cuando crea un conserje, y puede acceder a él posteriormente desde la configuración de tono y voz del conserje para los cambios en curso.

La expresión de marca se establece utilizando atributos como formalidad, calidez, alegría y energía, en lugar de un solo estilo con nombre. También puede configurar la longitud de respuesta (corta, media o larga) para que coincida con las preferencias de su marca.

**Para personalizar la expresión de marca**

1. En el conserje, abra **[!UICONTROL Tone &amp; Voice]**.
2. Ajuste la formalidad, la calidez, el juego, la energía y la longitud de respuesta preferida.
3. Seleccione **[!UICONTROL Guardar]** para asegurarse de que los cambios se reflejen en las respuestas futuras.

### Vista previa y prueba {#preview-and-test}

Pruebe el conserje antes de iniciar a los clientes con los modos Vista previa y Vista del comprobador.

>[!BEGINTABS]

>[!TAB Modo de vista previa]

Utilice el modo de vista previa para simular conversaciones mientras realiza ajustes en tiempo real.

1. Después de la configuración, regresa a la página principal y haz clic en **[!UICONTROL Vista previa]**.
1. Use la interfaz de chat para escribir su consulta (por ejemplo, _Recomiende un portátil por debajo de $1000_).
1. Revise las respuestas de los conserjes.
1. Utilice el panel derecho para ajustar la configuración de expresión de marca.
1. Haz clic en **[!UICONTROL Compartir]** para generar el vínculo de los comentarios del equipo.

>[!TAB Vista del comprobador]

Utilice la vista Probador para recopilar comentarios estructurados sobre el rendimiento del conserje y simular la experiencia del usuario final.

1. En la vista previa, haga clic en **[!UICONTROL Vista de comprobador]**.
1. Utilice la vista Probador para simular las conversaciones con el usuario final.
1. Utilice el mecanismo de pulgares hacia arriba y hacia abajo para clasificar cada respuesta que reciba.
1. Complete el formulario de comentarios para los pulgares hacia abajo:
   **Cobertura de la respuesta:** ¿Se refirió a la intención?
   **Tono de marca:** ¿Alineado con la personalidad?
   **Calidad de respuesta:** ¿Despejado y estructurado?
   **Características de respuesta:** ¿Seguimiento útil?
1. Añádanse comentarios y observaciones específicas.
1. Envíe comentarios para revisar el panel.

>[!ENDTABS]

### Comentarios {#feedback}

Después de realizar la prueba, puede utilizar la pestaña de comentarios de la página principal para proporcionar comentarios y revisiones detalladas.

La sección de comentarios proporciona varias funciones importantes para ayudarle a monitorizar y evaluar el rendimiento de Brand Concierge. Los siguientes elementos están disponibles:

* **Instantánea de rendimiento:** muestra tarjetas que resumen métricas clave, incluidas las conversaciones totales, los usuarios únicos, las tendencias de opinión y la tasa de participación.
* **Botón Ver informe:** Permite abrir un tablero con tecnología de Customer Journey Analytics para obtener acceso detallado a métricas avanzadas de análisis y rendimiento.
* **Lista de comentarios:** presenta una tabla de sesiones de comentarios. Puede hacer clic en filas individuales para ver la transcripción completa del chat de cada sesión.
* **Panel de comentarios:** Muestra las tarjetas de clasificación en el lado derecho de la interfaz. Al pasar el ratón por encima o hacer clic en estas tarjetas, se resaltarán las partes relevantes de la transcripción del chat para facilitar la referencia.

**Para enviar comentarios**

1. Vaya a la página principal de Brand Concierge y seleccione **[!UICONTROL Comentarios]**.
1. Utilice la instantánea proporcionada para ver información sobre tendencias de alto nivel.
1. Para acceder a una inmersión profunda con tecnología Customer Journey Analytics, selecciona **[!UICONTROL Ver informe]**.
1. También puede inspeccionar el panel para ver si hay comentarios conectados adicionales.
1. Cuando termine, puede exportar las perspectivas para utilizarlas más adelante y restringir el flujo de trabajo.

### Configuraciones {#configurations}

La ficha _[!UICONTROL Configuraciones]_ es una vista resumida de solo lectura que puede usar para revisar la configuración completa del conserje. Esto refleja directamente la página principal después de completar la configuración inicial y proporciona resúmenes de sus detalles, fuentes de conocimientos, habilidades y expresiones de marca configuradas. Puede utilizar esta función como referencia antes de obtener una vista previa o compartir su conserje.

## Qué puede hacer con Brand Concierge

Obtenga información acerca de las funciones del cliente, las funcionalidades empresariales y los casos de uso de Brand Concierge.

### Funciones del cliente

Brand Concierge ofrece una interfaz conversacional que permite a los clientes encontrar productos, comparar opciones y obtener respuestas mediante lenguaje natural. Con recomendaciones personalizadas, comparaciones de productos enriquecidas y la capacidad de convertirse en un agente activo, los clientes disfrutan de una experiencia intuitiva y sin problemas. La interacción es flexible: los clientes pueden utilizar texto, voz o imágenes, y cada respuesta se basa en la documentación de confianza de la marca y el contexto del cliente.

* Haga preguntas en lenguaje natural y obtenga recomendaciones personalizadas.
* Comparar productos en paralelo con visualizaciones visuales.
* Obtenga respuestas a partir de la documentación de su marca.
* Cambie a un agente en directo con un historial de conversaciones completo.

### Funcionalidades empresariales

Brand Concierge ofrece a las empresas capacidades avanzadas de IA conversacional para la participación de los clientes. Ayuda a las marcas a impulsar la conversión guiando a los clientes hacia los productos adecuados, reduce los costes de asistencia a través de respuestas instantáneas y precisas y garantiza la coherencia de la voz y el cumplimiento de la marca. Con análisis sólidos, transferencia de IA a persona sin problemas e integraciones profundas de Adobe, Brand Concierge optimiza tanto la experiencia del cliente como el rendimiento empresarial.

* Guíe a los clientes a los productos adecuados para aumentar la conversión.
* Reduzca los costes de asistencia con respuestas instantáneas y precisas.
* Controle los requisitos de voz, tono y conformidad de la marca.
* Realice un seguimiento del rendimiento con el tablero de Customer Journey Analytics.
* Habilite el traspaso de IA a persona sin problemas, incluida la programación de reuniones.
* Integración con Adobe Experience Platform y Experience Manager.

## Casos de uso

Brand Concierge admite casos de uso B2C y B2B en varios sectores.

| Industria | Casos de uso |
|---|---|
| Venta minorista y comercio electrónico | Los clientes pueden descubrir productos y recibir recomendaciones personalizadas. Brand Concierge proporciona orientación sobre el tamaño y el ajuste, ayuda a los usuarios a encontrar regalos adecuados y hace coincidir estilos o preferencias en función de los datos introducidos por el cliente. |
| Ventas B2B | Brand Concierge guía a los clientes a través de las evaluaciones de productos, ofrece comparaciones detalladas de funciones y precios, ayuda a programar reuniones de ventas y proporciona recomendaciones específicas del sector adaptadas a los clientes empresariales. |
| Atención al cliente | Los usuarios pueden recibir respuestas instantáneas obtenidas directamente de la base de conocimientos. Brand Concierge proporciona información sobre directivas y procedimientos, ayuda a solucionar problemas y proporciona actualizaciones sobre el estado y el seguimiento de los pedidos. |
| Viajes y hospitalidad | Los clientes reciben recomendaciones de destinos personalizadas, asistencia con la planificación de itinerarios, soporte durante todo el proceso de reserva y respuestas a preguntas sobre políticas de viajes. |
| Servicios financieros | Brand Concierge ofrece comparaciones de productos para ayudar a los clientes a elegir las soluciones financieras adecuadas, proporciona información de la cuenta, ofrece orientación según el cumplimiento y permite programar reuniones con asesores financieros. |

## Divulgación de inteligencia artificial conversacional {#disclosure}

Para proporcionar una experiencia transparente y fiable, los usuarios de Brand Concierge de Adobe son responsables de añadir una breve divulgación dentro de su experiencia de conversación. Esta divulgación ayuda a los usuarios finales a comprender cómo funciona la conversación y cómo se puede utilizar su información.

**Qué debe cubrir la divulgación**

La información que proporcione durante la conversación debe comunicar claramente tres cosas a los usuarios finales.

1. _La conversación usa IA generativa_

   Informe a los usuarios de que la IA genera las respuestas para que entiendan que están interactuando con un sistema automatizado.

1. _Se pueden revisar las conversaciones para mejorar la experiencia_

   Los usuarios deben ser informados de que usted (el cliente) y sus proveedores de servicios pueden acceder a las conversaciones para ayudar a personalizar las respuestas y mejorar la calidad y el rendimiento de la conversación.

1. _Usar la inteligencia artificial aplicada a la conversación significa aceptar este uso_

Deje en claro que, al seguir utilizando la inteligencia artificial aplicada a la conversación, los usuarios aceptan este procesamiento de los datos de sus conversaciones.

**Ejemplo (solo con fines de referencia)**

`"This conversational AI uses generative AI to help respond to you. Conversations may be recorded by [customer] and/or our service provider and used to help operate and improve services, make your interactions with us better, and provide a more personalized experience. By continuing to conversational AI you agree to this processing of data."`

Puede adaptar la redacción para que se ajuste a la voz de su marca y a la experiencia del usuario, siempre que los puntos clave anteriores se comuniquen claramente.

**Por qué es importante**

Ser franco sobre cómo funciona la IA conversacional ayuda a establecer las expectativas correctas para los usuarios y genera confianza en las experiencias con tecnología de IA.
