---
title: Ejecutar operaciones en tablas y vistas con tipos de datos de gran tamaño mediante el adaptador de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cec15b01-7a57-4917-8c21-44a1cfaadc59
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c1bc305e45747c4471894cc362ebeeec2ee36a9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013109"
---
# <a name="run-operations-on-tables-and-views-with-large-data-types-using-the-sql-adapter"></a>Ejecutar operaciones en tablas y vistas con tipos de datos de gran tamaño mediante el adaptador de SQL
El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] permite a los clientes del adaptador para leer y actualizar datos en columnas de tipos de datos de gran tamaño, es decir, varchar (max), nvarchar (max) o varbinary (max). Para leer datos de esas columnas, los clientes del adaptador pueden usar la operación de selección. Para insertar o actualizar datos en dichas columnas, el adaptador expone una operación Set < nombre_columna >, donde < nombre_columna > es el nombre de la columna de tipo varchar (max), nvarchar (max) o varbinary (max).  
  
 Además, en SQL Server 2008, puede hacer que la columna varbinay(max) almacene datos no estructurados como documentos de texto e imágenes. Estos datos no estructurados se denominan datos FILESTREAM. Los datos de FILESTREAM se pueden almacenar como archivos en el sistema de archivos. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] permite al cliente especificar datos FILESTREAM en columnas de tipo varbinary (max). Para obtener más información sobre el almacenamiento FILESTREAM, vea [información general de FILESTREAM](https://msdn.microsoft.com/library/bb933993(SQL.100).aspx).  
  
 Este tema proporciona información acerca de ciertas tareas que debe realizar en el equipo que ejecuta SQL Server y el equipo que ejecuta el cliente de adaptador para que pueda insertar o actualizar los datos FILESTREAM. En este tema también proporciona instrucciones sobre la realización de operaciones Set < nombre_columna > para insertar los datos FILESTREAM.  
  
> [!NOTE]
>  Si va a realizar la operación en tablas con columnas de tipos definidos por el usuario, asegúrese de que se hace referencia a [operaciones en tablas y vistas con tipos definidos por el usuario mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) antes de empezar a desarrollar su aplicación.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe realizar las tareas siguientes en el equipo que ejecuta SQL Server y el equipo que ejecuta al cliente del adaptador.  

  
- **En el equipo que ejecuta SQL Server**  
  
  -   Debe habilitar FILESTREAM en la instancia de SQL Server. Para obtener más información, consulte [ http://go.microsoft.com/fwlink/?LinkId=122486 ](http://go.microsoft.com/fwlink/?LinkId=122486).  
  
  -   Debe crear una base de datos habilitada para FILESTREAM. Para obtener más información, consulte [ http://go.microsoft.com/fwlink/?LinkId=122487 ](http://go.microsoft.com/fwlink/?LinkId=122487).  
  
  -   Debe tener una tabla para almacenar datos FILESTREAM. Para obtener más información, consulte [ http://go.microsoft.com/fwlink/?LinkId=122488 ](http://go.microsoft.com/fwlink/?LinkId=122488).  
  
  -   Debe configurar MSDTC en el equipo que hospeda la base de datos de SQL Server. Para obtener instrucciones sobre cómo configurar MSDTC, vea [configurar MSDTC en el cliente de SQL Server y el adaptador](../../adapters-and-accelerators/adapter-sql/configure-msdtc-on-sql-server-and-adapter-client.md).  
  
- **En el equipo que ejecuta al cliente de adaptador**  
  
  -   Debe tener instalado el SDK de conectividad de cliente de SQL. Puede instalar el SDK de conectividad de cliente SQL ejecutando el programa de instalación de SQL Server 2008 y seleccionando **SDK de conectividad de cliente SQL** en el **selección de características** página del asistente. El adaptador utiliza el sqlncli10.dll, instalado con el SDK de conectividad de cliente de SQL, para realizar operaciones de FILESTREAM.  
  
  -   Debe configurar MSDTC en el equipo que ejecuta al cliente del adaptador. Para obtener instrucciones sobre cómo configurar MSDTC, vea [configurar MSDTC en el cliente de SQL Server y el adaptador](../../adapters-and-accelerators/adapter-sql/configure-msdtc-on-sql-server-and-adapter-client.md).  
  
  Después de completar estas tareas, ya está listo para insertar o actualizar los datos FILESTREAM en tablas de base de datos de SQL Server 2008.  
  
## <a name="how-this-topic-demonstrates-operations-on-large-data-types"></a>Cómo en este tema muestra las operaciones en tipos de datos de gran tamaño  
 Para demostrar cómo realizar operaciones de conjunto < nombre_columna > en las tablas con tipos de datos de gran tamaño, toman una tabla, los registros, que tiene columnas de identidad y un documento. La columna de identificador es de tipo uniqueidentifier y toma un GUID. Columna del documento es de tipo varbinary (max). Se supone que la columna Id. ya tiene un GUID '`438B7B4C-5491-409F-BCC1-78817C399EC3`'. Para actualizar la columna del documento, el adaptador expone la operación SetDocument.  
  
> [!NOTE]
>  Para SQL Server 2008, para demostrar operaciones de FILESTREAM, supongamos que la columna del documento puede almacenar datos FILESTREAM.  
  
## <a name="how-to-perform-operations-on-a-sql-server-database"></a>Cómo realizar operaciones en una base de datos SQL Server  
 Realizar una operación en una base de datos de SQL Server mediante el uso de [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica tareas de procedimientos se describe en [bloques de creación para desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md). Para llevar a cabo operaciones en tablas con tipos de datos grandes, estas tareas son:  
  
1. Cree un proyecto de BizTalk y genere el esquema para la operación de establecimiento < nombre_columna >. Este tema, genere el esquema para el **SetDocument** operación para la **registros** tabla.  
  
2. Crear mensajes en el proyecto de BizTalk para enviar y recibir mensajes de la base de datos de SQL Server.  
  
3. Crear una orquestación para invocar la operación SetDocument en la tabla de registros.  
  
4. Compile e implemente el proyecto de BizTalk.  
  
5. Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
6. Inicie la aplicación de BizTalk.  
  
   Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="sample-based-on-this-topic"></a>Ejemplo basado en este tema.  
 Un ejemplo, FILESTREAMOperation, basado en este tema se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).  
  
## <a name="generating-schema"></a>Generar el esquema  
 Para demostrar cómo actualizar los valores de columnas de tipos de datos de gran tamaño, genere el esquema para la operación SetDocument de la tabla de registros. Debe crear un proyecto de BizTalk y utilice el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar el esquema. Consulte [recuperación de metadatos para operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md) para obtener más información acerca de cómo generar un esquema.  
  
## <a name="defining-messages-and-message-types"></a>Definición de los mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes de la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Ahora debe crear mensajes para la orquestación y vincularlos a los esquemas que generó en el paso anterior.  
  
#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vínculo a esquema  
  
1.  Agregar una orquestación al proyecto de BizTalk. Desde el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**. Escriba un nombre para la orquestación de BizTalk y, a continuación, haga clic en **agregar**.  
  
2.  Abra la ventana Vista orquestación del proyecto de BizTalk, si aún no está abierto. Para ello, haga clic en **vista**, apunte a **Other Windows**y, a continuación, haga clic en **Vista orquestación**.  
  
3.  En la Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
4.  Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  
  
5.  En el **propiedades** panel para el **Message_1**, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Escriba `Request`|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *SetOperation.TableOperation_dbo_Records.SetDocument*, donde SetOperation es el nombre de su proyecto de BizTalk. TableOperation_dbo_Records es el esquema generado para la operación SetDocument en la tabla de registros.|  
  
6.  Repita el paso 2 para crear un nuevo mensaje. En el **propiedades** panel para el nuevo mensaje, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Escriba `Response`|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *SetOperation.TableOperation_dbo_Records.SetDocumentResponse*.|  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para utilizar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para llevar a cabo una operación en SQL Server. En esta orquestación, se coloca un mensaje de solicitud en una determinada ubicación de recepción. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] consume este mensaje y lo pasa a SQL Server. La respuesta de SQL Server se guarda en otra ubicación. Debe incluir el envío y recepción de formas para enviar mensajes a SQL Server y recibir respuestas, respectivamente. Una orquestación de ejemplo para la operación SetDocument es similar al siguiente:  
  
 ![Orquestación para realizar operaciones de FILESTREAM](../../adapters-and-accelerators/adapter-sql/media/b8c1c04c-142f-44a0-a545-8ec0cfdd9a5b.gif "b8c1c04c-142f-44a0-a545-8ec0cfdd9a5b")  
  
### <a name="adding-message-shapes"></a>Agregar formas de mensaje  
 Asegúrese de que especificar las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación simplemente mencionadas.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-Establecer **nombre** a *ReceiveMessage*<br />-Establecer **activar** a *True*|  
|SendMessage|Send|-Establecer **nombre** a *SendMessage*|  
|ReceiveResponse|Receive|-Establecer **nombre** a *ReceiveResponse*<br />-Establecer **activar** a *False*|  
|SendResponse|Send|-Establecer **nombre** a *SendResponse*|  
  
### <a name="adding-ports"></a>Agregar puertos  
 Asegúrese de que especificar las siguientes propiedades para cada uno de los puertos lógicos. Los nombres que aparecen en la columna puerto son los nombres de los puertos tal como se muestra en la orquestación.  
  
|Puerto|Propiedades|  
|----------|----------------|  
|MessageIn|-Establecer **identificador** a *MessageIn*<br />-Establecer **tipo** a *MessageInType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *de recepción*|  
|LOBPort|-Establecer **identificador** a *LOBPort*<br />-Establecer **tipo** a *LOBPortType*<br />-Establecer **patrón de comunicación** a *de solicitud-respuesta*<br />-Establecer **dirección de comunicación** a *envío y recepción*|  
|ResponseOut|-Establecer **identificador** a *ResponseOut*<br />-Establecer **tipo** a *ResponseOutType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *enviar*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>Especifique los mensajes para las formas Acción y conectarlos a puertos  
 En la tabla siguiente especifica las propiedades y sus valores que se deben establecer para especificar los mensajes para las formas Acción y vincular los mensajes a los puertos. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación que se ha mencionado anteriormente.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *MessageIn.FileStream.Request*|  
|SendMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *LOBPort.FileStream.Request*|  
|ReceiveResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *LOBPort.FileStream.Response*|  
|SendResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *ResponseOut.FileStream.Request*|  
  
 Después de especificar estas propiedades, están conectados a los puertos y formas de mensaje y la orquestación completada.  
  
 Ahora debe compilar la solución de BizTalk e implementarlo en BizTalk Server. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el panel orquestaciones, en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Debe usar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para configurar la aplicación. Para ver un tutorial, vea [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).
  
 Configuración de una aplicación implica:  
  
- Selección de un host de la aplicación.  
  
- Asignación de los puertos que ha creado en la orquestación con puertos físicos en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para esta orquestación, debe:  
  
  - Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde se colocará un mensaje de solicitud. La orquestación de BizTalk usarán el mensaje de solicitud y enviarla a la base de datos de SQL Server.  
  
  - Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta de la base de datos de SQL Server.  
  
  - Definir un puerto de envío físico de WCF-Custom o WCF-SQL para enviar mensajes a la base de datos de SQL Server. También debe especificar la acción en el puerto de envío. Para obtener información sobre cómo crear los puertos, consulte [configurar manualmente un enlace de puerto físico al adaptador de SQL](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md).
  
    > [!IMPORTANT]
    >  La operación para introducir los datos FILESTREAM debe realizarse dentro de una transacción. Por lo tanto, asegúrese de que el **UseAmbientTransaction** enlaza la propiedad se establece en **True** puerto de envío en el WCF-Custom o WCF-SQL. Para obtener más información acerca de la propiedad de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  
    > 
    > [!IMPORTANT]
    >  Para realizar una operación para insertar los datos de FILESTREAM siempre debe utilizar la autenticación de Windows para conectarse a SQL Server en el WCF-Custom o puerto de envío WCF-SQL. Por lo tanto, en el **credenciales** ficha en el cuadro de diálogo de propiedades de puerto, seleccione la **no utilizar inicio de sesión único** opción y deje el nombre de usuario y la contraseña en blanco.  
    > 
    > [!NOTE]
    >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para crear puertos de envío (para las llamadas salientes) o la recepción (para las llamadas entrantes). Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto para usar el adaptador SQL](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).
  
## <a name="starting-the-application"></a>Iniciar la aplicación  
 Debe iniciar la aplicación de BizTalk para llevar a cabo la **SetDocument** operación en el **registros** tabla. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md).
  
 En esta etapa, asegúrese de que:  
  
-   El archivo de puerto de recepción para recibir mensajes de solicitud para la orquestación se está ejecutando.  
  
-   El puerto de envío de archivo para recibir los mensajes de respuesta de la orquestación se está ejecutando.  
  
-   El puerto de envío WCF-Custom o WCF-SQL para enviar mensajes a la base de datos de SQL Server se está ejecutando.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, debe quitar un mensaje de solicitud en el archivo de ubicación de recepción. El esquema del mensaje de solicitud debe cumplir el esquema para la operación de SetDocument que ha generado anteriormente. Por ejemplo, el mensaje de solicitud para actualizar la columna del documento es:  
  
```  
<SetDocument xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Records">  
  <Filter>WHERE Id='438B7B4C-5491-409F-BCC1-78817C399EC3'</Filter>  
  <Data>UwBlAHQAdgBfAHYAYQByAGIAaQBuAGEAcgB5AE0AQQBYAA==</Data>  
</SetDocument>  
```  
  
> [!IMPORTANT]
>  El `Filter` elemento debe contener la cláusula WHERE basada en el que el adaptador actualiza los registros. El `Data` elemento debe contener un valor codificado en base64 que desea insertar en la columna del documento.  
  
 Este mensaje de solicitud actualiza la columna del documento con el valor especificado. La orquestación consume el mensaje y lo envía a la base de datos de SQL Server. La respuesta de la base de datos de SQL Server se guarda en la otra ubicación de archivo definida como parte de la orquestación. Por ejemplo, la respuesta de la base de datos de SQL Server para el mensaje de solicitud anterior es:  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<SetDocumentResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Records" />  
```  
  
 El adaptador envía una respuesta vacía el **establecer < nombre_columna >** operación.  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez que haya implementado y configurado el proyecto de BizTalk, puede exportar opciones de configuración a un archivo XML llamado el archivo de enlace. Cuando genere un archivo de enlace, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear elementos como los puertos de envío y recepción para la misma orquestación. Para obtener más información acerca de los archivos de enlace, consulte [reutilizar los enlaces del adaptador](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md).
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)