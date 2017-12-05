---
title: Recibir notificaciones de consulta de forma incremental de SQL con BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6972e01-80be-47be-986a-c2e4e0fb0cd1
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fc9eda3ba1bee61b4737428f41870fc31504e3a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="receive-query-notifications-incrementally-from-sql-using-biztalk-server"></a>Recibir notificaciones de consulta de forma incremental de SQL con BizTalk Server
> [!IMPORTANT]
>  Por brevedad, en este tema solo se describe cómo recibir las notificaciones de forma incremental. En escenarios empresariales, la orquestación lo ideal es que debe incluir la lógica para extraer el tipo de mensaje de notificación recibido y, a continuación, realizar las operaciones siguientes. En otras palabras, se debe crear la orquestación se describe en este tema sobre la orquestación se describe en [procesar mensajes de notificación para completar tareas específicas en SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md).  
  
 Este tema muestra cómo configurar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir mensajes de notificación de consulta incremental de una base de datos de SQL Server. Para mostrar notificaciones incrementales, considere la posibilidad de una tabla de empleados, con una columna de "Status". Cuando se inserta un nuevo registro en esta tabla, el valor de la columna de estado se establece en 0. Puede configurar el adaptador para recibir notificaciones incrementales haciendo lo siguiente:  
  
-   Registrarse para notificaciones mediante una instrucción SQL que recupera todos los registros que tienen la columna de estado como 0. Puede hacerlo mediante la especificación de la instrucción SQL para la **NotificationStatement** propiedad de enlace.  
  
-   Si las filas para la notificación de que se han recibido mensajes, actualice la columna de estado en 1.  
  
 Este tema muestra cómo crear una orquestación de BizTalk y configurar una aplicación de BizTalk para lograr esto.  
  
## <a name="configuring-notifications-with-the-sql-adapter-binding-properties"></a>Configuración de notificaciones con el adaptador SQL propiedades de enlace  
 La siguiente tabla resume el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] propiedades de enlace que se utiliza para configurar la recepción de notificaciones de SQL Server. Debe especificar estas propiedades de enlace al configurar el puerto de recepción en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
> [!NOTE]
>  Puede especificar estas propiedades de enlace al generar el esquema para el **notificación** operación, aunque no es obligatorio. Si lo hace, el enlace de puerto de archivos que el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] genera como parte de la generación de metadatos también contiene los valores especificados para las propiedades de enlace. Más adelante puede importar este archivo de enlace en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] puerto de recepción de la consola de administración para crear el WCF-custom o WCF-SQL con el enlace de propiedades ya establecidas. Para obtener más información acerca de cómo crear un puerto mediante el archivo de enlace, vea [configurar un enlace de puerto físico mediante un archivo de enlace de puerto para utilizar el adaptador SQL](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).  
  
|Propiedad de enlace|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|Especifica la operación de entrada que se desea realizar. Para recibir mensajes de notificación, establezca esta propiedad en **notificación**.|  
|**NotificationStatement**|Especifica la instrucción SQL (SELECT o EXEC \<procedimiento almacenado\>) usa para registrar las notificaciones de consulta. El adaptador obtiene un mensaje de notificación de SQL Server sólo cuando el conjunto de resultados para que los cambios de instrucción SQL especificados.|  
|**NotifyOnListenerStart**|Especifica si el adaptador envía una notificación a los clientes de adaptador cuando se inicia el agente de escucha.|  
  
 Para obtener una descripción más completa de estas propiedades, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md). Para obtener una descripción completa de cómo usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir notificaciones de SQL Server, seguir leyendo.  
  
## <a name="how-this-topic-demonstrates-receiving-notification-messages"></a>Cómo en este tema se muestra cómo recibir mensajes de notificación  
 Para demostrar cómo [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] permite recibir mensajes de notificación de SQL Server, en este tema se demuestra cómo configurar el adaptador para recibir notificaciones de cambios en una tabla de empleados. Suponga que la tabla Employee tiene columnas IdDeEmpleado, el nombre y el estado. Cada vez que se agrega un nuevo empleado, el valor de la columna de estado se establece en 0.  
  
 Para demostrar la recepción de notificaciones, haga lo siguiente:  
  
-   Genere el esquema para el **notificación** (operación de entrada), y **seleccione** (operación saliente) en la tabla de empleados.  
  
-   Crear una orquestación que incluye lo siguiente:  
  
    -   Una ubicación de recepción para recibir mensajes de notificación. Puede configurar para la notificación mediante la especificación de la instrucción SELECT como:  
  
        ```  
        SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0  
        ```  
  
        > [!NOTE]
        >  En concreto, debe especificar los nombres de columna en la instrucción tal como se muestra en esta instrucción SELECT. Además, siempre debe especificar el nombre de la tabla junto con el nombre del esquema. Por ejemplo, `dbo.Employee`.  
  
    -   Un puerto de envío para actualizar las filas para el que ya se ha enviado notificación. Hacerlo estableciendo el valor en la columna de estado en 1. Para hacer esto como parte de la operación seleccionada enviando el mensaje siguiente al adaptador.  
  
        ```  
        <Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
          <Columns>Employee_ID,Name,Status</Columns>  
          <Query>where Status=0;UPDATE Employee SET Status=1 WHERE Status=0</Query>  
        </Select>  
        ```  
  
         En este mensaje, como parte de la `<Query>` elemento, especifica la instrucción UPDATE para actualizar la columna de estado. Tenga en cuenta que esta operación debe ejecutarse después de recibir la notificación de mensajes para que se actualicen las filas procesadas. Para hacer inmediatamente con la sobrecarga de espera para obtener la respuesta de notificación y, a continuación, quitar manualmente un mensaje de solicitud para actualizar las filas, se generará el mensaje de solicitud para actualizar las filas dentro de la propia orquestación. Puede hacerlo mediante el **construir mensaje** forma dentro de una orquestación.  
  
## <a name="how-to-receive-notification-messages-from-the-sql-server-database"></a>Cómo recibir mensajes de notificación de la base de datos SQL Server  
 Realizar una operación en la base de datos de SQL Server mediante [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] conlleva las tareas de procedimientos descritas en [bloques de creación para desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md). Para configurar el adaptador para recibir mensajes de notificación, estas tareas son:  
  
1.  Crear un proyecto de BizTalk y, a continuación, genere el esquema para el **notificación** (operación entrante) y **seleccione** (operación saliente) en la tabla de empleados. Si lo desea, puede especificar valores para la **InboundOperationType** y **NotificationStatement** propiedades de enlace.  
  
2.  Cree un mensaje en el proyecto de BizTalk para recibir notificaciones de la base de datos de SQL Server.  
  
3.  Crear mensajes en el proyecto de BizTalk para la realización de la información seleccionada en la base de datos de SQL Server y recibir mensajes de respuesta.  
  
4.  Crear una orquestación que realiza lo siguiente:  
  
    -   Recibe el mensaje de notificación de SQL Server.  
  
    -   Crea un mensaje para seleccionar y actualizar las filas para el que se recibe la notificación.  
  
    -   Envía este mensaje para el servidor SQL Server para actualizar las filas y recibe una respuesta.  
  
5.  Compilar e implementar el proyecto de BizTalk.  
  
6.  Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
    > [!NOTE]
    >  Para las operaciones de entrada, como recibir mensajes de notificación, solo se debe configurar un unidireccional WCF-Custom o puerto de recepción de WCF-SQL. Puertos de recepción bidireccional WCF-Custom o WCF-SQL no se admiten operaciones de entrada.  
  
7.  Inicie la aplicación de BizTalk.  
  
 Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="sample-based-on-this-topic"></a>Ejemplo basado en este tema  
 Un ejemplo, IncrementalNotification, basado en este tema se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).  
  
## <a name="generating-schema"></a>Generar el esquema  
 Debe generar el esquema para el **notificación** operación y **seleccione** operación en la tabla de empleados. Vea [obtener los metadatos de las operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md) para obtener más información acerca de cómo generar el esquema. Realice las tareas siguientes al generar el esquema. Omitir el primer paso si no desea especificar las propiedades de enlace en tiempo de diseño.  
  
1.  Especifique un valor para **InboundOperationType** y **NotificationStatement** propiedades de enlace al generar el esquema. Para obtener más información acerca de esta propiedad de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md). Para obtener instrucciones sobre cómo especificar las propiedades de enlace, consulte [configurar las propiedades de enlace para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).  
  
2.  Seleccione el tipo de contrato **(operaciones de entrada) de servicio**.  
  
3.  Genere el esquema para el **notificación** operación.  
  
4.  Seleccione el tipo de contrato **Client (Outbound operations)**.  
  
5.  Genere el esquema para el **seleccione** operación en **empleado** tabla.  
  
## <a name="defining-messages-and-message-types"></a>Definición de mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes en la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Una vez que se genera el esquema, debe vincular a los mensajes desde la vista de orquestación de BizTalk del proyecto.  
  
 En este tema, debe crear tres mensajes: uno para recibir notificaciones de la base de datos de SQL Server, uno para realizar la operación de selección y otro para recibir la respuesta para la operación de selección.  
  
 Realice los pasos siguientes para crear mensajes y vincularlas a esquema.  
  
#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vincular al esquema  
  
1.  Agregar una orquestación al proyecto de BizTalk. En el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**. Escriba un nombre para la orquestación de BizTalk y, a continuación, haga clic en **agregar**.  
  
2.  Abra la ventana de vista de orquestación de BizTalk del proyecto, si no está ya abierto. Haga clic en **vista**, seleccione **otras ventanas**y, a continuación, haga clic en **Vista orquestación**.  
  
3.  En el **Vista orquestación**, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
4.  Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  
  
5.  En el **propiedades** panel para **Message_1**, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Type `NotifyReceive`.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *SQLNotify.Notification*, donde *SQLNotify* es el nombre de su proyecto de BizTalk. *Notificación* es el esquema generado para el **notificación** operación.|  
  
6.  Repita el paso 3 para crear dos nuevos mensajes. En el **propiedades** panel para el nuevo mensaje, haga lo siguiente:  
  
    |Identificador de conjunto a|Establecer el tipo de mensaje en|  
    |-----------------------|-------------------------|  
    |Select|*SQLNotify.TableOperation_dbo_Employee.Select*, donde *TableOperation_dbo_Employee* es el esquema generado para el **seleccione** operación|  
    |SelectResponse|*SQLNotify.TableOperation_dbo_Employee.SelectResponse*|  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para usar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para recibir mensajes de notificación de la base de datos de SQL Server y, a continuación, actualizar las filas para el que ha recibido la notificación. En esta orquestación, el adaptador recibe el mensaje de notificación basado en la instrucción SELECT especificada para la **NotificationStatement** propiedad de enlace. El mensaje de notificación se recibe en una ubicación de archivo. Una vez que se recibe la respuesta, la orquestación construye un mensaje que se usará para actualizar las filas para el que se recibe la notificación. También se recibe la respuesta para este mensaje en la misma ubicación de archivo.  
  
 Por lo tanto, la orquestación debe contener lo siguiente:  
  
-   Un unidireccional puerto de recepción para recibir mensajes de notificación.  
  
-   Puerto para enviar mensajes a actualizar las filas y recibir la respuesta para el mismo de envío bidireccional.  
  
-   A **construir mensaje** forma para construir mensajes, para ejecutar la operación de actualización, en la orquestación.  
  
-   Un archivo de puerto de envío para guardar la respuesta para la operación de actualización.  
  
-   Formas de envío y recepción.  
  
 Una orquestación de ejemplo es similar al siguiente.  
  
 ![Orquestación para recibir notificaciones de SQL Server](../../adapters-and-accelerators/adapter-sql/media/f13ad3b8-8161-42e5-a521-424bbf549ad5.gif "f13ad3b8-8161-42e5-a521-424bbf549ad5")  
  
### <a name="adding-message-shapes"></a>Agregar formas de mensaje  
 Asegúrese de que especifique las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación just-mencionado.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ReceiveNotification|Receive|-Establecer **nombre** a *ReceiveNotification*<br /><br /> -Establecer **activar** a *es True*|  
|SaveNotification|Send|-Establecer **nombre** a *SaveNotification*|  
|SendSelectMessage|Send|-Establecer **nombre** a *SendSelectMessage*|  
|ReceiveSelectResponse|Receive|-Establecer **nombre** a *ReceiveSelectResponse*|  
|SaveSelectResponse|Send|-Establecer **nombre** a *SaveSelectResponse*|  
  
### <a name="adding-construct-message-shape"></a>Agregar forma construir mensaje  
 Puede usar el **construir mensaje** forma para generar un mensaje de solicitud dentro de la operación para realizar la operación de selección. Para ello, debe agregar una **construir mensaje** forma y en el que un **asignación de mensajes** forma a la orquestación. En este ejemplo, el **asignación de mensajes** forma invoca el código que genera un mensaje que se envía a SQL Server para realizar la operación de selección. El **asignación de mensajes** forma también establece la acción para el mensaje que se enviará a SQL Server.  
  
 Para la forma construir mensaje, establezca la **construir mensaje** propiedad **seleccione**.  
  
 El código para generar la respuesta podría ser parte de la misma solución de Visual Studio que el proyecto de BizTalk. Un código de ejemplo para generar un mensaje de respuesta tiene el siguiente aspecto.  
  
```  
namespace SampleMessageCreator  
{  
    public class SampleMessageCreator  
    {  
        private static XmlDocument Message;  
        private static string XmlFileLocation;  
        private static string ResponseDoc;  
        public static XmlDocument XMLMessageCreator()  
        {  
            XmlFileLocation = "C:\\TestLocation\\CreateMessage";  
            try  
            {  
                ResponseDoc = (Directory.GetFiles(XmlFileLocation, "*.xml", SearchOption.TopDirectoryOnly))[0];  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Trying to get XML from: " + XmlFileLocation);  
                Console.WriteLine("EXCEPTION: " + ex.ToString());  
                throw ex;  
            }  
            //Create Message From XML  
            Message = new XmlDocument();  
            Message.PreserveWhitespace = true;  
            Message.Load(ResponseDoc);  
            return Message;  
        }   
    }  
}  
```  
  
 Para que el fragmento de código anterior para que pueda generar un mensaje de solicitud, debe tener un mensaje de solicitud XML (para la operación de selección en la tabla de empleados) en la ubicación especificada para el `XmlFileLocation` variable.  
  
> [!NOTE]
>  Después de compilar el proyecto, SampleMessageCreator.dll se creará en el directorio del proyecto. Debe agregar este archivo DLL a la caché de ensamblados global (GAC). Además, debe agregar el SampleMessageCreator.dll como una referencia en el proyecto de BizTalk.  
  
 Agregue la siguiente expresión para invocar este código desde el **asignación de mensajes** forma y establecer la acción para el mensaje. Para agregar una expresión, haga doble clic en el **asignación de mensajes** forma para abrir el Editor de expresiones.  
  
```  
Select = SampleMessageCreator.SampleMessageCreator.XMLMessageCreator();  
Select(WCF.Action) = "TableOp/Select/dbo/Employee";  
```  
  
### <a name="adding-ports"></a>Agregar puertos  
 Asegúrese de que especifique las siguientes propiedades para cada uno de los puertos lógicos. Los nombres que aparecen en la columna de puerto son los nombres de los puertos, como se muestra en la orquestación.  
  
|Puerto|Propiedades|  
|----------|----------------|  
|SQLNotifyPort|-Establecer **identificador** a *SQLNotifyPort*<br /><br /> -Establecer **tipo** a *SQLNotifyPortType*<br /><br /> -Establecer **patrón de comunicación** a *unidireccional*<br /><br /> -Establecer **dirección de comunicación** a *de recepción*|  
|SaveMessagePort|-Establecer **identificador** a *SaveMessagePort*<br /><br /> -Establecer **tipo** a *SaveMessagePortType*<br /><br /> -Establecer **patrón de comunicación** a *unidireccional*<br /><br /> -Establecer **dirección de comunicación** a *enviar*<br /><br /> -Crear una operación *notificar*. Esta operación se usa para mensajes de notificación.<br /><br /> -Crear una operación *seleccione*. Esta operación se usa para los mensajes de respuesta de select.|  
|SQLOutboundPort|-Establecer **identificador** a *SQLOutboundPort*<br /><br /> -Establecer **tipo** a *SQLOutboundPortType*<br /><br /> -Establecer **patrón de comunicación** a *solicitudes y respuestas*<br /><br /> -Establecer **dirección de comunicación** a *envío y recepción*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>Especificar mensajes de las formas Acción y conectar a los puertos  
 En la tabla siguiente especifica las propiedades y sus valores que se deben establecer para especificar los mensajes para las formas de acción y vincular los mensajes a los puertos. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación que se ha mencionado anteriormente.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveNotification|-Establecer **mensaje** a *NotifyReceive*<br /><br /> -Establecer **operación** a *SQLNotifyPort.Notify.Request*|  
|SaveNotification|-Establecer **mensaje** a *NotifyReceive*<br /><br /> -Establecer **operación** a *SaveMessagePort.Notify.Request*|  
|SendSelectMessage|-Establecer **mensaje** a *seleccionar*<br /><br /> -Establecer **operación** a *SQLOutboundPort.Select.Request*|  
|ReceiveSelectResponse|-Establecer **mensaje** a *SelectResponse*<br /><br /> -Establecer **operación** a *SQLOutboundPort.Select.Response*|  
|SaveSelectResponse|-Establecer **mensaje** a *SelectResponse*<br /><br /> -Establecer **operación** a *SaveMessagePort.Select.Request*|  
  
 Después de especificar estas propiedades, las formas de mensaje y los puertos que están conectados y la orquestación se completa.  
  
 Ahora debe compilar la solución de BizTalk e implementarlo en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el **orquestaciones** panel de la consola de administración de BizTalk Server. Debe usar la consola de administración de BizTalk Server para configurar la aplicación. Para obtener un tutorial, vea [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).
  
 Configuración de una aplicación implica:  
  
-   Selección de un host de la aplicación.  
  
-   Asignación de los puertos que ha creado en la orquestación con puertos físicos en la consola de administración de BizTalk Server. Para que esta orquestación debe:  
  
    -   Definir un WCF-Custom físico o puerto de recepción unidireccionales de WCF-SQL. Este puerto de escucha notificaciones procedentes de la base de datos de SQL Server. Para obtener información sobre cómo crear puertos, consulte [configurar manualmente un enlace de puerto físico para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md). Asegúrese de que especificar las siguientes propiedades de enlace para el puerto de recepción.  
  
        > [!IMPORTANT]
        >  No es necesario realizar este paso si especifica las propiedades de enlace en tiempo de diseño. En tal caso, puede crear un WCF-custom o WCF-SQL puerto de recepción, en el conjunto de propiedades de enlace necesaria, importando el archivo de enlace creado por la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto para utilizar el adaptador SQL](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).  
  
        |Propiedad de enlace|Valor|  
        |----------------------|-----------|  
        |**InboundOperationType**|Establezca esta propiedad en **notificación**.|  
        |**NotificationStatement**|Establezca esta propiedad en:<br /><br /> `SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0`<br /><br /> **Nota:** específicamente debe especificar los nombres de columna en la instrucción tal y como se muestra en la siguiente instrucción SELECT. Además, siempre debe especificar el nombre de la tabla junto con el nombre del esquema. Por ejemplo, `dbo.Employee`.|  
        |**NotifyOnListenerStart**|Establezca esta propiedad en **True**.|  
  
         Para obtener más información acerca de las propiedades de enlace diferente, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  
  
        > [!NOTE]
        >  Se recomienda configurar el nivel de aislamiento de transacción y el tiempo de espera de transacciones al realizar operaciones de entrada mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Puede hacerlo agregando el servicio de puerto de recepción de comportamiento al configurar el WCF-Custom o WCF-SQL. Para obtener instrucciones sobre cómo agregar el comportamiento del servicio, consulte [configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con SQL](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md).  
  
    -   Definir un puerto de envío físico de WCF-Custom o WCF-SQL para enviar mensajes a la base de datos de SQL Server. También debe especificar la acción en el puerto de envío.  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk colocará los mensajes de la base de datos de SQL Server. Estos serán los mensajes de notificación recibidos de SQL Server y los mensajes para la instrucción Select y puerto de envío de la operación de actualización realice a través de WCF-Custom o WCF-SQL.  
  
## <a name="starting-the-application"></a>A partir de la aplicación  
 Debe iniciar la aplicación de BizTalk para recibir mensajes de notificación de la base de datos de SQL Server y para llevar a cabo las operaciones subsiguientes de Select y Update. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md).
  
 En esta fase, asegúrese de que:  
  
-   El WCF-Custom o WCF-SQL unidireccional puerto de recepción, que recibe los mensajes de notificación de SQL Server se ejecuta la base de datos.  
  
-   Seleccione el puerto de envío WCF-Custom o WCF-SQL para realizar y se está ejecutando operaciones de actualización en la tabla de empleados.  
  
-   El puerto de envío de archivo que recibe los mensajes de SQL Server, se está ejecutando.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Para ejecutar esta operación, debe insertar un registro en la tabla de empleados. Supongamos que inserta un registro con los detalles siguientes:  
  
```  
Name = John Smith  
Designation = Manager  
Salary = 100000  
```  
  
 Además, asegúrese de seleccionar el mensaje XML para realizar y las operaciones de actualización está disponible en C:\TestLocation\MessageIn. El archivo XML debe ser similar a lo siguiente:  
  
```  
<Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
  <Columns>Employee_ID,Name,Status</Columns>  
  <Query>where Status=0;UPDATE Employee SET Status=1 WHERE Status=0</Query>  
</Select>  
```  
  
 Una vez que se inserta el registro, el siguiente conjunto de acciones tienen lugar, en la misma secuencia:  
  
-   El adaptador recibe un mensaje de notificación que es similar al siguiente:  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Insert</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     Este mensaje indica que se insertó un registro en la tabla de empleados. Tenga en cuenta que el valor de la `<Info>` elemento es "Insertar".  
  
-   El adaptador ejecuta la operación de selección. Dado que la operación de selección XML también incluye una instrucción Update, también se ejecuta la instrucción Update. Es la siguiente respuesta de SQL Server para la instrucción Select.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <SelectResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
      <SelectResult>  
        <Employee xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
          <Employee_ID>10006</Employee_ID>   
          <Name>John</Name>   
          <Status>0</Status>  
        </Employee>  
      </SelectResult>  
    </SelectResponse>  
    ```  
  
     Esta respuesta muestra que se inserta un registro en la tabla de empleados y el estado de ese registro es 0.  
  
-   Como parte de la instrucción Select, también se ejecuta la instrucción Update y la columna de estado para el nuevo registro se cambia a 1. Esto desencadena nuevo otra notificación de SQL Server y el adaptador recibe un mensaje de notificación correspondiente, que es similar al siguiente:  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Update</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     Este mensaje indica que se actualiza un registro en la tabla de empleados. Tenga en cuenta que el valor de la `<Info>` elemento es "Actualización".  
  
-   Después de la segunda notificación, el adaptador ejecuta la instrucción Select. Sin embargo, dado que no hay ningún registro ahora tiene el estado como 0, el adaptador obtiene una respuesta vacía parecida a la siguiente.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <SelectResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
      <SelectResult />   
    </SelectResponse>  
    ```  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez haya implementado y configurado el proyecto de BizTalk, puede exportar la configuración en un archivo XML denominado archivo de enlace. Una vez que se genera un archivo de enlace, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear los puertos de envío y puertos de recepción para la misma orquestación. Para obtener más información acerca de los archivos de enlace, vea [enlaces del adaptador SQL reutilizar](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md).
  
## <a name="see-also"></a>Vea también  
 [Recibir notificaciones de consulta SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)