---
title: Crear una función con permiso de Brand Concierge
description: Obtenga información sobre cómo crear una función y concederle el permiso necesario para acceder a Brand Concierge.
source-git-commit: 591bd1600e586a0a4ce484dbff3f9fb97e24d43d
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 1%

---


# Crear una función con permiso de Brand Concierge

Cree una función en Permisos de Adobe Experience Platform para otorgar a los usuarios acceso a Brand Concierge.

## Requisitos previos

* Debe tener los permisos de administrador necesarios para administrar roles y permisos.
* Primero se debe agregar el usuario a la organización de Adobe Experience Platform. Para obtener más información, consulte Adición de un usuario a la organización (VÍNCULO).

## Creación de la función

1. Iniciar sesión en `experienceplatform.adobe.com`.

   >[!NOTE]
   >
   >Confirme la dirección URL de producción con el departamento de ingeniería antes de publicar este procedimiento. La grabación de origen utilizaba una URL informal o posiblemente mal transcrita.

2. En el panel de navegación de la izquierda, desplácese hasta **Permisos** y selecciónelos.
3. Seleccione **Roles** para ver los roles existentes y, a continuación, seleccione **Crear un nuevo rol**.
4. Escriba un nombre para la función, como `Brand Concierge Access Users`, agregue una descripción y confirme la creación.
5. Abra la nueva función y asigne permisos:

   1. Busque en la lista de permisos **Brand Concierge**.
   2. Seleccione **Administrar Brand Concierge**.

   Actualmente, **Administrar Brand Concierge** es el único permiso de Brand Concierge disponible. Los niveles de permisos granulares no están disponibles actualmente.

6. Seleccione la zona protegida o zonas protegidas a las que la función puede acceder.

   Una organización puede contener varios entornos limitados, que son espacios de trabajo aislados. Seleccione solo las zonas protegidas adecuadas para esta función.

7. Seleccione **Guardar**.

## Próximos pasos

Una vez creada la función, agregue usuarios. Para obtener más información, consulte &quot;Añadir usuarios a la función&quot; (VÍNCULO).

## Consideraciones relacionadas

* El proceso de creación y administración de zonas protegidas está fuera del ámbito de este procedimiento.
* Confirme si se han planificado permisos granulares de Brand Concierge adicionales antes de definir un modelo de función a largo plazo.
