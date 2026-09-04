---
title: Marco de aptitudes e integraciones
description: Aprenda cómo las habilidades y las integraciones trabajan juntas en el marco de conserjería. Las habilidades definen el comportamiento, mientras que las integraciones se conectan a los datos y proporcionan capacidad.
role: User, Admin
level: Beginner
source-git-commit: 60835c7971d86341194d773f9cf487c4cb6f171a
workflow-type: tm+mt
source-wordcount: '1698'
ht-degree: 0%

---

# Marco de aptitudes e integraciones {#skills-and-integrations}

Una integración (anteriormente conocida como herramienta) es una conexión a una fuente de datos o back-end. Una habilidad es un comportamiento.

Muchas aptitudes pueden utilizar una integración. Una aptitud puede utilizar varias integraciones. Los configura de forma independiente y los asigna juntos.

## Habilidades

Una habilidad es la capa de comportamiento de un conserje. Se trata de una unidad denominada y reutilizable que define un único trabajo que el conserje puede hacer: qué gestiona, cuándo interviene y cómo responde. Una habilidad no contiene datos propios; toma prestada la capacidad de las integraciones adjuntas a ella.

Cada aptitud consta de cinco partes:

| Parte | Qué es |
| --- | --- |
| Nombre | El identificador de la aptitud |
| Descripción | Para qué sirve la habilidad, su propósito en términos simples |
| Usar cuando | La condición de déclencheur. Esta es la señal de enrutamiento que le dice al conserje cuándo invocar esta habilidad en lugar de otra |
| Integraciones | Las herramientas específicas a las que puede recurrir esta aptitud para realizar su trabajo. Una aptitud solo puede utilizar lo que se adjunta aquí |
| Archivo de instrucciones | Las instrucciones detalladas que rigen el comportamiento de la aptitud y cómo interpreta una solicitud, formatea su respuesta y aplica sus protecciones |

Cómo se comporta una aptitud en tiempo de ejecución: cuando llega un mensaje de usuario, la plataforma lo compara con el déclencheur &quot;usar cuando&quot; de cada aptitud activa y enruta el mensaje a la aptitud coincidente. A continuación, esa aptitud ejecuta sus instrucciones y llama únicamente a las integraciones adjuntas a ella. Sus instrucciones se componen en el comportamiento general del tiempo de ejecución del conserje junto con el perfil de la marca y cualquier otra habilidad activa.

Una habilidad decide qué hacer y cuándo. No se conecta a ningún dato; esa es la función de la integración.

_Ejemplo de la aptitud de Site Advisory_

![Panel de detalles de aptitudes de Site Advisory que muestra su descripción, Usar cuando los déclencheur, integración de búsqueda de Knowledge Base adjunta e instrucciones de aptitudes](assets/skills-and-integrations-1.png){width="800" zoomable="yes"}

## Integraciones

Una integración es la capa de capacidad de un conserje. Es una conexión a un sistema externo o back-end (una base de conocimiento, una fuente de contenido, un catálogo de comercio en directo) que realmente recupera datos o realiza una acción. Cuando una aptitud es juicio, una integración es capacidad.

Cada integración tiene estas características:

| Característico | Lo que significa |
| --- | --- |
| Conexión y credenciales | Una integración se autentica en su servidor mediante su propia configuración, por ejemplo, un ID de entorno de comercio y una clave de API. Esta configuración es la que señala a la fuente de datos correcta |
| Funcionalidades expuestas | Una integración hace que una o más capacidades a las que se puede llamar estén disponibles, las acciones individuales que una aptitud puede invocar. Por ejemplo, Commerce MCP expone la búsqueda de productos, los detalles de productos, las variantes y la detección de facetas como funciones independientes |
| Reutilizable | Una integración se puede adjuntar a muchas habilidades, y la misma integración sirve a muchos conserjes y clientes. Esta reutilización es la eficiencia central del marco |

Cómo se comporta una integración en tiempo de ejecución: cuando una aptitud se activa y decide que necesita datos, llama a una de las herramientas de la integración. La integración ejecuta esa llamada en el servidor activo y devuelve datos estructurados a la aptitud, que esta utiliza para formar su respuesta.

Una integración proporciona capacidad de, pero no juzga. Espera a que una aptitud la llame, realiza el trabajo específico que se le ha pedido y devuelve el resultado.

### Capacidades y límites (límite de autoservicio)

- **Autoservicio, sin ingeniería:** Edite las instrucciones, edite los déclencheur de &quot;usar cuando&quot;, adjunte o desasocie integraciones existentes, habilite o deshabilite una aptitud y conecte una integración compatible (como Commerce MCP con credenciales válidas).

- **No es de autoservicio, necesita ingeniería:** Cree una herramienta o conector completamente nuevo que no exista ya en el catálogo, agregue una nueva categoría de protección que el marco de trabajo no admita o cambie los datos que expone un servidor.

- **La superposición de Déclencheur entre dos aptitudes representa un riesgo para la configuración:** Si dos aptitudes podrían activarse de forma plausible en el mismo mensaje, el enrutamiento puede ser incoherente. Escriba déclencheur para evitar ambigüedades reales en lugar de depender del enrutador para resolverlas.

## Integraciones disponibles de forma predeterminada

A continuación se muestran las integraciones del panel **Integraciones de exploración** del Compositor.

| Integración | Qué hace | Notas |
| --- | --- | --- |
| Búsqueda en base de conocimientos | Source para obtener información, precios, funciones y documentación del producto de una marca, mediante el rastreo del sitio | Este se crea automáticamente en la creación del conserje, rellenada por el rastree del sitio |
| Búsqueda por IA de contenido | Busca en el contenido de la marca a través de la inteligencia artificial aplicada al contenido | Una fuente de contenido alternativa; normalmente, solo se necesita una de Búsqueda de la base de conocimiento o Búsqueda por IA de contenido a la vez |
| Vinculación de entidades | Resuelve productos o menciones de la marca en un mensaje del usuario para entidades de catálogo específicas | Integración de soporte, utilizada junto con una integración de búsqueda en lugar de sola |
| MCP de Commerce | Servidor MCP de Commerce administrado por Adobe: búsqueda de productos, detalles, variantes y descubrimiento de facetas/atributos, respaldados por Adobe Live Search | No en la línea de base; se añade manualmente en los casos de uso de Commerce |
| Convocatoria de reunión | Permite a los visitantes reservar una reunión con un representante de ventas | Requiere una configuración con un calendario del representante de ventas, a través del producto Sales Qualifier complementario |
| Chat en vivo | Conecta a los visitantes con un representante de ventas en directo | Requiere configuración con disponibilidad de representante de ventas, a través del producto Sales Qualifier complementario |

![Panel de integraciones de exploración que muestra cuatro tarjetas de integración: Búsqueda por IA de contenido, Vinculación de entidades, Búsqueda en la base de conocimiento y MCP de Commerce](assets/skills-and-integrations-2.png){width="800" zoomable="yes"}

## Aptitudes disponibles de forma predeterminada

A continuación, se muestran las aptitudes en el panel **aptitudes de exploración** del compositor. Cada una enumera sus integraciones recomendadas.

| Habilidad | Para qué sirve | Integraciones recomendadas |
| --- | --- | --- |
| Site Advisory | Preguntas generales de marca: políticas, preguntas frecuentes, programas, procedimientos y asistencia | Búsqueda en la base de conocimiento, Búsqueda por IA de contenido y vinculación de entidades |
| Asesoramiento de productos | Descubre e investiga productos: tarjetas de producto basadas en nombres y preguntas de productos en prosa | Búsqueda en la base de conocimiento, vinculación de entidades |
| Descubrimiento del catálogo Adobe Commerce | Busque, examine, filtre y obtenga detalles completos sobre productos con un catálogo en directo | Herramientas de MCP de Commerce: buscar productos de Commerce, detalles del producto, variantes del producto, facetas del producto y atributos en los que se puede buscar |
| Comparación de productos de Adobe Commerce | Comparación paralela de dos o más productos con nombre en una tabla para Commerce | Herramientas de MCP de Commerce: buscar productos de Commerce, detalles del producto |
| Encuentro de Libros con Ventas | Sugiere y facilita la reserva de una reunión con un representante de ventas | Integración de Meeting Booking |
| Chat en vivo con Ventas | Sugiere y facilita un envío de chat en vivo a un representante de ventas | Integración de Live Chat |

Las dos aptitudes de comercio son capacidades solo de catálogo y dependen de la integración de Commerce MCP, que no forma parte de la línea de base. En un conserje que no sea de comercio, Site Advisory y Product Advisory se ejecutan con la búsqueda de la base de conocimiento creada automáticamente.

![Panel de aptitudes de exploración que muestra cuatro tarjetas de aptitudes: asesoramiento de producto, descubrimiento de catálogos de Adobe Commerce, comparación de productos de Adobe Commerce y asesoramiento de sitio](assets/skills-and-integrations-3.png){width="800" zoomable="yes"}

## ¿Qué es el cableado en la creación de conserjería?

Cuando se crea un conserje a través de la configuración con un solo clic, la línea de base se monta por usted.

| Cableado en la creación | Detalles |
| --- | --- |
| Base de conocimiento (datos) | El rastree anticipado crea una base de conocimiento a partir de las 10 a 15 páginas principales del sitio, que se encuentran a través del mapa del sitio. Este es el almacén de contenido, no una habilidad o integración |
| Búsqueda en la base de conocimientos (integración) | Integración integrada, conectada a la base de conocimiento rastreada y utilizada para buscarla. El rastreo no crea esto; apunta a lo que el rastreo produjo |
| Asesoramiento del sitio (aptitud) | Activo en la línea de base, cableado para llamar a la búsqueda de la base de conocimiento, que consulta la base de conocimiento rastreada |

## Preguntas frecuentes

**¿Cuál es la diferencia entre una aptitud y una integración?**

Una integración es una conexión a una fuente de datos o back-end; es a lo que el conserje puede llegar, como una base de conocimiento o un catálogo de comercio en directo. Una habilidad es un comportamiento; decide qué hace el conserje, cuándo lo hace y qué integraciones puede utilizar.

**Regla general:** Una integración es una capacidad; una habilidad es el criterio sobre cuándo y cómo usar esa capacidad.

**¿Puede usar la misma integración más de una aptitud?**

Sí, y esto es intencional. Las herramientas de MCP de Commerce se comparten entre la detección de catálogos y la comparación de productos. Crear una integración una vez y reutilizarla en muchas habilidades y muchos clientes es la eficiencia central del marco de trabajo 2.0; es lo que elimina la compilación personalizada por cliente.

**¿Puede un profesional agregar una capacidad completamente nueva sin ingeniería?**

Solo si ya existe una integración para él en el catálogo. Un profesional puede asignar, configurar e instruir libremente cualquier integración existente; es decir, autoservicio. Pero si la capacidad requiere un back-end o conector que aún no existe (una nueva API o un nuevo tipo de fuente de datos), es una tarea de ingeniería para crear primero la integración. Una vez que existe en el catálogo, la configuración vuelve a convertirse en autoservicio.

**¿En qué se diferencia esto del único aviso de sistema de BC 1.0?**

En la versión 1.0, el comportamiento estaba impulsado por un gran indicador del sistema (el manifiesto), que era difícil de editar con seguridad y que, por lo general, requería de ingeniería para cambiar. En 2.0 el manifiesto aún existe, pero está compuesto de piezas modulares en lugar de estar escrito como un bloque. Eso es lo que hace que el comportamiento sea configurable por un profesional y hace que las protecciones e instrucciones individuales sean legibles y auditables en lugar de estar enterradas en un solo mensaje.

**¿Qué crea exactamente la rastrea anticipada?**

El rastree crea una base de conocimiento, un almacén de búsqueda del contenido del sitio, creado a partir de las 10 a 15 páginas principales encontradas a través del mapa del sitio. Solo es la capa de datos. La rastrea no crea una aptitud ni una integración; produce el contenido sobre el que actúan posteriormente.

**Si el rastree crea la base de conocimiento, ¿qué es la integración de búsqueda de la base de conocimiento?**

La búsqueda en la base de conocimiento es una integración integrada cuyo trabajo consiste en buscar en esa base de conocimiento. La base de conocimiento son los datos; la búsqueda de la base de conocimiento es la capacidad que realiza la consulta. Son dos cosas separadas: una es el contenido, la otra es la herramienta que lee el contenido. Es un error común tratarlos como si fueran lo mismo; no lo son.

**¿Cómo responde el conserje a una pregunta general durante la creación, de principio a fin?**

Tres capas trabajan en secuencia y se asignan exactamente a la aptitud, la integración y el modelo de datos:

- La rastrea temprana crea la base de conocimiento a partir de las páginas del sitio (datos).
- La integración de búsqueda de la base de conocimiento busca en esa base de conocimiento (integración).
- La habilidad de Site Advisory está cableada para llamar a la Búsqueda de la base de conocimiento (comportamiento).
