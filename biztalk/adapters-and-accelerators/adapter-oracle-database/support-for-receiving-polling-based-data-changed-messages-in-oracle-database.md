---
title: Soporte para recibir mensajes de cambio de datos basados en el sondeo en base de datos de Oracle | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- notifications, polling-based
- post-polling
- POLLINGSTMT
- polling interval
- polling
ms.assetid: 9ff29d3f-ebb1-4d82-9106-150f939cbd9e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d8a29901672ba11f3ac48220f7096b2c355fc2e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="support-for-receiving-polling-based-data-changed-messages-in-oracle-database"></a>Soporte para recibir mensajes de cambio de datos basados en el sondeo en base de datos de Oracle
El[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] permite a los programas de cliente recibir mensajes de la base de datos de Oracle que les informa de los cambios en los datos almacenados en una base de datos de Oracle. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite la recepción de mensajes "basada en sondeo" en el que el adaptador ejecuta una consulta SELECT especificado, procedimiento almacenado, función o procedimiento o función dentro de un paquete, recupera los datos y proporciona el resultado al cliente en normal intervalos de tiempo. Para habilitar esto, la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone una operación POLLINGSTMT. Además, todos los procedimientos almacenados, funciones y procedimientos y función de los paquetes se exponen como operaciones entrantes para el sondeo.  
  
 El adaptador proporciona dos maneras de sondeo de la base de datos de Oracle:  
  
-   **Utilizar las instrucciones SELECT**. Puede especificar una instrucción SELECT simple para sondear las tablas y vistas en la base de datos de Oracle. El adaptador ejecuta la instrucción SELECT a los intervalos especificados y devuelve el resultado a los clientes de adaptador.  
  
-   **Usar procedimientos almacenados, funciones o procedimientos o funciones dentro de un paquete**. Puede especificar un procedimiento almacenado, función o procedimiento o función dentro de un paquete para sondear la base de datos de Oracle. El adaptador ejecuta el mensaje de solicitud a los intervalos especificados y devuelve el resultado a los clientes de adaptador.  
  
## <a name="polling-operation-workflow"></a>Flujo de trabajo de operación de sondeo  
 Una operación de sondeo típica mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] implica lo siguiente:  
  
1.  Deben especificar los clientes de adaptador **sondeo** como la operación de entrada en el **InboundOperationType** propiedad de enlace. El valor predeterminado de esta propiedad de enlace es **sondeo**.  
  
2.  Los clientes de adaptador deben especificar una instrucción SELECT para la **PolledDataAvailableStatement** propiedad para determinar si hay datos disponibles para el sondeo de enlace. En la ejecución de esta instrucción, si la primera columna de la primera fila del conjunto de resultados devuelto contiene un valor entero positivo, hay fecha disponible para el sondeo. De forma predeterminada, el valor de esta propiedad de enlace se establece en `Select 1 FROM DUAL`, lo cual implica que el adaptador debe continuar sondeo independientemente de si la tabla se sondean, tiene datos o no.  
  
3.  Los clientes de adaptador deben especificar un intervalo de sondeo para la **PollingInterval** enlace de propiedad para definir el intervalo en segundos en el que la instrucción especificada en el **PolledDataAvailableStatement** se ejecuta la propiedad de enlace. Al final de cada intervalo de sondeo, se ejecuta la instrucción disponibles datos extraídos y se devuelve el conjunto de resultados.  
  
4.  Los clientes de adaptador deben especificar una instrucción SELECT o un procedimiento almacenado para el **PollingStatement** propiedad de enlace.  
  
    -   Si desea sondear una tabla o vista, debe especificar una consulta SELECT en esta propiedad de enlace.  
  
    -   Si desea sondear mediante un procedimiento almacenado, función o procedimiento o función dentro de un paquete, debe especificar el mensaje de solicitud completo para la operación respectiva en esta propiedad de enlace.  
  
     La instrucción en el **PollingStatement** propiedad de enlace se ejecuta sólo si hay datos disponibles para el sondeo, que viene determinado por la **PolledDataAvailableStatement** propiedad de enlace en el paso 1.  
  
5.  Los clientes de adaptador deben especificar una acción para la operación de sondeo en el **PollingAction** propiedad de enlace. La acción de sondeo para una operación específica se determina a partir de los metadatos generados para la operación utilizando el complemento Consume Adapter Service.  
  
    > [!NOTE]
    >  Si se sondear una tabla o vista mediante una instrucción SELECT en la **PollingStatement** propiedad de enlace, no es necesario especificar ningún valor para el **PollingAction** propiedad de enlace. El valor predeterminado valor Null, se pasa en este caso.  
  
6.  Pueden usar los clientes de adaptador el **PollWhileDataFound** enlace de propiedad para omitir el intervalo de sondeo y los datos, un sondeo continuo como y cuando esté disponible.  
  
    > [!IMPORTANT]
    >  Si establece el valor de la **PollWhileDataFound** propiedad de enlace en True, los clientes de adaptador un sondeo continuo de datos de Oracle y en el proceso de abrir y cerrar las conexiones a la base de datos de Oracle en un bucle. Como la velocidad a la que se abren las conexiones por ODP.NET es mayor que las conexiones que se va a cerrar, las conexiones agotarse más tarde y se produce una excepción. Como una solución alternativa, asegúrese de que el valor de la **UseOracleConnectionPool** está establecida en True, y un valor adecuado se menciona en la **IncrPoolSize** enlace de propiedad para controlar el número de conexiones que se puede abrir los clientes de adaptador.  
  
7.  Los clientes de adaptador pueden especificar una instrucción posterior a la encuesta, un bloque de PL/SQL de Oracle, para la **PostPollStatement** propiedad de enlace. La instrucción especificada en esta propiedad de enlace se ejecuta después de la instrucción especificada en el **PollingStatement** propiedad de enlace se ejecuta.  
  
 El adaptador encapsula la instrucción de sondeo y la instrucción de sondeo posterior a la de una transacción y el valor de tiempo de espera de la transacción se establece como el valor especificado para la **PollingInterval** propiedad de enlace. Por lo tanto, es fundamental para especificar un valor de tiempo de espera que sea mayor o igual que el tiempo necesario para procesar el mensaje entrante y enviar una respuesta. Si el tiempo que tarda el programa de cliente para consumir el mensaje o ejecutar la consulta de sondeo posterior es mayor que el valor de tiempo de espera, se revierte la transacción. Si el tiempo necesario es menor que el valor de tiempo de espera, el adaptador confirma la transacción y "suspensión" durante el tiempo restante en el sondeo antes de realizar el siguiente sondeo.  
  
 El adaptador suprime cualquier respuesta de sondeo vacío procedentes de la base de datos de Oracle.  
  
## <a name="differences-between-polling-and-notification"></a>Diferencias entre el sondeo y la notificación  
 Aunque sondeo y la notificación son dos operaciones de entrada e informar a los clientes de adaptador acerca de los cambios de datos en la base de datos de Oracle, la tabla siguiente muestra algunas diferencias entre los dos. Las siguientes diferencias le ayudará a decidir sobre una operación según sus requisitos:  
  
|Sondeo|Notification|  
|-------------|------------------|  
|Sondeo es compatible con todas las versiones de la base de datos de Oracle que son compatibles con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].|La notificación es compatible únicamente para versiones de base de datos de Oracle 10.2 y posteriores.|  
|Se puede configurar el intervalo de sondeo para comprobar los datos disponibles para el sondeo a intervalos regulares o instantáneamente como y cuando los datos están disponibles. **Sugerencia:** sondeo puede proporcionar un mejor rendimiento en escenarios donde los cambios de datos se producen de forma continua y no desea recibir una notificación de cada cambio como y cuando esto ocurre. En su lugar, especifique un intervalo de sondeo después del cual desea recibir una notificación de todos los cambios que se han producido desde la última notificación de cambios.|La notificación de cambio de datos siempre es instantánea.|  
|Sondeo se inicia el adaptador. El adaptador ejecuta una instrucción SQL para validar si los datos están disponibles para el sondeo y, a continuación, inicia el sondeo mediante la ejecución de la instrucción de sondeo si algunos datos están disponibles para el sondeo.|Se inicia la notificación de la base de datos de Oracle. La instrucción de notificación emitida por el adaptador simplemente indica a la base de datos para iniciar la notificación en caso de que hay un cambio en el conjunto de resultados de la instrucción. Notificación es una característica de la base de datos de Oracle.|  
|Puede usar la instrucción de sondeo para leer o actualizar datos en la base de datos de Oracle.|Puede usar la instrucción de notificación sólo para leer datos en una base de datos de Oracle.|  
|Sondeo le informa sobre los datos reales que han cambiado.|Notificación informa solo sobre el tipo de cambio en los datos, como Insert, Update y Delete.|  
  
 Para obtener más información acerca de:  
  
-   Cómo el adaptador admite la recepción de mensajes de sondeo de base de datos de Oracle, vea [recibir mensajes de cambio de datos basado en sondeo](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md).  
  
-   Recibir mensajes de sondeo de base de datos de Oracle mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [invocar funciones y procedimientos de la base de datos de Oracle mediante Biztalk Server](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-biztalk-server.md).  
  
-   Recibir mensajes de sondeo de base de datos de Oracle mediante el modelo de servicio WCF, vea [mensajes de datos cambiado basados en la recepción de sondeo de SQL Server mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-channel.md).  
  
-   Recibir mensajes de sondeo de base de datos de Oracle utilizando el modelo del canal WCF, vea [mensajes de datos cambiado basados en la recepción de sondeo de SQL Server mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-channel.md).  
  
-   Estructura y acciones de SOAP para realizar una consulta de sondeo de mensajes, vea [esquemas de mensaje para las operaciones de sondeo](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-polling-operations2.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)