---
title: Los esquemas de mensajes para la notificación Operation1 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f98d76d0-6084-4de7-b6ff-124202ca92ab
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cdf371335a1242423c4497f186fa5764f5b2fb2f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991693"
---
# <a name="message-schemas-for-the-notification-operation"></a>Esquemas de mensaje para la operación de notificación
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] superficies de la operación de notificación para recibir notificaciones de cambio de base de datos de la base de datos de Oracle.  
  
 Configurar la operación de notificación mediante el establecimiento de propiedades de enlace en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Para obtener más información acerca de las propiedades de enlace relacionadas con notificaciones, consulte [Obtenga información sobre las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md). Establece el **NotificationStatement** enlaza la propiedad para especificar una instrucción SELECT para la notificación de consulta.  
  
## <a name="message-structure-for-the-notification-operation"></a>Estructura de mensaje para la operación de notificación  
 En la tabla siguiente se muestra la estructura del mensaje XML para la operación de notificación.  
  
|Operación|Mensaje XML|Descripción|  
|---------------|-----------------|-----------------|  
|Notification|`<?xml version="1.0" encoding="utf-8" ?>  <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification">    <Info>Value</Info>    <Source>Value</Source>    <Type>Value</Type> </Notification>`|Este es el mensaje entrante que se envía a la base de datos de Oracle a los clientes del adaptador. En el mensaje:<br /><br /> -El `<Info>` etiqueta indica el motivo de la notificación. Por ejemplo, un valor de "insert" en esta etiqueta indica que se ha insertado datos en una o varias de las tablas que se hace referencia en la instrucción de notificación.<br /><br /> -El `<Source>` etiqueta indica el origen de la notificación. Por ejemplo, un valor de "datos" en esta etiqueta indica un cambio en los datos de un objeto que se hace referencia. De forma similar, un valor de "objeto" en esta etiqueta indica un cambio en un objeto que se hace referencia.<br /><br /> -El `<Type>` etiqueta indica el tipo de cambio de datos. Por ejemplo, una "actualización" de valor en el `<Type>` etiqueta indica que se han actualizado los resultados de la consulta.|  
  
## <a name="message-action-for-the-notification-operation"></a>Acción de mensaje para la operación de notificación  
 La acción de mensaje para la operación de notificación es "<http://Microsoft.LobServices.OracleDB/2007/03/Notification”>.  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)