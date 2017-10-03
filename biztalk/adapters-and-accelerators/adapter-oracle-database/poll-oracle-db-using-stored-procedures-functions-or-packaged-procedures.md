---
title: Sondear la base de datos de Oracle mediante procedimientos almacenados, funciones, o empaquetados procedimientos y funciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c34843a-d02b-4941-baf6-6bc80b5821ad
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0646f1c447cfc4949edafe94d634a6c651083307
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="poll-oracle-database-using-stored-procedures-functions-or-packaged-procedures-and-functions"></a>Sondeo de base de datos de Oracle mediante procedimientos almacenados, funciones, o empaquetados procedimientos y funciones
Puede configurar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para recibir mensajes de cambio de datos periódicas mediante el uso de procedimientos almacenados, funciones, o empaquetados procedimientos y funciones que éstos sondeen periódicamente la base de datos de Oracle. Puede especificar un procedimiento almacenado, función o procedimiento empaquetada y funcionar como una instrucción de sondeo que el adaptador se ejecuta periódicamente para sondear la base de datos de Oracle.  
  
 Para habilitar esta opción, debe especificar ciertas propiedades de enlace en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. También puede modificar el espacio de nombres de destino para la operación POLLINGSTMT estableciendo la **PollingId** propiedad en el URI de conexión. Para obtener más información, consulte [compatibilidad para mensajes de cambio de datos basados en la recepción de sondeo en base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/support-for-receiving-polling-based-data-changed-messages-in-oracle-database.md) y [recibir mensajes de cambio de datos basado en sondeo en el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md). Para obtener información acerca de la estructura del mensaje SOAP para las operaciones de sondeo, consulte [esquemas de mensaje para las operaciones de sondeo](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-polling-operations2.md).  
  
## <a name="configuring-a-polling-operation-with-oracle-database-adapter-binding-properties"></a>Configuración de una operación de sondeo con propiedades de enlace de adaptador de base de datos de Oracle  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] se ejecuta la consulta de sondeo y cualquier bloque de código de PL/SQL posterior a la encuesta dentro de una transacción. La siguiente tabla resume los [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] mensajes de cambio de propiedades de enlace que se utiliza para configurar el adaptador para recibir datos. Debe especificar el puerto de recepción de estas propiedades de enlace al configurar el WCF-Custom o WCF-OracleDB la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
|Propiedad de enlace|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|Especifica si desea realizar el sondeo o la notificación operación entrante. Valor predeterminado es **sondeo**.|  
|**PolledDataAvailableStatement**|Especifica la instrucción SQL que se ejecuta el adaptador para determinar si los datos están disponibles para el sondeo. Sólo si hay un registro, el procedimiento almacenado que especificó para la **PollingStatement** se va a ejecutar la propiedad de enlace.|  
|**PollingInterval**|Especifica el intervalo, en segundos, en el que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] se ejecuta la instrucción especificada para la **PolledDataAvailableStatement** propiedad de enlace. El valor predeterminado es 500 segundos. El intervalo de sondeo determina el intervalo de tiempo entre sondeos sucesivos. Si la instrucción se ejecuta en el intervalo especificado, el adaptador se suspende durante el tiempo restante en el intervalo. El valor predeterminado es `SELECT 1 FROM DUAL`, lo cual implica que el adaptador debe continuar sondeo independientemente de si la tabla se sondean, tiene datos o no.|  
|**PollingStatement**|Especifica la instrucción de sondeo. Para sondear mediante un procedimiento almacenado, función o procedimiento empaquetada o función, debe especificar el mensaje de solicitud completo para la operación respectiva en esta propiedad de enlace. El mensaje de solicitud debe ser el mismo que envíe al adaptador para invocar las operaciones respectivas como una operación de salida. El valor predeterminado es null.<br /><br /> Debe especificar un valor para **PollingStatement** propiedad para habilitar el sondeo de enlace. Se ejecuta la instrucción de sondeo solo si hay datos disponibles para el sondeo, que viene determinado por la **PolledDataAvailableStatement** propiedad de enlace.|  
|**PollingAction**|Especifica la acción para la operación de sondeo. Puede determinar la acción de sondeo para una operación específica de los metadatos que se ha generado para la operación con el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].|  
|**PostPollStatement**|Especifica un bloque de instrucciones que se ejecuta después de la instrucción especificada por el **PollingStatement** propiedad de enlace se ejecuta.|  
|**PollWhileDataFound**|Especifica si el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] pasa por alto el intervalo de sondeo y ejecuta continuamente la instrucción de sondeo, si los datos están disponibles en la tabla que se va a sondear. Si no hay datos disponibles en la tabla, el adaptador vuelve para ejecutar la instrucción de sondeo en el intervalo de sondeo especificado. El valor predeterminado es False.|  
  
 Para obtener una descripción más completa de estas propiedades, vea [leer acerca de las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md). Para obtener una descripción completa de cómo usar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para sondear la base de datos de Oracle, seguir leyendo.  
  
## <a name="how-this-topic-demonstrates-polling"></a>Cómo este tema muestra el sondeo  
 Este tema muestra cómo puede sondear la base de datos de Oracle mediante un procedimiento almacenado. Cree un proyecto de BizTalk y genere el esquema para el procedimiento almacenado que desea usar para sondear la base de datos de Oracle. En este tema, usamos el procedimiento almacenado de GET_ACTIVITYS para sondear la tabla ACCOUNTACTIVITY. Este procedimiento almacenado está disponible con el paquete ACCOUNT_PKG en el esquema SCOTT. Puede ejecutar los scripts SQL que se proporciona con los ejemplos para crear estos objetos en la base de datos.  
  
> [!NOTE]
>  La orquestación en este sondeos de tema la ACCOUNTACTIVITY de tabla, que es una tabla de base de datos creada mediante la ejecución de las secuencias de comandos que se proporciona con los ejemplos. Debe realizar procesos similares, como se describe en este tema para sondear cualquier otra tabla.  
  
 Para mostrar una operación de sondeo, llevamos a cabo lo siguiente:  
  
-   Especifique una instrucción SELECT para la **PolledDataAvailableStatement** propiedad para determinar donde la tabla se sondea, (ACCOUNTACTIVITY) de enlace tiene los datos. En este ejemplo, puede establecer esta propiedad de enlace como:  
  
    ```  
    SELECT COUNT (*) FROM ACCOUNTACTIVITY  
    ```  
  
     Esto garantiza que el adaptador ejecuta la instrucción de sondeo solo cuando la tabla ACCOUNTACTIVITY tiene algunos registros.  
  
-   Ejecutar un procedimiento almacenado, GET_ACTIVITYS, proporcionando el mensaje de solicitud como parte de la **PollingStatement** propiedad de enlace. Este procedimiento almacenado recuperará todas las filas de la tabla ACCOUNTACTIVITY y aparecerá un mensaje de respuesta desde el adaptador.  
  
-   EJECUTAR un bloque de PL/SQL como parte de la **PostPollStatement** propiedad de enlace. Esta instrucción moverá todos los datos de tabla ACCOUNTACTIVITY a otra tabla en la base de datos. Una vez que esto ocurre, la próxima vez que **PollingStatement** será ejecuta, no capturará los datos y, por tanto, el procedimiento almacenado de GET_ACTIVITYS devolverá un mensaje de respuesta vacío.  
  
-   Hasta que se agregan más datos a la tabla ACCOUNTACTIVITY, se seguirá pudiendo obtener mensajes de respuesta vacío. Por lo tanto, debe volver a rellenar la tabla ACCOUNTACTIVITY con nuevos registros. Puede hacerlo ejecutando el script more_activity_data.sql proporcionado con los ejemplos. Después de ejecutar este script, la siguiente operación de sondeo capturará los nuevos registros que se insertan en la tabla.  
  
## <a name="how-to-receive-data-change-messages-from-oracle"></a>Cómo recibir mensajes de cambio de datos de Oracle  
 Realizar una operación en la base de datos de Oracle mediante [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica las siguientes tareas de procedimientos descritas en [bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md). Para configurar el adaptador para sondear la base de datos de Oracle mediante un procedimiento almacenado:  
  
1.  Crear un proyecto de BizTalk y genere el esquema para el procedimiento almacenado que desea usar para el sondeo.  
  
2.  Cree un mensaje en el proyecto de BizTalk para recibir mensajes de la base de datos de Oracle.  
  
3.  Crear una orquestación para recibir mensajes de la base de datos de Oracle y guardarlos en una carpeta.  
  
4.  Compilar e implementar el proyecto de BizTalk.  
  
5.  Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
    > [!IMPORTANT]
    >  Para escenarios de entrada de sondeo siempre debe configurar un puerto de recepción unidireccional. Bidireccional de recepción no se admiten los puertos para las operaciones de entrada.  
  
6.  Inicie la aplicación de BizTalk.  
  
 Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="generating-schema"></a>Generar el esquema  
 Debe generar el esquema para la operación de GET_ACTIVITYS. Realizar las tareas siguientes al generar el esquema mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
-   Seleccione el tipo de contrato **(operación de entrada) de servicio**.  
  
-   Genere el esquema para el **GET_ACTIVITYS** procedimiento.  
  
 Para obtener más información sobre cómo generar el esquema, consulte [exploración, búsqueda y metadatos de get para las operaciones de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/browse-search-and-get-metadata-for-oracle-database-operations.md).  
  
## <a name="defining-messages-and-message-types"></a>Definición de mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes en la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Una vez que se genera el esquema, debe vincular a los mensajes desde la vista de orquestación de BizTalk del proyecto.  
  
 De este tema, debe crear un mensaje para recibir mensajes de Oracle.  
  
 Realice los pasos siguientes para crear mensajes y vincularlas a esquema.  
  
#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vincular al esquema  
  
1.  Agregar una orquestación al proyecto de BizTalk. En el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**. Escriba un nombre para la orquestación de BizTalk y, a continuación, haga clic en **agregar**.  
  
2.  Abra la ventana de vista de orquestación de BizTalk del proyecto, si no está ya abierto. Haga clic en **vista**, seleccione **otras ventanas**y, a continuación, haga clic en **Vista orquestación**.  
  
3.  En el **Vista orquestación**, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
4.  Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  
  
5.  En el **propiedades** panel para **Message_1**, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo de **recibir**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *Polling.OracleEBSBindingSchema*, donde *sondeo* es el nombre de su proyecto de BizTalk. *OracleEBSBindingSchema* es el esquema de respuesta generado para el **GET_ACTIVITYS** procedimiento almacenado.<br /><br /> **Importante:** porque sondeo es una operación unidireccional, el esquema generado por el adaptador no contiene un nodo de respuesta y, por lo tanto, hay solo un nodo raíz en el esquema. Si utiliza estos esquemas para un tipo de mensaje, debe identificar el esquema por el nombre de archivo del esquema generado.<br /><br /> Por ejemplo, si crea el esquema para una operación bidireccional, los nodos en el esquema de archivo con un nombre `OracleEBSBindingSchema` puede ser similar a "Solicitud" y "Respuesta". Si desea crear un mensaje en la orquestación que se asigna al esquema de solicitud, puede identificar el esquema en la lista, busque `OracleEBSBindingSchema.Request`. Sin embargo, en el caso de la operación de sondeo, dado que el único nodo es "Sondeo", no resulta sencillo identificar el esquema que desea asignar a porque esquemas con nodos únicos no se muestran como \<schemafilename >.\< rootnodename >. En su lugar, estos esquemas se enumeran por solo el nombre de archivo. En tal caso, la única manera de identificar el esquema es por el nombre de archivo de esquema, por ejemplo, OracleEBSBindingSchema.|  
  
     El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] esquema se genera para las operaciones entrantes y salientes para el GET_ACTIVITYS de procedimiento almacenan. Debe usar el esquema para que la operación de entrada:  
  
    -   Asignar el mensaje que se crea como parte de la orquestación.  
  
    -   Para recuperar la acción que se debe especificar para la **PollingAction** propiedad de enlace en tiempo de ejecución.  
  
     Debe usar el esquema para la operación de salida para obtener el mensaje de solicitud que se debe especificar como parte de la **PollingStatement** propiedad de enlace.  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para usar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para recibir mensajes de cambio de datos basado en sondeo de Oracle. En esta orquestación, el adaptador recibe la respuesta al ejecutar el procedimiento almacenado para el que especificó el mensaje de solicitud como parte de la **PollingStatement** propiedad de enlace. El mensaje de respuesta para el procedimiento almacenado se guarda en una ubicación de archivo. Contendría una orquestación típica para el sondeo de base de datos de Oracle:  
  
-   Recepción y envío formas a fin de recibir mensajes de Oracle y enviar a un puerto de archivo, respectivamente.  
  
-   Un unidireccional puerto de recepción para recibir mensajes de la base de datos de Oracle.  
  
    > [!IMPORTANT]
    >  Para escenarios de entrada de sondeo siempre debe configurar un puerto de recepción unidireccional. Bidireccional de recepción no se admiten los puertos para las operaciones de entrada.  
  
-   Un puerto de envío unidireccional para enviar las respuestas de sondeo de base de datos de Oracle.  
  
 Una orquestación de ejemplo es similar al siguiente.  
  
 ![Orquestación para una consulta de sondeo para Oracle](../../adapters-and-accelerators/adapter-oracle-database/media/6eddfe32-bfd0-4bd9-9e2a-fb4a7d0b53e3.gif "6eddfe32-bfd0-4bd9-9e2a-fb4a7d0b53e3")  
  
### <a name="adding-message-shapes"></a>Agregar formas de mensaje  
 Asegúrese de que especifique las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación just-mencionado.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-Establecer **nombre** a *ReceiveMessage*<br /><br /> -Establecer **activar** a *es True*|  
|SaveMessage|Send|-Establecer **nombre** a *SaveMessage*|  
  
### <a name="adding-ports"></a>Agregar puertos  
 Asegúrese de que especifique las siguientes propiedades para cada uno de los puertos lógicos. Los nombres que aparecen en la columna de puerto son los nombres de los puertos, como se muestra en la orquestación.  
  
|Puerto|Propiedades|  
|----------|----------------|  
|OracleReceivePort|-Establecer **identificador** a *OracleReceivePort*<br /><br /> -Establecer **tipo** a *OracleReceivePortType*<br /><br /> -Establecer **patrón de comunicación** a *unidireccional*<br /><br /> -Establecer **dirección de comunicación** a *de recepción*|  
|SaveMessagePort|-Establecer **identificador** a *SaveMessagePort*<br /><br /> -Establecer **tipo** a *SaveMessagePortType*<br /><br /> -Establecer **patrón de comunicación** a *unidireccional*<br /><br /> -Establecer **dirección de comunicación** a *enviar*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>Especificar mensajes de las formas Acción y conectar a los puertos  
 En la tabla siguiente especifica las propiedades y sus valores que se deben establecer para especificar los mensajes para las formas de acción y vincular los mensajes a los puertos. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación que se ha mencionado anteriormente.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveMessage|-Establecer **mensaje** a *de recepción*<br /><br /> -Establecer **operación** a *OracleReceivePort.Polling.Request*|  
|SaveMessage|-Establecer **mensaje** a *de recepción*<br /><br /> -Establecer **operación** a *SaveMessagePort.Polling.Request*|  
  
 Después de especificar estas propiedades, las formas de mensaje y los puertos que están conectados y la orquestación se completa.  
  
 Ahora debe compilar la solución de BizTalk e implementarlo en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md)).  
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el **orquestaciones** panel de la consola de administración de BizTalk Server. Debe usar la consola de administración de BizTalk Server para configurar la aplicación. Para obtener un tutorial, vea [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).
  
 Configuración de una aplicación implica:  
  
-   Selección de un host de la aplicación.  
  
-   Asignación de los puertos que ha creado en la orquestación con puertos físicos en la consola de administración de BizTalk Server. Para que esta orquestación debe:  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk colocará los mensajes de Oracle. Estos mensajes se encontrarán en respuesta a la instrucción de sondeo que especifique para el puerto de recepción.  
  
    -   Definir un WCF-Custom físico o puerto de recepción unidireccionales de WCF-OracleDB. Este puerto sondea la base de datos de Oracle. Para obtener información sobre cómo crear puertos de recepción, vea [configurar manualmente un enlace de puerto físico para el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md). Asegúrese de que especificar las siguientes propiedades de enlace para el puerto de recepción.  
  
        |Propiedad de enlace|Valor|  
        |----------------------|-----------|  
        |**InboundOperationType**|Establezca esta propiedad en **sondeo**.|  
        |**PolledDataAvailableStatement**|En este ejemplo, establezca esta propiedad de enlace en:<br /><br /> `SELECT COUNT (*) FROM ACCOUNTACTIVITY`<br /><br /> Esto garantiza que el adaptador ejecuta la instrucción de sondeo solo cuando la tabla ACCOUNTACTIVITY tiene algunos registros.|  
        |**PollingAction**|Recuperar la acción de sondeo desde el esquema generado para el mensaje entrante para el procedimiento GET_ACTIVITYS. En este ejemplo, establezca esta propiedad de enlace en **http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/PollingPackage//ACCOUNT_PKG/GET_ACTIVITYS**.|  
        |**PollingStatement**|Para esta propiedad de enlace, especifique el mensaje de solicitud para invocar la GET_ACTIVITYS procedimiento almacenado. Puede obtener el mensaje de solicitud del esquema para la operación de salida generada por la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Debe proporcionar el mensaje XML completo como entrada para esta propiedad de enlace. En este ejemplo, establezca esta propiedad de enlace en:<br /><br /> `<GET_ACTIVITYS xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY">   <INRECS>OPEN ? FOR SELECT * FROM ACCOUNTACTIVITY</INRECS> </GET_ACTIVITYS>`<br /><br /> El GET_ACTIVITYS almacena un REF CURSOR de entrada del procedimiento toma como parámetro.|  
        |**PostPollStatement**|Especifique la instrucción posterior a la de sondeo para mover todos los datos de tabla ACCOUNTACTIVITY a otra tabla. En este ejemplo, establezca esta propiedad de enlace en:<br /><br /> `BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;`|  
  
         Para obtener más información acerca de las propiedades de enlace diferente, consulte [leer acerca de las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).  
  
        > [!NOTE]
        >  Se recomienda configurar el nivel de aislamiento de transacción y el tiempo de espera de transacciones al realizar operaciones de entrada mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Puede hacerlo agregando el comportamiento del servicio al configurar el puerto de recepción. Para obtener instrucciones sobre cómo agregar el comportamiento del servicio, consulte [configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md).  
  
## <a name="starting-the-application"></a>A partir de la aplicación  
 Debe iniciar la aplicación de BizTalk para el sondeo de base de datos de Oracle. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md).  
  
 En esta fase, asegúrese de que:  
  
-   El WCF-Custom o WCF-OracleDB unidireccional puerto de recepción, que realiza un sondeo Oracle se realiza mediante el procedimiento almacenado especificado para la **PollingStatement** enlaza la propiedad, se ejecuta.  
  
-   El puerto de envío de archivo que recibe los mensajes de base de datos de Oracle, se está ejecutando.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, el siguiente conjunto de acciones tienen lugar, en la misma secuencia:  
  
-   El adaptador se ejecuta el **PolledDataAvailableStatement** que devuelve un valor positivo que indica el adaptador para ejecutar la instrucción especificada para **PollingStatement** propiedad de enlace.  
  
-   El adaptador ejecuta el procedimiento almacenado de GET_ACTIVITYS especificado para la **PollingStatement** enlace de propiedad y devuelve todas las filas de la tabla ACCOUNTACTIVITY. La respuesta de base de datos de Oracle es similar al siguiente:  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <GET_ACTIVITYS xmlns=" http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/PollingPackage/ACCOUNT_PKG">  
      <OUTRECS>  
        <OUTRECSRecord xmlns=" http://Microsoft.LobServices.OracleDB/2007/03/ReferencedRecordTypes/SCOTT/ACCOUNT_PKG/GET_ACTIVITYS/SCOTT/GET_ACTIVITYS">  
          <TID>1</TID>   
          <ACCOUNT>100001</ACCOUNT>   
          <AMOUNT>500</AMOUNT>   
          <DESCRIPTION />   
          <TRANSDATE>2008-06-21T15:52:19</TRANSDATE>   
          <PROCESSED>n</PROCESSED>   
        </OUTRECSRecord>  
        <OUTRECSRecord xmlns=" http://Microsoft.LobServices.OracleDB/2007/03/ReferencedRecordTypes/SCOTT/ACCOUNT_PKG/GET_ACTIVITYS/SCOTT/GET_ACTIVITYS">  
          ......  
          ......   
        </OUTRECSRecord>  
        ......  
        ......  
      </OUTRECS>  
    </GET_ACTIVITYS>  
    ```  
  
-   El adaptador ejecuta la instrucción posterior a la encuesta, que mueve todos los datos de tabla ACCOUNTACTIVITY a otra tabla.  
  
-   Después del intervalo de sondeo, el adaptador ejecuta nuevo **PolledDataAvailableStatement**. Porque la tabla ACCOUNTACTIVITY no tiene ningún registro ahora, **PolledDataAvailableStatement** no devuelve un valor positivo y, por tanto, el adaptador no ejecuta la instrucción especificada para la **PollingStatement**enlaza la propiedad. Como resultado, el cliente de adaptador no obtiene cualquier mensaje de sondeo.  
  
-   El cliente del adaptador no obtendrá ningún mensaje de sondeo más hasta que algunos registros se insertan explícitamente en la tabla ACCOUNTACTIVITY. Para insertar más registros, puede ejecutar el script more_activity_data.sql proporcionado con los ejemplos. Después de ejecutar este script, la próxima vez que **PolledDataAvailableStatement** es ejecuta, devuelve un valor positivo. Como resultado, el adaptador ejecuta la instrucción de sondeo y los clientes de adaptador volverá a reciban un mensaje de sondeo.  
  
> [!NOTE]
>  El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] continuarán sondea hasta que se deshabilite explícitamente el puerto de recepción desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez haya implementado y configurado el proyecto de BizTalk, puede exportar la configuración en un archivo XML denominado archivo de enlaces. Una vez que se genera un archivo de enlaces, puede importar los valores de configuración desde el archivo para que no es necesario crear los puertos de envío y puertos de recepción para la misma orquestación. Para obtener más información acerca de los archivos de enlace, vea [enlaces del adaptador de base de datos de Oracle reutilizar](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md).  
  
## <a name="see-also"></a>Vea también  
 [Sondeo de base de datos de Oracle mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-database-using-biztalk-server.md)