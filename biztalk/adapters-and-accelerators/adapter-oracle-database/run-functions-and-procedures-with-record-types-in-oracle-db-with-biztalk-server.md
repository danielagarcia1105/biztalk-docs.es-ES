---
title: Invocar funciones y procedimientos con tipos de registro en la base de datos de Oracle mediante BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccdc150e-055a-47df-af3e-64931946455d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d8aa9b3202adaf57e7ec213a81384606eb1b8a4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963042"
---
# <a name="invoke-functions-and-procedures-with-record-types-in-oracle-database-using-biztalk-server"></a>Invocar funciones y procedimientos con tipos de registro en la base de datos de Oracle mediante BizTalk Server
Tipos de registros de Oracle se usan para representar la información jerárquica de parámetros pasados a los procedimientos y funciones de PL/SQL. La [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone los tipos de registros como tipos XML complejos. Para obtener más información acerca de cómo los [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es compatible con tipos de registros, consulte [operaciones en funciones y procedimientos con tipos de registro en la base de datos de Oracle.](../../adapters-and-accelerators/adapter-oracle-database/operations-on-functions-and-procedures-with-record-types-in-oracle-database.md). Para obtener información acerca de la estructura XML para tipos de registros, vea [esquemas de mensaje para tipos de registros](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-record-types.md).  
  
## <a name="how-to-invoke-functions-in-an-oracle-database"></a>¿Cómo invocar funciones en una base de datos de Oracle?  
 Realizar una operación en una base de datos de Oracle mediante [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica procedimientos tareas que se describen en [bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md). Para invocar una función en una base de datos de Oracle que devuelve simple y anidados son tipos de registros, estas tareas:  
  
1.  Cree un proyecto de BizTalk y genere el esquema para la función que desea invocar en una base de datos de Oracle.  
  
2.  Crear mensajes en el proyecto de BizTalk para enviar y recibir mensajes de la base de datos de Oracle.  
  
3.  Crear una orquestación para invocar la función en la base de datos de Oracle.  
  
4.  Compilar e implementar el proyecto de BizTalk.  
  
5.  Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
6.  Inicie la aplicación de BizTalk.  
  
 Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="sample-based-on-this-topic"></a>Ejemplo basado en este tema  
 Un ejemplo, Func_RecordTypes, basado en este tema también se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).  
  
## <a name="generating-schema"></a>Generar el esquema  
 En este tema, para demostrar cómo [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite la invocación de función que devuelven el registro de tipo de parámetros que se va a invocar:  
  
-   La función GET_ACCOUNTADDRESS que devuelve un tipo de registro simple.  
  
-   La función GET_ACCOUNTINFO que devuelve un tipo de registro anidado.  
  
 Estas funciones están disponibles como parte de la ACCOUNT_PKG creado mediante la ejecución de los scripts SQL que se proporciona con los ejemplos. Para obtener más información sobre los ejemplos y las secuencias de comandos SQL, consulte [ejemplos de esquema](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md).  
  
 Por lo tanto, nos debemos genere el esquema para el tanto las funciones, GET_ACCOUNTADDRESS y GET_ACCOUNTINFO, disponible en el esquema de SCOTT\Package\ACCOUNT_PKG. Vea [recuperar metadatos para operaciones de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md) para obtener más información sobre cómo generar el esquema.  
  
## <a name="defining-messages-and-message-types"></a>Definición de mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes en la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Debe vincular el esquema generado en el primer paso para los mensajes de la ventana Vista orquestación del proyecto de BizTalk.  
  
 En este tema, debe crear dos conjuntos de mensajes de solicitud-respuesta: establece una solicitud y respuesta para invocar la función GET_ACCOUNTADDRESS y recibir una respuesta; establece el otro mensaje de solicitud y respuesta para invocar la función GET_ACCOUNTINFO y recibir una respuesta.  
  
 Realice los pasos siguientes para crear mensajes y vincularlas al esquema.  
  
#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vincular al esquema  
  
1.  Abra la ventana Vista orquestación del proyecto de BizTalk, si no está ya abierto. Para ello, haga clic en **vista**, seleccione **otras ventanas**y, a continuación, haga clic en **Vista orquestación**.  
  
2.  En Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
3.  Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  
  
4.  En el **propiedades** panel para **Message_1**, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo de **solicitar**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *Func_RecordTypes.OracleDBBindingSchema.GET_ACCOUNTINFO*, donde *Func_RecordTypes* es el nombre de su Proyecto de BizTalk. *OracleDBBindingSchema* es el esquema generado para la función GET_ACCOUNTADDRESS.|  
  
5.  Repita el paso anterior para crear mensajes de más de tres. En el **propiedades** panel para los mensajes nuevos, haga lo siguiente:  
  
    |Identificador de conjunto a|Establecer el tipo de mensaje en|  
    |-----------------------|-------------------------|  
    |Respuesta|*Func_RecordTypes.OracleDBBindingSchema.GET_ACCOUNTINFOResponse*|  
    |Solicitud2|*Func_RecordTypes.OracleDBBindingSchema.GET_ACCOUNTADDRESS*|  
    |: 2|*Func_RecordTypes.OracleDBBindingSchema.GET_ACCOUNTADDRESSResponse*|  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para usar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para invocar una función devuelve los tipos de registro simples y complejos. En esta orquestación, coloque dos mensajes de solicitud:  
  
-   Uno para la función GET_ACCOUNTADDRESS que devuelve un tipo de registro simple.  
  
-   Uno para la función GET_ACCOUNTINFO que devuelve un tipo de registro anidado.  
  
 Estos mensajes se quitan en una ubicación de recepción. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] consume los mensajes y los pasa a la base de datos de Oracle a través de ODP. La respuesta de la base de datos de Oracle se guarda en otra ubicación. Dado que la orquestación toma dos solicitudes simultáneamente, debe incluir una forma acciones paralelas en la orquestación. Para cada acción paralela, debe incluir el envío y recepción formas a fin de enviar mensajes a la base de datos de Oracle y recibir respuestas, respectivamente. Sin embargo, puede usar los mismos puertos para enviar y recibir mensajes para ambas operaciones. Contendría una orquestación típica para llevar a cabo ambas operaciones al mismo tiempo:  
  
-   Enviar y recibir formas a fin de enviar mensajes a la base de datos de Oracle y recibir respuestas.  
  
-   Un unidireccional puerto de recepción para recibir mensajes de solicitud para enviar a la base de datos de Oracle.  
  
-   Puerto para enviar mensajes de solicitud con Oracle con la base de datos y reciban respuestas de envío bidireccional.  
  
-   Un puerto de envío unidireccional para enviar las respuestas de base de datos de Oracle en una carpeta.  
  
 Una orquestación de ejemplo es similar al siguiente:  
  
 ![Orquestación para usar tipos de registro en Oracle](../../adapters-and-accelerators/adapter-oracle-database/media/6ee5e57b-48d5-435a-a16b-83bac878d0b7.gif "6ee5e57b-48d5-435a-a16b-83bac878d0b7")  
  
### <a name="adding-message-shapes"></a>Agregar formas de mensaje  
 Asegúrese de que especifique las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación just-mencionado. En la tabla siguiente se enumera las formas en que se debe incluir por una de las acciones paralelas.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-Establecer **nombre** a *ReceiveMessage*<br />-Establecer **activar** a *es True*|  
|SendMessage|Send|-Establecer **nombre** a *SendMessage*|  
|ReceiveResponse|Receive|-Establecer **nombre** a *ReceiveResponse*<br />-Establecer **activar** a *False*|  
|SendResponse|Send|-Establecer **nombre** a *SendResponse*|  
  
 En la tabla siguiente se enumera las formas que se deben incluir por otras acciones paralelas.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ReceiveMessage2|Receive|-Establecer **nombre** a *ReceiveMessage2*<br />-Establecer **activar** a *es True*|  
|SendMessage2|Send|-Establecer **nombre** a *SendMessage2*|  
|ReceiveResponse2|Receive|-Establecer **nombre** a *ReceiveResponse2*<br />-Establecer **activar** a *False*|  
|SendResponse2|Send|-Establecer **nombre** a *SendResponse2*|  
  
### <a name="adding-ports"></a>Agregar puertos  
 Asegúrese de que especifique las siguientes propiedades para cada uno de los puertos lógicos. Los nombres que aparecen en la columna de puerto son los nombres de los puertos, como se muestra en la orquestación.  
  
|Puerto|Propiedades|  
|----------|----------------|  
|FileIn|-Establecer **identificador** a *FileIn*<br />-Establecer **tipo** a *FileInType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *de recepción*|  
|LOBPort|-Establecer **identificador** a *LOBPort*<br />-Establecer **tipo** a *LOBPortType*<br />-Establecer **patrón de comunicación** a *solicitudes y respuestas*<br />-Establecer **dirección de comunicación** a *envío y recepción*|  
|SaveResponse|-Establecer **identificador** a *SaveResponse*<br />-Establecer **tipo** a *SaveResponseType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *enviar*|  
  
 Dado que se van a procesar la solicitud de dos y mensajes de respuesta usando estos puertos, debe crear dos operaciones para cada puerto, donde cada operación corresponde a un tipo de mensaje. Para crear una operación, haga clic en la forma de puerto y seleccione **nueva operación**. Nombre de la primera operación para cada puerto como **NestedRecType** y la segunda operación para cada puerto como **SimpleRecType**.  
  
### <a name="using-correlations"></a>Uso de correlaciones  
 La correlación es el proceso de hacer coincidir un mensaje entrante con la instancia apropiada de una orquestación. En la orquestación que se esté quitando dos mensajes de solicitud, uno para cada sobrecarga. Uso de la correlación, se asocia un mensaje de solicitud con la orquestación derecha. Para obtener más información acerca de la correlación, vea [usar correlaciones en orquestaciones](../../core/using-correlations-in-orchestrations.md)  
  
##### <a name="to-use-correlations"></a>Para utilizar las correlaciones  
  
1.  Promocionar una propiedad desde el esquema generado para cada función. Por ejemplo, promover la propiedad CUSTNAME desde el esquema de la función GET_ACCOUNTADDRESS; promocionar la propiedad de la Ayuda desde el esquema de función GET_ACCOUNTINFO. Para promocionar una propiedad, haga clic en la propiedad en la vista Esquema, seleccione **promover**y, a continuación, seleccione **promoción rápida**. Esto agrega un archivo PropertySchema.xsd al proyecto de BizTalk.  
  
     Para obtener información acerca de cómo promover una propiedad, vea [promocionar propiedades](../../core/promoting-properties.md).  
  
2.  Desde la Vista orquestación, haga clic en **tipos de correlaciones**y, a continuación, seleccione **nuevo tipo de correlación**.  
  
3.  El **propiedades de correlación** cuadro de diálogo muestra las propiedades promocionadas en el paso 1. Seleccione una propiedad y, a continuación, haga clic en **agregar**.  
  
4.  Haga clic en **Aceptar**.  
  
5.  Para crear tipos de correlaciones para los otros derechos de propiedad promocionada, repita estos pasos.  
  
6.  Cambiar el nombre de los tipos de correlaciones en función de la propiedad a la que están asociados. Puede cambiar el nombre de los tipos de correlaciones para *CorrelationType_CUSTNAME* (para la propiedad CUSTNAME) y *CorrelationType_AID* (para la propiedad de Ayuda).  
  
7.  Desde la Vista orquestación, haga clic en **conjuntos de correlaciones**y, a continuación, seleccione **nuevo conjunto de correlaciones**.  
  
8.  Haga clic en el conjunto de correlaciones recién agregada y, a continuación, haga clic en **propiedades**. En el **propiedades** panel, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Tipo de correlación|*Func_RecordTypes.CorrelationType_CUSTNAME*|  
    |Identificador|*Correlation_CUSTNAME*|  
  
9. Agregar otro conjunto de correlación y especifique las siguientes propiedades de la **propiedades** panel.  
  
    |Use|Para|  
    |--------------|----------------|  
    |Tipo de correlación|*Func_RecordTypes.CorrelationType_AID*|  
    |Identificador|*Correlation_AID*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>Especificar mensajes de las formas de acción y conéctelos a los puertos  
 En la tabla siguiente especifica las propiedades y sus valores que se deben establecer para especificar los mensajes para las formas de acción y vincularlas a los puertos. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación que se ha mencionado anteriormente.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveMessage|-Establecer **Inicializando conjuntos de correlaciones** a *Correlation_AID*<br />-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *FileIn.NestedRecType.Request*|  
|SendMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *LOBPort.NestedRecType.Request*|  
|ReceiveResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *LOBPort.NestedRecType.Response*|  
|SendResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *SaveResponse.NestedRecType.Request*|  
|ReceiveMessage2|-Establecer **Inicializando conjuntos de correlaciones** a *Correlation_CUSTNAME*<br />-Establecer **mensaje** a *Solicitud2*<br />-Establecer **operación** a *FileIn.SimpleRecType.Request*|  
|SendMessage2|-Establecer **mensaje** a *Solicitud2*<br />-Establecer **operación** a *LOBPort.SimpleRecType.Request*|  
|ReceiveResponse2|-Establecer **mensaje** a *: 2*<br />-Establecer **operación** a *LOBPort.SimpleRecType.Response*|  
|SendResponse2|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *SaveResponse.SimpleRecType.Request*|  
  
 Después de especificar estas propiedades, las formas de mensaje y los puertos que están conectados y la orquestación se completa.  
  
 Ahora debe compilar la solución de BizTalk e implementarlo en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).  
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el **orquestaciones** panel de la consola de administración de BizTalk Server. Debe usar la consola de administración de BizTalk Server para configurar la aplicación. Para obtener un tutorial, vea [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).
  
 Configuración de una aplicación implica:  
  
-   Selección de un host de la aplicación.  
  
-   Asignación de los puertos que ha creado en la orquestación con puertos físicos en la consola de administración de BizTalk Server. Para que esta orquestación debe:  
  
-   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde se colocará los mensajes de solicitud, uno para cada procedimiento sobrecargado. La orquestación de BizTalk se consumen los mensajes de solicitud y enviarla a la base de datos de Oracle.  
  
-   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk colocará los mensajes de respuesta, uno para cada función, que contiene la respuesta de la base de datos de Oracle.  
  
    -   Definir un puerto de envío WCF-Custom o WCF-OracleDB físico para enviar mensajes a la base de datos de Oracle. También debe especificar la acción en el puerto de envío. Para obtener información sobre cómo crear puertos de WCF-Custom o WCF-OracleDB, consulte [configurar manualmente un enlace de puerto físico para el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md). Dado que el WCF-Custom o WCF-OracleDB puerto de envío envía y recibe mensajes sean conformes a más de un esquema y realiza dos operaciones, debe establecer acción dinámico para las operaciones. Para obtener más información acerca de las acciones, vea [configurar la acción SOAP para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md). Para esta orquestación, debe establecerse la acción como se indica a continuación:  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="NestedRecType" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTINFO" />  
          <Operation Name="SimpleRecType" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTADDRESS" />  
        </BtsActionMapping>  
        ```  
  
        > [!NOTE]
        >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde la consola de administración de BizTalk Server para crear puertos de envío (para las llamadas salientes) o puertos de recepción (para las llamadas entrantes). Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).
  
## <a name="starting-the-application"></a>A partir de la aplicación  
 Debe iniciar la aplicación de BizTalk para invocar una función en una tabla de base de datos de Oracle. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md).  
  
 En esta fase, asegúrese de que:  
  
-   El archivo de puerto de recepción para recibir mensajes de solicitud de ejecución de la orquestación.  
  
-   El puerto de envío de archivo para recibir los mensajes de respuesta de la orquestación se está ejecutando.  
  
-   El puerto de envío WCF-Custom o WCF-OracleDB para enviar mensajes a la base de datos de Oracle se está ejecutando.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, debe quitar dos mensajes (uno para cada función) en el archivo de ubicación de recepción de solicitud. El esquema para los mensajes de solicitud debe ajustarse al esquema para las funciones que ha generado anteriormente. La orquestación consume los mensajes de solicitud y los envía a la base de datos de Oracle. La respuesta de la base de datos de Oracle se guarda en otra ubicación de archivo definido como parte de la orquestación.  
  
 Vea [esquemas de mensaje para funciones y procedimientos](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md) para obtener más información acerca del esquema de mensaje de solicitud para invocar las funciones que usan el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
 Por ejemplo, el mensaje de solicitud para invocar la función GET_ACCOUNINFO es:  
  
```  
<GET_ACCOUNTINFO xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
  <AID>100000</AID>  
</GET_ACCOUNTINFO>  
```  
  
 De forma similar, el mensaje de solicitud para invocar la función GET_ACCOUNTADDRESS es:  
  
```  
<GET_ACCOUNTADDRESS xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
  <CUSTNAME>Mindy Martin</CUSTNAME>  
</GET_ACCOUNTADDRESS>  
```  
  
 El primer mensaje de solicitud, invoca la función GET_ACCOUNTINFO que devuelve un tipo de registro anidado. El mensaje de respuesta para invocar la función GET_ACCOUNTINFO es:  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<GET_ACCOUNTINFOResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
  <GET_ACCOUNTINFOResult>  
    <ACCT xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTINFO">  
      <ACCTID>100000</ACCTID>   
      <NAME>Kim Ralls</NAME>   
      <BALANCE>10000</BALANCE>   
    </ACCT>  
    <ADDRESS xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTINFO">  
      <STREET>1234 Main St.</STREET>   
      <CITY>Seattle</CITY>   
      <STATE>WA</STATE>   
    </ADDRESS>  
  </GET_ACCOUNTINFOResult>  
</GET_ACCOUNTINFOResponse>  
```  
  
 El segundo mensaje de solicitud, invoca la función GET_ACCOUNTADDRESS que devuelve un tipo de registro simple. El mensaje de respuesta para invocar la función GET_ACCOUNTADDRESS es:  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<GET_ACCOUNTADDRESSResponse mlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
  <GET_ACCOUNTADDRESSResult>  
    <ID xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTADDRESS">100004</ID>  
    <NAME xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTADDRESS">Mindy Martin</NAME>  
    <STREET xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTADDRESS">6789 Cherry St.</STREET>  
    <CITY xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTADDRESS">New York</CITY>  
    <STATE xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTADDRESS">NY</STATE>  
  </GET_ACCOUNTADDRESSResult>  
</GET_ACCOUNTADDRESSResponse>  
```  
  
## <a name="possible-exceptions"></a>Posibles excepciones  
 Para obtener información sobre las excepciones puede surgir al llamar a funciones o procedimientos mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [excepciones y control de errores con el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md).  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez haya implementado y configurado el proyecto de BizTalk, puede exportar la configuración en un archivo XML denominado archivo de enlaces. Una vez que se genera un archivo de enlaces, puede importar los valores de configuración desde el archivo para que no es necesario crear los puertos de envío, recepción, puertos, etc. para la misma orquestación. Para obtener más información acerca de los archivos de enlace, vea [enlaces del adaptador de base de datos de Oracle reutilizar](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md).  
  
## <a name="see-also"></a>Vea también  
[Bloques de creación de aplicaciones de BizTalk de desarrollar con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)