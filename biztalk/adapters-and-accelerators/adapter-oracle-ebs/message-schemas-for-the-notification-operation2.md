---
title: "Esquemas de mensajes para la notificación Operation2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dddab2ef-94db-46c8-95c1-57517681e8dd
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8c004e83ada00b41013c2a22c5e48f29bb39ffd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-the-notification-operation"></a>Esquemas de mensaje para la operación de notificación
El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]superficies de la operación de notificación para recibir notificaciones de cambio de base de datos de la base de datos subyacente en Oracle E-Business Suite.  
  
 Configurar la operación de notificación estableciendo las propiedades de enlace el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Para obtener más información acerca de las propiedades de enlace relacionadas con notificaciones, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md). Establece el **NotificationStatement** enlace de propiedad para especificar una instrucción SELECT para la notificación de consulta.  
  
## <a name="message-structure-for-the-notification-operation"></a>Estructura del mensaje para la operación de notificación  
 En la tabla siguiente se muestra la estructura del mensaje XML para la operación de notificación.  
  
|Operación|Mensaje XML|Description|  
|---------------|-----------------|-----------------|  
|Notification|`<?xml version="1.0" encoding="utf-8" ?>  <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification">    <Info>Value</Info>    <Source>Value</Source>    <Type>Value</Type> </Notification>`|Este es el mensaje entrante que se envía por Oracle E-Business Suite a los clientes de adaptador. En el mensaje:<br /><br /> -El `<Info>` etiqueta indica el motivo de la notificación. Por ejemplo, un valor de "inserción" en esta etiqueta indica que se ha insertado datos en una o varias de las tablas que se hace referencia en la instrucción de notificación.<br /><br /> -El `<Source>` etiqueta indica el origen para la notificación. Por ejemplo, un valor de "datos" en esta etiqueta indica un cambio en los datos de referencia a un objeto. De forma similar, un valor de "object" en esta etiqueta indica un cambio en un objeto que se hace referencia.<br /><br /> -El `<Type>` etiqueta indica el tipo de cambio de datos. Por ejemplo, una "actualización" valor de la `<Type>` etiqueta indica que se han actualizado los resultados de la consulta.|  
  
## <a name="message-action-for-the-notification-operation"></a>Acción de mensaje para la operación de notificación  
 La acción de mensaje para la operación de notificación es "Notificaciones".  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)