---
title: Recibir mensajes de cambio de datos basado en sondeo desde SQL Server mediante BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9ecaf6f7-974b-4487-8c65-d1ab628cbfeb
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b86a58a092f5f38c4a09c014feb0b4fe85d1fc9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-polling-based-data-changed-messages-from-sql-server-using-biztalk-server"></a>Recibir mensajes de cambio de datos basado en sondeo desde SQL Server mediante BizTalk Server
Puede configurar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir mensajes de cambio de datos periódicos para SQL Server tablas o vistas. Puede especificar una instrucción de sondeo que el adaptador se ejecuta para sondear la base de datos. La instrucción de sondeo puede ser una instrucción SELECT o un procedimiento almacenado que devuelve un conjunto de resultados.  

  
 Para obtener más información sobre cómo el adaptador admite el sondeo, consulte [soporte técnico para el sondeo](https://msdn.microsoft.com/library/dd788416.aspx). Para obtener información acerca de la estructura del mensaje SOAP para las operaciones de sondeo, consulte [esquemas de mensaje para el sondeo y las operaciones de TypedPolling](../../adapters-and-accelerators/adapter-sql/message-schemas-for-the-polling-and-typedpolling-operations.md).  
  
> [!NOTE]
>  Este tema muestra cómo utilizar el **sondeo** operación usar los mensajes de sondeo de entrada. El mensaje para la operación de sondeo no está fuertemente tipadas y se recupera el esquema del objeto se sondean, junto con el mensaje en tiempo de ejecución. Si desea obtener el mensaje de sondeo fuertemente tipado, debe utilizar el **TypedPolling** operación. También debe utilizar el **TypedPolling** operación tener varias operaciones de sondeo en una única aplicación de BizTalk. Para obtener instrucciones sobre cómo realizar **TypedPolling** operación, vea [recibir fuertemente tipado basado en sondeo mensajes de datos cambiado desde SQL Server mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-messages-from-sql-in-biztalk.md).  
  
> [!IMPORTANT]
>  Si desea tener más de un sondeo operación en una sola aplicación de BizTalk, debe especificar un **InboundID** propiedad de conexión como parte de la conexión de URI para que sea único. Con un URI de conexión único, puede crear varios puertos de recepción que sondean la misma base de datos, o incluso la misma tabla en una base de datos. Para obtener más información, consulte [de recepción de sondeo mensajes a través de varios puertos de recepción de SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md).  
  
## <a name="how-this-topic-demonstrates-polling"></a>Cómo este tema muestra el sondeo  
 En este tema, para demostrar cómo [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] admite la recepción de datos de los mensajes de cambio, crear un proyecto de BizTalk y genere el esquema para el **sondeo** operación. Si desea especificar el sondeo relacionados con propiedades de enlace en tiempo de diseño, especifique la **PolledDataAvailableStatement** como:  
  
```  
SELECT COUNT(*) FROM Employee  
```  
  
 El **PolledDataAvailableStatement** debe devolver un conjunto de resultados con la primera celda que contiene un valor positivo. Si la primera celda no contiene un valor positivo, el adaptador no ejecuta la instrucción de sondeo.  
  
 Como parte de la instrucción de sondeo, realice las siguientes operaciones:  
  
-   Seleccione todas las filas de la tabla de empleados.  
  
-   Ejecutar un procedimiento almacenado (MOVE_EMP_DATA) para mover todos los registros de la tabla de empleados a una tabla HistorialEmpleados.  
  
-   Ejecutar un procedimiento almacenado (ADD_EMP_DETAILS) para agregar un nuevo registro a la tabla de empleados. Este procedimiento toma el nombre de empleado, designación y salario como parámetros.  
  
 Para llevar a cabo estas operaciones, debe especificar lo siguiente para el **PollingStatement** propiedad de enlace:  
  
```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  
  
 Después de ejecuta la instrucción de sondeo, se seleccionan todos los registros de la tabla de empleados y se quita el mensaje de SQL Server en una ubicación de recepción. Una vez que se ejecuta el procedimiento almacenado de MOVE_EMP_DATA por el adaptador, todos los registros se mueven a la tabla HistorialEmpleados. A continuación, se ejecuta el procedimiento almacenado de ADD_EMP_DETAILS para agregar un nuevo registro a la tabla de empleados. La siguiente ejecución de sondeo solo devolverá un único registro. Este ciclo continúa hasta que deshabilite la recepción puerto que sondea el servidor SQL.  
  
## <a name="configuring-a-polling-query-with-the-sql-adapter-binding-properties"></a>Configuración de una consulta de sondeo con el adaptador de SQL propiedades de enlace  
 La siguiente tabla resume el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] propiedades de enlace que se utiliza para configurar el adaptador para recibir mensajes de cambio de datos. Debe especificar estas propiedades de enlace al configurar el puerto de recepción en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
> [!NOTE]
>  Puede especificar estas propiedades de enlace al generar el esquema para el **sondeo** operación, aunque no es obligatorio. Si lo hace, el enlace de puerto de archivos que el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] genera como parte de la generación de metadatos también contiene los valores especificados para las propiedades de enlace. Más adelante puede importar este archivo de enlace en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] puerto de recepción de la consola de administración para crear el WCF-custom o WCF-SQL con el enlace de propiedades ya establecidas. Para obtener más información acerca de cómo crear un puerto mediante el archivo de enlace, vea [configurar un enlace de puerto físico mediante un archivo de enlace de puerto para utilizar el adaptador SQL](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).  
  
|Propiedad de enlace|Description|  
|---|---|  
|**InboundOperationType**|Especifica si desea realizar **sondeo**, **TypedPolling**, o **notificación** operación entrante. Valor predeterminado es **sondeo**.|  
|**PolledDataAvailableStatement**|Especifica la instrucción SQL que se ejecuta el adaptador para determinar si los datos están disponibles para el sondeo. La instrucción SQL debe devolver un conjunto que consta de filas y columnas de resultados. Solo si una fila está disponible, la instrucción SQL especificada para el **PollingStatement** se va a ejecutar la propiedad de enlace.|  
|**PollingIntervalInSeconds**|Especifica el intervalo, en segundos, en el que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se ejecuta la instrucción especificada para la **PolledDataAvailableStatement** propiedad de enlace. El valor predeterminado es 30 segundos. El intervalo de sondeo determina el intervalo de tiempo entre sondeos sucesivos. Si la instrucción se ejecuta en el intervalo especificado, el adaptador espera el tiempo restante en el intervalo.|  
|**PollingStatement**|Especifica la instrucción SQL para sondear la tabla de base de datos de SQL Server. Puede especificar una instrucción SELECT simple o un procedimiento almacenado para la instrucción de sondeo. El valor predeterminado es null. Debe especificar un valor para **PollingStatement** para habilitar el sondeo. Se ejecuta la instrucción de sondeo solo si hay datos disponibles para el sondeo, que viene determinado por la **PolledDataAvailableStatement** propiedad de enlace. Puede especificar cualquier número de instrucciones SQL separados por un punto y coma.|  
|**PollWhileDataFound**|Especifica si el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] pasa por alto el intervalo de sondeo y ejecuta continuamente la instrucción SQL especificada para el **PolledDataAvailableStatement** enlaza la propiedad, si los datos están disponibles en la tabla que se va a sondear. Si no hay datos disponibles en la tabla, el adaptador vuelve para ejecutar la instrucción SQL en el intervalo de sondeo especificado. Valor predeterminado es **false**.|  
  
 Para obtener una descripción más completa de estas propiedades, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md). Para obtener una descripción completa de cómo usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para sondear SQL Server, seguir leyendo.  
  
## <a name="how-to-receive-data-change-messages-from-the-sql-server-database"></a>Cómo recibir mensajes de cambio de datos de la base de datos SQL Server  
 Realizar una operación en la base de datos de SQL Server mediante [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] conlleva las tareas de procedimientos descritas en [bloques de creación para desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md). Para configurar el adaptador para recibir mensajes de cambio de datos, estas tareas son:  
  
1.  Crear un proyecto de BizTalk y, a continuación, genere el esquema para el **sondeo** operación. Si lo desea, puede especificar valores para la **PolledDataAvailableStatement** y **PollingStatement** propiedades de enlace.  
  
2.  Cree un mensaje en el proyecto de BizTalk para recibir mensajes de la base de datos de SQL Server.  
  
3.  Crear una orquestación para recibir mensajes de la base de datos de SQL Server y guardarlas en una carpeta.  
  
4.  Compilar e implementar el proyecto de BizTalk.  
  
5.  Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
    > [!IMPORTANT]
    >  Para escenarios de entrada de sondeo siempre debe configurar un unidireccional WCF-Custom o puerto de recepción de WCF-SQL. Puertos de recepción bidireccional WCF-Custom o WCF-SQL no se admiten operaciones de entrada.  
  
6.  Inicie la aplicación de BizTalk.  
  
 Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="generating-schema"></a>Generar el esquema  
 Debe generar el esquema para el **sondeo** operación. Vea [recuperación de metadatos para operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md) para obtener más información acerca de cómo generar el esquema. Realice las tareas siguientes al generar el esquema. Omitir el primer paso si no desea especificar las propiedades de enlace en tiempo de diseño.  
  
1.  Especifique un valor para **PolledDataAvailableStatement** y **PollingStatement** propiedades de enlace al generar el esquema. Para obtener más información acerca de esta propiedad de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  
  
     Para obtener instrucciones sobre cómo especificar las propiedades de enlace, consulte [configurar las propiedades de enlace para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).  
  
2.  Seleccione el tipo de contrato **(operación de entrada) de servicio**.  
  
3.  Genere el esquema para el **sondeo** operación.  
  
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
    |Identificador|Tipo de **recibir**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *PollingQuery.Polling*, donde *PollingQuery* es el nombre de su proyecto de BizTalk. *Sondeo* es el esquema generado para el **sondeo** operación.|  
  
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
|ReceiveMessage|-Establecer **mensaje** a *de recepción*<br /><br /> -Establecer **operación** a *SQLReceivePort.Polling.Request*|  
|SaveMessage|-Establecer **mensaje** a *de recepción*<br /><br /> -Establecer **operación** a *SaveMessagePort.Polling.Request*|  
  
 Después de especificar estas propiedades, las formas de mensaje y los puertos que están conectados y la orquestación se completa.  
  
 Ahora debe compilar la solución de BizTalk e implementarlo en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md). 
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el **orquestaciones** panel de la consola de administración de BizTalk Server. Debe usar la consola de administración de BizTalk Server para configurar la aplicación. Para obtener un tutorial, vea [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).  
  
 Configuración de una aplicación implica:  
  
-   Selección de un host de la aplicación.  
  
-   Asignación de los puertos que ha creado en la orquestación con puertos físicos en la consola de administración de BizTalk Server. Para que esta orquestación debe:  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk colocará los mensajes de la base de datos de SQL Server. Estos mensajes se encontrarán en respuesta a la instrucción de sondeo que especifique para el puerto de recepción.  
  
    -   Definir un WCF-Custom físico o puerto de recepción unidireccionales de WCF-SQL. Este puerto sondea la base de datos de SQL Server con la instrucción de sondeo que especifique para el puerto. Para obtener información sobre cómo crear puertos, consulte [configurar manualmente un enlace de puerto físico para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md). Asegúrese de que especificar las siguientes propiedades de enlace para el puerto de recepción.  
  
        > [!IMPORTANT]
        >  No es necesario realizar este paso si especifica las propiedades de enlace en tiempo de diseño. En tal caso, puede crear un WCF-custom o WCF-SQL puerto de recepción, en el conjunto de propiedades de enlace necesaria, importando el archivo de enlace creado por la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto para utilizar el adaptador SQL](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).  
  
        |Propiedad de enlace|Valor|  
        |----------------------|-----------|  
        |**InboundOperationType**|Asegúrese de que se establece en **sondeo**.|  
        |**PolledDataAvailableStatement**|Asegúrese de que especificar una instrucción SQL. En este tema, especificar:<br /><br /> `SELECT COUNT(*) FROM Employee`|  
        |**PollingStatement**|Asegúrese de que especificar la instrucción de sondeo. En este tema, especificar:<br /><br /> `SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000`|  
  
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
  
-   El adaptador ejecuta la instrucción de sondeo. Dado que la instrucción de sondeo consta de una instrucción SELECT y procedimientos almacenados, el adaptador ejecutará todas las instrucciones uno detrás de otra.  
  
    -   El adaptador ejecuta primero la instrucción SELECT que devuelve todos los registros de la tabla Employee.  
  
    -   El adaptador, a continuación, ejecuta el procedimiento MOVE_EMP_DATA almacenados que mueve todos los datos de la tabla de empleados a la tabla HistorialEmpleados. Este procedimiento almacenado no devuelve ningún valor.  
  
    -   El adaptador, a continuación, ejecuta el procedimiento ADD_EMP_DETAILS almacenados que agrega un registro a la tabla de empleados. Este procedimiento almacenado devuelve el identificador de empleado para el registro insertado.  
  
     Por lo tanto, el mensaje recibido de SQL Server contendrá varios conjuntos de resultados (para la instrucción SELECT y de procedimiento almacenado de ADD_EMP_DETAILS) y será similar al siguiente:  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <Polling xmlns="http://schemas.microsoft.com/Sql/2008/05/Polling/">  
      <PolledData>  
        <DataSet xmlns="http://schemas.datacontract.org/2004/07/System.Data">  
          \<xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
            \<xs:element msdata:IsDataSet="true" name="NewDataSet">  
              \<xs:complexType>  
                \<xs:sequence>  
                  \<xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                    \<xs:complexType>  
                      \<xs:sequence>  
                        \<xs:element minOccurs="0" name="Employee_ID" type="xs:int" />   
                        \<xs:element minOccurs="0" name="Name" type="xs:string" />   
                        \<xs:element minOccurs="0" name="DOJ" type="xs:dateTime" />   
                        \<xs:element minOccurs="0" name="Designation" type="xs:string" />   
                        \<xs:element minOccurs="0" name="Job_Description" type="xs:string" />   
                        \<xs:element minOccurs="0" name="Photo" type="xs:base64Binary" />   
                        \<xs:element minOccurs="0" name="Rating" type="xs:string" />   
                        \<xs:element minOccurs="0" name="Salary" type="xs:decimal" />   
                        \<xs:element minOccurs="0" name="Last_Modified" type="xs:base64Binary" />   
                      \</xs:sequence>  
                    \</xs:complexType>  
                  \</xs:element>  
                \</xs:sequence>  
              \</xs:complexType>  
            \</xs:element>  
          \</xs:schema>  
          \<diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
            <NewDataSet xmlns="">  
              <NewTable>  
                <Employee_ID>10001</Employee_ID>   
                <Name>John</Name>   
                <Designation>Tester</Designation>   
                <Salary>100000.00</Salary>   
                <Last_Modified>AAAAAAAAF34=</Last_Modified>   
              </NewTable>  
              ........  
              ........  
              <NewTable>  
                <Employee_ID>10005</Employee_ID>   
                <Name>Wilson</Name>   
                <Designation>Tester3</Designation>   
                <Salary>100000.00</Salary>   
                <Last_Modified>AAAAAAAAF4E=</Last_Modified>   
              </NewTable>  
            </NewDataSet>  
          \</diffgr:diffgram>  
        </DataSet>  
        <DataSet xmlns="http://schemas.datacontract.org/2004/07/System.Data">  
          \<xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
            \<xs:element msdata:IsDataSet="true" name="NewDataSet">  
              \<xs:complexType>  
                \<xs:sequence>  
                  \<xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                    \<xs:complexType>  
                      \<xs:sequence>  
                        \<xs:element minOccurs="0" name="Employee_ID" type="xs:int" />   
                      \</xs:sequence>  
                    \</xs:complexType>  
                  \</xs:element>  
                \</xs:sequence>  
              \</xs:complexType>  
            \</xs:element>  
          \</xs:schema>  
          \<diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
            <NewDataSet xmlns="">  
              <NewTable>  
                <Employee_ID>10006</Employee_ID>  
              </NewTable>  
            </NewDataSet>  
          \</diffgr:diffgram>  
        </DataSet>  
      </PolledData>  
    </Polling>  
    ```  
  
     La respuesta anterior contiene dos conjuntos de datos. El primer conjunto de datos contiene la respuesta de la instrucción SELECT. La instrucción SELECT selecciona todos los registros de la tabla Employee. Es el segundo conjunto de datos para el procedimiento almacenado de ADD_EMP_DETAILS. Este procedimiento almacenado agrega un registro a la tabla de empleados y devuelve el identificador de empleado para el nuevo registro.  
  
    > [!NOTE]
    >  El procedimiento almacenado de MOVE_EMP_DATA no devuelve un conjunto de resultados. Por lo tanto, no hay ningún conjunto de datos correspondiente en el mensaje de respuesta.  
  
-   Cuando se ejecuta el adaptador el **PollDataAvailableStatement** ahora, encuentra un registro que ha insertado el ADD_EMP_DETAILS procedimiento almacenado. El adaptador, a continuación, ejecuta las tres instrucciones que se especifican para la **PollingStatement** propiedad de enlace. Esta vez, la respuesta de SQL Server contiene un solo registro para la instrucción SELECT y un registro para el ADD_EMP_DETAILS de procedimiento almacenado. Todos los sondeos subsiguientes devolverá respuestas similar.  
  
> [!NOTE]
>  El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] continuarán sondea hasta que se deshabilite explícitamente el puerto de recepción desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez haya implementado y configurado el proyecto de BizTalk, puede exportar la configuración en un archivo XML denominado archivo de enlace. Una vez que se genera un archivo de enlace, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear los puertos de envío y puertos de recepción para la misma orquestación. Para obtener más información acerca de los archivos de enlace, vea [reutilizar enlaces del adaptador](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md).
  
## <a name="see-also"></a>Vea también  
 [Sondear el servidor de SQL con el adaptador de SQL BizTalk Server](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)