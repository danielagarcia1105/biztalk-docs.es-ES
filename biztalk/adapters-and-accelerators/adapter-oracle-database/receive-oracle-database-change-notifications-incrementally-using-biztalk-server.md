---
title: Recibir notificaciones de cambios de base de datos de Oracle incrementalmente mediante BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 17cef39f-a1aa-4f46-993f-620008f3890d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eebcd37124e0ddde2171f21b233ca8bd8ce23f55
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="receive-oracle-database-change-notifications-incrementally-using-biztalk-server"></a>Recibir notificaciones de cambio de base de datos de Oracle mediante BizTalk Server de forma incremental
> [!IMPORTANT]
>  Por brevedad, en este tema solo se describe cómo recibir las notificaciones de forma incremental. En escenarios empresariales, la orquestación lo ideal es que debe incluir la lógica para extraer el tipo de mensaje de notificación recibido y, a continuación, realizar las operaciones siguientes. En otras palabras, se debe crear la orquestación se describe en este tema sobre la orquestación se describe en [mensajes de notificación de proceso para completar tareas específicas en la base de datos de Oracle mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md).  
  
 Este tema muestra cómo configurar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para recibir mensajes de notificación de consulta incremental de Oracle. Para mostrar notificaciones incrementales, consideramos que una tabla, ACCOUNTACTIVITY, con una columna "Procesados". Cuando se inserta un nuevo registro en esta tabla, el valor de la columna "Procesados" se establece en ' n '. Puede configurar el adaptador para recibir notificaciones incrementales haciendo lo siguiente:  
  
-   Registrarse para recibir notificaciones mediante una instrucción SELECT que recupera todos los registros que tienen "Procesados" columna como ' n '. Puede hacerlo mediante la especificación de la instrucción SELECT para la **NotificationStatement** propiedad de enlace.  
  
-   Para las filas que han sido notificadas para, actualice la columna "Procesada" en 'y'.  
  
 Este tema muestra cómo crear una orquestación de BizTalk y configurar una aplicación de BizTalk para lograr esto.  
  
## <a name="configuring-notifications-with-the-oracle-database-adapter-binding-properties"></a>Configuración de notificaciones con el adaptador de la base de datos de Oracle propiedades de enlace  
 La siguiente tabla resume el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] propiedades de enlace que se utiliza para configurar la recepción de notificaciones de la base de datos de Oracle. Debe especificar estas propiedades de enlace al configurar el puerto de recepción en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
> [!NOTE]
>  Puede especificar estas propiedades de enlace al generar el esquema para el **notificación** operación, aunque no es obligatorio. Si lo hace, el enlace de puerto de archivos que el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] genera como parte de la generación de metadatos también contiene los valores especificados para las propiedades de enlace. Más adelante puede importar este archivo de enlace en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] puerto de recepción de la consola de administración para crear el WCF-custom o WCF-OracleDB con el enlace de propiedades ya establecidas. Para obtener más información acerca de cómo crear un puerto de recepción mediante el archivo de enlace, vea [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).  
  
|Propiedad de enlace|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|Especifica la operación de entrada que se desea realizar. Para recibir mensajes de notificación, establezca esta propiedad en **notificación**.|  
|**NotificationPort**|Especifica el número de puerto que debe abrir ODP.NET para realizar escuchas de notificación de cambio de base de datos de base de datos de Oracle.|  
|**NotificationStatement**|Especifica la instrucción SELECT que se usa para registrar las notificaciones de consulta. El adaptador obtiene un mensaje de notificación solo cuando el conjunto de resultados para que los cambios de la instrucción SELECT especificada.|  
|**NotifyOnListenerStart**|Especifica si el adaptador envía una notificación a los clientes de adaptador cuando se inicia el agente de escucha.|  
  
 Para obtener una descripción más completa de estas propiedades, vea [trabajar con el adaptador de BizTalk para propiedades de enlace de base de datos de Oracle](https://msdn.microsoft.com/library/dd788467.aspx). Para obtener una descripción completa de cómo usar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para recibir notificaciones de la base de datos de Oracle, seguir leyendo.  
  
## <a name="how-this-topic-demonstrates-receiving-notification-messages"></a>Cómo en este tema se muestra cómo recibir mensajes de notificación  
 En este tema, para demostrar cómo [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] permite recibir mensajes de notificación de cambio incremental de la base de datos de la base de datos de Oracle, se va a configurar el adaptador para recibir notificaciones de cambios en la tabla ACCOUNTACTIVTY. Supongamos que la tabla ACCOUNTACTIVITY tiene las columnas "TID", "Cuenta" y "Procesados". Cada vez que se agrega un nuevo registro, el valor de la columna "Procesados" se establece en ' n '. Por lo tanto, para obtener notificaciones incrementales que tendrá que hacer lo siguiente como parte de la orquestación de BizTalk:  
  
-   Notificación de todos los registros donde "Procesados" es ' n '. Puede hacerlo mediante la especificación de una instrucción SELECT como una instrucción de notificación.  
  
-   Tras recibe la notificación para un determinado registro, establezca "Procesada" en 'y'. Puede hacerlo mediante la ejecución de un procedimiento almacenado, PROCESS_RECORDS, que actualiza la columna "Procesados".  
  
 Para demostrar la recepción de notificaciones incrementales, llevamos a cabo lo siguiente:  
  
-   Genere el esquema para el **notificación** (operación de entrada), y **PROCESS_RECORDS** (operación saliente) en la tabla ACCOUNTACTIVITY.  
  
-   Crear una orquestación que incluye lo siguiente:  
  
    -   Una ubicación de recepción para recibir mensajes de notificación. Puede configurar para la notificación mediante la especificación de la instrucción SELECT como:  
  
        ```  
        SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’  
        ```  
  
        > [!NOTE]
        >  Debe especificar el nombre de la tabla junto con el nombre del esquema. Por ejemplo, `SCOTT.ACCOUNTACTIVITY`.  
  
    -   Un puerto de envío para actualizar las filas para el que ya se ha enviado notificación. Se ejecutará el procedimiento almacenado de PROCESS_RECORDS en este puerto para establecer el valor de columna de "Procesada" en 'y' para los registros para el que se recibe la notificación.  
  
         Tenga en cuenta que esta operación debe ejecutarse después de recibir la notificación de mensajes para que se actualicen las filas procesadas. Para hacer inmediatamente con la sobrecarga de espera para obtener la respuesta de notificación y, a continuación, quitar manualmente un mensaje de solicitud para ejecutar el procedimiento PROCESS_RECORDS, se generará el mensaje de solicitud para el procedimiento PROCESS_RECORDS dentro de la propia orquestación. Puede hacerlo mediante el **construir mensaje** forma dentro de una orquestación.  
  
## <a name="how-to-receive-notification-messages-from-the-oracle-database"></a>Cómo recibir mensajes de notificación de la base de datos de Oracle  
 Realizar una operación en la base de datos de Oracle mediante [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] conlleva las tareas de procedimientos descritas en [bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md). Para configurar el adaptador para recibir mensajes de notificación, estas tareas son:  
  
1.  Crear un proyecto de BizTalk y, a continuación, genere el esquema para el **notificación** (operación entrante) y **PROCESS_RECORDS** procedimiento (operación saliente) en la tabla ACCOUNTACTIVITY. Si lo desea, puede especificar valores para la **InboundOperationType**, **NotificationPort**, y **NotificationStatement** propiedades de enlace.  
  
2.  Cree un mensaje en el proyecto de BizTalk para recibir notificaciones de la base de datos de Oracle.  
  
3.  Crear mensajes en el proyecto de BizTalk para ejecutar el procedimiento almacenado de PROCESS_RECORDS y recibir mensajes de respuesta.  
  
4.  Crear una orquestación que realiza lo siguiente:  
  
    -   Recibe el mensaje de notificación de la base de datos de Oracle.  
  
    -   Crea un mensaje para ejecutar el procedimiento PROCESS_RECORDS.  
  
    -   Este mensaje se envía a la base de datos de Oracle para seleccionar y actualizar los registros y recibir una respuesta.  
  
5.  Compilar e implementar el proyecto de BizTalk.  
  
6.  Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
    > [!NOTE]
    >  Para las operaciones de entrada, como recibir mensajes de notificación, solo se debe configurar un unidireccional WCF-Custom o WCF-OracleDB puerto de recepción. Bidireccional de recepción no se admiten los puertos para las operaciones de entrada.  
  
7.  Inicie la aplicación de BizTalk.  
  
 Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="generating-schema"></a>Generar el esquema  
 Debe generar el esquema para el **notificación** operación y **PROCESS_RECORDS** procedimiento. Vea [recuperar metadatos para operaciones de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md) para obtener más información acerca de cómo generar el esquema. Realice las tareas siguientes al generar el esquema. Omitir el primer paso si no desea especificar las propiedades de enlace en tiempo de diseño.  
  
1.  Especifique un valor para **InboundOperationType**, **NotificationPort**, y **NotificationStatement** propiedades de enlace al generar el esquema. Para obtener más información acerca de esta propiedad de enlace, vea [trabajar con el adaptador de BizTalk para propiedades de enlace de base de datos de Oracle](https://msdn.microsoft.com/library/dd788467.aspx). Para obtener instrucciones sobre cómo especificar las propiedades de enlace, consulte [especificar propiedades de enlace](https://msdn.microsoft.com/library/dd788420.aspx).  
  
2.  Seleccione el tipo de contrato **(operaciones de entrada) de servicio**.  
  
3.  Genere el esquema para el **notificación** operación.  
  
4.  Seleccione el tipo de contrato **Client (Outbound operations)**.  
  
5.  Genere el esquema para el **PROCESS_RECORDS** procedimiento. Este procedimiento está disponible en la **ACCOUNT_PKG** paquete.  
  
## <a name="defining-messages-and-message-types"></a>Definición de mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes en la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Una vez que se genera el esquema, debe vincular a los mensajes desde la vista de orquestación de BizTalk del proyecto.  
  
 En este tema, debe crear tres mensajes: uno para recibir notificaciones de la base de datos de Oracle, uno para ejecutar el procedimiento PROCESS_RECORDS y otro para recibir la respuesta para el procedimiento.  
  
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
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *OracleNotifyIncremental.OracleDBBinding.Notification*, donde *OracleNotifyIncremental* es el nombre de el proyecto de BizTalk. *OracleDBBinding* es el esquema generado para el **notificación** operación.|  
  
6.  Repita el paso 3 para crear dos nuevos mensajes. En el **propiedades** panel para el nuevo mensaje, haga lo siguiente:  
  
    |Identificador de conjunto a|Establecer el tipo de mensaje en|  
    |-----------------------|-------------------------|  
    |Procedimiento|*OracleNotifyIncremental.OracleDBBinding1.PROCESS_RECORDS*, donde *OracleDBBinding1* es el esquema generado para el **PROCESS_RECORDS** procedimiento.|  
    |ProcedureResponse|*OracleNotifyIncremental.OracleDBBinding1.PROCESS_RECORDSResponse*|  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para usar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para recibir mensajes de notificación de la base de datos de Oracle y, a continuación, actualizar las filas para el que ha recibido la notificación. En esta orquestación, el adaptador recibe el mensaje de notificación basado en la instrucción SELECT especificada para la **NotificationStatement** propiedad de enlace. El mensaje de notificación se recibe en una ubicación de archivo. Una vez que se recibe la respuesta, la orquestación construye un mensaje para invocar el procedimiento PROCESS_RECORDS, que actualiza las filas para el que se recibe la notificación. También se recibe la respuesta para este mensaje en la misma ubicación de archivo.  
  
 Por lo tanto, la orquestación debe contener lo siguiente:  
  
-   Un unidireccionales WCF-Custom o WCF-OracleDB puerto de recepción para recibir mensajes de notificación.  
  
-   Un bidireccional WCF-Custom o WCF-OracleDB puerto de envío para enviar mensajes al ejecutar el procedimiento PROCESS_RECORDS.  
  
-   A **construir mensaje** forma para construir mensajes, para ejecutar procedimiento PROCESS_RECORDS, dentro de la orquestación.  
  
-   Un archivo de puerto de envío para guardar el mensaje de notificación y la respuesta para el procedimiento PROCESS_RECORDS.  
  
-   Formas de envío y recepción.  
  
 Una orquestación de ejemplo es similar al siguiente.  
  
 ![Orquestación para recibir notificaciones de Oracle](../../adapters-and-accelerators/adapter-oracle-database/media/cef49414-490a-4bd5-a32d-b3f4cde5950a.gif "cef49414-490a-4bd5-a32d-b3f4cde5950a")  
  
### <a name="adding-message-shapes"></a>Agregar formas de mensaje  
 Asegúrese de que especifique las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación just-mencionado.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ReceiveNotification|Receive|-Establecer **nombre** a *ReceiveNotification*<br /><br /> -Establecer **activar** a *es True*|  
|SaveNotification|Send|-Establecer **nombre** a *SaveNotification*|  
|SendProcMessage|Send|-Establecer **nombre** a *SendProcMessage*|  
|ReceiveProcResponse|Receive|-Establecer **nombre** a *ReceiveProcResponse*|  
|SaveProcResponse|Send|-Establecer **nombre** a *SaveProcResponse*|  
  
### <a name="adding-construct-message-shape"></a>Agregar forma construir mensaje  
 Puede usar el **construir mensaje** forma para generar un mensaje de solicitud en la orquestación para ejecutar el procedimiento PROCESS_RECORDS. Para ello, debe agregar una **construir mensaje** forma y en el que un **asignación de mensajes** forma a la orquestación. En este ejemplo, el **asignación de mensajes** forma invoca el código que genera un mensaje que se envía a la base de datos de Oracle para ejecutar el procedimiento. El **asignación de mensajes** forma también establece la acción del mensaje que se va a enviar a la base de datos de Oracle.  
  
 Para la forma construir mensaje, establezca la **construir mensaje** propiedad **procedimiento**.  
  
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
            XmlFileLocation = "C:\\TestLocation\\MessageIn";  
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
  
 Para que el fragmento de código anterior para que pueda generar un mensaje de solicitud, debe tener un mensaje de solicitud XML (para el procedimiento PROCESS_RECORDS) en la ubicación especificada para el `XmlFileLocation` variable.  
  
> [!NOTE]
>  Después de compilar el proyecto, MessageCreator.dll se creará en el directorio del proyecto. Debe agregar este archivo DLL a la caché de ensamblados global (GAC). Además, debe agregar el MessageCreator.dll como una referencia en el proyecto de BizTalk.  
  
 Agregue la siguiente expresión para invocar este código desde el **asignación de mensajes** forma y establecer la acción para el mensaje. Para agregar una expresión, haga doble clic en el **asignación de mensajes** forma para abrir el Editor de expresiones.  
  
```  
Procedure = SampleMessageCreator.SampleMessageCreator.XMLMessageCreator();  
Procedure(WCF.Action) = "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/PROCESS_RECORDS";  
```  
  
### <a name="adding-ports"></a>Agregar puertos  
 Asegúrese de que especifique las siguientes propiedades para cada uno de los puertos lógicos. Los nombres que aparecen en la columna de puerto son los nombres de los puertos, como se muestra en la orquestación.  
  
|Puerto|Propiedades|  
|----------|----------------|  
|OracleNotifyPort|-Establecer **identificador** a *OracleNotifyPort*<br /><br /> -Establecer **tipo** a *OracleNotifyPortType*<br /><br /> -Establecer **patrón de comunicación** a *unidireccional*<br /><br /> -Establecer **dirección de comunicación** a *de recepción*|  
|SaveMessagePort|-Establecer **identificador** a *SaveMessagePort*<br /><br /> -Establecer **tipo** a *SaveMessagePortType*<br /><br /> -Establecer **patrón de comunicación** a *unidireccional*<br /><br /> -Establecer **dirección de comunicación** a *enviar*<br /><br /> -Crear una operación *notificar*. Esta operación se usa para mensajes de notificación.<br /><br /> -Crear una operación *procedimiento*. Esta operación se usa para los mensajes de respuesta de select.|  
|OracleOutboundPort|-Establecer **identificador** a *OracleOutboundPort*<br /><br /> -Establecer **tipo** a *OracleOutboundPortType*<br /><br /> -Establecer **patrón de comunicación** a *solicitudes y respuestas*<br /><br /> -Establecer **dirección de comunicación** a *envío y recepción*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>Especificar mensajes de las formas Acción y conectar a los puertos  
 En la tabla siguiente especifica las propiedades y sus valores que se deben establecer para especificar los mensajes para las formas de acción y vincular los mensajes a los puertos. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación que se ha mencionado anteriormente.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveNotification|-Establecer **mensaje** a *NotifyReceive*<br /><br /> -Establecer **operación** a *OracleNotifyPort.Notify.Request*|  
|SaveNotification|-Establecer **mensaje** a *NotifyReceive*<br /><br /> -Establecer **operación** a *SaveMessagePort.Notify.Request*|  
|SendProcMessage|-Establecer **mensaje** a *procedimiento*<br /><br /> -Establecer **operación** a *OracleOutboundPort.Procedure.Request*|  
|ReceiveProcResponse|-Establecer **mensaje** a *ProcedureResponse*<br /><br /> -Establecer **operación** a *OracleOutboundPort.Procedure.Response*|  
|SaveProcResponse|-Establecer **mensaje** a *ProedureResponse*<br /><br /> -Establecer **operación** a *SaveMessagePort.Procedure.Request*|  
  
 Después de especificar estas propiedades, las formas de mensaje y los puertos que están conectados y la orquestación se completa.  
  
 Ahora debe compilar la solución de BizTalk e implementarlo en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).  
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el **orquestaciones** panel en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Debe utilizar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para configurar la aplicación. Para obtener un tutorial, vea [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).
  
 Configuración de una aplicación implica:  
  
-   Selección de un host de la aplicación.  
  
-   Asignación de los puertos que ha creado en la orquestación con puertos físicos en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para que esta orquestación debe:  
  
    -   Definir un WCF-Custom físico o puerto de recepción unidireccionales de WCF-OracleDB. Este puerto de escucha notificaciones procedentes de la base de datos de Oracle. Para obtener información sobre cómo crear puertos de recepción, vea [configurar manualmente un enlace de puerto físico para el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md). Asegúrese de que especificar las siguientes propiedades de enlace para el puerto de recepción.  
  
        > [!IMPORTANT]
        >  No es necesario realizar este paso si especifica las propiedades de enlace en tiempo de diseño. En tal caso, puede crear un puerto de recepción, en el conjunto de propiedades de enlace necesaria, importando el archivo de enlace creado por la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).  
  
        |Propiedad de enlace|Valor|  
        |----------------------|-----------|  
        |**InboundOperationType**|Establezca esta propiedad en **notificación**.|  
        |**NotificationPort**|Especifica el número de puerto que debe abrir ODP.NET para realizar escuchas de notificación de cambio de base de datos de base de datos de Oracle. Establecer esto en el mismo número de puerto que debe haber agregado a la lista de excepciones de Firewall de Windows. Para obtener instrucciones sobre cómo agregar puertos a la lista de excepciones de Firewall de Windows, vea [http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959).<br /><br /> **Importante:** si se establece en el valor predeterminado de -1, tendrá que deshabilitar completamente el Firewall de Windows para recibir mensajes de notificación.|  
        |**NotificationStatement**|Establezca esta propiedad en:<br /><br /> `SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’`<br /><br /> **Nota:** debe especificar el nombre de la tabla junto con el nombre del esquema. Por ejemplo, `SCOTT.ACCOUNTACTIVITY`.|  
        |**NotifyOnListenerStart**|Establezca esta propiedad en **True**.|  
  
         Para obtener más información acerca de las propiedades de enlace diferente, consulte [trabajar con el adaptador de BizTalk para propiedades de enlace de base de datos de Oracle](https://msdn.microsoft.com/library/dd788467.aspx).  
  
        > [!NOTE]
        >  Se recomienda configurar el nivel de aislamiento de transacción y el tiempo de espera de transacciones al realizar operaciones de entrada mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Puede hacerlo agregando el servicio de comportamiento al configurar el WCF-Custom o WCF-OracleDB puerto de recepción. Para obtener instrucciones sobre cómo agregar el comportamiento del servicio, consulte [configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md).  
  
    -   Definir un puerto de envío WCF-Custom o WCF-OracleDB físico para enviar mensajes a la base de datos de Oracle para ejecutar el procedimiento PROCESS_REOCRDS. También debe especificar la acción en el puerto de envío.  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk colocará los mensajes de la base de datos de Oracle. Estos serán los mensajes de notificación recibidos de la base de datos de Oracle y los mensajes para el procedimiento PROCESS_RECORDS que ejecutar a través de WCF-Custom o WCF-OracleDB puerto de envío.  
  
## <a name="starting-the-application"></a>A partir de la aplicación  
 Debe iniciar la aplicación de BizTalk para recibir los mensajes de notificación de la base de datos de Oracle y para ejecutar el procedimiento PROCESS_RECORDS. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md).  
  
 En esta fase, asegúrese de que:  
  
-   El WCF-Custom o WCF-OracleDB unidireccional puerto de recepción, que recibe los mensajes de notificación de la base de datos se ejecuta de Oracle.  
  
-   El puerto de envío WCF-Custom o WCF-OracleDB para ejecutar el procedimiento PROCESS_RECORDS se está ejecutando.  
  
-   El puerto de envío de archivo que recibe mensajes de la base de datos de Oracle, se está ejecutando.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Suponga que la tabla ACCOUNTACTIVITY ya tiene algunos registros. Además, asegúrese de que el mensaje XML para ejecutar el procedimiento PROCESS_RECORDS está disponible en C:\TestLocation\MessageIn. El archivo XML debe ser similar a lo siguiente:  
  
```  
<PROCESS_RECORDS xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG"/>  
```  
  
 Una vez que se inicia la orquestación de BizTalk, el siguiente conjunto de acciones tienen lugar, en la misma secuencia:  
  
-   El adaptador recibe un mensaje de notificación que es similar al siguiente:  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?\>   
    <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
      <Info>ListenerStarted</Info>   
      <Source>OracleDBBinding</Source>   
      <Type>Startup</Type>   
    </Notification>  
    ```  
  
     Este mensaje indica que se ha iniciado el puerto de recepción para recibir los mensajes de notificación. Tenga en cuenta que el valor de la `<Info>` elemento es "ListnerStarted".  
  
-   El adaptador ejecuta el procedimiento PROCESS_RECORDS. Es la siguiente respuesta de la base de datos de Oracle para el procedimiento.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <PROCESS_RECORDSResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
      <TABLE_DATA>  
        <xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
          <xs:element msdata:IsDataSet="true" name="NewDataSet">  
            <xs:complexType>  
              <xs:sequence>  
                <xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                  <xs:complexType>  
                    <xs:sequence>  
                      <xs:element minOccurs="0" name="TID" type="xs:decimal" />   
                      <xs:element minOccurs="0" name="ACCOUNT" type="xs:decimal" />   
                      <xs:element minOccurs="0" name="PROCESSED" type="xs:string" />   
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
            <TID>1</TID>   
            <ACCOUNT>100001</ACCOUNT>   
            <PROCESSED>n</PROCESSED>   
          </NewTable>  
          <NewTable>  
            ......  
            ......  
          </NewTable>  
          ......  
          ......  
        </NewDataSet>  
        </diffgr:diffgram>  
      </TABLE_DATA>  
    </PROCESS_RECORDSResponse>  
    ```  
  
     Se trata de la respuesta para ejecutar la instrucción SELECT como parte del procedimiento PROCESS_RECORDS.  
  
-   El procedimiento PROCESS_RECORDS también actualiza las filas para establecer procesados en 'y'. Por lo tanto, el adaptador recibe otra notificación para la operación de actualización.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
      <Details>  
        <NotificationDetails>  
          <ResourceName>SCOTT.ACCOUNTACTIVITY</ResourceName>   
          <Info>32</Info>   
          <QueryId>0</QueryId>   
        </NotificationDetails>  
      </Details>  
      <Info>Update</Info>   
      <ResourceNames>  
        <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">SCOTT.ACCOUNTACTIVITY</string>   
      </ResourceNames>  
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     Tenga en cuenta que el `Info` elemento contiene una "Actualización".  
  
-   Después de la segunda notificación, el adaptador nuevo ejecuta el procedimiento PROCESS_RECORDS. Sin embargo, ahora porque no hay ningún registro que procesados columna esté establecida en ' n ', el procedimiento devuelve una respuesta vacía similar a lo siguiente.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <PROCESS_RECORDSResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
      <TABLE_DATA>  
        <xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
          <xs:element msdata:IsDataSet="true" name="NewDataSet">  
            <xs:complexType>  
              <xs:sequence>  
                <xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                  <xs:complexType>  
                    <xs:sequence>  
                      <xs:element minOccurs="0" name="TID" type="xs:decimal" />   
                      <xs:element minOccurs="0" name="ACCOUNT" type="xs:decimal" />   
                      <xs:element minOccurs="0" name="PROCESSED" type="xs:string" />   
                    </xs:sequence>  
                  </xs:complexType>  
                </xs:element>  
              </xs:sequence>  
            </xs:complexType>  
          </xs:element>  
        </xs:schema>  
        <diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
          <NewDataSet xmlns="" />   
        </diffgr:diffgram>  
      </TABLE_DATA>  
    </PROCESS_RECORDSResponse>  
    ```  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez haya implementado y configurado el proyecto de BizTalk, puede exportar la configuración en un archivo XML denominado archivo de enlace. Una vez que se genera un archivo de enlace, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear los puertos de envío y puertos de recepción para la misma orquestación. Para obtener más información acerca de los archivos de enlace, vea [enlaces del adaptador de base de datos de Oracle reutilizar](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md).  
  
## <a name="see-also"></a>Vea también  
 [Recibir notificaciones de cambio de base de datos de Oracle mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)