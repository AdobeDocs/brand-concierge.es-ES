---
title: Analizar el rendimiento del conserje
description: Aprenda a revisar el análisis de conserjería, inspeccionar transcripciones de conversaciones, añadir preguntas de visitantes a conjuntos de evaluación y abrir informes de Customer Journey Analytics.
hide: true
source-git-commit: fc22eb8e724437483e5d87283f46fb629a4e507c
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 0%

---


# Analizar el rendimiento del conserje

**Para quién es:** Especialistas en marketing que utilizan la experiencia de autoservicio. No se requiere ninguna configuración después de que se implemente el conserje.

**Cadencia recomendada:** Revise los análisis según sea necesario. Un check-in semanal es un punto de partida razonable.

Analytics le ayuda a comprender cómo los visitantes interactúan con un conserje en directo. Después de la implementación, la pestaña **Analytics** muestra automáticamente las métricas de conversación y proporciona acceso a transcripciones individuales y a un informe de Customer Journey Analytics más detallado.

## Ver análisis

1. Abra el conserje y seleccione la ficha **Analytics**.

1. Establezca el intervalo de fechas para el período que desea revisar.

1. Si lo desea, filtre los resultados por tipo de conversación.

La pestaña Analytics muestra automáticamente las siguientes métricas:

| Métrica | Descripción |
|---|---|
| Conversiones | Número de conversaciones durante el período seleccionado. |
| Visitantes comprometidos | El número de visitantes que se comprometieron con el conserje. |
| Opinión positiva | La cantidad de opinión positiva identificada en las conversaciones. |
| Mensajes por conversación | El número promedio de mensajes intercambiados en una conversación. |

>[!NOTE]
>
>No se requiere ninguna configuración para ver estas métricas después de implementar el conserje.

## Revisar transcripciones de conversaciones

Las transcripciones de conversación le permiten revisar lo que los visitantes preguntaron y cómo respondió el conserje.

1. En la pestaña Analytics, seleccione una conversación.

1. Lea la transcripción completa.

1. Revise si los visitantes han seleccionado una clasificación de miniaturas arriba o abajo para las respuestas individuales.

Cada conversación tiene un ID de conversación único. Utilice este ID para hacer coincidir la transcripción con los registros de otros sistemas cuando la implementación admita ese flujo de trabajo.

### Agregar una conversación a un conjunto de evaluación

Si un visitante hace una pregunta que resulta útil para futuras pruebas, añádala directamente a un conjunto de evaluación de la transcripción.

1. Abra la transcripción de la conversación.

1. Seleccione **Agregar a evaluación**.

Añadir preguntas reales al visitante ayuda a mantener los conjuntos de evaluación basados en las preguntas que los visitantes realmente formulan. Para obtener más información sobre los conjuntos de evaluación, vea [Evaluar a un conserje](../evaluation/evaluation.md).

>[!TIP]
>
>Revise las transcripciones regularmente y añada preguntas representativas, no solo preguntas que recibieron comentarios negativos, para ayudar a mantener un conjunto de evaluación equilibrado.

## Abra el informe de Customer Journey Analytics

Seleccione **Ver informe** para abrir un tablero más detallado en Adobe Customer Journey Analytics (CJA). El tablero se aprovisiona automáticamente y no requiere ninguna configuración adicional.

El tablero de CJA incluye:

- Tendencias de conversación semanales.
- Repita el compromiso, incluidas las conversaciones por persona.
- Mensajes por conversación.
- Tendencias de comentarios de visitantes.
- Intento del visitante.
- Opinión y tono del visitante.
- Recomendaciones de conserjería hechas durante las conversaciones.

Utilice el tablero para examinar las tendencias a lo largo del tiempo e identificar los cambios en la participación, los comentarios, la intención y la opinión de los visitantes.

## Exportar conversaciones

El material de origen identifica el ID de conversación como una forma de hacer coincidir transcripciones con registros de otros sistemas, pero no documenta un mecanismo de exportación.

>[!IMPORTANT]
>
>No trate los ID de conversación como un flujo de trabajo de exportación. Se requiere un tutorial dedicado de Productos o Ingeniería antes de documentar cómo exportar conversaciones o transcripciones.
