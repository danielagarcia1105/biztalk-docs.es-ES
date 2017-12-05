---
title: Invocar funciones sobrecargadas y los procedimientos de la base de datos de Oracle mediante BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: overloaded functions and procedures, invoking by using BizTalk Server
ms.assetid: a3d76361-6b0c-415a-b4f9-31939abfdc36
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30d036313a69025e7fcf0e37116fc729623ac782
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="invoke-overloaded-functions-and-procedures-in-oracle-database-using-biztalk-server"></a>Invocar funciones sobrecargadas y los procedimientos de la base de datos de Oracle mediante BizTalk Server
Funciones y procedimientos almacenados se pueden sobrecargar en una base de datos de Oracle. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite sobrecarga funciones y procedimientos, cambie el espacio de nombres de destino de la operación. Por ejemplo, la estructura del mensaje para ver los dos procedimientos sobrecargados el siguiente aspecto:  
  
```  
Stored Procedure Overload 1:  
<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]/overload1">    
  <[PRM1_NAME]>value1</[PRM1_NAME]>  
  <[PRM2_NAME]>value1</[PRM2_NAME]>  
  …  
</[SP_NAME]>  
  
Stored Procedure Overload 2:  
<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]/overload2">    
  <[PRM1_NAME]>value1</I_[PRM1_NAME]>  
  <[PRM2_NAME]>value1</I_[PRM2_NAME]>  
  …  
</[SP_NAME]>  
```  
  
 La estructura del mensaje SOAP y la acción SOAP necesarios para invocar una función sobrecargada o procedimiento es similar a invocar una función y el procedimiento, tal y como se describe en la sección [esquemas de mensaje para funciones y procedimientos](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md).  
  
 Invocar un procedimiento sobrecargado es similar a invocar cualquier otra función, como se describe en [invocar funciones y procedimientos de la base de datos de Oracle mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-biztalk-server.md). Sin embargo diferenciar sobrecarga funciones, la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] anexa una cadena única para el identificador de nodo y el espacio de nombres que se pone de manifiesto de artefacto sobrecargado. Esta cadena es "overload1" para la primera sobrecarga, "overload2" para la siguiente sobrecarga y así sucesivamente.  
  
## <a name="how-to-invoke-overloaded-functions-and-procedures"></a>¿Cómo llamar a procedimientos y funciones sobrecargadas?  
 Realizar una operación en una base de datos de Oracle mediante [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica procedimientos tareas que se describen en [bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md). Para invocar una función en una base de datos de Oracle, estas tareas son:  
  
1.  Cree un proyecto de BizTalk y genere el esquema para la función sobrecargada que desea invocar en una base de datos de Oracle.  
  
2.  Crear mensajes en el proyecto de BizTalk para enviar y recibir mensajes de la base de datos de Oracle. Debe crear mensajes para cada sobrecarga.  
  
3.  Crear una orquestación para invocar la función sobrecargada en la base de datos de Oracle.  
  
4.  Compilar e implementar el proyecto de BizTalk.  
  
5.  Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
6.  Inicie la aplicación de BizTalk.  
  
 Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="sample-based-on-this-topic"></a>Ejemplo basado en este tema  
 Un ejemplo, InvokeOverloadedProc, basado en este tema también se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).  
  
## <a name="generating-schema"></a>Generar el esquema  
 En este tema, para demostrar cómo invocar una función sobrecargada o un procedimiento, se invoca el procedimiento GET_ACCOUNT bajo el esquema SCOTT\Package\ACCOUNT_PKG. Este paquete se crea en el esquema SCOTT mediante la ejecución de los scripts SQL que se proporciona con los ejemplos. Se trata de un procedimiento sobrecargado donde:  
  
-   Una sobrecarga toma el identificador de cuenta como parámetro IN y devuelve una cuenta % ROWTYPE como parámetro OUT.  
  
-   Segunda sobrecarga toma el nombre de cuenta como parámetro IN y devuelve una cuenta % ROWTYPE como parámetro OUT.  
  
 Para obtener más información sobre los ejemplos y las secuencias de comandos SQL, consulte [ejemplos de esquema](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md).  
  
 Para invocar una función sobrecargada, se genere el esquema para ambos los procedimientos sobrecargados, GET_ACCOUNT.1 y GET_ACCOUNT.2. Vea [recuperar metadatos para operaciones de base de datos de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md) para obtener más información sobre cómo generar el esquema.  
  
## <a name="defining-messages-and-message-types"></a>Definición de mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes en la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Debe vincular el esquema generado en el primer paso para los mensajes de la ventana Vista orquestación del proyecto de BizTalk.  
  
 En este tema, debe crear dos conjuntos de mensajes de solicitud-respuesta, una respuesta de solicitud establecida para la primera sobrecarga de procedimiento y la segunda solicitud-respuesta establecida para el segundo procedimiento sobrecargado.  
  
 Realice los pasos siguientes para crear mensajes y vincularlas al esquema.  
  
#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vincular al esquema  
  
1.  Abra la ventana Vista orquestación del proyecto de BizTalk, si no está ya abierto. Para ello, haga clic en **vista**, seleccione **otras ventanas**y, a continuación, haga clic en **Vista orquestación**.  
  
2.  En Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
3.  Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  
  
4.  En el **propiedades** panel para **Message_1**, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo de **solicitar**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *InvokeOverloadedProc.OracleDBBindingSchema.GET_ACCOUNT*, donde *InvokeOverloadedProc* es el nombre de el proyecto de BizTalk. *OracleDBBindingSchema* es el esquema generado para el procedimiento GET_ACCOUNT.|  
  
5.  Repita el paso anterior para crear mensajes de más de tres. En el **propiedades** panel para los mensajes nuevos, haga lo siguiente:  
  
    |Identificador de conjunto a|Establecer el tipo de mensaje en|  
    |-----------------------|-------------------------|  
    |Respuesta|*InvokeOverloadedProc.OracleDBBindingSchema.GET_ACCOUNTResponse*|  
    |Solicitud2|*InvokeOverloadedProc.OracleDBBindingSchema1.GET_ACCOUNT*|  
    |: 2|*InvokeOverloadedProc.OracleDBBindingSchema1.GET_ACCOUNTResponse*|  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para utilizar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para llamar a un procedimiento sobrecargado en una base de datos de Oracle. En esta orquestación, coloque dos mensajes de solicitud, uno correspondiente a cada procedimiento sobrecargado, en las personalizaciones definidas ubicación de recepción. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] consume los mensajes y los pasa a la base de datos de Oracle a través de ODP. La respuesta de la base de datos de Oracle se guarda en otra ubicación.  
  
 Dado que la orquestación toma dos solicitudes simultáneamente, debe incluir una forma acciones paralelas en la orquestación. Para cada acción paralela, debe incluir envío y recepción formas a fin de enviar mensajes a la base de datos de Oracle y recibir respuestas. Sin embargo, puede usar los mismos puertos para enviar y recibir mensajes para ambas operaciones. Contendría una orquestación para invocar procedimientos sobrecargados simultáneamente típica:  
  
-   Enviar y recibir formas a fin de enviar mensajes a la base de datos de Oracle y recibir respuestas.  
  
-   Un unidireccional puerto de recepción para recibir mensajes de solicitud para enviar a la base de datos de Oracle.  
  
-   Puerto para enviar mensajes de solicitud con Oracle con la base de datos y reciban respuestas de envío bidireccional.  
  
-   Un puerto de envío unidireccional para enviar las respuestas de base de datos de Oracle en una carpeta.  
  
 Una orquestación de ejemplo para invocar las sobrecargas de primeros y segunda procedimiento GET_ACCOUNT es similar al siguiente:  
  
 ![Orquestación para invocar paquetes sobrecargados](../../adapters-and-accelerators/adapter-oracle-database/media/f8e4ad6f-9140-43b1-b931-28c9ba11cc8e.gif "f8e4ad6f-9140-43b1-b931-28c9ba11cc8e")  
  
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
  
 Dado que se van a procesar la solicitud de dos y mensajes de respuesta usando estos puertos, debe crear dos operaciones para cada puerto, donde cada operación corresponde a un tipo de mensaje. Para crear una operación, haga clic en la forma de puerto y, a continuación, seleccione **nueva operación**. Nombre de la primera operación para cada puerto como **Overload1** y la segunda operación para cada puerto como **Overload2**.  
  
### <a name="using-correlation"></a>Uso de la correlación  
 La correlación es el proceso de hacer coincidir un mensaje entrante con la instancia apropiada de una orquestación. En la orquestación que se esté quitando dos mensajes de solicitud, uno para cada sobrecarga. Uso de la correlación, se asocia un mensaje de solicitud con la orquestación derecha. Para obtener más información acerca de la correlación, vea [usar correlaciones en orquestaciones](../../core/using-correlations-in-orchestrations.md).  
  
##### <a name="to-use-correlations"></a>Para utilizar las correlaciones  
  
1.  Promocionar una propiedad desde el esquema generado para cada función sobrecargada. Por ejemplo, promocionar la propiedad de la Ayuda desde el esquema para la primera sobrecarga; promocionar la propiedad ANAME del esquema de la segunda sobrecarga. Para promocionar una propiedad, haga clic en la propiedad en la vista Esquema, seleccione **promover**y, a continuación, seleccione **promoción rápida**. Esto agrega un archivo PropertySchema.xsd al proyecto de BizTalk.  
  
     Para obtener información acerca de cómo promover una propiedad, vea [promocionar propiedades](../../core/promoting-properties.md).  
  
2.  Desde la Vista orquestación, haga clic en **tipos de correlaciones**y, a continuación, seleccione **nuevo tipo de correlación**.  
  
3.  El **propiedades de correlación** cuadro de diálogo muestra las propiedades que usted ha promocionado en el paso 1. Seleccione una propiedad y, a continuación, haga clic en **agregar**.  
  
4.  Haga clic en **Aceptar**.  
  
5.  Para crear tipos de correlaciones para los otros derechos de propiedad promocionada, repita estos pasos.  
  
6.  Cambiar el nombre de los tipos de correlaciones en función de la propiedad a la que están asociados. Puede cambiar el nombre de los tipos de correlaciones para *CorrelationType_AID* (para la propiedad de Ayuda) y *CorrelationType_ANAME* (para la propiedad ANAME).  
  
7.  Desde la Vista orquestación, haga clic en **conjuntos de correlaciones**y, a continuación, seleccione **nuevo conjunto de correlaciones**.  
  
8.  Haga clic en el conjunto de correlaciones recién agregada y, a continuación, haga clic en **propiedades**. En el panel Propiedades, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Tipo de correlación|*InvokeOverloadedProc.CorrelationType_AID*|  
    |Identificador|*Correlation_AID*|  
  
9. Agregar otro conjunto de correlación y especifique las siguientes propiedades en el panel Propiedades.  
  
    |Use|Para|  
    |--------------|----------------|  
    |Tipo de correlación|*InvokeOverloadedProc.CorrelationType_ANAME*|  
    |Identificador|*Correlation_ANAME*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>Especificar mensajes de las formas de acción y conéctelos a los puertos  
 En la tabla siguiente especifica las propiedades y sus valores que se deben establecer para especificar los mensajes para las formas de acción y vincular los mensajes a los puertos. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación que se ha mencionado anteriormente.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveMessage|-Establecer **Inicializando conjuntos de correlaciones** a *Correlation_AID*<br />-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *FileIn.Overload1.Request*|  
|SendMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *LOBPort.Overload1.Request*|  
|ReceiveResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *LOBPort.Overload1.Response*|  
|SendResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *SaveResponse.Overload1.Request*|  
|ReceiveMessage2|-Establecer **Inicializando conjuntos de correlaciones** a *Correlation_ANAME*<br />-Establecer **mensaje** a *Solicitud2*<br />-Establecer **operación** a *FileIn.Overload2.Request*|  
|SendMessage2|-Establecer **mensaje** a *Solicitud2*<br />-Establecer **operación** a *LOBPort.Overload2.Request*|  
|ReceiveResponse2|-Establecer **mensaje** a *: 2*<br />-Establecer **operación** a *LOBPort.Overload2.Response*|  
|SendResponse2|-Establecer **mensaje** a *: 2*<br />-Establecer **operación** a *SaveResponse.Overload2.Request*|  
  
 Después de especificar estas propiedades, las formas de mensaje y los puertos que están conectados y la orquestación se completa.  
  
 Ahora debe compilar la solución de BizTalk e implementarlo en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).  
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el **orquestaciones** panel de la consola de administración de BizTalk Server. Debe usar la consola de administración de BizTalk Server para configurar la aplicación. Para obtener un tutorial, vea [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).
  
 Configuración de una aplicación implica:  
  
-   Selección de un host de la aplicación.  
  
-   Asignación de los puertos que ha creado en la orquestación con puertos físicos en la consola de administración de BizTalk Server. Para que esta orquestación debe:  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde se colocará los mensajes de solicitud, uno para cada procedimiento sobrecargado. La orquestación de BizTalk se consumen los mensajes de solicitud y enviarla a la base de datos de Oracle.  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk colocará los mensajes de respuesta, uno para cada procedimiento sobrecargado, que contiene la respuesta de la base de datos de Oracle.  
  
    -   Definir un puerto de envío WCF-Custom o WCF-OracleDB físico para enviar mensajes a la base de datos de Oracle. También debe especificar la acción en el puerto de envío. Para obtener información sobre cómo crear puertos de WCF-Custom o WCF-OracleDB, consulte [configurar manualmente un enlace de puerto físico para el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md). Dado que el WCF-Custom o WCF-OracleDB puerto de envío envía y recibe mensajes sean conformes a más de un esquema y realiza dos operaciones, debe establecer acción dinámico para las operaciones. Para obtener más información acerca de las acciones, vea [configurar la acción SOAP para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md). Para esta orquestación, debe establecerse la acción como se indica a continuación:  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Overload1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT/overload1" />  
          <Operation Name="Overload2" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT/overload2" />  
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
 Después de ejecutar la aplicación, debe quitar dos mensajes (uno para cada procedimiento sobrecargado) en el archivo de ubicación de recepción de solicitud. El esquema para los mensajes de solicitud debe ajustarse al esquema para el procedimiento que ha generado anteriormente. Vea [esquemas de mensaje para funciones y procedimientos](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md) para obtener más información acerca del esquema de mensaje de solicitud para invocar las funciones que usan el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
 Por ejemplo, el mensaje de solicitud para invocar la primera sobrecarga del procedimiento GET_ACCOUNT es:  
  
```  
<GET_ACCOUNT xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT/overload1">  
  <AID>100001</AID>  
</GET_ACCOUNT>  
```  
  
 De forma similar, el mensaje de solicitud para invocar la segunda sobrecarga del procedimiento GET_ACCOUNT es:  
  
```  
<GET_ACCOUNT xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT/overload2">  
  <ANAME>Mindy Martin</ANAME>  
</GET_ACCOUNT>  
```  
  
 El primer mensaje de solicitud, invoca el procedimiento GET_ACCOUNT para recuperar el registro con el identificador de cuenta igual a 100020. El segundo mensaje de solicitud, invoca el procedimiento GET_ACCOUNT para recuperar los registros que contienen el nombre de cuenta como "John Smith".  
  
 La orquestación consume los mensajes de solicitud y los envía a la base de datos de Oracle. La respuesta de la base de datos de Oracle se guarda en otra ubicación de archivo definido como parte de la orquestación. Por ejemplo, la respuesta para invocar el primer procedimiento sobrecargado es:  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<GET_ACCOUNTResponse mlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT/overload1">  
 <ACCT>  
  <ACCTID>100001</ACCTID>  
  <NAME>Ty Carlson</NAME>  
  <BALANCE>9000</BALANCE>  
 </ACCT>  
</GET_ACCOUNTResponse>  
```  
  
## <a name="possible-exceptions"></a>Posibles excepciones  
 Para obtener información sobre las excepciones puede surgir al invocar paquetes sobrecargados con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [excepciones y control de errores](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md).  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez haya implementado y configurado el proyecto de BizTalk, puede exportar la configuración en un archivo XML denominado archivo de enlaces. Una vez que se genera un archivo de enlaces, puede importar los valores de configuración desde el archivo para que no es necesario crear los puertos de envío, recepción, puertos, etc. para la misma orquestación. Para obtener más información acerca de los archivos de enlace, vea [enlaces del adaptador de base de datos de Oracle reutilizar](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md).  
  
## <a name="see-also"></a>Vea también  
[Bloques de creación de aplicaciones de BizTalk de desarrollar con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)