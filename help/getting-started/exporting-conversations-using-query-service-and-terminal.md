---
title: Exportación de conversaciones mediante el servicio de consultas y el terminal
description: Obtenga información sobre cómo exportar conversaciones de Brand Concierge a CSV mediante Experience Platform Query Service y Terminal, con instrucciones sobre credenciales y datos personales.
topic: Development
role: Developer
level: Experienced
doc-type: Tutorial
duration: 260
last-substantial-update: 2026-10-15
jira: KT-22874
source-git-commit: 04c844e16a8fb13e54dfcbb29c776896674532b9
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%
---
# Exportación de conversaciones mediante el servicio de consultas y el terminal

Obtenga información sobre cómo guardar y exportar conversaciones de Adobe Brand Concierge mediante el servicio de consultas y el terminal de Adobe Experience Platform. Este vídeo muestra cómo buscar nombres de tablas de conjuntos de datos, configurar el cliente de línea de comandos PostgreSQL y exportar datos de conversación para un intervalo de fechas a un archivo CSV.

## ¿Para quién es este vídeo?

* Desarrolladores que necesiten exportar datos de conversación de Brand Concierge mediante herramientas de línea de comandos

## Contenido de vídeo

* Busque conjuntos de datos de conversación en Experience Platform y copie sus nombres de tabla
* Instale el cliente PostgreSQL con Homebrew y configure su ruta de línea de comandos
* Copie el comando de conexión PSQL de la ficha Credenciales del servicio de consultas
* Seleccione un conjunto de datos y un intervalo de fechas y, a continuación, exporte los resultados de la consulta a un archivo CSV local
* Compruebe los resultados exportados y actualice las credenciales caducadas cuando sea necesario

>[!VIDEO](https://video.tv.adobe.com/v/3504643)

```bash
psql "sslmode=require host=... password=..." --csv -o ~/brand-concierge-conversation-export/oct-1-2026-till-today-responses.csv -c "SELECT * FROM cja_brand_concierge_responses_dataset_b4c15126_bd9b_4d52_8151_26 WHERE timestamp >= TIMESTAMP '2026-10-01 00:00:00' AND timestamp <= NOW() ORDER BY timestamp ASC LIMIT 1000"
```

>[!IMPORTANT]
>
> El comando de conexión PSQL contiene una contraseña activa. No lo comparta ni lo pegue en chats, agentes de IA ni correos electrónicos. Si la autenticación falla después de que caduque la contraseña, copie un comando nuevo de la pestaña Credenciales del servicio de consulta.

>[!NOTE]
>
> Las conversaciones exportadas pueden contener información de identificación personal (PII). Siga las políticas de gestión de datos de su organización al almacenar archivos CSV.

Para obtener documentación, consulte [Ayuda de Brand Concierge](../documentation/overview.md).

## Tutoriales relacionados

* [Exportación de conversaciones mediante Adobe CX Enterprise Coworker](exporting-conversations-using-adobe-cx-enterprise-coworker.md)
