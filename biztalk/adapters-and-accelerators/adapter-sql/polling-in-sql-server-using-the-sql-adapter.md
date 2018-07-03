---
title: Sondeo de SQL Server con el adaptador de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c31b3cda-c05e-46db-827b-6c47a53d1a3a
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73bb47bfd631576fe992ef072eee8ff3ff5ba5bf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967133"
---
# <a name="polling-in-sql-server-using-the-sql-adapter"></a>Sondeo de SQL Server con el adaptador de SQL
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] permite a los clientes del adaptador recibir mensajes de cambio de datos de la base de datos de SQL Server. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] admite la recepción de mensajes "basados en sondeos" en la que el adaptador ejecuta una instrucción SQL especificada (instrucción SELECT o procedimiento almacenado), recupera o actualiza los datos y proporciona el resultado al cliente de adaptador a intervalos regulares de tiempo.  
  
 La [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expone las siguientes operaciones para el sondeo:  
  
- **Sondeo**: le permite recibir mensajes de cambio de datos periódica o vistas de tablas de SQL Server. Los mensajes no son fuertemente tipada.  
  
- **TypedPolling**: le permite recibir mensajes fuertemente tipada de la base de datos de SQL Server. Debe usar esta operación si va a asignar los elementos en el mensaje de sondeo a cualquier otro esquema.  
  
- **XmlPolling**. Le permite usar las instrucciones SELECT o procedimientos almacenados que utilizan una cláusula FOR XML y devuelvan los datos como los mensajes XML. Esta operación devuelve el mensaje de sondeo como un mensaje XML.  
  
   Para obtener más información acerca de la cláusula FOR XML, vea [ http://go.microsoft.com/fwlink/?LinkId=131402 ](http://go.microsoft.com/fwlink/?LinkId=131402).  
  
  Para obtener más información acerca del sondeo en el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [basado en sondeo recibe mensajes de cambio de datos desde SQL Server mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md).  
  
## <a name="polling"></a>Sondeo  
 Una operación de sondeo típico mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] implica lo siguiente:  
  
1. Deben especificar los clientes del adaptador `Polling` como la operación de entrada en el **InboundOperationType** enlaza la propiedad. El valor predeterminado para esta propiedad de enlace es `Polling`.  
  
2. Los clientes del adaptador deben especificar una instrucción SQL para la **PolledDataAvailableStatement** enlaza la propiedad que determina si hay datos disponibles para el sondeo. La primera columna de la primera fila del primer conjunto de resultados devuelto al ejecutar esta instrucción contiene un valor entero. Si no hay ningún dato disponible para el sondeo, el valor devuelto es 0 (cero). Si hay datos disponibles, el valor devuelto es mayor que cero.  
  
3. Los clientes del adaptador deben especificar un intervalo de sondeo para el **PollingIntervalInSeconds** enlace de propiedad para definir el intervalo en el que la instrucción en el **PolledDataAvailableStatement** enlace se ejecuta la propiedad. Al final de cada intervalo de sondeo, se ejecuta la instrucción disponibles datos extraídos y se devuelve el conjunto de resultados.  
  
4. Los clientes del adaptador deben especificar una instrucción SQL de sondeo (procedimiento almacenado o instrucción SELECT) para el **PollingStatement** enlaza la propiedad. Si hay datos disponibles para el sondeo (determinado por la **PolledDataAvailableStatement** propiedad de enlace), el adaptador ejecuta la instrucción de sondeo para obtener y actualizar (si procede) los datos en la base de datos de SQL Server. Cuando el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se usa con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], también se usa la misma transacción para enviar el mensaje a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
5. Los clientes del adaptador pueden usar el **PollWhileDataFound** enlaza la propiedad para omitir el intervalo de sondeo y datos, un sondeo continuo como y cuando esté disponible.  
  
6. Los conjuntos de resultados se devuelven como resultado de ejecutar la instrucción de sondeo se envían al cliente de adaptador que el mensaje entrante.  
  
> [!NOTE]
>  La operación XmlPolling implica los mismos pasos que la operación de sondeo.  
  
## <a name="strongly-typed-polling"></a>Sondeo fuertemente tipado  
 Una operación típica sondeo fuertemente tipado mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] implica lo siguiente:  
  
1. Deben especificar los clientes del adaptador `TypedPolling` como la operación de entrada en el **InboundOperationType** enlaza la propiedad. El valor predeterminado para esta propiedad de enlace es `Polling`.  
  
2. Los clientes del adaptador deben especificar un Id. de entrada como parte de la URI de conexión. El Id. de entrada puede ser cualquier cadena y se anexa al espacio de nombres estándar de la operación TypedPolling para evitar conflictos de espacio de nombres.  
  
3. El resto de los pasos son los mismos que los pasos 2 a 6 aparece en la operación de sondeo se describe en la sección anterior.  
  
   Para obtener información detallada acerca de las propiedades de enlace relacionadas con el sondeo y sondeo fuertemente tipado, vea [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  
  
> [!NOTE]
>  Como resultado de ejecutar la instrucción de sondeo se pueden devolver varios conjuntos de resultados. Si los conjuntos de resultados no contiene ninguna fila, no hay mensajes se envían al cliente de adaptador.  
  
 La ilustración siguiente proporciona información sobre el flujo de trabajo de sondeo en [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Se muestran dos escenarios para el flujo de trabajo de sondeo:  
  
1. Cuando el valor de la **PollWhileDataFound** está establecido en "False" (valor predeterminado).  
  
2. Cuando el valor de la **PollWhileDataFound** está establecido en "True".  
  
   ![Flujo de trabajo de sondeo &#40;PollWhileDataFound &#61; False&#41;](../../adapters-and-accelerators/adapter-sql/media/15598c14-3a62-4b8d-90bf-84e004a386db.gif "15598c14-3a62-4b8d-90bf-84e004a386db") ![flujo de trabajo de sondeo &#40;PollWhileDataFound &#61; True&#41; ] (../../adapters-and-accelerators/adapter-sql/media/c20535be-ea45-4456-8b62-4d4585cb1d8c.gif "c20535be-ea45-4456-8b62-4d4585cb1d8c")  
  
## <a name="differences-between-polling-and-query-notification"></a>Diferencias entre el sondeo y la notificación de consulta  
 Aunque la notificación de sondeo y la consulta son ambas operaciones de entrada e informar a los clientes del adaptador acerca de los cambios de datos en la base de datos de SQL Server, en la tabla siguiente se enumera algunas diferencias entre los dos. Las siguientes diferencias le ayudará a decidirse por una operación según sus requisitos:  
  
|Sondeo|Notificación de consulta|  
|-------------|------------------------|  
|Sondeo es iniciado por el adaptador. El adaptador ejecuta una instrucción para validar si los datos está disponibles para el sondeo y, a continuación, inicia el sondeo al ejecutar la instrucción de sondeo si algunos datos están disponibles para el sondeo.|Notificación de consulta se inicia SQL Server. La instrucción de notificación emitida el adaptador simplemente indica a la base de datos para iniciar la notificación en caso de que hay un cambio en el conjunto de resultados de la instrucción.|  
|Puede usar la instrucción de sondeo para leer o actualizar datos en una tabla de base de datos de SQL Server.|Puede usar la instrucción de notificación de consulta sólo para leer datos de una tabla de base de datos de SQL Server.|  
|Sondeo le informa sobre los datos reales que han cambiado.|Notificación de consulta solo se informa sobre el tipo de cambio en los datos, como Insert, Update y Delete.|  
|El intervalo de sondeo depende de la notificación de cambio de datos y los clientes del adaptador se informaren sobre los cambios de datos al final de cada intervalo de sondeo. **Sugerencia:** sondeo puede ofrecerle un mejor rendimiento en escenarios donde los cambios de datos se producen de forma continua, y no desea recibir una notificación de cada cambio como y cuando ocurre. En su lugar, especifique un intervalo de sondeo después del cual desea recibir una notificación de todos los cambios que se han producido desde la última notificación de cambio de datos.|La notificación de cambio de datos es instantánea.|  
  
 Para obtener más información acerca de la notificación de consulta en [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)], consulte [recibir notificaciones de consulta SQL que utiliza BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)