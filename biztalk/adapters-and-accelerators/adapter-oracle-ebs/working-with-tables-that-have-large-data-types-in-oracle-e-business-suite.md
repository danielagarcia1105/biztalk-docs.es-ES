---
title: Trabajar con tablas que tienen tipos de datos de gran tamaño en Oracle E-Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 501aa302-0f82-4221-b99f-423bc8621a6a
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf03c256ed525274c808c75704ce252728dc2aa2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971653"
---
# <a name="working-with-tables-that-have-large-data-types-in-oracle-e-business-suite"></a>Trabajar con tablas que tienen tipos de datos de gran tamaño en Oracle E-Business Suite
El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] permite a los clientes del adaptador realizar operaciones en tablas y vistas con tipos de datos de gran tamaño como BLOB, CLOB, NCLOB y BFILE.  
  
- Las columnas de tipo BLOB, CLOB y NCLOB el adaptador permite a los clientes leer, así como actualizar los datos. El adaptador expone Read_\<LOBColName\> y Update_\<LOBColName\> operations para leer y actualizar datos, respectivamente, donde \<LOBColName\> es el nombre de columna con grandes tipo de datos. Si hay más de una columna con el tipo de datos de gran tamaño en una tabla de interfaz único, el adaptador se expone como muchos leer y actualización las operaciones de dicha tabla de interfaz.  
  
- Las columnas de tipo BFILE, los clientes del adaptador sólo pueden leer los datos. El adaptador expone Read_\<LOBColName\> operación para leer datos de las columnas de tipo BFILE. Si hay más de una columna con el tipo de datos de gran tamaño en una tabla de interfaz único, el adaptador se expone como muchas operaciones para la tabla de interfaz de lectura.  
  
  Para obtener más información acerca de estas operaciones, consulte [operaciones en tablas, vistas de interfaz, tablas y vistas que contienen LOB datos](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md). Para obtener información acerca de los esquemas de mensaje para realizar estas operaciones, vea [esquemas de mensaje para operaciones especiales de LOB](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-special-lob-operations1.md).  
  
## <a name="how-to-perform-operations-on-columns-with-large-data-types"></a>Cómo realizar operaciones en columnas con tipos de datos de gran tamaño  
 Realizar una operación en Oracle E-Business Suite mediante el uso de [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica tareas de procedimientos se describe en [bloques de creación para crear aplicaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md). Para realizar operaciones en tablas y vistas de interfaz en Oracle E-Business Suite que contienen tipos de datos de gran tamaño, estas tareas son:  
  
1. Crear un proyecto de BizTalk y genere el esquema para la operación (Read_\<LOBColName\> o Update_\<LOBColName\>) que desea invocar en una tabla o vista.  
  
2. Crear mensajes en el proyecto de BizTalk para enviar y recibir mensajes de Oracle E-Business Suite.  
  
3. Crear una orquestación para invocar la operación en la tabla de interfaz o la vista.  
  
4. Compile e implemente el proyecto de BizTalk.  
  
5. Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
6. Inicie la aplicación de BizTalk.  
  
   Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="how-this-topic-demonstrates-reading-and-writing-data-into-columns-of-large-data-types"></a>Cómo en este tema muestra cómo leer y escribir datos en columnas de tipos de datos de gran tamaño  
 Para demostrar que leer y escribir datos en columnas de tipos de datos de gran tamaño, en este tema proporciona instrucciones para crear una orquestación que hace lo siguiente:  
  
- Actualice la columna PHOTO (del tipo de datos BLOB) de la tabla CUSTOMER.  
  
- Leer el valor de la columna PHOTO del registro actualizado.  
  
  Esta orquestación está diseñada de tal manera que sólo proporcione el mensaje de solicitud para la operación de actualización en tiempo de ejecución. Dentro de la operación se construirá el mensaje para la operación de lectura.  
  
> [!NOTE]
>  La orquestación en este tema lee y actualiza los datos de la tabla CUSTOMER, que es una tabla de base de datos crean mediante la ejecución de los scripts proporcionados con los ejemplos. Debe realizar procedimientos similares, como se describe en este tema para operaciones de lectura o de operaciones update en cualquier vista de tabla o la interfaz de la interfaz.  
  
## <a name="generating-schema"></a>Generar el esquema  
 En este tema se muestra cómo las operaciones de lectura básico y operaciones update en una columna de la foto (del tipo de datos BLOB) en una tabla de clientes. Esta tabla se crea mediante la ejecución de los scripts proporcionados con los ejemplos.  
  
 Para demostrar cómo leer y escribir datos en una columna de tipo de datos de gran tamaño, se genera el esquema para el **Update_PHOTO** y **Read_PHOTO** operaciones para la tabla CUSTOMER. Debe crear un proyecto de BizTalk y utilice el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar el esquema. Consulte [recuperación de metadatos para las operaciones de Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md) para obtener más información acerca de cómo generar esquemas.  
  
## <a name="defining-messages-and-message-types"></a>Definición de los mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes de la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Ahora debe crear mensajes para la orquestación y vincularlos a los esquemas que generó en el paso anterior.  
  
 En esta orquestación debe crear cuatro mensajes, Establece una respuesta de recepción para el **Update_PHOTO** operación y la otra recepción-respuesta establecen para el **Read_PHOTO** operación.  
  
#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vínculo a esquema  
  
1.  Agregar una orquestación al proyecto de BizTalk. Desde el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**. Escriba un nombre para la orquestación de BizTalk y, a continuación, haga clic en **agregar**.  
  
2.  Abra la ventana Vista orquestación del proyecto de BizTalk, si aún no está abierto. Para ello, haga clic en **vista**, apunte a **Other Windows**y, a continuación, haga clic en **Vista orquestación**.  
  
3.  En la Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
4.  Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  
  
5.  En el **propiedades** panel para el **Message_1**, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Escriba `UpdateMessage`|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *LOBOperations.OracleEBSBinding.Update_PHOTO*, donde LOBOperations es el nombre de su proyecto de BizTalk. OracleEBSBindingSchema es el esquema generado para invocar el **Update_PHOTO** operación en la tabla CUSTOMER.|  
  
6.  Repita el paso 3 para crear tres nuevo mensaje. En el **propiedades** panel para el nuevo mensaje, haga lo siguiente:  
  
    |Identificador de conjunto para|Establecer el tipo de mensaje en|  
    |-----------------------|-------------------------|  
    |UpdateResponse|*LOBOperations.OracleEBSBinding.Update_PHOTOResponse*|  
    |ReadMessage|*LOBOperations.OracleEBSBinding1.Read_PHOTO*|  
    |ReadResponse|*LOBOperations.OracleEBSBinding1.Read_PHOTOResponse*|  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 En esta orquestación, el adaptador recibe un mensaje de solicitud para realizar una operación Update_PHOTO en una tabla de clientes. El mensaje de notificación se recibe en una ubicación de archivo. El adaptador usa este mensaje y lo pasa por base de datos de Oracle. La respuesta de la base de datos de Oracle se guarda en otra ubicación. Una vez que se recibe la respuesta, la orquestación construye un mensaje para invocar la operación Read_PHOTO, que lee el valor de la columna PHOTO actualizado por la operación Update_PHOTO. También se recibe la respuesta para este mensaje en la misma ubicación de archivo.  
  
 Por lo tanto, la orquestación debe contener lo siguiente:  
  
- Un archivo de puerto de recepción para colocar un mensaje de solicitud para **Update_PHOTO** operación.  
  
- Un bidireccional WCF-Custom o WCF-OracleEBS puerto de envío para enviar mensajes al ejecutar el **Update_PHOTO** operación.  
  
- Un bidireccional WCF-Custom o WCF-OracleEBS puerto de envío para enviar mensajes al ejecutar el **Read_PHOTO** operación. También puede realizar ambas **Read_PHOTO** y **Update_PHOTO** con el mismo WCF-Custom o WCF-OracleEBS de puerto de envío. En este tema, utilizará un puerto de envío solo para las operaciones.  
  
- Un **construir mensaje** forma para construir mensajes dentro de la orquestación.  
  
- Un archivo de puerto de envío para guardar los mensajes de respuesta para **Update_PHOTO** y **Read_PHOTO** operaciones.  
  
- Formas de envío y recepción.  
  
  Una orquestación de ejemplo es similar al siguiente.  
  
  ![Orquestación para operar en columna de tipo de datos de gran tamaño](../../adapters-and-accelerators/adapter-oracle-ebs/media/1976ab27-94c3-4039-a1ca-8790e8897ad5.gif "1976ab27-94c3-4039-a1ca-8790e8897ad5")  
  
### <a name="adding-message-shapes"></a>Agregar formas de mensaje  
 Asegúrese de que especificar las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación simplemente mencionadas.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ReceiveUpdateMessage|Receive|-Establecer **nombre** a *ReceiveUpdateMessage*<br />-Establecer **activar** a *True*|  
|SendUpdateMessage|Send|-Establecer **nombre** a *SendUpdateMessage*|  
|ReceiveUpdateResponse|Receive|-Establecer **nombre** a *ReceiveUpdateResponse*|  
|SendUpdateResponse|Receive|-Establecer **nombre** a *SendUpdateResponse*|  
|SendReadMessage|Send|-Establecer **nombre** a *SendReadMessage*|  
|ReceiveReadResponse|Receive|-Establecer **nombre** a *ReceiveReadResponse*|  
|SaveReadResponse|Send|-Establecer **nombre** a *SaveReadResponse*|  
  
### <a name="adding-construct-message-shape"></a>Adición de la forma construir mensaje  
 Puede usar el **construir mensaje** forma para generar un mensaje de solicitud dentro de la orquestación para ejecutar el **Read_PHOTO** operación. Para ello, debe agregar un **construir mensaje** forma y dentro de ese un **asignación de mensajes** forma a la orquestación. En este ejemplo, el **asignación de mensajes** forma invoca el código que genera un mensaje que se envía a Oracle E-Business Suite para ejecutar el **Read_PHOTO** operación. El **asignación de mensajes** forma también establece la acción para el mensaje se envíe a Oracle E-Business Suite.  
  
 Para la forma construir mensaje, establezca la **mensaje construido** propiedad **ReadMessage**.  
  
 El código para generar la respuesta podría ser parte de la misma solución de Visual Studio que el proyecto de BizTalk. Un código de ejemplo para generar un mensaje de respuesta tiene este aspecto.  
  
```  
namespace MessageCreator  
{  
    public class MessageCreator  
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
  
 Para que el fragmento de código anterior para que pueda generar un mensaje de solicitud, debe tener un mensaje de solicitud XML (para el **Read_PHOTO** operación) en la ubicación especificada para el `XmlFileLocation` variable.  
  
> [!NOTE]
>  Después de compilar el proyecto, se crearán MessageCreator.dll en el directorio del proyecto. Debe agregar este archivo DLL a la caché de ensamblados global (GAC). Además, debe agregar el MessageCreator.dll como referencia en el proyecto de BizTalk.  
  
 Agregue la siguiente expresión para invocar este código desde el **asignación de mensajes** forma y para establecer la acción para el mensaje. Para agregar una expresión, haga doble clic en el **asignación de mensajes** forma para abrir el Editor de expresiones.  
  
```  
ReadMessage = MessageCreator.MessageCreator.XMLMessageCreator();  
ReadMessage(WCF.Action) = "Tables/ReadLOB/SCOTT/CUSTOMER/PHOTO ";  
```  
  
### <a name="adding-ports"></a>Agregar puertos  
 Asegúrese de que especificar las siguientes propiedades para cada uno de los puertos lógicos. Los nombres que aparecen en la columna puerto son los nombres de los puertos tal como se muestra en la orquestación.  
  
|Puerto|Propiedades|  
|----------|----------------|  
|MessageIn|-Establecer **identificador** a *MessageIn*<br />-Establecer **tipo** a *MessageInType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *de recepción*|  
|LOBPort|-Establecer **identificador** a *LOBPort*<br />-Establecer **tipo** a *LOBPortType*<br />-Establecer **patrón de comunicación** a *de solicitud-respuesta*<br />-Establecer **dirección de comunicación** a *envío y recepción*<br />-Creación de una operación *Read_LOB*. Esta operación se usa para los mensajes para leer los valores de las columnas de tipo de datos de gran tamaño.<br />-Creación de una operación *Update_LOB*. Esta operación se usa para los mensajes para actualizar valores en columnas de tipo de datos de gran tamaño.|  
|ResponseOut|-Establecer **identificador** a *ResponseOut*<br />-Establecer **tipo** a *ResponseOutType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *enviar*<br />-Creación de una operación *Read_LOB*. Esta operación se usa para los mensajes para leer los valores de las columnas de tipo de datos de gran tamaño.<br />-Creación de una operación *Update_LOB*. Esta operación se usa para los mensajes para actualizar valores en columnas de tipo de datos de gran tamaño.|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>Especifique los mensajes para las formas Acción y conectar a los puertos  
 En la tabla siguiente especifica las propiedades y sus valores que se deben establecer para especificar los mensajes para las formas Acción y vincular los mensajes a los puertos. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación que se ha mencionado anteriormente.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveUpdateMessage|-Establecer **mensaje** a *UpdateMessage*<br />-Establecer **operación** a *MessageIn.Update_LOB. Solicitud*|  
|SendUpdateMessage|-Establecer **mensaje** a *UpdateMessage*<br />-Establecer **operación** a *LOBPort.Update_LOB. Solicitud*|  
|ReceiveUpdateResponse|-Establecer **mensaje** a *UpdateResponse*<br />-Establecer **operación** a *LOBPort.Update_LOB. Respuesta*|  
|SendUpdateResponse|-Establecer **mensaje** a *UpdateResponse*<br />-Establecer **operación** a *ResponseOut.Update_LOB. Solicitud*|  
|SendReadMessage|-Establecer **mensaje** a *ReadMessage*<br />-Establecer **operación** a *LOBPort.Read_LOB. Solicitud*|  
|ReceiveReadResponse|-Establecer **mensaje** a *ReadResponse*<br />-Establecer **operación** a *LOBPort.Read_LOB. Respuesta*|  
|SendReadResponse|-Establecer **mensaje** a *ReadResponse*<br />-Establecer **operación** a *ResponseOut.Read_LOB. Solicitud*|  
  
 Después de especificar estas propiedades, están conectados a los puertos y formas de mensaje y se completa la orquestación.  
  
 Ahora debe compilar la solución de BizTalk e implementarla en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).  
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el panel orquestaciones, en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Debe usar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para configurar la aplicación. Para ver un tutorial, vea [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).
  
 Configuración de una aplicación implica:  
  
- Selección de un host de la aplicación.  
  
- Asignación de los puertos que ha creado en la orquestación con puertos físicos en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para esta orquestación, debe:  
  
  - Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde se colocará un mensaje de solicitud. La orquestación de BizTalk usarán el mensaje de solicitud y enviarla a la base de datos de Oracle.  
  
  - Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta de la base de datos de Oracle.  
  
  - Definir un puerto de envío WCF-Custom o WCF-OracleEBS físico para enviar mensajes a la base de datos de Oracle. También debe especificar la acción en el puerto de envío. Para obtener información sobre cómo crear los puertos, consulte [configurar manualmente un enlace de puerto físico al adaptador de Oracle E-Business](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md). Debe realizar las siguientes consideraciones al configurar el WCF-Custom o WCF-OracleEBS de puerto de envío.  
  
    -   Un `Update_<LOBColName>` operación debe realizarse como parte de la transacción. Para asegurarse de esto, el **UseAmbientTransaction** enlaza la propiedad debe establecerse en **True**.  
  
    -   Dado que el WCF-Custom o WCF-OracleEBS puertos de envío envían y recibe los mensajes sean conformes a más de un esquema y realiza dos operaciones, debe establecer acciones dinámicas para las operaciones. Para obtener más información acerca de las acciones, vea [configurar la acción SOAP para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md). Para esta orquestación, se debe establecer la acción siguiente:  
  
        ```  
        <BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
          <Operation Name="Update_LOB" Action="Tables/UpdateBlob/SCOTT/CUSTOMER/PHOTO" />  
          <Operation Name="Read_LOB" Action="Tables/ReadLOB/SCOTT/CUSTOMER/PHOTO" />  
        </BtsActionMapping>  
        ```  
  
        > [!IMPORTANT]
        >  Tenga en cuenta que el nombre de la operación en una acción dinámica debe ser igual que el nombre de la operación especificada en los puertos lógicos durante la creación de la orquestación de BizTalk.  
  
    > [!NOTE]
    >  Para llevar a cabo operaciones en tablas o vistas de interfaz también debe establecer el contexto de la aplicación. Para obtener más información sobre cómo el adaptador admite establecer el contexto de la aplicación, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md). Puede establecer el contexto de la aplicación mediante la especificación de las propiedades de enlace o estableciendo las propiedades de contexto expuestas por el mensaje el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Para obtener instrucciones sobre cómo establecer las propiedades de enlace, consulte [configurar las propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md). Para obtener instrucciones sobre cómo establecer el contexto de la aplicación mediante las propiedades de contexto de mensaje, consulte [configurar las propiedades del mensaje utilizando aplicación contexto contexto en Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md).  
    > 
    > [!NOTE]
    >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para crear puertos de envío (para las llamadas salientes) o la recepción (para las llamadas entrantes). Para obtener más información, consulte [configurar un físico puerto de enlace con un archivo de enlace de puerto para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md).  
  
## <a name="starting-the-application"></a>Iniciar la aplicación  
 Antes de iniciar la orquestación de BizTalk, asegúrese de que la solicitud XML para invocar el **Read_PHOTO** operación está disponible en C:\TestLocation\MessageIn. La solicitud de XML debe ser similar a lo siguiente:  
  
```  
<Read_PHOTO xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/CUSTOMER">  
  <FILTER>WHERE NAME='Mindy Martin'</FILTER>  
</Read_PHOTO>  
```  
  
> [!NOTE]
>  El mensaje de solicitud tiene un filtro en el nombre específico porque en el mensaje de solicitud para **Update_PHOTO** operación, el valor de la columna PHOTO se actualizó con el mismo nombre. Por lo tanto, la operación de lectura leerá el mismo valor que se inserta mediante la operación de actualización.  
  
 Ahora debe iniciar la aplicación de BizTalk para leer y escribir valores de tipos de datos de gran tamaño de una base de datos de Oracle. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md).  
  
 En esta etapa, asegúrese de que:  
  
-   El archivo de puerto de recepción para recibir mensajes de solicitud para la orquestación se está ejecutando.  
  
-   El puerto de envío de archivo para recibir los mensajes de respuesta de la orquestación se está ejecutando.  
  
-   El WCF-Custom o WCF-OracleEBS puerto de envío para enviar mensajes a se está ejecutando la base de datos de Oracle.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de iniciar la aplicación, debe quitar un mensaje de solicitud en el archivo de ubicación de recepción. El esquema del mensaje de solicitud debe cumplir el esquema para el **Update_PHOTO** operación ha generado anteriormente. Por ejemplo, un mensaje de solicitud que actualiza la columna PHOTO de la tabla CUSTOMER es similar a lo siguiente:  
  
```  
<Update_PHOTO xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/CUSTOMER">  
  <FILTER>WHERE Name='Mindy Martin'</FILTER>  
  <DATA>U2FtcGxlIERhdGE=</DATA>  
</Update_PHOTO>  
```  
  
> [!NOTE]
>  Al actualizar columnas BLOB, el elemento de datos siempre debe contener un valor codificado en base64. Para el objeto CLOB y NCLOB, el elemento de datos puede tener los valores de cadena.  
  
 El mensaje de solicitud anterior actualiza el valor en la columna PHOTO para el registro que coincida con la cláusula WHERE. Vea los esquemas de mensaje para operaciones en tipos de datos grandes para obtener más información sobre el esquema de mensaje de solicitud para realizar operaciones en tipos de datos de gran tamaño mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
 La orquestación consume el mensaje y lo envía a la base de datos de Oracle. La respuesta de la base de datos de Oracle se guarda en la otra ubicación de archivo definida como parte de la orquestación. Por ejemplo, la respuesta de la base de datos de Oracle para el mensaje de solicitud anterior es similar al siguiente:  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<Update_PHOTOResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/CUSTOMER" />  
```  
  
 Ahora la orquestación construye un mensaje de solicitud para el **Read_PHOTO** operación utilizando el mensaje de solicitud disponible en C:\TestLocation\MessageIn. El mensaje de solicitud se envía a la base de datos de Oracle y la respuesta se guarda en la misma ubicación de archivo. La respuesta para la operación de lectura en la columna PHOTO es similar al siguiente:  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<Read_PHOTOResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/CUSTOMER">  
  <Read_PHOTOResult>U2FtcGxlIERhdGE=</Read_PHOTOResult>  
</Read_PHOTOResponse>  
```  
  
> [!NOTE]
>  Tenga en cuenta que la respuesta contiene el mismo valor para la columna PHOTO que pasa el **Update_PHOTO** operación.  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez que haya implementado y configurado el proyecto de BizTalk, puede exportar opciones de configuración a un archivo XML llamado el archivo de enlace. Cuando genere un archivo de enlace, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear elementos como puertos de envío y recepción para la misma orquestación. Para obtener más información acerca de los archivos de enlace, consulte [reutilizar enlaces del adaptador con Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md).  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)