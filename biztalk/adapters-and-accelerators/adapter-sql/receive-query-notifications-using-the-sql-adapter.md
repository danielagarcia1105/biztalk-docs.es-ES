---
title: Recibir notificaciones de consulta mediante el adaptador de SQL | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b2ed0f0-d005-4eec-b1a6-97a0c94678dc
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37d333a2248c943d1d404aa086565ae4b1662226
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-query-notifications-using-the-sql-adapter"></a>Recibir notificaciones de consulta mediante el adaptador de SQL
Los clientes de adaptador pueden suscribirse para recibir notificaciones de consulta sobre los cambios de datos en la base de datos de SQL Server. Una instrucción SELECT de SQL o un procedimiento almacenado especifica los criterios de cambio de datos en una tabla para la activación de las notificaciones de consulta y el servidor SQL Server envía notificaciones de consulta como y cuando el conjunto de resultados de la instrucción SELECT o el procedimiento almacenado cambia.  
  
> [!IMPORTANT]
>  Para admitir las notificaciones de consulta, los clientes de adaptador y de la base de datos de SQL Server deben cumplir ciertos requisitos. Para obtener información detallada acerca de estos requisitos, consulte "Habilitar las notificaciones de consulta" en [http://go.microsoft.com/fwlink/?LinkID=122323](http://go.microsoft.com/fwlink/?LinkID=122323).  
  
 Una notificación de consulta típica implica lo siguiente:  
  
-   Deben especificar los clientes de adaptador `Notification` como la operación de entrada en el **InboundOperationType** propiedad de enlace. El valor predeterminado de esta propiedad de enlace es `Polling`.  
  
-   Los clientes de adaptador deben especificar una instrucción SQL para registrar las notificaciones de consulta en el **NotificationStatement** propiedad de enlace. El cliente de adaptador recibe una notificación de SQL Server tan pronto como el conjunto de resultados para que los cambios de instrucción SQL especificados.  
  
    > [!IMPORTANT]
    >  Para recibir notificaciones, la instrucción SQL para la suscripción de notificación *debe* cumplen determinados criterios. Para obtener información acerca de las instrucciones SQL que se puede usar para las notificaciones de consulta, vea [http://go.microsoft.com/fwlink/?LinkId=122160](http://go.microsoft.com/fwlink/?LinkId=122160).  
  
-   Los clientes de adaptador deben especificar si el adaptador envía una notificación a los clientes de adaptador en cuanto se inicia el agente de escucha en el **NotifyOnListenerStart** propiedad de enlace.  
  
-   La notificación se envía a los clientes de adaptador como y cuando el conjunto de resultados de la instrucción SQL especificada en el **NotificationStatement** se cambia la propiedad de enlace.  
  
 Para obtener más información acerca de estas propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  
  
> [!NOTE]
>  La suscripción de notificación se confirma siempre, independientemente de si se confirma o revierte la transacción en el que se ejecutó la instrucción. Por lo tanto, la operación de notificación no puede garantizar que se ha cambiado el resultado de la consulta que se ha suscrito para la notificación. Por ejemplo, suponga que se insertan datos en una fila de tabla (suscrita para la notificación) en una transacción y se envía inmediatamente una notificación para el adaptador que informa sobre el cambio (inserción). Por algún motivo, la transacción se revierte y no se inserta realmente ningún dato en la fila de la tabla. Sin embargo, el servidor SQL Server no envía una notificación al adaptador sobre el revertir las transacciones. Para obtener información acerca de las notificaciones de consulta en SQL Server, vea [http://go.microsoft.com/fwlink/?LinkId=145367](http://go.microsoft.com/fwlink/?LinkId=145367).  
  
## <a name="differences-between-query-notification-and-polling"></a>Diferencias entre la notificación de consulta y sondeo  
 Aunque el sondeo y la notificación de consulta son ambas operaciones de entrada e informar a los clientes de adaptador acerca de los cambios de datos en la base de datos de SQL Server, la tabla siguiente enumeran algunas diferencias entre los dos. Las siguientes diferencias le ayudará a decidir sobre una operación según sus requisitos:  
  
|Notificación de consulta|Sondeo|  
|------------------------|-------------|  
|Notificación de consulta se inicia SQL Server. La instrucción de notificación emitida por el adaptador simplemente indica a la base de datos para iniciar la notificación en caso de que hay un cambio en el conjunto de resultados de la instrucción.|Sondeo se inicia el adaptador. El adaptador ejecuta una instrucción para validar si los datos están disponibles para el sondeo y, a continuación, inicia el sondeo mediante la ejecución de la instrucción de sondeo si algunos datos están disponibles para el sondeo.|  
|Puede usar la instrucción de notificación de consulta sólo para leer datos de una tabla de base de datos de SQL Server.|Puede usar la instrucción de sondeo para leer o actualizar datos en una tabla de base de datos de SQL Server.|  
|Notificación de consulta informa solo sobre el tipo de cambio en los datos, como Insert, Update y Delete.|Sondeo le informa sobre los datos reales que han cambiado.|  
|La notificación de cambio de datos es instantánea.|Depende de la notificación de cambio de datos en el intervalo de sondeo y los clientes de adaptador están informados sobre los cambios de datos al final de cada intervalo de sondeo. **Sugerencia:** sondeo puede proporcionar un mejor rendimiento en escenarios donde los cambios de datos se producen de forma continua y no desea recibir una notificación de cada cambio como y cuando esto ocurre. En su lugar, especifique un intervalo de sondeo después del cual desea recibir una notificación de todos los cambios que se han producido desde la última notificación de cambios.|  
  
 Para obtener más información acerca de las notificaciones de consulta en [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)], consulte [recibir las notificaciones de consulta de SQL por mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)