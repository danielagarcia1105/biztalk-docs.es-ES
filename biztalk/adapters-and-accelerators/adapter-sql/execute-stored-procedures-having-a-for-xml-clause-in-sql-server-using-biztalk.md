---
title: "Ejecutar procedimientos almacenados que tengan una cláusula FOR XML en SQL Server mediante BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d8fe927-90bf-48fc-a418-63b920b409ed
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c1b69c522f01f2561ea8145c11dec3e36b5cd4e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="execute-stored-procedures-having-a-for-xml-clause-in-sql-server-using-biztalk-server"></a>Ejecutar procedimientos almacenados que tengan una cláusula FOR XML en SQL Server con BizTalk Server
Una instrucción SELECT de SQL puede tener una cláusula FOR XML que devuelve el resultado de la consulta como XML en lugar de un conjunto de filas. También puede tener un procedimiento almacenado que contiene una instrucción SELECT con una cláusula FOR XML. [FOR XML (SQL Server)](https://msdn.microsoft.com/library/ms178107.aspx) se proporciona más información.
  
 Puede usar basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para ejecutar como procedimientos almacenados.  
  
> [!IMPORTANT]
>  El adaptador SQL "nativo" disponible con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] requiere procedimientos almacenados para tener la cláusula FOR XML como parte de la instrucción SELECT. Puede utilizar estos procedimientos almacenados con basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] sin realizar ningún cambio en la definición del procedimiento almacenado.  
>   
>  Siempre puede utilizar los esquemas generados mediante el adaptador de SQL 'native' proporcionado con versiones anteriores de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [consultas mediante FOR XML con el adaptador de WCF-SQL](http://go.microsoft.com/fwlink/?LinkId=223428) (http://go.microsoft.com/fwlink/?LinkId=223428).  
  
## <a name="how-to-invoke-stored-procedures-with-for-xml-clause"></a>Cómo invocar procedimientos almacenados con la cláusula FOR XML  
 Cuando se invoca un procedimiento almacenado con la cláusula FOR XML en SQL Server Management Studio o mediante el adaptador de SQL disponible con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], el resultado tiene el formato de un mensaje xml. Para utilizar estos procedimientos con basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], debe tener el esquema para el mensaje de salida. Basado en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] requiere este esquema al recibir el mensaje de respuesta de SQL Server después de ejecutar un procedimiento almacenado con la cláusula FOR XML. Tenga en cuenta que el propio adaptador generará el mensaje de solicitud para invocar este procedimiento almacenado.  
  
 Además de tener el esquema para el mensaje de respuesta, también debe realizar ciertas tareas para invocar un procedimiento almacenado con la cláusula FOR XML con basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
1.  Generar el esquema para el mensaje de respuesta para el procedimiento almacenado con la cláusula FOR XML. Si ya tiene el esquema de respuesta generado por el adaptador SQL "nativo" disponible con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], puede omitir este paso.  
  
2.  Cree un proyecto de BizTalk y agregue el esquema generado para el proyecto.  
  
3.  Genere el esquema para el procedimiento almacenado con la cláusula FOR XML con basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Esto proporciona el esquema del mensaje de solicitud que el adaptador envía a SQL Server para invocar el procedimiento almacenado.  
  
4.  Crear mensajes en el proyecto de BizTalk para enviar y recibir mensajes de SQL Server. El mensaje de solicitud debe ajustarse al esquema del mensaje de solicitud generado por el adaptador. El mensaje de respuesta debe ajustarse al esquema del mensaje de respuesta que se obtienen utilizando el adaptador SQL "nativo" o mediante la ejecución del procedimiento almacenado con la cláusula FOR XML en SQL Server Management Studio.  
  
5.  Crear una orquestación para invocar el procedimiento almacenado en la base de datos de SQL Server.  
  
6.  Compilar e implementar el proyecto de BizTalk.  
  
7.  Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
8.  Inicie la aplicación de BizTalk.  
  
##  <a name="BKMK_RespSchema"></a>Generar el esquema para el mensaje de respuesta para el procedimiento almacenado  
  
> [!NOTE]
>  No es necesario realizar este paso si tiene el esquema de respuesta generado por el adaptador de SQL disponible con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
 Puede generar el esquema para el mensaje de respuesta para el procedimiento almacenado, siempre que la instrucción SELECT en el procedimiento almacenado tenga el `xmlschema` cláusula con el `for xml` cláusula. En este tema, se utiliza el procedimiento almacenado de GET_EMP_DETAILS_FOR_XML que recupera los detalles del empleado para un identificador de empleado especificado. Para recuperar el esquema mediante la ejecución del procedimiento almacenado, la instrucción SELECT es similar a lo siguiente:  
  
```  
SELECT [Employee_ID] ,[Name] ,[DOJ] ,[Designation] ,[Job_Description] ,[Photo] ,cast([Rating] as varchar(100)) as Rating ,[Salary] ,[Last_Modified] ,[Status] ,[Address]   
FROM [Adapt_Doc].[dbo].[Employee] for xml auto, xmlschema  
```  
  
 Ejecute este procedimiento almacenado para obtener el esquema para el mensaje de respuesta. Tenga en cuenta que la respuesta del procedimiento almacenado contiene el esquema, así como los datos de ejecución del procedimiento almacenado. Debe copiar el esquema de la respuesta y guárdelo en un panel de texto. En este ejemplo, puede asignar este esquema como **ResponseSchema.xsd**. Ahora debe crear un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y agregue este esquema al proyecto.  
  
> [!IMPORTANT]
>  Asegúrese de que quite el `xmlschema` cláusula tras ejecutar el procedimiento almacenado para generar el esquema. Si no puede hacer esto, al ejecutar el procedimiento almacenado a través de BizTalk por último, volver a generará el esquema del mensaje de respuesta. Por lo tanto, para obtener el mensaje de respuesta como xml, debe quitar la `xmlschema` cláusula.  
  
#### <a name="to-add-the-schema-to-a-biztalk-project"></a>Para agregar el esquema a un proyecto de BizTalk  
  
1.  Crear un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].  
  
2.  Agregue el esquema de respuesta generados para el procedimiento almacenado al proyecto de BizTalk. Haga clic en el proyecto de BizTalk en el Explorador de soluciones, seleccione **agregar**y, a continuación, haga clic en **elemento existente**. En el cuadro de diálogo Agregar elemento existente, navegue a la ubicación donde guardó el esquema y haga clic en **agregar**.  
  
3.  Abra el esquema en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y realice los cambios siguientes.  
  
    1.  Agregar un nodo en el esquema y mover el nodo raíz existente bajo este nodo recién agregado. Asigne un nombre al nodo raíz. De este tema, cambie el nombre del nodo raíz a **raíz**.  
  
    2.  El esquema de respuesta generado para el procedimiento almacenado hace referencia a un sqltypes.xsd. Puede obtener el esquema sqltypes.xsd de [http://go.microsoft.com/fwlink/?LinkId=131087](http://go.microsoft.com/fwlink/?LinkId=131087). Agregue el esquema sqltypes.xsd al proyecto de BizTalk.  
  
    3.  En el esquema generado para el procedimiento almacenado, cambie el valor de `import schemaLocation` al siguiente.  
  
        ```  
        import schemaLocation=”sqltypes.xsd”  
        ```  
  
         Esto es necesario porque el esquema sqltypes.xsd ya ha agregado al proyecto de BizTalk.  
  
    4.  Proporciona un espacio de nombres de destino para el esquema. Haga clic en el  **\<esquema\>**  nodo y en el panel Propiedades, especifique un espacio de nombres en el **Target Namespace** propiedad. De este tema, asigne el espacio de nombres como `http://ForXmlStoredProcs/namespace`.  
  
## <a name="generating-schema-for-the-request-message-to-invoke-the-stored-procedure"></a>Generar el esquema para el mensaje de solicitud invocar el procedimiento almacenado  
 Para generar el esquema del mensaje de solicitud puede usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] desde un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. En este tema, generar el esquema para el procedimiento almacenado de GET_EMP_DETAILS_FOR_XML. Para obtener más información sobre cómo generar el esquema mediante [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], consulte [recuperación de metadatos para operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).  
  
> [!IMPORTANT]
>  Debe generar el esquema, seleccione el procedimiento sólo desde el **procedimientos** nodo [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
## <a name="defining-messages-and-message-types"></a>Definición de mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes de la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Ahora debe crear mensajes de la orquestación y vincularlos a los esquemas que generó en el paso anterior.  
  
#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vincular al esquema  
  
1.  Agregar una orquestación al proyecto de BizTalk. En el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**. Escriba un nombre para la orquestación de BizTalk y, a continuación, haga clic en **agregar**.  
  
2.  Abra la ventana Vista orquestación del proyecto de BizTalk, si no está ya abierto. Para ello, haga clic en **vista**, seleccione **otras ventanas**y, a continuación, haga clic en **Vista orquestación**.  
  
3.  En Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
4.  Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  
  
5.  En el **propiedades** panel para la **Message_1**, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Escriba `Request`|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *ForXMLProcedure.Procedure_dbo. GET_EMP_DETAILS_FOR_XML*, donde ForXMLProcedure es el nombre de su proyecto de BizTalk. Procedure_dbo es el esquema generado para invocar el procedimiento GET_EMP_DETAILS_FOR_XML.|  
  
6.  Repita el paso 2 para crear un nuevo mensaje. En el **propiedades** panel para el nuevo mensaje, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Escriba `Response`|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *ForXMLProcedure.ResponseSchema*, donde ResponseSchema es el nombre del esquema de respuesta generado por la ejecución del procedimiento almacenado como se describe en [generar esquema para el mensaje de respuesta para el procedimiento almacenado](#BKMK_RespSchema).|  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para usar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para ejecutar un procedimiento almacenado en SQL Server. En esta orquestación, se coloca un mensaje de solicitud en una determinada ubicación de recepción. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] consume este mensaje y lo pasa al SQL Server. La respuesta de SQL Server se guarda en otra ubicación. Debe incluir el envío y recepción formas para enviar mensajes a SQL Server y recibir respuestas, respectivamente. Una orquestación para invocar un procedimiento de ejemplo es similar al siguiente:  
  
 ![Orquestación para invocar procedimientos almacenados](../../adapters-and-accelerators/adapter-sql/media/eac6e8b6-f0f4-44af-8218-03ca3864b267.gif "eac6e8b6-f0f4-44af-8218-03ca3864b267")  
  
### <a name="adding-message-shapes"></a>Agregar formas de mensaje  
 Asegúrese de que especifique las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación just-mencionado.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-Establecer **nombre** a *ReceiveMessage*<br />-Establecer **activar** a *es True*|  
|SendMessage|Send|-Establecer **nombre** a *SendMessage*|  
|ReceiveResponse|Receive|-Establecer **nombre** a *ReceiveResponse*<br />-Establecer **activar** a *False*|  
|SendResponse|Send|-Establecer **nombre** a *SendResponse*|  
  
### <a name="adding-ports"></a>Agregar puertos  
 Asegúrese de que especifique las siguientes propiedades para cada uno de los puertos lógicos. Los nombres que aparecen en la columna de puerto son los nombres de los puertos, como se muestra en la orquestación.  
  
|Puerto|Propiedades|  
|----------|----------------|  
|MessageIn|-Establecer **identificador** a *MessageIn*<br />-Establecer **tipo** a *MessageInType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *de recepción*|  
|LOBPort|-Establecer **identificador** a *LOBPort*<br />-Establecer **tipo** a *LOBPortType*<br />-Establecer **patrón de comunicación** a *solicitudes y respuestas*<br />-Establecer **dirección de comunicación** a *envío y recepción*|  
|ResponseOut|-Establecer **identificador** a *ResponseOut*<br />-Establecer **tipo** a *ResponseOutType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *enviar*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>Especificar mensajes de las formas de acción y conéctelos a los puertos  
 En la tabla siguiente especifica las propiedades y sus valores que se deben establecer para especificar los mensajes para las formas de acción y vincular los mensajes a los puertos. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación que se ha mencionado anteriormente.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *MessageIn.FOR_XML. Solicitud*|  
|SendMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *LOBPort.FOR_XML. Solicitud*|  
|ReceiveResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *LOBPort.FOR_XML. Respuesta*|  
|SendResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *ResponseOut.FOR_XML. Solicitud*|  
  
 Después de especificar estas propiedades, las formas de mensaje y los puertos que están conectados y la orquestación se completa.  
  
 Ahora debe compilar la solución de BizTalk e implementarlo en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, la orquestación que creó anteriormente se muestra en el panel de orquestaciones en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Debe utilizar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para configurar la aplicación. Para obtener un tutorial, vea [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).
  
 Configuración de una aplicación implica:  
  
-   Selección de un host de la aplicación.  
  
-   Asignación de los puertos que ha creado en la orquestación con puertos físicos en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para que esta orquestación debe:  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde se colocará un mensaje de solicitud. La orquestación de BizTalk consumirá el mensaje de solicitud y enviarla a la base de datos de SQL Server.  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta de base de datos de SQL Server.  
  
    -   Definir un puerto de envío físico de WCF-Custom o WCF-SQL para enviar mensajes a la base de datos de SQL Server. Para obtener instrucciones sobre cómo crear un puerto de envío, consulte [configurar manualmente un enlace de puerto físico para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md).
  
         También debe especificar la acción en el puerto de envío. Para conocer los procedimientos que contienen la cláusula FOR XML, debe establecer la acción en el formato siguiente.  
  
        ```  
        XmlProcedure/<schema_name>/<procedure_name>  
        ```  
  
         Por lo tanto, en este tema donde se está ejecutando el procedimiento GET_EMP_DETAILS_FOR_XML, la acción será:  
  
        ```  
        XmlProcedure/dbo/GET_EMP_DETAILS_FOR_XML  
        ```  
  
         Para obtener más información acerca de la acción de configuración, consulte [configurar la acción SOAP para el adaptador de SQL ](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md).
  
         También debe establecer las siguientes propiedades de enlace cuando se ejecuta un procedimiento almacenado con la cláusula FOR XML.  
  
        |Nombre de la propiedad de enlace|Establezca esta propiedad en|  
        |---------------------------|-----------------|  
        |XmlStoredProcedureRootNodeName|Especifique el nombre del nodo raíz que agregó en el esquema de respuesta generados para el procedimiento almacenado, tal y como se describe en la sección [generar esquema para el mensaje de respuesta para el procedimiento almacenado](#BKMK_RespSchema). De este tema, establezca esta propiedad en **raíz**.|  
        |XmlStoredProcedureRootNodeNamespace|Especifique el espacio de nombres de destino para el esquema de respuesta generados para el procedimiento almacenado, tal y como se describe en la sección [generar esquema para el mensaje de respuesta para el procedimiento almacenado](#BKMK_RespSchema). De este tema, establezca esta propiedad en `http://ForXmlStoredProcs/namespace`.|  
  
         Para obtener más información acerca de cómo especificar valores para propiedades de enlace, vea [configurar las propiedades de enlace para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).  
  
        > [!NOTE]
        >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para crear puertos de envío (para las llamadas salientes) o puertos de recepción (para las llamadas entrantes). Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto para utilizar el adaptador SQL](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).
  
## <a name="starting-the-application"></a>A partir de la aplicación  
 Debe iniciar la aplicación de BizTalk para invocar procedimientos en la base de datos de SQL Server. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md).
  
 En esta fase, asegúrese de que:  
  
-   El archivo de puerto de recepción para recibir mensajes de solicitud de ejecución de la orquestación.  
  
-   El puerto de envío de archivo para recibir los mensajes de respuesta de la orquestación se está ejecutando.  
  
-   El puerto de envío WCF-Custom o WCF-SQL para enviar mensajes a la base de datos de SQL Server se está ejecutando.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, debe quitar un mensaje de solicitud en el archivo de ubicación de recepción. El esquema del mensaje de solicitud debe ajustarse al esquema de solicitud para el procedimiento generados mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Por ejemplo, el mensaje de solicitud para invocar el XML de GET_EMP_DETAILS_FOR es:  
  
```  
<GET_EMP_DETAILS_FOR_XML xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/dbo">  
  <emp_id>10765</emp_id>  
</GET_EMP_DETAILS_FOR_XML>  
```  
  
 Vea [esquemas de mensaje para los procedimientos y funciones](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md) para obtener más información acerca del esquema de mensaje de solicitud para invocar procedimientos de SQL Server de base de datos mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
 La orquestación consume el mensaje y lo envía a la base de datos de SQL Server. La respuesta de base de datos de SQL Server se guarda en la otra ubicación de archivo definida como parte de la orquestación. Por ejemplo, la respuesta de la base de datos de SQL Server para el mensaje de solicitud anterior es:  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<Root xmlns="http://ForXmlStoredProcs/namespace">  
  <Adapt_Doc.dbo.Employee Employee_ID="10765" Name="John" Designation="asdfaf" Salary="3434.00" Last_Modified="AAAAAAAANso=" Status="0" xmlns="" />  
</Root>  
```  
  
 Tenga en cuenta que se recibe la respuesta en el mismo esquema, tal y como se generan al ejecutar el procedimiento almacenado. Tenga en cuenta también que el nodo raíz y el espacio de nombres es el mismo que especificó como valores para **XmlStoredProcedureRootNodeName** y **XmlStoredProcedureRootNodeNamespace** propiedades de enlace respectivamente.  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez haya implementado y configurado el proyecto de BizTalk, puede exportar la configuración en un archivo XML denominado archivo de enlace. Una vez que se genera un archivo de enlace, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear elementos, como los puertos de envío y puertos de recepción para la misma orquestación. Para obtener más información acerca de los archivos de enlace, vea [reutilizar enlaces del adaptador](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md).  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)