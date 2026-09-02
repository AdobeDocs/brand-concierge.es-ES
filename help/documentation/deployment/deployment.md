---
title: Implementar un conserje
description: Obtenga información sobre cómo implementar un Brand Concierge configurando una secuencia de datos, instalando el script de implementación, definiendo reglas de superficie y comprobando la implementación.
hide: true
source-git-commit: fc22eb8e724437483e5d87283f46fb629a4e507c
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 0%

---


# Implementar un conserje

La implementación hace que un conserje esté disponible para los visitantes reales del sitio web. El especialista en marketing configura las opciones de implementación, mientras que el equipo de TI o de análisis proporciona el ID del conjunto de datos y el equipo del sitio web instala el script de implementación en el sitio web.

La implementación suele ser una configuración breve y única para cada sitio. Planifique durante aproximadamente 15 minutos de parte del experto en marketing, además del tiempo necesario para que el equipo del sitio web instale la secuencia de comandos.

>[!IMPORTANT]
>
>Haga participar al equipo de TI o de análisis y al equipo del sitio web desde el principio. Su participación es necesaria para proporcionar el ID de la secuencia de datos e instalar la secuencia de comandos, por lo que la implementación no debe tratarse como el último paso de la implementación.

## Antes de empezar

- Coordínese con el equipo de TI o de análisis para obtener un ID de conjunto de datos.
- Identifique al equipo responsable del sitio web o del administrador de etiquetas. Este artículo se refiere a este grupo como el equipo del sitio web.
- Decida si el conserje debe aparecer como un componente en las páginas existentes o como una página completa y dedicada.
- Identifique los dominios y las rutas de páginas donde debería aparecer el conserje.

## Configuración de la secuencia de datos

Un conjunto de datos es el destino de los datos de actividad generados por las interacciones del visitante con el conserje. Algunos ejemplos de estas interacciones son los clics, los envíos de formularios, las reuniones reservadas y los chats en directo. La secuencia de datos permite ver esta actividad en Analytics más adelante.

No es necesario crear una secuencia de datos como parte de este procedimiento. Solo necesita su ID.

### Obtener el ID de secuencia de datos

Solicite el ID de la secuencia de datos al equipo de TI o de análisis. El identificador se encuentra en Adobe Experience Platform en **Recopilación de datos** > **Flujos de datos**.

### Añadir la configuración de secuencia de datos

1. Tenga preparado el ID de la secuencia de datos.
1. En la sección Implementación de Brand Concierge, seleccione **Agregar configuración**.
1. Pegue el ID de la secuencia de datos.
1. Guarde la configuración.
1. Una vez guardada la configuración, seleccione la opción de instalación adecuada:
   - **Instalación del componente:** Utilice un fragmento de código que el equipo del sitio web coloque en una ubicación específica del sitio web.
   - **Instalación de página completa:** Use una página completa y lista para hospedar para una página de aterrizaje de conserjería dedicada.
1. Proporcione el script o la página seleccionados al equipo del sitio web.
1. Pida al equipo del sitio web que instale la secuencia de comandos directamente en el código de página o a través de un administrador de etiquetas.

>[!NOTE]
>
>La instalación la suele gestionar el equipo del sitio web, de forma similar a añadir una etiqueta de análisis o de herramienta de chat.

## Configuración de la superficie

Una vez instalada la secuencia de comandos, la configuración de superficie controla las páginas en las que aparece el conserje. Por ejemplo, puede configurar el servicio de conserjería para que aparezca en páginas de productos pero no en una página de ofertas de empleo.

### Agregar un dominio y reglas de página

1. Agregue un dominio como `blog.example.com`.
1. Elija cómo deben coincidir las rutas del dominio. Los patrones de coincidencia disponibles incluyen:
   - Cualquier página del dominio.
   - Rutas que comienzan con un valor especificado.
   - Rutas que terminan con un valor especificado.
   - Una coincidencia de ruta exacta.
1. Combine varias reglas para definir una cobertura de página más precisa.
1. Guarde la configuración de superficie.

## Verificar la implementación

Una vez que el equipo del sitio web instala la secuencia de comandos y se guardan las reglas de superficie, compruebe lo siguiente:

- El script está presente en las páginas del sitio web objetivo.
- El conserje solo aparece en las páginas cubiertas por las reglas configuradas.
- El conserje no aparece en páginas excluidas.
- Las interacciones de visitante generan datos de actividad para el conjunto de datos configurado.

>[!TIP]
>
>Pruebe una página incluida y una página excluida. Esto confirma que las reglas de superficie están funcionando como se pretende antes de que el conserje esté disponible en general.

## Preguntas abiertas y notas de ámbito

El material de origen no define los siguientes detalles:

- La lista completa y canónica de tipos de evento enviados al conjunto de datos. Los ejemplos proporcionados incluyen clics, envíos de formularios, reuniones reservadas y charlas en directo, pero la lista completa debe confirmarse con ingeniería.
- Si la configuración del flujo de datos difiere entre los clientes de prueba y los de pago.
- En qué producto de análisis específico se ve la actividad del flujo de datos; el material de origen se refiere a esto únicamente como &quot;Analytics&quot;.

Estas preguntas pueden superponerse a los requisitos de telemetría independientes y deben resolverse con el equipo de ingeniería o de producto adecuado antes de publicar las directrices de implementación como referencia definitiva.

## Contenido de origen incompleto

La fuente suministrada termina abruptamente en el paso 8, que no tiene contenido.
