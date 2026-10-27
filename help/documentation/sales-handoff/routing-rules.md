---
title: Enrutar conversaciones a los representantes
description: Elija cómo decide Brand Concierge qué representante de ventas recibe una conversación en directo o una reserva de reunión, utilizando la operación por turnos, un agente directo o reglas de enrutamiento personalizadas.
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
source-git-commit: 91cbec8d6f4e4800e3bdc8c8f60bfe9ed168a963
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 0%
---
# Dirija las conversaciones a los representantes {#routing}

El enrutamiento responde a una pregunta: cuando este visitante pregunta por una persona, *¿qué persona* obtiene?

Usted elige un tipo de enrutamiento por separado para la integración de **[!UICONTROL Meeting Booking]** y la integración de **[!UICONTROL Live Chat]**, de manera que un conserje pueda distribuir las reuniones de manera uniforme mientras envía cada chat a un especialista o a cualquier otra combinación.

## Tipos de enrutamiento {#routing-types}

| Tipo de enrutamiento | Quién recibe la conversación | Requiere [!DNL Marketo Engage] |
| --- | --- | --- |
| **[!UICONTROL Operación por turnos]** | Distribuido entre todos los representantes aptos | No |
| **[!UICONTROL Agente directo]** | Un representante que usted nombre | No |
| **[!UICONTROL Enrutamiento personalizado]** | Los representantes asignados a la regla de enrutamiento de mayor prioridad a la que el visitante pertenece | Sí |

La operación por turnos está disponible de forma predeterminada y no necesita configuración. El tipo de enrutamiento se establece en la propia integración. Ver [Activar chat en vivo y reserva de reuniones](configure-in-composer.md).

### Round Robin {#round-robin}

Round Robin se comporta de forma diferente para las reuniones que para las charlas, porque las dos tienen objetivos diferentes.

Para la reserva de reuniones, round robin distribuye las reuniones uniformemente. Primero se ofrece el primer representante elegible que ha conectado un calendario. Una vez que se reserva una reunión con ellos, se sacan de la piscina y se ofrece el siguiente representante. Con cinco representantes, las primeras cinco reuniones van a cinco personas diferentes. Después de que todos hayan recibido uno, el grupo se restablece y el ciclo comienza de nuevo.

La piscina también se restablece cada 24 horas, de modo que las reuniones de cada día se distribuyen uniformemente.

>[!NOTE]
>
>El restablecimiento de operación por turnos de 24 horas se ejecuta en UTC, no en la zona horaria local del representante.

Para el chat en vivo, no hay rotación secuencial. Cada representante elegible es notificado del chat entrante al mismo tiempo, y el primero en aceptar toma la conversación.

### Agente directo {#direct-agent}

Cada reunión o chat de este conserje va a la única representante que usted seleccione. Utilícelo para una página de aterrizaje de campaña propiedad de un ejecutivo de cuentas o para una región con un especialista.

### Enrutamiento personalizado {#custom-routing}

El enrutamiento personalizado evalúa las reglas que genera en [!DNL Adobe Marketo Qualifier] con respecto a los atributos del posible cliente y de la compañía [!DNL Marketo] del visitante. Utilícelo cuando el representante adecuado dependa de algo que conozca sobre el visitante, como:

* Geografía: los visitantes de un conjunto de países acuden al equipo regional.
* Interés del producto: los visitantes interesados en un producto específico acuden a los especialistas de ese producto.
* Unidad de negocio, tamaño de empresa o sector: cualquier combinación de cliente potencial y atributos de empresa.

>[!IMPORTANT]
>
>El enrutamiento personalizado es la única parte de una reserva de reunión y chat en vivo que requiere [!DNL Adobe Marketo Engage], ya que las reglas se basan en los atributos del posible cliente y de la compañía [!DNL Marketo]. Round robin y agente directo trabajan sin él.

## Crear una regla de enrutamiento personalizada {#create-rule}

1. En [!DNL Adobe Marketo Qualifier], en **[!UICONTROL Administración]**, seleccione **[!UICONTROL Reglas de enrutamiento]**.

   La lista muestra todas las reglas de la organización con su prioridad, nombre, creador y fecha de creación.

   ![La página de reglas de enrutamiento enumera las reglas existentes con las columnas Prioridad, Nombre, Creado por y Creado en](../assets/sales-handoff-routing-1.png){width="800" zoomable="yes"}

1. Seleccione **[!UICONTROL Crear regla]** y asígnele un nombre.

1. Genere los criterios.

   En el panel izquierdo se enumeran los atributos disponibles [!DNL Marketo] de los objetos **[!UICONTROL Compañía]** y **[!UICONTROL Posible cliente]** (persona). Busque un atributo y, a continuación, arrástrelo al lienzo para añadir una condición.

1. Establezca un operador y un valor para cada condición.

   Los operadores incluyen **[!UICONTROL es igual a]**, **[!UICONTROL no es igual a]** y **[!UICONTROL contiene]**, entre otros. Por ejemplo, `Country` **[!UICONTROL es igual a]** `United States`.

1. Combinar condiciones en grupos.

   Agregue varias condiciones a un grupo y únalas con **[!UICONTROL AND]** o **[!UICONTROL OR]**. Agregue más grupos y únase a los grupos con **[!UICONTROL AND]** o **[!UICONTROL OR]** también. Anidar condiciones dentro de grupos de esta manera le permite expresar criterios complejos, como *(el país es Estados Unidos O Canadá) Y (el interés del producto contiene Analytics)*.

1. Asigne la regla a los representantes.

   En la sección de asignación, busque un representante por nombre y selecciónelo en la lista. Añada tantos representantes como desee. Cualquiera de ellos puede recibir una conversación que coincida con la regla.

1. Seleccione **[!UICONTROL Guardar]**.

## Aplicación de la prioridad {#priority}

Cada regla de enrutamiento tiene una prioridad. La prioridad solo importa cuando un visitante cumple los requisitos para más de una regla.

Cuando esto sucede, solo se aplica la regla de coincidencia de prioridad más alta y la conversación se redirige a los representantes asignados a esa regla. Se omiten las reglas para las que el visitante también cumple los requisitos, pero cuyo rango sea menor.

>[!NOTE]
>
>Un número menor significa una prioridad mayor. Una regla con prioridad 1 prevalece sobre una regla con prioridad 2. La persona que crea una regla establece su prioridad.

Dentro de la regla ganadora, los representantes asignados a él son el grupo apto, y el comportamiento de round robin para reuniones y el comportamiento notify-every para charlas, ambos descritos anteriormente, se aplican a ese grupo.

## Siguiente paso {#next}

Con los representantes configurados y el enrutamiento decidido, añada las capacidades a un conserje. Ver [Activar chat en vivo y reserva de reuniones](configure-in-composer.md).
