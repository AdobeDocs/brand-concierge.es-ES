---
title: Evaluar a un conserje
description: Aprenda a crear conjuntos de evaluaciones y ejecutar evaluaciones funcionales, fuera de ámbito y de salvaguardia para evaluar la precisión y la seguridad de las respuestas de un conserje.
hide: true
source-git-commit: fc22eb8e724437483e5d87283f46fb629a4e507c
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 0%

---


# Evaluar a un conserje

**Para quién es:** Especialistas en marketing que utilizan la experiencia de autoservicio. No se requiere asistencia de TI.

**Tiempo necesario:** Unos minutos para crear un conjunto de evaluación. La ejecución de una evaluación tarda más en función del tamaño del conjunto.

Las evaluaciones le ayudan a generar confianza en que las respuestas de un conserje son precisas antes de que el conserje sea revisado por alguien fuera de su equipo inmediato. A diferencia de las pruebas ad hoc en la experiencia de vista previa, las evaluaciones proporcionan una forma repetible de medir las respuestas frente a las respuestas esperadas.

## Tipos de evaluación

Las evaluaciones se dividen en tres categorías:

| Tipo | Objetivo |
|---|---|
| Funcional | Comprueba las respuestas a preguntas normales y relevantes acerca de sus productos o servicios. |
| Fuera de ámbito | Comprueba cómo el conserje gestiona las preguntas que no debe responder pero que no son perjudiciales, como las preguntas sobre un competidor o un tema no relacionado. |
| Salvaguardar | Comprueba cómo el conserje gestiona los datos dañinos o contradictorios, incluidas las preguntas engañosas, las blasfemias y los intentos de manipularlos. |

## Creación de un conjunto de evaluación

Un conjunto de evaluación, también denominado *conjunto de datos dorado* o *verdad básica*, es una lista de preguntas de ejemplo emparejadas con las respuestas que se consideran correctas. Las respuestas reales del conserje se comparan con las respuestas esperadas durante una evaluación.

### Creación de un conjunto de evaluación

1. Asigne un nombre al conjunto de evaluación. Por ejemplo, `About my products`.

1. Elija cómo crear el conjunto:

   * **Generado por IA:** El compositor lee la fuente de conocimiento y redacta una lista de preguntas probables y respuestas esperadas para su revisión.
   * **Carga manual o de hoja de cálculo:** Proporcione una lista de preguntas y respuestas directamente.

1. Si está creando un conjunto generado por IA, asegúrese de que la fuente de conocimiento esté completamente configurada antes de generar el conjunto. Compositor utiliza la fuente de conocimiento para redactar las preguntas y respuestas.

1. Revise cada par de pregunta y respuesta generado:

   * Editar una respuesta para ajustar su redacción.
   * Elimine una pregunta que no sea relevante.

1. De forma opcional, descargue el conjunto como una hoja de cálculo para que la revise un compañero. Después de la revisión, vuelva a cargar la hoja de cálculo.

>[!TIP]
>
>Los conjuntos de evaluación generados por IA son borradores basados en la fuente de conocimiento. Revise y corrija de la misma manera que revisa el perfil de la marca y las instrucciones durante la creación del conserje.

## Ejecutar una evaluación

1. Seleccione **Ejecutar evaluación**.

1. Seleccione el conjunto de evaluación que se ejecutará y, a continuación, seleccione **Ejecutar**.

1. Espera mientras el conserje se hace cada pregunta en el conjunto. Las respuestas reales del conserje se comparan con las respuestas esperadas.

   El tiempo de procesamiento aumenta con la cantidad de preguntas del conjunto. El progreso se muestra como porcentaje.

1. Una vez completado el procesamiento, revise la puntuación general y el número de respuestas marcadas.

Las respuestas marcadas son respuestas potencialmente problemáticas que pueden requerir una revisión adicional.

## Revisar resultados de evaluación

**Resultados de la evaluación** muestra todas las ejecuciones anteriores de un conjunto de evaluación, para que pueda realizar un seguimiento de los resultados a lo largo del tiempo.

Para revisar una ejecución:

1. Abra una ejecución de evaluación de **Resultados de evaluación**.

1. Revise cada pregunta junto con la respuesta real del conserje y la respuesta esperada.

1. Revise la clasificación asignada a cada resultado. Los resultados reciben una calificación de **high**, **medium** o **low** e incluyen una nota que explica el razonamiento. Por ejemplo, un resultado podría marcarse **necesita atención** con un motivo para la clasificación.

1. Revise las respuestas marcadas directamente para centrarse en los resultados potencialmente problemáticos sin leer todos los resultados de la ejecución.

## Prácticas recomendadas

* Configure completamente la fuente de conocimiento antes de generar un conjunto de evaluación basado en IA. Un contenido de origen más completo genera mejores preguntas de borrador.
* Cree al menos un pequeño conjunto de evaluación para cada tipo de evaluación: funcional, fuera de ámbito y de protección. Cada tipo detecta una clase diferente de problema.
* Vuelva a ejecutar las evaluaciones después de cualquier cambio de configuración significativo, incluidos los cambios en las instrucciones, las protecciones, las aptitudes o las integraciones. Trate las evaluaciones como una práctica continua en lugar de una puerta de una sola vez.
* Agregue preguntas reales de los visitantes de Analytics a un conjunto de evaluación cuando revelen un vacío que merezca la pena probar.
