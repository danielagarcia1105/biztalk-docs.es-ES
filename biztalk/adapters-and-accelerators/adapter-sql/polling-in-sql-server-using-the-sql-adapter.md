---
title: Sondeo en SQL Server mediante el adaptador de SQL | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c31b3cda-c05e-46db-827b-6c47a53d1a3a
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d01bc3d004da60b98e0132aa3c8e04442a45426
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="polling-in-sql-server-using-the-sql-adapter"></a>Sondeo en SQL Server mediante el adaptador de SQL
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]permite a los clientes de adaptador recibir mensajes de cambio de datos de la base de datos de SQL Server. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] admite la recepción de mensajes "basada en sondeo" en el que el adaptador ejecuta una instrucción SQL especificada (instrucción SELECT o procedimiento almacenado), recupera o actualiza los datos y proporciona el resultado al cliente de adaptador a intervalos regulares de hora.  
  
 La [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expone las siguientes operaciones para el sondeo:  
  
-   **Sondeo**: le permite recibir mensajes de cambio de datos periódicos para SQL Server tablas o vistas. Los mensajes no son fuertemente tipada.  
  
-   **TypedPolling**: le permite recibir mensajes fuertemente tipada de la base de datos de SQL Server. Debe usar esta operación si va a asignar los elementos en el mensaje de sondeo para cualquier otro esquema.  
  
-   **XmlPolling**. Le permite utilizar las instrucciones SELECT o procedimientos almacenados que utilice una cláusula FOR XML y devuelvan los datos como mensajes XML. Esta operación devuelve el mensaje de sondeo como un mensaje XML.  
  
     Para obtener más información acerca de la cláusula FOR XML, vea [http://go.microsoft.com/fwlink/?LinkId=131402](http://go.microsoft.com/fwlink/?LinkId=131402).  
  
 Para obtener más información acerca del sondeo en el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [mensajes de datos cambiado basados en la recepción de sondeo de SQL Server mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md).  
  
## <a name="polling"></a>Sondeo  
 Una operación de sondeo típica mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] implica lo siguiente:  
  
1.  Deben especificar los clientes de adaptador `Polling` como la operación de entrada en el **InboundOperationType** propiedad de enlace. El valor predeterminado de esta propiedad de enlace es `Polling`.  
  
2.  Los clientes de adaptador deben especificar una instrucción SQL para la **PolledDataAvailableStatement** propiedad que determina si hay datos disponibles para el sondeo de enlace. La primera columna de la primera fila del primer conjunto de resultados devuelto al ejecutar esta instrucción contiene un valor entero. Si no hay ningún dato disponible para el sondeo, el valor devuelto es 0 (cero). Si hay datos disponibles, el valor devuelto es mayor que cero.  
  
3.  Los clientes de adaptador deben especificar un intervalo de sondeo para la **PollingIntervalInSeconds** enlace de propiedad para definir el intervalo en el que la instrucción en el **PolledDataAvailableStatement** enlace se ejecuta la propiedad. Al final de cada intervalo de sondeo, se ejecuta la instrucción disponibles datos extraídos y se devuelve el conjunto de resultados.  
  
4.  Los clientes de adaptador deben especificar una instrucción SQL de sondeo (instrucción SELECT o un procedimiento almacenado) para la **PollingStatement** propiedad de enlace. Si no hay datos disponibles para el sondeo (determinado por la **PolledDataAvailableStatement** propiedad de enlace), el adaptador ejecuta la instrucción de sondeo para obtener y actualizar (si procede) los datos en la base de datos de SQL Server. Cuando el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se utiliza con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], también se utiliza la misma transacción para enviar el mensaje a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
5.  Pueden usar los clientes de adaptador el **PollWhileDataFound** enlace de propiedad para omitir el intervalo de sondeo y los datos, un sondeo continuo como y cuando esté disponible.  
  
6.  Los conjuntos de resultados que se devuelven como resultado de ejecutar la instrucción de sondeo se envían al cliente de adaptador como el mensaje entrante.  
  
> [!NOTE]
>  Una operación XmlPolling implica los mismos pasos que la operación de sondeo.  
  
## <a name="strongly-typed-polling"></a>Sondeo fuertemente tipado  
 Una operación típica sondeo fuertemente tipado mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] implica lo siguiente:  
  
1.  Deben especificar los clientes de adaptador `TypedPolling` como la operación de entrada en el **InboundOperationType** propiedad de enlace. El valor predeterminado de esta propiedad de enlace es `Polling`.  
  
2.  Los clientes de adaptador deben especificar un Id. de entrada como parte del URI de conexión. El identificador de entrada puede ser cualquier cadena y se anexa al espacio de nombres estándar de la operación TypedPolling para evitar conflictos de espacio de nombres.  
  
3.  El resto de los pasos son los mismos que los pasos 2 a 6 aparece en la operación de sondeo se describe en la sección anterior.  
  
 Para obtener información detallada acerca de las propiedades de enlace relacionado con el sondeo y sondeo fuertemente tipado, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  
  
> [!NOTE]
>  Como resultado de ejecutar la instrucción de sondeo se pueden devolver varios conjuntos de resultados. Si los conjuntos de resultados no contiene ninguna fila, no hay mensajes se envían al cliente de adaptador.  
  
 La ilustración siguiente proporciona información sobre el flujo de trabajo de sondeo en [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Se ilustran dos escenarios para el flujo de trabajo de sondeo:  
  
1.  Cuando el valor de la **PollWhileDataFound** se establece en "False" (valor predeterminado).  
  
2.  Cuando el valor de la **PollWhileDataFound** está establecido en "True".  
  
 ![Flujo de trabajo de sondeo &#40; PollWhileDataFound &#61; False &#41; ] (../../adapters-and-accelerators/adapter-sql/media/15598c14-3a62-4b8d-90bf-84e004a386db.gif "15598c14-3a62-4b8d-90bf-84e004a386db") ![sondeo de flujo de trabajo &#40; PollWhileDataFound &#61; True &#41; ] (../../adapters-and-accelerators/adapter-sql/media/c20535be-ea45-4456-8b62-4d4585cb1d8c.gif "c20535be-ea45-4456-8b62-4d4585cb1d8c")  
  
## <a name="differences-between-polling-and-query-notification"></a>Diferencias entre el sondeo y la notificación de consulta  
 Aunque la notificación de sondeo y la consulta son ambas operaciones de entrada e informar a los clientes de adaptador acerca de los cambios de datos en la base de datos de SQL Server, la tabla siguiente enumeran algunas diferencias entre los dos. Las siguientes diferencias le ayudará a decidir sobre una operación según sus requisitos:  
  
|Sondeo|Notificación de consulta|  
|-------------|------------------------|  
|Sondeo se inicia el adaptador. El adaptador ejecuta una instrucción para validar si los datos están disponibles para el sondeo y, a continuación, inicia el sondeo mediante la ejecución de la instrucción de sondeo si algunos datos están disponibles para el sondeo.|Notificación de consulta se inicia SQL Server. La instrucción de notificación emitida por el adaptador simplemente indica a la base de datos para iniciar la notificación en caso de que hay un cambio en el conjunto de resultados de la instrucción.|  
|Puede usar la instrucción de sondeo para leer o actualizar datos en una tabla de base de datos de SQL Server.|Puede usar la instrucción de notificación de consulta sólo para leer datos de una tabla de base de datos de SQL Server.|  
|Sondeo le informa sobre los datos reales que han cambiado.|Notificación de consulta solo le informa sobre el tipo de cambio en los datos, como Insert, Update y Delete.|  
|Depende de la notificación de cambio de datos en el intervalo de sondeo y los clientes de adaptador están informados sobre los cambios de datos al final de cada intervalo de sondeo. **Sugerencia:** sondeo puede proporcionar un mejor rendimiento en escenarios donde los cambios de datos se producen de forma continua y no desea recibir una notificación de cada cambio como y cuando esto ocurre. En su lugar, especifique un intervalo de sondeo después del cual desea recibir una notificación de todos los cambios que se han producido desde la última notificación de cambio de datos.|La notificación de cambio de datos es instantánea.|  
  
 Para obtener más información acerca de las notificaciones de consulta en [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)], consulte [recibir las notificaciones de consulta de SQL por mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)