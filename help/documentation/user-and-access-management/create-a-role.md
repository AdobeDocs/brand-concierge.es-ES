---
title: Crear una función con permiso de Brand Concierge
description: Obtenga información sobre cómo crear una función y concederle el permiso necesario para acceder a Brand Concierge.
source-git-commit: 60835c7971d86341194d773f9cf487c4cb6f171a
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 1%

---


# Crear una función con permiso de Brand Concierge

Cree una función en Permisos de Adobe Experience Platform para otorgar a los usuarios acceso a Brand Concierge.

>[!PREREQUISITES]
>
>- Debe tener los permisos de administrador necesarios para administrar roles y permisos.
>- Primero se debe agregar el usuario a la organización de Adobe Experience Platform. Para obtener más información, consulte [Agregar un usuario a la organización](./add-a-user-to-the-org.md).

## Creación de la función

1. Iniciar sesión en `experienceplatform.adobe.com`.

1. En el panel de navegación de la izquierda, desplácese hasta **Permisos** y selecciónelos.
1. Vaya a **Roles** para ver los roles existentes y seleccione **Crear un nuevo rol**.
1. Escriba un nombre para la función, como `Brand Concierge Access Users`, agregue una descripción y confirme la creación.
1. Abra la nueva función y asigne permisos:

   1. Busque en la lista de permisos **Brand Concierge**.
   1. Seleccione **Administrar Brand Concierge**.

   En este momento, **Administrar Brand Concierge** es el único permiso de Brand Concierge disponible; los niveles de permisos granulares aún no están disponibles.

1. Seleccione la zona protegida o zonas protegidas a las que la función puede acceder.

   Una organización puede contener varios entornos limitados, que son espacios de trabajo aislados. Seleccione solo las zonas protegidas adecuadas para esta función.

1. Seleccione **Guardar**.

## Próximos pasos

Una vez creada la función, agregue usuarios. Para obtener más información, consulte [Agregar usuarios al rol de Brand Concierge](./add-a-user-to-the-role.md).
