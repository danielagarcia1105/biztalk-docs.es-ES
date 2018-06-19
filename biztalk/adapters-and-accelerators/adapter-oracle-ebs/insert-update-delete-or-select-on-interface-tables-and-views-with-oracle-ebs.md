---
title: Insertar, actualizar, eliminar o seleccionar en tablas de interfaz y las vistas de interfaz con Oracle E-Business Suite | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 85f42431-80fb-49be-86d1-bb21eee5e4f5
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adc837fb72c0e18370d28450bf40f162f9849230
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968018"
---
# <a name="insert-update-delete-or-select-on-interface-tables-and-interface-views-with-oracle-e-business-suite"></a>Insertar, actualizar, eliminar o seleccionar en tablas de interfaz y las vistas de interfaz con Oracle E-Business Suite
El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]superficies de un conjunto de operaciones estándares, como Insert, Update, Delete, Select en la interfaz de tablas y vistas. Este tema proporciona instrucciones sobre cómo realizar estas operaciones mediante el adaptador. Para obtener más información acerca del modo en que el adaptador admite estas operaciones, vea [operaciones en tablas de interfaz y vistas de interfaz](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md). Para obtener información acerca de la estructura del mensaje SOAP para estas operaciones, vea [esquemas de mensaje para Insert, Update, Delete y las operaciones de Select](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md).  
  
> [!NOTE]
>  El adaptador también expone las operaciones específicas de tablas y vistas que contienen tipos de datos de gran tamaño como BLOB, CLOB, NCLOB y BFILE. Para obtener más información acerca de estas operaciones, vea [operaciones en tablas de interfaz, vistas de interfaz, tablas y vistas que contienen LOB datos](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md). Para obtener instrucciones sobre cómo realizar operaciones en tablas y columnas con tipos de datos de gran tamaño mediante BizTalk Server, consulte [completar las operaciones en tablas con tipos de datos de gran tamaño en Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/run-table-operations-with-large-data-types-in-oracle-ebs-using-a-wcf-service.md).  
  
## <a name="how-to-perform-basic-operations-on-oracle-e-business-suite"></a>Cómo realizar operaciones básicas en Oracle E-Business Suite  
 Realizar una operación en Oracle E-Business Suite mediante [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica procedimientos tareas que se describen en [bloques de creación para crear aplicaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md). Para llevar a cabo Insert, Update, Delete o las operaciones Select en las tablas y vistas en Oracle E-Business Suite, estas tareas son:  
  
1.  Crear un proyecto de BizTalk y genere el esquema para la operación que desea invocar en una tabla de interfaz o la vista.  
  
2.  Crear mensajes en el proyecto de BizTalk para enviar y recibir mensajes de Oracle E-Business Suite.  
  
3.  Crear una orquestación para invocar la operación en la tabla de interfaz o la vista.  
  
4.  Compilar e implementar el proyecto de BizTalk.  
  
5.  Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
6.  Inicie la aplicación de BizTalk.  
  
 Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="generating-schema"></a>Generar el esquema  
 Este tema muestra cómo realizar las operaciones Select, Update, Delete o Insert básica mediante la inserción de registros en la tabla de interfaz AR_ARCHIVE_PURGE_INTERIM en Oracle E-Business Suite. Esta tabla de interfaz está disponible en la **cuentas por cobrar** aplicación en Oracle E-Business Suite.  
  
 Para demostrar cómo insertar registros, se genera el esquema para la operación de inserción para la tabla AR_ARCHIVE_PURGE_INTERIM. Debe crear un proyecto de BizTalk y utilizar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar el esquema. Vea [recuperación de metadatos para las operaciones de Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md) para obtener más información acerca de cómo generar esquemas.  
  
## <a name="defining-messages-and-message-types"></a>Definición de mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes de la orquestación. Normalmente, un mensaje es una variable cuyo tipo está definido por el esquema correspondiente. Ahora debe crear mensajes de la orquestación y vincularlos a los esquemas generados en el paso anterior.  
  
#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vincular al esquema  
  
1.  Agregar una orquestación al proyecto de BizTalk. En el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**. Escriba un nombre para la orquestación de BizTalk y, a continuación, haga clic en **agregar**.  
  
2.  Abra la ventana Vista orquestación del proyecto de BizTalk, si no está ya abierto. Para ello, haga clic en **vista**, seleccione **otras ventanas**y, a continuación, haga clic en **Vista orquestación**.  
  
3.  En Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
4.  Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  
  
5.  En el **propiedades** panel para la **Message_1**, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Escriba `Request`|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *InsertInterfaceTable.OracleEBSBinding.Insert*, donde InsertInterfaceTable es el nombre de su proyecto de BizTalk. OracleEBSBinding es el esquema generado para la operación de inserción en la tabla AR_ARCHIVE_PURGE_INTERIM.|  
  
6.  Repita el paso 2 para crear un nuevo mensaje. En el **propiedades** panel para el nuevo mensaje, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Escriba `Response`|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *InsertInterfaceTable.OracleEBSBinding.InsertResponse*.|  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para usar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para realizar una operación en Oracle E-Business Suite. En esta orquestación, se coloca un mensaje de solicitud en una determinada ubicación de recepción. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] consume este mensaje y lo pasa al Oracle E-Business Suite. La respuesta de Oracle E-Business Suite se guarda en otra ubicación. Contendría una orquestación típica para realizar operaciones básicas de la tabla de base de datos de Oracle:  
  
-   Enviar y recibir formas a fin de enviar mensajes a la base de datos de Oracle y recibir respuestas.  
  
-   Un unidireccional puerto de recepción para recibir mensajes de solicitud para enviar a la base de datos de Oracle.  
  
-   Puerto para enviar mensajes de solicitud con Oracle con la base de datos y reciban respuestas de envío bidireccional.  
  
-   Un puerto de envío unidireccional para enviar las respuestas de base de datos de Oracle en una carpeta.  
  
 Una orquestación de ejemplo para la operación de selección es similar al siguiente:  
  
 ![Orquestación para insertar datos en tablas de interfaz](../../adapters-and-accelerators/adapter-oracle-ebs/media/8a4508c5-9949-4043-9de5-d1226db8117b.gif "8a4508c5-9949-4043-9de5-d1226db8117b")  
  
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
|ReceiveMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *MessageIn.Insert.Request*|  
|SendMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *LOBPort.Insert.Request*|  
|ReceiveResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *LOBPort.Insert.Response*|  
|SendResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *ResponseOut.Insert.Request*|  
  
 Después de especificar estas propiedades, las formas de mensaje y los puertos que están conectados y la orquestación está completa.  
  
 Ahora deberá compilar la solución de BizTalk e implementarlo en BizTalk Server. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).  
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, la orquestación que creó anteriormente se muestra en el panel de orquestaciones en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Debe utilizar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para configurar la aplicación. Para obtener un tutorial, vea [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).  
  
 Configuración de una aplicación implica:  
  
-   Selección de un host de la aplicación.  
  
-   Asignación de los puertos que ha creado en la orquestación con puertos físicos en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para que esta orquestación debe:  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde se colocará un mensaje de solicitud. La orquestación de BizTalk consumirá el mensaje de solicitud y enviar a Oracle E-Business Suite.  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta de Oracle E-Business Suite.  
  
    -   Definir un puerto de envío WCF-Custom o WCF-OracleEBS físico para enviar mensajes a Oracle E-Business Suite. También debe especificar la acción en el puerto de envío. Para obtener información sobre cómo crear puertos, consulte [configurar manualmente un puerto físico enlazado con el adaptador de Oracle E-Business](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)  
  
         Para realizar operaciones en tablas de interfaz o interfaz vistas mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], debe establecer el contexto de la aplicación correcta en el que se invoca la operación. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] proporciona ciertas propiedades de enlace para especificar el contexto de la aplicación para cualquier operación. Debe establecer estas propiedades de enlace en el puerto WCF-Custom o WCF-OracleEBS usado para realizar operaciones en tablas de interfaz.  
  
        -   Si el **ClientCredentialType** enlaza la propiedad se establece en **base de datos**, a continuación, debe especificar las siguientes propiedades de enlace para establecer el contexto de las aplicaciones.  
  
            |Propiedad de enlace|Valor|  
            |----------------------|-----------|  
            |**OracleUserName**|Especifique el nombre de un usuario de Oracle E-Business Suite. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no conserva el caso del valor que especifique para la **OracleUserName** propiedad de enlace cuando se conecta a Oracle E-Business Suite. El nombre de usuario se pasa a Oracle E-Business Suite utilizando las reglas estándar de SQL * Plus. Sin embargo, si desea que el caso de que se conserve el nombre de usuario o si desea escribir un nombre de usuario que contiene caracteres especiales, debe especificar el valor entre comillas dobles.|  
            |**OraclePassword**|La contraseña para el usuario de Oracle E-Business Suite. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no conserva el caso del valor que especifique para la **OraclePassword** propiedad de enlace cuando se conecta a Oracle E-Business Suite. La contraseña se pasa a Oracle E-Business Suite utilizando las reglas estándar de SQL * Plus. Sin embargo, si desea que el caso de la contraseña que se va a conservar o si desea escribir una contraseña que contiene caracteres especiales, debe especificar el valor entre comillas dobles.|  
            |**OracleEBSResponsibilityName**|La responsabilidad asociada al usuario de Oracle E-Business Suite.|  
  
        -   Si el **ClientCredentialType** enlaza la propiedad se establece en **EBusiness**, deben haber especificado las credenciales de Oracle E-Business al establecer la conexión. En tal caso solo se debe especificar valor de la **OracleEBSResponsibilityName** propiedad de enlace.  
  
         Para obtener más información acerca de las propiedades de enlace diferente, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md). Para obtener más información sobre cómo el adaptador admite establecer el contexto de la aplicación, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
  
        > [!NOTE]
        >  Puede establecer el contexto de la aplicación mediante la especificación de las propiedades de enlace o estableciendo el mensaje propiedades de contexto expuestas por la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Para obtener instrucciones sobre cómo establecer las propiedades de enlace, consulte [configurar las propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md). Para obtener instrucciones sobre cómo establecer el contexto de la aplicación mediante las propiedades de contexto de mensaje, consulte [configurar las propiedades contexto de mensaje usando de contexto de aplicación en Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md).  
  
        > [!NOTE]
        >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para crear puertos de envío (para las llamadas salientes) o puertos de recepción (para las llamadas entrantes). Para obtener más información, consulte [configurar un físico puerto de enlace utilizando un archivo de enlace de puerto para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md).  
  
## <a name="starting-the-application"></a>A partir de la aplicación  
 Debe iniciar la aplicación de BizTalk para insertar registros en la tabla de interfaz AR_ARCHIVE_PURGE_INTERIM. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md).  
  
 En esta fase, asegúrese de que:  
  
-   El archivo de puerto de recepción para recibir mensajes de solicitud de ejecución de la orquestación.  
  
-   El puerto de envío de archivo para recibir los mensajes de respuesta de la orquestación se está ejecutando.  
  
-   El WCF-Custom o WCF-OracleEBS puerto de envío para enviar mensajes a Oracle E-Business Suite se está ejecutando.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, debe quitar un mensaje de solicitud en el archivo de ubicación de recepción. El esquema del mensaje de solicitud debe cumplir el esquema para la operación de inserción que ha generado anteriormente. Por ejemplo, el mensaje de solicitud para seleccionar todos los registros de la tabla de interfaz AR_ARCHIVE_PURGE_INTERIM es:  
  
```  
<Insert xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/AR/AR/AR_ARCHIVE_PURGE_INTERIM">  
  <RECORDSET>  
    <InsertRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/AR/AR_ARCHIVE_PURGE_INTERIM">  
      <TRX_ID>001</TRX_ID>  
      <RELATED_ID>002</RELATED_ID>  
    </InsertRecord>  
  </RECORDSET>    
</Insert>  
```  
  
 Este mensaje de solicitud, inserta registros en la tabla de interfaz AR_ARCHIVE_PURGE_INTERIM. Vea [esquemas de mensaje para Insert, Update, Delete y las operaciones de Select](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md) para obtener más información acerca del esquema de mensaje de solicitud para realizar operaciones de DML básicas sobre el uso de Oracle E-Business Suite el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
 Para las columnas de datos simples, como en el mensaje de solicitud anterior, también puede usar el **InlineValue** atributo. Para obtener más información sobre el atributo InlineValue, vea la descripción de la operación de inserción en [operaciones en tablas de interfaz y vistas de interfaz](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md).  
  
 Por ejemplo, el mensaje de solicitud anterior con valores en línea será similar al siguiente:  
  
```  
<Insert xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/AR/AR/AR_ARCHIVE_PURGE_INTERIM">  
  <RECORDSET>  
    <InsertRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/AR/AR_ARCHIVE_PURGE_INTERIM">  
      <TRX_ID InlineValue="(Select TRX_ID FROM table_name)">001</TRX_ID>  
      <RELATED_ID>002</RELATED_ID>  
    </InsertRecord>  
  </RECORDSET>    
</Insert>  
```  
  
 En este mensaje de solicitud, se recupera el valor de columna TRX_ID de otra tabla. Por lo tanto, aunque "001" se especifica como un valor para TRX_ID, el valor de la instrucción SELECT especificada para el atributo InlineValue obtener incrustarán en la tabla.  
  
 La orquestación consume el mensaje y lo envía a Oracle E-Business Suite. La respuesta de Oracle E-Business Suite se guarda en la otra ubicación de archivo definida como parte de la orquestación. Por ejemplo, la respuesta de Oracle E-Business Suite para el mensaje de solicitud anterior es:  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<InsertResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/AR/AR/AR_ARCHIVE_PURGE_INTERIM">  
  <InsertResult>1</InsertResult>   
</InsertResponse>  
```  
  
 La respuesta contiene el número de filas insertadas en la tabla.  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez haya implementado y configurado el proyecto de BizTalk, puede exportar la configuración en un archivo XML denominado archivo de enlace. Después de generar un archivo de enlace, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear elementos como los puertos de envío y puertos de recepción para la misma orquestación. Para obtener más información acerca de los archivos de enlace, vea [reutilizar enlaces del adaptador con Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md).  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)