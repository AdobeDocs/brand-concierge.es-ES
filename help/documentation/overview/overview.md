---
title: Información general de Brand Concierge
description: Descubra qué es Brand Concierge, cómo encajan sus componentes principales y el glosario de términos clave que encontrará en la interfaz del Compositor.
source-git-commit: 60835c7971d86341194d773f9cf487c4cb6f171a
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 1%

---

# Información general de Brand Concierge

Brand Concierge es una plataforma auténtica que permite a las empresas y marcas lanzar experiencias conversacionales personalizadas en sus superficies de cara al cliente: sitios web, aplicaciones móviles y otras propiedades digitales. Cada conversación se basa en el contenido y las protecciones de la propia marca, y las integraciones permiten que las perspectivas de esas conversaciones fluyan al resto del ecosistema de la marca, como Marketo Engage.

## Componentes principales

Una implementación de Brand Concierge tiene dos partes principales:

| Pedazo | Qué es |
|---|---|
| **Experiencia del visitante** | La superficie orientada a la marca, como un sitio web o una aplicación móvil, en la que los visitantes se relacionan con el conserje y obtienen respuestas en tiempo real. |
| **Compositor** | La interfaz de profesional utilizada para diseñar experiencias de conserjería y administrar conserjerías, integraciones, configuraciones, evaluaciones, implementación y análisis. |

## Módulos de Compositor

En Composer, los módulos principales son:

- [Administración de usuarios y acceso](../user-and-access-management/add-a-user-to-the-org.md)
- [Creación y administración de fuentes de conocimiento](../knowledge-sources/knowledge-sources.md), compartidas entre conserjes
- [Administración de conserjería](../concierge-management/concierge-management.md): integraciones, habilidades, instrucciones de conserjería, tono y voz, estilo visual y componentes de chat
- [Evaluación](../evaluation/evaluation.md)
- [Implementación](../deployment/deployment.md)
- [Lista de comprobación de Go-live](../go-live-checklist/go-live-checklist.md)
- [Analytics](../analytics/analytics.md)

## Cómo se conectan las piezas

Una fuente de conocimiento (contenido) se consulta mediante una integración (conexión), a la que llama una habilidad (comportamiento), todo ello envuelto en un conserje (la experiencia general) con el que los visitantes interactúan.

## Glosario

Estos términos aparecen en toda la interfaz de Composer.

| Término | Definición |
|---|---|
| **Conserje** | La propia experiencia de chat de IA: una por marca, sitio web o caso de uso. Una cuenta puede tener varias. |
| **Compositor** | Interfaz utilizada para crear y administrar conserjes, distinta de la que ven los visitantes del sitio web. |
| **Origen de conocimiento** | El contenido que un conserje puede utilizar para responder preguntas, como páginas web o una lista de productos. Sin una, el conserje no tiene nada de qué responder. |
| **Integración** | Una conexión a un sistema que puede recuperar información, como contenido de un sitio web o un catálogo de productos en directo. |
| **Habilidad** | Una capacidad específica que el conserje puede realizar, como responder preguntas generales, comparar productos o reservar una reunión. Una aptitud utiliza una o más integraciones para desempeñar su función. |
| **Mecanismos de protección** | Reglas que definen lo que el conserje no debe hacer o discutir, como competidores o asesoramiento legal. |
| **Evaluación** | Una prueba estructurada que consiste en preguntas de muestra emparejadas con respuestas esperadas, utilizadas para evaluar el rendimiento del conserje. |
| **ID de secuencia de datos** | Identificador técnico que especifica dónde se envían los datos de actividad del visitante en los sistemas de Adobe. Lo proporciona el equipo de TI o de análisis. |
| **espacio aislado** | Espacio de trabajo aislado dentro de una organización. Una organización puede tener más de uno; cada uno puede albergar varios conserjes. |
| **organización de IMS** | Término de Adobe para la cuenta general de una organización. |
| **MCP** (por ejemplo, Commerce MCP) | Un conector administrado por Adobe a un sistema específico, como un catálogo de productos activo, configurado con códigos o claves proporcionadas por TI o el equipo de comercio. |
| **CJA (Customer Journey Analytics)** | producto de análisis de Adobe. Brand Concierge aprovisiona automáticamente un tablero de inicio aquí sin necesidad de ninguna configuración adicional. |

>[!NOTE]
>
>Los especialistas en marketing generalmente pueden omitir [Administración de usuarios y acceso](../user-and-access-management/add-a-user-to-the-org.md) por completo (alguien en TI la completa una vez) y comenzar en [Fuentes de conocimiento](../knowledge-sources/knowledge-sources.md). Volver a la administración de usuarios y acceso solo cuando se configuren nuevos compañeros de equipo.
