---
title: Recibir notificaciones de cambio de base de datos de Oracle | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ffabf27-7223-4473-b33e-af6f2990cb96
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d1c33ef7bacf96a152d4b02d0c8c08991f96d64
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-oracle-database-change-notifications"></a>Recibir notificaciones de cambio de base de datos de Oracle
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] es compatible con la característica de notificación de cambio de base de datos de ODP.NET. Con esta característica, los clientes de adaptador pueden registrar una instrucción SELECT como las notificaciones de consulta en la base de datos y la base de datos envía una notificación al cliente de adaptador como y cuando el conjunto de resultados de los cambios de la instrucción SELECT. La notificación de cambio de la base de datos se implementa en el adaptador mediante la clase OracleDependency. Para obtener más información acerca de la característica de compatibilidad del cambio de base de datos de ODP.NET y la clase OracleDependency, consulte [http://go.microsoft.com/fwlink/?LinkId=124801](http://go.microsoft.com/fwlink/?LinkId=124801).  
  
 La [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone una operación de entrada, una notificación, para admitir la notificación de cambio de base de datos. Sin embargo, para la base de datos de notificación de cambio de trabajar con [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], debe asegurarse de lo siguiente:  
  
-   Conectarse a la base de datos de Oracle con la versión de base de datos de Oracle subyacente 10,2 o una versión posterior. Las versiones de la base de datos de Oracle anteriores 10.2 no son compatibles con las notificaciones.  
  
-   Conectarse a la base de datos de Oracle como un usuario que tiene el privilegio de notificación de cambio para crear un registro de notificaciones. Para conceder el privilegio de notificación de cambio a un usuario, conectarse a la base de datos de Oracle como un usuario con privilegios de administrador y ejecute el siguiente comando en el símbolo del sistema SQL:  
  
    ```  
    grant change notification to <user name>  
    ```  
  
-   Decida en un puerto TCP que puede utilizarse por ODP.NET para recibir notificaciones de cambio de base de datos de base de datos de Oracle. Agregue el puerto TCP a la lista de excepciones de Firewall de Windows. Para obtener instrucciones sobre cómo agregar puertos a la lista de excepciones de Firewall de Windows, vea [http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959). Debe proporcionar el mismo número de puerto TCP para la **NotificationPort** propiedad de enlace. Para obtener más información acerca de la propiedad de enlace, vea [trabajar con propiedades de enlace](https://msdn.microsoft.com/library/dd788467.aspx).  
  
 Cambiar de una base de datos típica notificación mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] implica lo siguiente:  
  
1.  Deben especificar los clientes de adaptador `Notification` como la operación de entrada en el **InboundOperationType** propiedad de enlace. El valor predeterminado de esta propiedad de enlace es el sondeo.  
  
2.  Los clientes de adaptador deben especificar una instrucción SELECT de SQL para registrar las notificaciones de cambio de base de datos en el **NotificationStatement** propiedad de enlace. El cliente de adaptador recibe una notificación de base de datos de Oracle como y cuando el conjunto de resultados para que los cambios de instrucción SQL especificados.  
  
3.  Los clientes de adaptador deben especificar si el adaptador envía una notificación a los clientes de adaptador en cuanto se inicia el agente de escucha en el **NotifyOnListenerStart** propiedad de enlace.  
  
4.  La notificación se envía a los clientes de adaptador como y cuando el conjunto de resultados de la instrucción SELECT especificada en el **NotificationStatement** se cambia la propiedad de enlace.  
  
> [!CAUTION]
>  Si se produce una interrupción de red entre la base de datos de Oracle y el cliente de adaptador, las notificaciones no se enviará a los clientes de adaptador para que los cambios que realice en la base de datos de Oracle durante el período de interrupción de red y a partir de ahí. Por lo tanto, debe utilizar la operación de sondeo en lugar de la operación de notificación de escenarios críticos.  
  
## <a name="differences-between-notification-and-polling"></a>Diferencias entre la notificación y sondeo  
 Aunque notificación y sondeo sean ambas operaciones entrantes e informar a los clientes de adaptador acerca de los cambios de datos en la base de datos de Oracle, la tabla siguiente muestra algunas diferencias entre los dos. Las siguientes diferencias le ayudará a decidir sobre una operación según sus requisitos:  
  
|Notification|Sondeo|  
|------------------|-------------|  
|La notificación es compatible únicamente para versiones de base de datos de Oracle 10.2 y posteriores.|Sondeo es compatible con todas las versiones de la base de datos de Oracle que son compatibles con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].|  
|La notificación de cambio de datos siempre es instantánea.|Se puede configurar el intervalo de sondeo para comprobar los datos disponibles para el sondeo a intervalos regulares o instantáneamente como y cuando los datos están disponibles. **Sugerencia:** sondeo puede proporcionar un mejor rendimiento en escenarios donde los cambios de datos se producen de forma continua y no desea recibir una notificación de cada cambio como y cuando esto ocurre. En su lugar, especifique un intervalo de sondeo después del cual desea recibir una notificación de todos los cambios que se han producido desde la última notificación de cambios.|  
|Se inicia la notificación de la base de datos de Oracle. La instrucción de notificación emitida por el adaptador simplemente indica a la base de datos para iniciar la notificación en caso de que hay un cambio en el conjunto de resultados de la instrucción. Notificación es una característica de la base de datos de Oracle.|Sondeo se inicia el adaptador. El adaptador ejecuta una instrucción SQL para validar si los datos están disponibles para el sondeo y, a continuación, inicia el sondeo mediante la ejecución de la instrucción de sondeo si algunos datos están disponibles para el sondeo.|  
|Puede usar la instrucción de notificación sólo para leer datos en una base de datos de Oracle.|Puede usar la instrucción de sondeo para leer o actualizar datos en la base de datos de Oracle.|  
|Notificación informa solo sobre el tipo de cambio en los datos, como Insert, Update y Delete.|Sondeo le informa sobre los datos reales que han cambiado.|  
  
 Para obtener más información acerca de:  
  
-   Las propiedades de enlace relacionada con la operación de notificación, consulte [trabajar con propiedades de enlace](https://msdn.microsoft.com/library/dd788467.aspx).  
  
-   Cómo utilizar la operación de notificación en [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [recibir Oracle base de datos modificados notificaciones mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)