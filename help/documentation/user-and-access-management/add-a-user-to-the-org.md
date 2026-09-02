---
title: Añadir un usuario a la organización
description: Obtenga información sobre cómo añadir un usuario a la organización de Adobe Experience Platform antes de conceder acceso a Brand Concierge.
source-git-commit: fc22eb8e724437483e5d87283f46fb629a4e507c
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 3%

---


# Añadir un usuario a la organización

Para que un usuario pueda acceder a Brand Concierge, agréguelo a la organización de Adobe Experience Platform en Adobe Admin Console.

>[!PREREQUISITES]
>
>- Debe tener acceso de administrador a la organización.
>- El usuario debe estar disponible para añadirlo de forma individual o a través de una carga de usuario masiva.

## Agregar un usuario

1. Vaya a **Admin Console**.
1. Seleccione **Administrar** o vaya a **Usuarios**.
1. Añada usuarios individualmente o agregue varios usuarios mediante una carga masiva.
1. Si el usuario aún no existe en la organización, seleccione la opción para agregar el usuario como nuevo usuario cuando se le solicite.
1. Seleccione el perfil de producto:

   - **Adobe Experience Platform**
   - El perfil de usuario predeterminado

1. Seleccione **Guardar**.

El usuario recibe una invitación por correo electrónico que confirma el acceso a la organización.

>[!IMPORTANT]
>
>La invitación de la organización proporciona al usuario acceso a la organización, pero no concede acceso a Brand Concierge. Para proporcionar acceso a Brand Concierge, cree y asigne un rol con el permiso de Brand Concierge como se describe en [Crear un rol con el permiso de Brand Concierge](./create-a-role.md).

## Próximos pasos

Una vez agregado el usuario a la organización, cree una función con el permiso **Administrar Brand Concierge** y asígnele la función.
