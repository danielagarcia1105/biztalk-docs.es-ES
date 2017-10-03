---
title: "Recibir mensajes de sondeo mediante las instrucciones SELECT con la cláusula FOR XML de SQL mediante BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 65c629c1-9ef7-4aa1-8ec1-f94a3cb41cb0
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77ac34fb06497f72b778592b3ce4c927b0ca3a07
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-polling-messages-using-select-statements-with-for-xml-clause-from-sql-using-biztalk-server"></a>Recibir mensajes de sondeo mediante las instrucciones SELECT con la cláusula FOR XML de SQL con BizTalk Server
Puede configurar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir mensajes de cambio de datos periódicos para SQL Server tablas o vistas mediante las instrucciones SELECT o procedimientos almacenados que incluyan una cláusula FOR XML. Puede especificar estas instrucciones como instrucción de sondeo que el adaptador se ejecuta para sondear la base de datos. La instrucción de sondeo puede ser una instrucción SELECT o un procedimiento almacenado que devuelve un conjunto de resultados.  
  
 Para obtener más información sobre cómo el adaptador admite el sondeo, consulte [soporte técnico para el sondeo](https://msdn.microsoft.com/library/dd788416.aspx). Para obtener información acerca de la estructura del mensaje SOAP para las operaciones de sondeo, consulte [esquemas de mensaje para el sondeo y las operaciones de TypedPolling](../../adapters-and-accelerators/adapter-sql/message-schemas-for-the-polling-and-typedpolling-operations.md). La instrucción SQL [cláusula FOR XML](https://docs.microsoft.com/sql/relational-databases/xml/for-xml-sql-server) proporcionan más detalles.
  
> [!NOTE]
>  Este tema muestra cómo utilizar el **XmlPolling** operación para recibir mensajes de sondeo de entrada. El **XmlPolling** operación se usa para sondear una base de datos de SQL Server mediante las instrucciones SELECT o procedimientos almacenados que incluyen una cláusula FOR XML. El mensaje para la **XmlPolling** operación incluye el mensaje xml recibido mediante la ejecución de la instrucción SELECT o el procedimiento almacenado en SQL Server Management Studio.  
>   
>  También puede usar el adaptador para recibir los distintos tipos de mensajes de sondeo.  
>   
>  -   Si desea obtener un mensaje de sondeo débilmente tipada, debe utilizar la operación de sondeo. Para obtener más información, consulte [mensajes de datos cambiado basados en la recepción de sondeo de SQL Server mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md).  
> -   Si desea obtener el mensaje de sondeo fuertemente tipado, debe utilizar el **TypedPolling** operación. También debe utilizar el **TypedPolling** operación tener varias operaciones de sondeo en una única aplicación de BizTalk. Para obtener instrucciones sobre cómo realizar **TypedPolling** operación, vea [recibir fuertemente tipado basado en sondeo mensajes de datos cambiado desde SQL Server mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-messages-from-sql-in-biztalk.md).  
  
> [!IMPORTANT]
>  Si desea tener más de un sondeo operación en una sola aplicación de BizTalk, debe especificar un **InboundID** propiedad de conexión como parte de la conexión de URI para que sea único. Con un URI de conexión único, puede crear varios puertos de recepción que sondean la misma base de datos, o incluso la misma tabla en una base de datos. Para obtener más información, consulte [de recepción de sondeo mensajes a través de varios puertos de recepción de SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md).  
  
## <a name="how-this-topic-demonstrates-polling"></a>Cómo este tema muestra el sondeo  
 En este tema, para demostrar cómo [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] admite la recepción de datos de los mensajes de cambio, utilizamos una instrucción SELECT con la cláusula FOR XML para sondear la base de datos de SQL Server. Cuando se invoca una instrucción en SQL Server Management Studio, el resultado es en forma de un mensaje xml. Para usar estas instrucciones para sondear una base de datos de SQL Server, debe tener el esquema del mensaje de respuesta xml. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] requiere este esquema para recibir un mensaje de sondeo después de ejecutar una instrucción SELECT con la cláusula FOR XML. Por lo tanto, para usar una instrucción SELECT con la cláusula FOR XML para sondear la base de datos de SQL Server, debe realizar el siguiente conjunto de tareas.  
  
1.  Generar el esquema para el mensaje de respuesta XML para la instrucción SELECT con la cláusula FOR XML.  
  
2.  Cree un proyecto de BizTalk y agregue el esquema generado para el proyecto.  
  
3.  Cree un mensaje en el proyecto de BizTalk para recibir mensajes de respuesta XML de la base de datos de SQL Server.  
  
4.  Crear una orquestación para recibir mensajes de la base de datos de SQL Server y guardarlas en una carpeta.  
  
5.  Compilar e implementar el proyecto de BizTalk.  
  
6.  Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
    > [!IMPORTANT]
    >  Para escenarios de entrada de sondeo siempre debe configurar un unidireccional WCF-Custom o puerto de recepción de WCF-SQL. Puertos de recepción bidireccional WCF-Custom o WCF-SQL no se admiten operaciones de entrada.  
  
7.  Inicie la aplicación de BizTalk.  
  
##  <a name="BKMK_RespSchema"></a>Generar el esquema para el mensaje de respuesta para la instrucción SELECT  
 Puede generar el esquema para el mensaje de respuesta para la instrucción SELECT mediante la inclusión de la `xmlschema` cláusula con el `for xml` cláusula. En este tema, se utiliza una instrucción SELECT para recuperar los detalles del empleado para un identificador de empleado especificado. Para recuperar el esquema mediante la ejecución de una instrucción SELECT, la instrucción SELECT debe escribirse de la siguiente manera:  
  
```  
SELECT Employee_ID ,Name ,Designation FROM Employee for xml auto, xmlschema  
```  
  
 Ejecute esta instrucción SELECT para obtener el esquema para el mensaje de respuesta. Guarde el esquema. Ahora debe crear un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y agregue este esquema al proyecto. En este ejemplo, puede asignar este esquema como **PollingResponse.xsd**.  
  
> [!IMPORTANT]
>  Asegúrese de que quite el `xmlschema` cláusula tras ejecutar la instrucción SELECT para generar el esquema. Si no puede hacer esto, al ejecutar la instrucción SELECT a través de BizTalk como parte de la operación XmlPolling por último, volver a generará el esquema del mensaje de respuesta. Por lo tanto, para obtener el mensaje de respuesta como xml, debe quitar la `xmlschema` cláusula.  
  
#### <a name="to-add-the-schema-to-a-biztalk-project"></a>Para agregar el esquema a un proyecto de BizTalk  
  
1.  Crear un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].  
  
2.  Agregue el esquema de respuesta generados para el procedimiento almacenado al proyecto de BizTalk. Haga clic en el proyecto de BizTalk en el Explorador de soluciones, seleccione **agregar**y, a continuación, haga clic en **elemento existente**. En el cuadro de diálogo Agregar elemento existente, navegue a la ubicación donde guardó el esquema y haga clic en **agregar**.  
  
3.  Abra el esquema en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y realice los cambios siguientes.  
  
    1.  Agregar un nodo en el esquema y mover el nodo raíz existente bajo este nodo recién agregado. Asigne un nombre al nodo raíz. De este tema, cambie el nombre del nodo raíz a **raíz**.  
  
    2.  El esquema de respuesta generado para la instrucción SELECT hace referencia a un sqltypes.xsd. Puede obtener el esquema sqltypes.xsd de [http://go.microsoft.com/fwlink/p/?LinkId=131087](http://go.microsoft.com/fwlink/p/?LinkId=131087). Agregue el esquema sqltypes.xsd al proyecto de BizTalk.  
  
    3.  En el esquema generado para la instrucción SELECT, cambie el valor de `import schemaLocation` al siguiente.  
  
        ```  
        import schemaLocation=”sqltypes.xsd”  
        ```  
  
         Esto es necesario porque el esquema sqltypes.xsd ya ha agregado al proyecto de BizTalk.  
  
    4.  Proporciona un espacio de nombres de destino para el esquema. Haga clic en el  **\<esquema >** nodo y en el panel Propiedades, especifique un espacio de nombres en el **Target Namespace** propiedad. De este tema, asigne el espacio de nombres como `http://ForXmlPolling/namespace`.  
  
## <a name="defining-messages-and-message-types"></a>Definición de mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes en la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Una vez que se genera el esquema, debe vincular a los mensajes desde la vista de orquestación de BizTalk del proyecto.  
  
 De este tema, debe crear un mensaje para recibir mensajes de la base de datos de SQL Server.  
  
 Realice los pasos siguientes para crear mensajes y vincularlas a esquema.  
  
#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vincular al esquema  
  
1.  Agregar una orquestación al proyecto de BizTalk. En el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**. Escriba un nombre para la orquestación de BizTalk y, a continuación, haga clic en **agregar**.  
  
2.  Abra la ventana de vista de orquestación de BizTalk del proyecto, si no está ya abierto. Haga clic en **vista**, seleccione **otras ventanas**y, a continuación, haga clic en **Vista orquestación**.  
  
3.  En el **Vista orquestación**, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
4.  Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  
  
5.  En el **propiedades** panel para **Message_1**, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo de **PollingMessage**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *ForXMLPolling.PollingResponse*, donde *ForXMLPolling* es el nombre de su proyecto de BizTalk. *PollingResponse* es el nombre del esquema de respuesta generado mediante la ejecución de la instrucción SELECT como se describe en [recibir mensajes de sondeo mediante las instrucciones SELECT con la cláusula FOR XML de SQL mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md).|  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para usar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para recibir mensajes de cambio de datos basado en sondeo de la base de datos de SQL Server. En esta orquestación, el adaptador recibe la respuesta de la instrucción select especificada para la **PollingStatement** propiedad de enlace. La respuesta para la instrucción SELECT se guarda en una ubicación de archivo. Contendría una orquestación típica para sondear una base de datos de SQL Server:  
  
-   Recepción y envío formas a fin de recibir mensajes de SQL Server y enviar a un puerto de archivo, respectivamente.  
  
-   Un unidireccional puerto de recepción para recibir mensajes de SQL Server.  
  
    > [!IMPORTANT]
    >  Para escenarios de entrada de sondeo siempre debe configurar un puerto de recepción unidireccional. Bidireccional de recepción no se admiten los puertos para las operaciones de entrada.  
  
-   Un puerto de envío unidireccional para enviar las respuestas del sondeo de una base de datos de SQL Server a una carpeta.  
  
 Una orquestación de ejemplo es similar al siguiente.  
  
 ![Orquestación para sondear una base de datos de SQL Server](../../adapters-and-accelerators/adapter-sql/media/5cf65d53-d70d-444d-82f7-2561efcd9ee4.gif "5cf65d53-d70d-444d-82f7-2561efcd9ee4")  
  
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
|SQLReceivePort|-Establecer **identificador** a *SQLReceivePort*<br /><br /> -Establecer **tipo** a *SQLReceivePortType*<br /><br /> -Establecer **patrón de comunicación** a *unidireccional*<br /><br /> -Establecer **dirección de comunicación** a *de recepción*|  
|SaveMessagePort|-Establecer **identificador** a *SaveMessagePort*<br /><br /> -Establecer **tipo** a *SaveMessagePortType*<br /><br /> -Establecer **patrón de comunicación** a *unidireccional*<br /><br /> -Establecer **dirección de comunicación** a *enviar*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>Especificar mensajes de las formas Acción y conectar a los puertos  
 En la tabla siguiente especifica las propiedades y sus valores que se deben establecer para especificar los mensajes para las formas de acción y vincular los mensajes a los puertos. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación que se ha mencionado anteriormente.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveMessage|-Establecer **mensaje** a *de recepción*<br /><br /> -Establecer **operación** a *SQLReceivePort.XmlPolling.Request*|  
|SaveMessage|-Establecer **mensaje** a *de recepción*<br /><br /> -Establecer **operación** a *SaveMessagePort.XmlPolling.Request*|  
  
 Después de especificar estas propiedades, las formas de mensaje y los puertos que están conectados y la orquestación se completa.  
  
 Ahora debe compilar la solución de BizTalk e implementarlo en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el **orquestaciones** panel de la consola de administración de BizTalk Server. Debe utilizar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para configurar la aplicación. Para obtener un tutorial, vea [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).
  
 Configuración de una aplicación implica:  
  
-   Selección de un host de la aplicación.  
  
-   Asignación de los puertos que ha creado en la orquestación con puertos físicos en la consola de administración de BizTalk Server. Para que esta orquestación debe:  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk colocará los mensajes de la base de datos de SQL Server. Estos mensajes se encontrarán en respuesta a la instrucción de sondeo que especifique para el puerto de recepción.  
  
    -   Definir un WCF-Custom físico o puerto de recepción unidireccionales de WCF-SQL. Este puerto sondea la base de datos de SQL Server con la instrucción de sondeo que especifique para el puerto. Para obtener información sobre cómo crear puertos, consulte [configurar manualmente un enlace de puerto físico para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md). Asegúrese de que especificar las siguientes propiedades de enlace para el puerto de recepción.  
  
        > [!IMPORTANT]
        >  No es necesario realizar este paso si especifica las propiedades de enlace en tiempo de diseño. En tal caso, puede crear un WCF-custom o WCF-SQL puerto de recepción, en el conjunto de propiedades de enlace necesaria, importando el archivo de enlace creado por la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto para utilizar el adaptador SQL](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).  
  
        |Propiedad de enlace|Valor|  
        |----------------------|-----------|  
        |**InboundOperationType**|Asegúrese de que se establece en **XmlPolling**.|  
        |**PolledDataAvailableStatement**|Asegúrese de que especificar una instrucción SQL. En este tema, especificar:<br /><br /> `SELECT COUNT(*) FROM Employee`|  
        |**PollingStatement**|Asegúrese de proporcionar la misma instrucción sin el `xmlschema` cláusula, que especificó al generar el esquema, como se describe en [recibir mensajes de sondeo mediante las instrucciones SELECT con la cláusula FOR XML de SQL mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md).<br /><br /> `SELECT Employee_ID ,Name ,Designation FROM Employee for xml auto`<br /><br /> **Nota:** tenga en cuenta que la instrucción SELECT no contiene el `xmlschema` cláusula.|  
        |**XmlStoredProcedureRootNodeName**|Especifique el nombre del nodo raíz que agrega al esquema de respuesta generado para la instrucción SELECT, tal y como se describe en la sección [generar esquema para el mensaje de respuesta para la instrucción SELECT](#BKMK_RespSchema). De este tema, establezca esta propiedad en **raíz**.|  
        |**XmlStoredProcedureRootNodeNamespace**|Especificar el espacio de nombres de destino para el esquema de respuesta generado para la instrucción SELECT, como se describe en [generar esquema para el mensaje de respuesta para la instrucción SELECT](#BKMK_RespSchema). De este tema, establezca esta propiedad en `http://ForXmlPolling/namespace`.|  
  
         Para obtener más información acerca de las propiedades de enlace diferente, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  
  
        > [!NOTE]
        >  Se recomienda configurar el nivel de aislamiento de transacción y el tiempo de espera de transacciones al realizar operaciones de entrada mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Puede hacerlo agregando el servicio de puerto de recepción de comportamiento al configurar el WCF-Custom o WCF-SQL. Para obtener instrucciones sobre cómo agregar el comportamiento del servicio, consulte [configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con SQL](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md).  
  
## <a name="starting-the-application"></a>A partir de la aplicación  
 Debe iniciar la aplicación de BizTalk para recibir mensajes de la base de datos de SQL Server. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md).
  
 En esta fase, asegúrese de que:  
  
-   El WCF-Custom o WCF-SQL unidireccional puerto de recepción, que sondea la base de datos de SQL Server mediante las instrucciones especificadas para el **PollingStatement** enlaza la propiedad, se ejecuta.  
  
-   El puerto de envío de archivo que recibe los mensajes de SQL Server, se está ejecutando.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, el siguiente conjunto de acciones tienen lugar, en la misma secuencia:  
  
-   El adaptador se ejecuta el **PolledDataAvailableStatement** en el empleado de la tabla y determina que la tabla tiene registros de sondeo.  
  
-   El adaptador ejecuta la instrucción de sondeo y recibe un mensaje de sondeo de la base de datos de SQL Server. Dado que la instrucción de sondeo está formada por una instrucción SELECT con una cláusula FOR XML, el mensaje de sondeo recibido por el adaptador es similar al siguiente:  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <Root xmlns="http://ForXmlPolling/namespace">  
      <Employee Employee_ID="10765" Name="John" Designation="Tester" xmlns="" />   
      <Employee Employee_ID="10766" Name="Sam" Designation="Manager" xmlns="" />   
      .....  
      .....  
    </Root>  
    ```  
  
     Tenga en cuenta que se recibe el mensaje de sondeo en el mismo esquema, tal y como se generan al ejecutar la instrucción SELECT con la **xmlschema** cláusula. Tenga en cuenta también que el nodo raíz y el espacio de nombres es el mismo que especificó como valores para **XmlStoredProcedureRootNodeName** y **XmlStoredProcedureRootNodeNamespace** propiedades de enlace respectivamente.  
  
> [!NOTE]
>  El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] continuarán sondea hasta que se deshabilite explícitamente el puerto de recepción desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez haya implementado y configurado el proyecto de BizTalk, puede exportar la configuración en un archivo XML denominado archivo de enlace. Una vez que se genera un archivo de enlace, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear los puertos de envío y puertos de recepción para la misma orquestación. Para obtener más información acerca de los archivos de enlace, vea [reutilizar enlaces del adaptador](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md).
  
## <a name="see-also"></a>Vea también  
 [Sondear el servidor SQL mediante el adaptador SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)