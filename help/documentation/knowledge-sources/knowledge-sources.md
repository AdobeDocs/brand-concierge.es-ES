---
title: Creación y administración de fuentes de conocimiento para Brand Concierge
description: Obtenga información sobre cómo crear AEM Sites, vínculos a sitios web y fuentes de conocimiento de catálogos de productos para Brand Concierge, monitorizar el estado de procesamiento y resolver problemas de rastrea.
hide: true
source-git-commit: 60835c7971d86341194d773f9cf487c4cb6f171a
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 1%

---


# Creación y administración de fuentes de conocimiento para Brand Concierge

Una fuente de conocimientos es el contenido que un conserje puede utilizar para responder a las preguntas de los visitantes. Todos los conserjes necesitan al menos una fuente de conocimientos configurada. Las fuentes de conocimiento se crean de forma independiente y se pueden reutilizar en varios conserjes.

Un conserje responde a las preguntas utilizando únicamente sus fuentes de conocimiento configuradas. No responde desde el conocimiento general del mundo.

>[!NOTE]
>
>Si un visitante pregunta por información fuera de las fuentes de conocimiento configuradas, el conserje está diseñado para indicar que no tiene la información en lugar de generar una respuesta no admitida. Utilice el proceso de evaluación para verificar este comportamiento.

## Elegir una fuente de conocimiento

Brand Concierge admite los siguientes tipos de fuentes de conocimientos:

| Fuente de conocimiento | Úselo cuando | Capacidad principal |
| --- | --- | --- |
| AEM Sites (índice de IA de contenido) | El cliente utiliza AEM Sites as a Cloud Service con la inteligencia artificial aplicada al contenido habilitada. | Utiliza un índice de inteligencia artificial aplicada al contenido existente y hace que el contenido actualizado de AEM Sites esté disponible sin un paso separado de rastrea o actualización. |
| Vínculos al sitio web | El cliente debe rastrear un sitio web, independientemente de la plataforma utilizada para crearlo. | Rastrea un mapa del sitio, direcciones URL individuales seleccionadas o direcciones URL proporcionadas en un archivo CSV. |
| Catálogo de productos | El cliente tiene un catálogo de productos o servicios relativamente pequeño y no utiliza Adobe Commerce. | Habilita vínculos profundos de productos y tarjetas de producto en las respuestas del conserje. |

>[!IMPORTANT]
>
>Los clientes que vendan a través de Adobe Commerce con un catálogo grande deben utilizar la integración MCP de Commerce. Los detalles sobre esa integración están fuera del ámbito de este artículo.

## Creación de una fuente de conocimientos de AEM Sites

Utilice una fuente de conocimiento de AEM Sites cuando el cliente ya utilice AEM Sites as a Cloud Service con la inteligencia artificial aplicada al contenido habilitada.

1. Seleccione **Generar conocimiento en Source**.
1. Elija **AEM Sites** y seleccione **Continuar**.
1. Introduzca un nombre y una descripción para la fuente de conocimientos. Por ejemplo, use `My main website` como nombre.
1. Seleccione un índice de inteligencia artificial aplicada al contenido existente de la lista. La lista se rellena desde la instancia de AEM Sites as a Cloud Service.
1. Seleccione **Guardar**.

Esta integración nativa hace que el contenido de AEM Sites actualizado esté disponible para Brand Concierge automáticamente. No es necesario rastrear ni actualizar por separado.

## Crear una fuente de conocimientos de vínculos a sitios web

Utilice una fuente de conocimiento de vínculos a sitios web para un sitio web rastreable. Esta opción funciona para sitios web creados en cualquier plataforma y es la opción recomendada para la mayoría de los usuarios nuevos.

1. Seleccione **Generar conocimiento en Source**.
1. Elija **Vínculos al sitio web** y seleccione **Continuar**.
1. Introduzca un nombre para la fuente de conocimientos.
1. Añada las fuentes de contenido mediante uno de los métodos siguientes:

   - **URL de mapa del sitio:** Agregue una URL que enumere las páginas del sitio. Se rastrearán todas las páginas enumeradas en el mapa del sitio.
   - **Direcciones URL individuales:** Agregar direcciones URL de página específicas de una en una. Solo se rastrean las páginas agregadas.
   - **Carga de CSV:** Descargue el archivo de muestra, agregue las direcciones URL y cargue el archivo CSV completado.

1. (Opcional) Programe una frecuencia de actualización, como semanal en un día y hora especificados, para mantener la fuente de conocimiento actualizada a medida que cambie el sitio web.
1. Seleccione **Agregar** o **Crear**.

El sistema rastrea las direcciones URL especificadas y crea una secuencia de comandos del contenido para crear la fuente de conocimiento.

>[!TIP]
>
>Un mapa del sitio suele estar disponible en `yourwebsite.com/sitemap.xml`. Si el sitio web no proporciona un mapa del sitio, agregue direcciones URL de página individuales en su lugar.

## Crear una fuente de conocimiento del catálogo de productos

Utilice una fuente de conocimiento de catálogo de productos para clientes con un conjunto más pequeño de productos o servicios, aproximadamente menos de 100, que no utilicen Adobe Commerce.

Cuando una respuesta de conserjería hace referencia a un producto, el catálogo de productos puede proporcionar un vínculo profundo a la página del producto y habilitar una tarjeta de producto. Una tarjeta de producto puede incluir una imagen, un título, una descripción y uno o dos botones.

1. Seleccione **Generar conocimiento en Source**.
1. Elija **Catálogo de productos** y seleccione **Continuar**.
1. Introduzca un nombre para la fuente de conocimientos. Por ejemplo, use `My product catalog - US region` como nombre.
1. Seleccione un esquema. El esquema define qué campos de producto (como imagen, título, descripción y botones) se muestran y dónde se vinculan los botones.
1. Descargue la hoja de cálculo de muestra para el esquema seleccionado.
1. Añada los datos del producto a la hoja de cálculo y cárguelos.
1. Seleccione **Guardar**.

Las distintas configuraciones de botón requieren esquemas diferentes.

## Monitorizar estado de fuente de conocimiento

Cada fuente de conocimiento muestra un estado de procesamiento.

| Estado | Significado |
| --- | --- |
| En progreso | La fuente de conocimientos se está procesando actualmente. |
| Correcto | La fuente de conocimiento está completamente procesada y lista para usarse. |
| Programado | La fuente de conocimiento se procesará en un momento programado futuro. |
| Éxito parcial | Algunas páginas se procesaron correctamente y otras no. |

La página de detalles de la fuente de conocimiento proporciona información como:

- El creador.
- La fecha de creación.
- Número de vínculos o páginas proporcionados.
- Número de vínculos o páginas que se han realizado correctamente o que han fallado.
- Hora de la última actualización.
- Las direcciones URL consideradas para el procesamiento.

## Solucionar errores de procesamiento

Si una fuente de conocimiento muestra un estado de éxito parcial, utilice el informe de problemas para identificar las direcciones URL que no se han podido procesar.

1. Abra la página de detalles de la fuente de conocimientos.
1. Seleccione **Solucionar problemas** para descargar un archivo que contenga direcciones URL rotas o que no se hayan podido eliminar, junto con los detalles del error.
1. Corrija las direcciones URL no válidas o elimínelas de la lista de origen.
1. Cargue de nuevo la lista de direcciones URL corregidas, si corresponde.
1. Solicite el reprocesamiento para añadir el contenido corregido a la fuente de conocimientos.
