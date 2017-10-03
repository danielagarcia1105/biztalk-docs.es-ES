---
title: "Esquemas de mensajes de notificación de consulta mediante el adaptador de SQL en BizTalk | Documentos de Microsoft"
description: Usar el adaptador SQL para recibir las notificaciones de consulta de una base de datos de SQL Server de BizTalk
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5183655-64d4-4767-a923-0a575e3708cd
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c78c817470bd8acd41f44204653c41e9012d154
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-query-notification"></a>Esquemas de mensaje de notificación de consulta
El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] superficies de la operación de notificación para recibir las notificaciones de consulta de la base de datos de SQL Server.  
  
 Configurar la operación de notificación estableciendo las propiedades de enlace el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Para obtener más información acerca de las propiedades de enlace relacionadas con notificaciones, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md). Establece el **NotificationStatement** enlace de propiedad para especificar una instrucción SQL (SELECT o EXEC \<procedimiento almacenado >) para la notificación de consulta. El conjunto de resultados de esta consulta se devuelve como datos fuertemente tipados en el código en la operación de notificación.  
  
## <a name="message-structure-for-the-notification-operation"></a>Estructura del mensaje para la operación de notificación  
 En la tabla siguiente se muestra la estructura del mensaje XML para la operación de notificación.  

**Operación**:`Notification`

**Mensaje XML**:  
```xml
<?xml version="1.0" encoding="utf-8" ?>
  <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification">
    <Info>Value</Info>
    <Source>Value</Source>
    <Type>Value</Type>
 </Notification>
```

**Descripción**: este es el mensaje entrante que se envía el servidor SQL Server a los clientes de adaptador. En el mensaje:

- La `<Info>` etiqueta indica el motivo de la notificación. Por ejemplo, un valor de "inserción" en esta etiqueta indica que se ha insertado datos en una o varias de las tablas que se hace referencia en la instrucción de notificación.
- La `<Source>` etiqueta indica el origen para la notificación. Por ejemplo, un valor de "datos" en esta etiqueta indica un cambio en los datos de referencia a un objeto. De forma similar, un valor de "object" en esta etiqueta indica un cambio en un objeto que se hace referencia.
- La `<Type>` etiqueta indica el tipo de cambio de datos. Mensajes de notificación de consulta son de dos tipos: cambiar y suscribirse. Un "cambiar" valor de la `<Type>` etiqueta indica que los resultados de la consulta han cambiado, mientras que un valor "suscribirse" en la `<Type>` etiqueta indica que ha fallado una solicitud de suscripción.

  
## <a name="message-action-for-the-notification-operation"></a>Acción de mensaje para la operación de notificación  
 La acción de mensaje para la operación de notificación es "Notificaciones".  
  