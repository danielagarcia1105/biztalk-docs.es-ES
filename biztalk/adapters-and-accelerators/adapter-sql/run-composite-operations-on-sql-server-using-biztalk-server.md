---
title: Ejecutar operaciones compuestas en SQL Server con BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86fd2aa1-20c7-4b58-9f35-83ba0c959cf1
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f6891f300a89684481184bf255f3cdd54d25845
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="run-composite-operations-on-sql-server-using-biztalk-server"></a>Ejecutar operaciones compuestas en SQL Server con BizTalk Server
El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] permite a los clientes de adaptador realizar operaciones compuestas en la base de datos de SQL Server. Puede incluir una operación compuesta:  
  
-   Insertar, actualizar y eliminar operaciones. No se admite una operación de selección como parte de una operación compuesta.  
  
-   Procedimientos almacenados ejecutados como operaciones.  
  
 Una única operación compuesta puede tener cualquier número de estas operaciones, en cualquier orden. Por ejemplo, puede tener dos operaciones de inserción seguidas de una operación de eliminación y, finalmente, la ejecución de un procedimiento almacenado. Además, puede tener diferentes operaciones de base de datos diferentes tablas o vistas de destino. Para obtener más información acerca del modo en que el adaptador admite operaciones compuestas, consulte [ejecutar operaciones compuestas en SQL Server mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/run-composite-operations-in-sql-server-using-the-sql-adapter.md). Para obtener información acerca de la estructura del mensaje SOAP para operaciones compuestas, consulte [esquemas de mensaje para operaciones compuestas](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md).  
  
> [!NOTE]
>  Si va a realizar la operación en tablas con columnas de tipos definidos por el usuario, asegúrese de que hace referencia a [operaciones en tablas y vistas con tipos definidos por el usuario mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) antes de empezar a desarrollar la aplicación.  
  
## <a name="how-to-perform-composite-operations-on-sql-server"></a>Cómo realizar operaciones compuestas en SQL Server  
 Realizar una operación en SQL Server mediante la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica procedimientos tareas que se describen en [bloques de creación para desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md). Para llevar a cabo operaciones compuestas en la base de datos de SQL Server, estas tareas son:  
  
1.  Crear un proyecto de BizTalk y genere el esquema para todas las operaciones que desea invocar.  
  
2.  Crear manualmente un archivo de esquema que incluya referencias a todos los esquemas generados en el paso anterior.  
  
3.  Crear mensajes en el proyecto de BizTalk para enviar y recibir mensajes de la base de datos de SQL Server. Estos mensajes deben cumplir el esquema de solicitud y respuesta que ha creado en el paso anterior.  
  
4.  Crear una orquestación para invocar la operación compuesta en la base de datos de SQL Server.  
  
5.  Compilar e implementar el proyecto de BizTalk.  
  
6.  Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
7.  Inicie la aplicación de BizTalk.  
  
 Este tema proporciona instrucciones sobre cómo realizar estas tareas.  
  
## <a name="sample-based-on-this-topic"></a>Ejemplo basado en este tema  
 Un ejemplo, CompositeOperations, basado en este tema se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).  
  
## <a name="generating-schema"></a>Generar el esquema  
 En este tema, para demostrar cómo realizar operaciones compuestas, las siguientes tareas se realizará en el orden especificado:  
  
-   Insertar registro en la tabla de empleados.  
  
-   Recuperar todas las columnas para el último registro insertado invocando el procedimiento almacenado de GET_LAST_EMP_DATA.  
  
-   Elimine el registro de la tabla de empleados.  
  
 Ejecute los scripts que se proporciona con los ejemplos para crear la tabla de empleados. Para obtener más información acerca de los ejemplos, vea [ejemplos de esquema](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md).  
  
 Debe crear un proyecto de BizTalk y utilizar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar el esquema para estas operaciones. Vea [recuperación de metadatos para operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md) para obtener más información acerca de cómo generar esquemas.  
  
## <a name="creating-a-composite-schema-definition"></a>Crear una definición de esquema compuesto  
 Ahora debe crear un esquema compuesto que hace referencia a los esquemas creados para las operaciones individuales. Realice los pasos siguientes para crear una definición de esquema compuesto.  
  
#### <a name="to-add-a-composite-schema-definition"></a>Para agregar una definición de esquema compuesto  
  
1.  Agregue un archivo de esquema al proyecto de BizTalk. Haga clic en el nombre del proyecto, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**. En el **Agregar nuevo elemento** cuadro de diálogo, desde el **categorías** cuadro, haga clic en **archivos de esquema**. Desde el **plantillas** cuadro, haga clic en **esquema**. Especifique un nombre para el archivo de esquema y, a continuación, haga clic en **Aceptar**.  
  
     En este ejemplo, especifique el nombre de archivo de esquema como `CompositeSchema.xsd`.  
  
2.  Agregar referencias para el esquema generado para las diferentes operaciones que desea realizar. En este ejemplo, los distintos esquemas generados para las operaciones son:  
  
    -   TableOperation.dbo.Employee.xsd, para las operaciones de inserción y eliminación.  
  
    -   Procedure.dbo.xsd, para el GET_LAST_EMP_DATA procedimiento almacenado.  
  
     Para agregar referencias:  
  
    1.  Haga clic en la raíz  **\<esquema\>**  nodo en el CompositeSchema.xsd y haga clic en **propiedades**.  
  
    2.  En el **propiedad** cuadro, haga clic en el botón de puntos suspensivos **(...)**  contra la **importaciones** propiedad.  
  
         ![Importar definiciones de esquema](../../adapters-and-accelerators/adapter-oracle-database/media/d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca.gif "d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca")  
  
    3.  En el **importaciones** cuadro de diálogo, desde el **importar un esquema nuevo como** lista, seleccione **XSD Import**y, a continuación, haga clic en **agregar**.  
  
    4.  En el **selector de tipos de BizTalk** cuadro de diálogo, expanda el nodo de nombre de proyecto de BizTalk, expanda **esquemas**y, a continuación, seleccione el esquema que desea importar. En este ejemplo, seleccione < BizTalk_project_name >. TableOperation_dbo_Employee. Haga clic en **Aceptar**.  
  
         Repita este paso para importar < BizTalk_project_name >. Procedure_dbo demasiado.  
  
    5.  En el **importaciones** cuadro de diálogo, haga clic en **Aceptar**.  
  
3.  Agregue dos nodos secundarios al nodo de esquema raíz. Un nodo secundario corresponde al esquema de solicitud para realizar la operación compuesta. El otro nodo secundario corresponde al esquema de respuesta. El nodo que se corresponde con el esquema de solicitud puede tener cualquier nombre. El nodo que se corresponde con el esquema de respuesta debe llamarse < request_schema_node > respuesta. En este ejemplo, llamaremos al nodo de esquema de solicitud como **solicitud**. Por lo tanto, el nodo de esquema de respuesta se denomina **RequestResponse**.  
  
    > [!NOTE]
    >  De forma predeterminada, un **raíz** nodo también se agrega a un nuevo archivo de esquema. Puede cambiar el nombre de la **raíz** nodo **solicitar**. Para cambiar el nombre de un nodo, haga clic en el nombre del nodo y haga clic en **cambiar el nombre de**.  
  
     Para agregar un nodo en el  **\<esquema\>**  nodo:  
  
    1.  Haga clic en el  **\<esquema\>**  nodo, seleccione **Insertar nodo de esquema**y haga clic en **registro secundario**.  
  
    2.  Cambiar el nombre del nuevo nodo a **RequestResponse**.  
  
4.  Agregar nodos secundarios en el **solicitud** nodo que se corresponden con el esquema de solicitud para cada operación que llevarán a cabo como parte de la operación de composición. En este ejemplo, debe agregar los nodos secundarios correspondientes a la siguiente:  
  
    -   Insertar y eliminar operaciones en la tabla de empleados.  
  
    -   GET_LAST_EMP_DATA el procedimiento almacenado.  
  
    > [!IMPORTANT]
    >  Debe agregar los nodos en el mismo orden en el que desea realizar las operaciones. Por ejemplo, si desea insertar un registro, a continuación, ejecutar un procedimiento almacenado y, a continuación, eliminar un registro en primer lugar debe agregar un nodo para la operación de inserción, seguido de un nodo para el procedimiento almacenado y, finalmente, un nodo para la operación de eliminación.  
  
     Para agregar los nodos secundarios para el **solicitar** nodo:  
  
    1.  Haga clic en el **solicitar** nodo, seleccione **Insertar nodo de esquema**y, a continuación, haga clic en **registro secundario**.  
  
         ![Insertar nodos secundarios para un esquema](../../adapters-and-accelerators/adapter-oracle-database/media/58992131-13a6-45c3-9513-5c0995091fae.gif "58992131-13a6-45c3-9513-5c0995091fae")  
  
    2.  Cambie el nombre del registro para que correspondan a un esquema de solicitud para una operación que se realiza como parte de la operación de composición. Por ejemplo, cambie el nombre del nodo para "Insertar".  
  
    3.  Mapa de la **insertar** nodo el esquema de solicitud para la operación de inserción en la tabla de empleados. Para ello, haga clic en el **insertar** nodo y haga clic en **propiedades**. En el **propiedades** cuadro, desde el **Data Structure Type** lista, seleccione **Insert (referencia)**.  
  
         ![Asignar nodos secundarios al esquema de solicitud](../../adapters-and-accelerators/adapter-sql/media/5ace18be-0fe8-44c6-bd2f-cb19035494b5.gif "5ace18be-0fe8-44c6-bd2f-cb19035494b5")  
  
    4.  Repita estos pasos para agregar nodos de los esquemas de solicitud de procedimiento almacenado de GET_LAST_EMP_DATA y la operación de eliminación. Especifique los nombres de nodo y asignarlos al esquema correspondiente, como se mencionó en la tabla siguiente.  
  
        |Nombre de nodo|Asignado al esquema|  
        |---------------|----------------------|  
        |GET_LAST_EMP_DATA|GET_LAST_EMP_DATA (referencia)|  
        |DELETE|Delete (referencia)|  
  
5.  Agregar nodos secundarios en el **RequestResponse** nodo que se corresponden con el esquema de respuesta para cada operación que llevarán a cabo como parte de la operación de composición. En este ejemplo, debe agregar los nodos secundarios correspondientes a la siguiente:  
  
    -   Insertar y eliminar operaciones en la tabla de empleados.  
  
    -   GET_LAST_EMP_DATA el procedimiento almacenado.  
  
    > [!IMPORTANT]
    >  Debe agregar los nodos secundarios en el mismo orden que los nodos secundarios bajo el **solicitar** nodo.  
  
     Para agregar los nodos secundarios para el **RequestResponse** nodo:  
  
    1.  Haga clic en el **RequestResponse** nodo, seleccione **Insertar nodo de esquema**y haga clic en **registro secundario**.  
  
    2.  Cambie el nombre del registro para que correspondan a un esquema de respuesta para una operación que se realiza como parte de la operación de composición. Por ejemplo, cambie el nombre del nodo para "InsertResponse".  
  
    3.  Mapa de la **InsertResponse** nodo el esquema de respuesta para la operación de inserción en la tabla de empleados. Para ello, haga clic en el **InsertResponse** nodo y haga clic en **propiedades**. En el **propiedades** cuadro, desde el **Data Structure Type** lista, seleccione **InsertResponse (referencia)**.  
  
    4.  Repita estos pasos para agregar nodos de los esquemas de respuesta para el procedimiento almacenado de GET_LAST_EMP_DATA y la operación de eliminación. Especifique los nombres de nodo y asignarlos al esquema correspondiente, como se mencionó en la tabla siguiente.  
  
        |Nombre de nodo|Asignado al esquema|  
        |---------------|----------------------|  
        |GET_LAST_EMP_DATAResponse|GET_LAST_EMP_DATAResponse (referencia)|  
        |DeleteResponse|DeleteResponse (referencia)|  
  
6.  Guardar el **CompositeSchema.xsd** archivo.  
  
## <a name="defining-messages-and-message-types"></a>Definición de mensajes y tipos de mensaje  
 El esquema compuesto que creó en el último paso describe los "tipos" necesarios para los mensajes de una orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Ahora debe crear mensajes de la orquestación y vincularlos a esquema que ha creado en el paso anterior.  
  
#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vincular al esquema  
  
1.  Agregar una orquestación al proyecto de BizTalk. En el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**. Escriba un nombre para la orquestación de BizTalk y, a continuación, haga clic en **agregar**.  
  
2.  Abra la ventana Vista orquestación del proyecto de BizTalk, si no está ya abierto. Para ello, haga clic en **vista**, seleccione **otras ventanas**y, a continuación, haga clic en **Vista orquestación**.  
  
3.  En Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
4.  Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  
  
5.  En el **propiedades** panel para la **Message_1**, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Escriba `Request`|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *CompositeOp.CompositeSchema.Request*, donde CompositeOp es el nombre de su proyecto de BizTalk. CompositeSchema es el esquema que haya creado manualmente para las operaciones compuestas.|  
  
6.  Repita el paso 2 para crear un nuevo mensaje. En el **propiedades** panel para el nuevo mensaje, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Escriba `Response`|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *CompositeOp.CompositeSchema.RequestResponse*.|  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para usar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para llevar a cabo operaciones compuestas en SQL Server. En esta orquestación, se coloca un mensaje de solicitud en una determinada ubicación de recepción. El mensaje de solicitud debe ajustarse al esquema compuesto que creó anteriormente. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] consume este mensaje y lo pasa al SQL Server. La respuesta de SQL Server se guarda en otra ubicación. Debe incluir el envío y recepción formas para enviar mensajes a SQL Server y recibir respuestas, respectivamente. Una orquestación básica para realizar operaciones compuestas es similar al siguiente:  
  
 ![Orquestación para efectuar operaciones compuestas](../../adapters-and-accelerators/adapter-oracle-database/media/4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb.gif "4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb")  
  
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
|ReceiveMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *MessageIn.CompositeOp.Request*|  
|SendMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *LOBPort.CompositeOp.Request*|  
|ReceiveResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *LOBPort.CompositeOp.Response*|  
|SendResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *ResponseOut.CompositeOp.Request*|  
  
 Después de especificar estas propiedades, las formas de mensaje y los puertos que están conectados y la orquestación se completa.  
  
 Ahora debe compilar la solución de BizTalk e implementarlo en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, la orquestación que creó anteriormente se muestra en el panel de orquestaciones en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Debe utilizar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para configurar la aplicación. Para obtener un tutorial, vea [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).
  
 Configuración de una aplicación implica:  
  
-   Selección de un host de la aplicación.  
  
-   Asignación de los puertos que ha creado en la orquestación con puertos físicos en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para que esta orquestación debe:  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde se colocará un mensaje de solicitud. La orquestación de BizTalk consumirá el mensaje de solicitud y enviarla a la base de datos de SQL Server.  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta de la base de datos de SQL Server.  
  
    -   Definir un puerto de envío físico de WCF-Custom o WCF-SQL para enviar mensajes a la base de datos de SQL Server. Dado que las operaciones que están radica como parte de la operación compuesta se ejecutan en una sola transacción, asegúrese de que el **UseAmbientTransaction** enlaza la propiedad se establece en **True**.  
  
         También debe especificar la acción en el puerto de envío. La acción para una operación compuesta es "**CompositeOperation**". Para obtener información sobre cómo crear puertos, consulte [configurar manualmente un enlace de puerto físico para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md). Para obtener más información sobre cómo especificar acciones para los puertos, consulte [configurar la acción SOAP para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md).
  
        > [!NOTE]
        >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para crear puertos de envío (para las llamadas salientes) o puertos de recepción (para las llamadas entrantes). Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto para utilizar el adaptador SQL](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md). Si importa este archivo de enlace, se establece la acción en el puerto de envío WCF-Custom o WCF-SQL en una acción dinámica relacionadas con todas las operaciones que seleccionó en el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] al generar el esquema. Para una operación compuesta, debe reemplazar la acción dinámica con "CompositeOperation".  
  
## <a name="starting-the-application"></a>A partir de la aplicación  
 Debe iniciar la aplicación de BizTalk para realizar operaciones compuestas en la base de datos de SQL Server. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md).
  
 En esta fase, asegúrese de que:  
  
-   El archivo de puerto de recepción para recibir mensajes de solicitud de ejecución de la orquestación.  
  
-   El puerto de envío de archivo para recibir los mensajes de respuesta de la orquestación se está ejecutando.  
  
-   El puerto de envío WCF-Custom o WCF-SQL para enviar mensajes a la base de datos de SQL Server se está ejecutando.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, debe quitar un mensaje de solicitud en el archivo de ubicación de recepción. El esquema del mensaje de solicitud debe cumplir el esquema para las operaciones compuestas que creó anteriormente. Por ejemplo, un mensaje de solicitud que inserta un registro en la tabla de empleados, invoca el procedimiento almacenado de GET_LAST_EMP_DATA y elimina un registro de la tabla de empleados es:  
  
```  
<Request xmlns="http://CompositeTest.CompositeSchema">  
  <Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <Rows>  
      <Employee xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
        <Name>John</Name>  
        <Designation>Manager</Designation>  
        <Salary>100000</Salary>  
      </Employee>  
    </Rows>  
  </Insert>  
  <GET_LAST_EMP_DATA xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/dbo" />  
  <Delete xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <Rows>  
      <Employee xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
        <Name>John</Name>  
      </Employee>  
    </Rows>  
  </Delete>  
</Request>  
```  
  
 Vea [esquemas de mensaje para operaciones compuestas](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md) para obtener más información acerca del esquema de mensaje de solicitud para llevar a cabo operaciones compuestas en el servidor SQL Server de base de datos mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
 La orquestación consume el mensaje y lo envía a la base de datos de SQL Server. La respuesta de la base de datos de SQL Server se guarda en la otra ubicación de archivo definida como parte de la orquestación. Por ejemplo, la respuesta de la base de datos de SQL Server para el mensaje de solicitud anterior es:  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<RequestResponse xmlns="http://CompositeTest.CompositeSchema">  
  <InsertResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <InsertResult>  
      <long xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">10080</long>   
    </InsertResult>  
  </InsertResponse>  
  <GET_LAST_EMP_DATAResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/dbo">  
    <GET_LAST_EMP_DATAResult>  
      <DataSet xmlns="http://schemas.datacontract.org/2004/07/System.Data">  
        <xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
          <xs:element msdata:IsDataSet="true" name="NewDataSet">  
            <xs:complexType>  
              <xs:sequence>  
                <xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                  <xs:complexType>  
                    <xs:sequence>  
                      <xs:element minOccurs="0" name="Employee_ID" type="xs:int" />   
                      <xs:element minOccurs="0" name="Name" type="xs:string" />   
                      <xs:element minOccurs="0" name="DOJ" type="xs:dateTime" />   
                      <xs:element minOccurs="0" name="Designation" type="xs:string" />   
                      <xs:element minOccurs="0" name="Job_Description" type="xs:string" />   
                      <xs:element minOccurs="0" name="Photo" type="xs:base64Binary" />   
                      <xs:element minOccurs="0" name="Rating" type="xs:string" />   
                      <xs:element minOccurs="0" name="Salary" type="xs:decimal" />   
                      <xs:element minOccurs="0" name="Last_Modified" type="xs:base64Binary" />   
                    </xs:sequence>  
                  </xs:complexType>  
                </xs:element>  
              </xs:sequence>  
            </xs:complexType>  
          </xs:element>  
        </xs:schema>  
        <diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
          <NewDataSet xmlns="">  
            <NewTable>  
              <Employee_ID>10080</Employee_ID>   
              <Name>John</Name>   
              <Designation>Manager</Designation>   
              <Salary>100000.00</Salary>   
              <Last_Modified>AAAAAAAAF40=</Last_Modified>   
            </NewTable>  
          </NewDataSet>  
        </diffgr:diffgram>  
      </DataSet>  
    </GET_LAST_EMP_DATAResult>  
    <ReturnValue>0</ReturnValue>   
  </GET_LAST_EMP_DATAResponse>  
  <DeleteResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <DeleteResult>1</DeleteResult>   
  </DeleteResponse>  
</RequestResponse>  
```  
  
 La respuesta anterior contiene varios conjuntos de resultados correspondiente a las diferentes operaciones realizadas como parte de la operación de composición. Por ejemplo, el `InsertResult` elemento contiene 10080, que es el identificador único para el registro recién agregado.  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez haya implementado y configurado el proyecto de BizTalk, puede exportar la configuración en un archivo XML denominado archivo de enlace. Una vez que se genera un archivo de enlace, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear elementos, como los puertos de envío y puertos de recepción para la misma orquestación. Para obtener más información acerca de los archivos de enlace, vea [reutilizar enlaces del adaptador](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md).
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)