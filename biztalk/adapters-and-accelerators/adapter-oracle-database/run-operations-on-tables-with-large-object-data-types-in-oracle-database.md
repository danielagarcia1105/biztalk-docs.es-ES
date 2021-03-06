---
title: Ejecutar operaciones en tablas con tipos de datos de objetos grandes en la base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, performing on tables
- operations, performing on LOB data
ms.assetid: 74276b85-daf1-4d0f-92f9-46d5c27a95a6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ea86bd08a926c3274b16b26b093380396f17887
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966989"
---
# <a name="run-operations-on-tables-with-large-object-data-types-in-oracle-database"></a>Ejecutar operaciones en tablas con tipos de datos de objetos grandes en la base de datos de Oracle
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] proporciona compatibilidad para los tipos de datos de objetos grandes (LOB) de Oracle:  

- Objeto binario grande (BLOB)  

- Objeto grande de caracteres (CLOB)  

- Objetos grandes de carácter nacional (NCLOB)  

- Archivo binario (BFILE). Para obtener más información, consulte [realizar operaciones en tablas con tipos de datos BFILE de base de datos de Oracle con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-bfile-data-types-in-oracle-db-using-biztalk.md).  

  El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] hacerlo mediante la exposición de las operaciones de ReadLOB y UpdateLOB para las tablas que contengan columnas de LOB. Para obtener más información acerca de estas operaciones, consulte [operaciones en tablas y vistas que contienen LOB de datos en la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-and-views-that-contain-lob-data-in-oracle-database.md). Para obtener más información acerca de la estructura del mensaje SOAP para llamar a estas operaciones, consulte [esquemas de mensaje para operaciones especiales de LOB](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md).  

> [!NOTE]
>  Cuando se usa el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], la operación ReadLOB no admite la transmisión por secuencias datos de tipo LOB de una base de datos de Oracle. Para transmitir datos LOB de una base de datos de Oracle mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] en su lugar, debe usar la operación de selección. Para obtener más información sobre el streaming, consulte [compatibilidad con Streaming para tipos de datos LOB en la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md). Además, la respuesta de la base de datos de Oracle para la operación ReadLOB generará un error de validación en el WSDL. Para obtener instrucciones sobre cómo solucionar el error, vea [solución de problemas operativos](https://msdn.microsoft.com/library/dd787883.aspx).  

## <a name="how-to-perform-operations-on-lob-data"></a>¿Cómo realizar operaciones en los datos LOB?  
 Realizar una operación en una base de datos de Oracle mediante [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica tareas de procedimientos se describe en [bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md). Para invocar operaciones ReadLOB y UpdateLOB en una tabla en una base de datos de Oracle, estas tareas son:  

1. Cree un proyecto de BizTalk y genere el esquema para las operaciones de ReadLOB y UpdateLOB.  

2. Crear mensajes en el proyecto de BizTalk para enviar y recibir mensajes de la base de datos de Oracle. Debe crear mensajes para enviar la solicitud y recibir respuestas para las operaciones.  

3. Crear una orquestación para invocar operaciones ReadLOB y UpdateLOB.  

4. Compile e implemente el proyecto de BizTalk.  

5. Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  

6. Inicie la aplicación de BizTalk.  

   Este tema proporciona instrucciones para realizar estas tareas.  

## <a name="sample-based-on-this-topic"></a>Ejemplo basado en este tema.  
 Un ejemplo, Operate_LOB, basado en este tema también se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).  

## <a name="generating-schema"></a>Generar el esquema  
 En este tema, para demostrar cómo realizar operaciones ReadLOB y UpdateLOB, se generará los metadatos para estas operaciones que se exponen para la tabla CUSTOMER en el esquema SCOTT en la base de datos de Oracle. Esta tabla se crea bajo el esquema SCOTT ejecutando los scripts SQL que se proporciona con los ejemplos. Para obtener más información acerca de los ejemplos, vea [ejemplos de esquema](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md).  

## <a name="defining-messages-and-message-types"></a>Definición de los mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes en la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Debe vincular el esquema generado en el primer paso para los mensajes desde la ventana Vista orquestación del proyecto de BizTalk.  

 Este tema, debe crear dos conjuntos de mensajes de solicitud y respuesta, establezca una solicitud y respuesta para la operación de ReadLOB y la segunda solicitud y respuesta establecida para la operación UpdateLOB.  

 Realice los pasos siguientes para crear mensajes y vincularlas al esquema.  

#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vínculo a esquema  

1. Abra la ventana Vista orquestación del proyecto de BizTalk, si aún no está abierto. Para ello, haga clic en **vista**, apunte a **Other Windows**y, a continuación, haga clic en **Vista orquestación**.  

2. En la Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  

3. Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  

4. En el **propiedades** panel **Message_1**, realice lo siguiente:  


   |   Use   |                                                                                                                                       Para                                                                                                                                       |
   |--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  Identificador  |                                                                                                                                   Tipo **solicitar**.                                                                                                                                    |
   | Tipo de mensaje | En la lista desplegable, expanda **esquemas**y seleccione *Operate_LOB. OracleDBBindingSchema.ReadLOB*<em>,</em> donde *Operate_LOB* es el nombre de su proyecto de BizTalk. *OracleDBBindingSchema* es el esquema generado para las operaciones ReadLOB y UpdateLOB en la tabla CUSTOMER. |


5. Repita el paso anterior para crear más de tres mensajes. En el **propiedades** panel para los mensajes nuevos, haga lo siguiente:  

   |Identificador de conjunto para|Establecer el tipo de mensaje en|  
   |-----------------------|-------------------------|  
   |Respuesta|*Operate_LOB. OracleDBBindingSchema.ReadLOBResponse*|  
   |Solicitud2|*Operate_LOB. OracleDBBindingSchema.UpdateLOB*|  
   |: 2|*Operate_LOB. OracleDBBindingSchema.UpdateLOBResponse*|  

## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para utilizar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para invocar operaciones ReadLOB y UpdateLOB en una tabla. En esta orquestación, coloque dos mensajes de solicitud, uno para la operación ReadLOB y otro para la operación UpdateLOB. Estos mensajes se quitan en una ubicación de recepción. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] consume los mensajes y los pasa a la base de datos de Oracle a través de ODP. La respuesta de la base de datos de Oracle se guarda en otra ubicación.  

 Dado que la orquestación toma dos solicitudes simultáneamente, deberá incluir una forma acciones paralelas en la orquestación. Para cada acción paralela, debe incluir el envío y recepción formas para enviar mensajes a la base de datos de Oracle y recibir respuestas. Sin embargo, puede usar los mismos puertos para enviar y recibir mensajes para ambas operaciones. Contendría una orquestación para realizar las operaciones de ReadLOB y UpdateLOB simultáneamente típica:  

- Enviar y recibir las formas para enviar mensajes a la base de datos de Oracle y recibir respuestas.  

- Puerto para recibir mensajes de solicitud para enviar a la base de datos de Oracle de recepción unidireccional.  

- Puerto para enviar mensajes de solicitud para Oracle de base de datos y reciban respuestas de envío bidireccional.  

- Un puerto de envío unidireccional para enviar las respuestas de base de datos de Oracle en una carpeta.  

  Una orquestación de ejemplo es similar al siguiente:  

  ![Orquestación para leer y actualizar datos LOB](../../adapters-and-accelerators/adapter-oracle-database/media/6523b5e4-3689-433a-8287-eebc36f10442.gif "6523b5e4-3689-433a-8287-eebc36f10442")  

### <a name="adding-message-shapes"></a>Agregar formas de mensaje  
 Asegúrese de que especificar las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación simplemente mencionadas. En la tabla siguiente se enumera las formas en que se debe incluir por una de las acciones paralelas.  

|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-Establecer **nombre** a *ReceiveMessage*<br />-Establecer **activar** a *True*|  
|SendMessage|Send|-Establecer **nombre** a *SendMessage*|  
|ReceiveResponse|Receive|-Establecer **nombre** a *ReceiveResponse*<br />-Establecer **activar** a *False*|  
|SendResponse|Send|-Establecer **nombre** a *SendResponse*|  

 En la tabla siguiente se enumera las formas que se deben incluir para que otras acciones paralelas.  

|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ReceiveMessage2|Receive|-Establecer **nombre** a *ReceiveMessage2*<br />-Establecer **activar** a *True*|  
|SendMessage2|Send|-Establecer **nombre** a *SendMessage2*|  
|ReceiveResponse2|Receive|-Establecer **nombre** a *ReceiveResponse2*<br />-Establecer **activar** a *False*|  
|SendResponse2|Send|-Establecer **nombre** a *SendResponse2*|  

### <a name="adding-ports"></a>Agregar puertos  
 Asegúrese de que especificar las siguientes propiedades para cada uno de los puertos lógicos. Los nombres que aparecen en la columna puerto son los nombres de los puertos tal como se muestra en la orquestación.  

|Puerto|Propiedades|  
|----------|----------------|  
|FileIn|-Establecer **identificador** a *FileIn*<br />-Establecer **tipo** a *FileInType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *de recepción*|  
|LOBPort|-Establecer **identificador** a *LOBPort*<br />-Establecer **tipo** a *LOBPortType*<br />-Establecer **patrón de comunicación** a *de solicitud-respuesta*<br />-Establecer **dirección de comunicación** a *envío y recepción*|  
|SaveResponse|-Establecer **identificador** a *SaveResponse*<br />-Establecer **tipo** a *SaveResponseType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *enviar*|  

 Dado que se van a procesar la solicitud de dos y los mensajes de respuesta usando estos puertos, debe crear dos operaciones para cada puerto, donde cada operación corresponde a un tipo de mensaje. Para crear una operación, haga clic en la forma de puerto y, a continuación, seleccione **nueva operación**. Nombre de la primera operación para cada puerto como **ReadLOB** y la segunda operación para cada puerto como **UpdateLOB**.  

### <a name="using-correlation"></a>Uso de la correlación  
 La correlación es el proceso de hacer coincidir un mensaje entrante con la instancia apropiada de una orquestación. En la orquestación que se pueden colocar dos mensajes de solicitud, uno para cada sobrecarga. Uso de la correlación, asociar un mensaje de solicitud con la orquestación derecha. Para obtener más información sobre la correlación, vea [utilizando las correlaciones en orquestaciones](../../core/using-correlations-in-orchestrations.md).  

##### <a name="to-use-correlations"></a>Para utilizar las correlaciones  

1.  Promocionar una propiedad desde el esquema generado para cada operación. Por ejemplo, promocionar la propiedad LOB_COLUMN desde el esquema de operación ReadLOB; promover la propiedad FILTER del esquema de operación UpdateLOB. Para promocionar una propiedad, haga clic en la propiedad en la vista de esquema, seleccione **promover**y, a continuación, seleccione **promoción rápida**. Esto agrega un archivo PropertySchema.xsd al proyecto de BizTalk.  

     Para obtener información acerca de la promoción de una propiedad, vea [promocionar propiedades](../../core/promoting-properties.md).  

2.  En la Vista orquestación, haga clic en **tipos de correlaciones**y, a continuación, seleccione **nuevo tipo de correlación**.  

3.  El **las propiedades de correlación** cuadro de diálogo enumera las propiedades promocionadas en el paso 1. Seleccione una propiedad y, a continuación, haga clic en **agregar**.  

4.  Haga clic en **Aceptar**.  

5.  Para crear tipos de correlación para la otra propiedad promocionada, repita estos pasos.  

6.  Cambiar el nombre de los tipos de correlaciones en función de la operación que están asociados. Puede cambiar el nombre de los tipos de correlaciones para *CorrelationType_ReadLOB* (para la operación ReadLOB) y *CorrelationType_UpdateLOB* (para la operación UpdateLOB).  

7.  Desde la Vista orquestación, haga clic en **conjuntos de correlaciones**y, a continuación, seleccione **nuevo conjunto de correlaciones**.  

8.  Haga clic en el conjunto de correlaciones recién agregado y, a continuación, haga clic en **propiedades**. En el **propiedades** panel, haga lo siguiente:  

    |Use|Para|  
    |--------------|----------------|  
    |Tipo de correlación|*Operate_LOB. CorrelationType_ReadLOB*|  
    |Identificador|*Correlation_ReadLOB*|  

9. Agregue otro conjunto de correlaciones y especifique las siguientes propiedades en el panel Propiedades.  

    |Use|Para|  
    |--------------|----------------|  
    |Tipo de correlación|*Operate_LOB. CorrelationType_UpdateLOB*|  
    |Identificador|*Correlation_UpdateLOB*|  

## <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>Especifique los mensajes para las formas Acción y conectarlos a puertos  
 En la tabla siguiente especifica las propiedades y sus valores que se deben establecer para especificar los mensajes para las formas Acción y vincularlos a los puertos. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación que se ha mencionado anteriormente.  

|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveMessage|-Establecer **Inicializando conjuntos de correlaciones** a *Correlation_ReadLOB*<br />-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *FileIn.ReadLOB.Request*|  
|SendMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *LOBPort.ReadLOB.Request*|  
|ReceiveResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *LOBPort.ReadLOB.Response*|  
|SendResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *SaveResponse.ReadLOB.Request*|  
|ReceiveMessage2|-Establecer **Inicializando conjuntos de correlaciones** a *Correlation_UpdateLOB*<br />-Establecer **mensaje** a *Solicitud2*<br />-Establecer **operación** a *FileIn.UpdateLOB.Request*|  
|SendMessage2|-Establecer **mensaje** a *Solicitud2*<br />-Establecer **operación** a *LOBPort.UpdateLOB.Request*|  
|ReceiveResponse2|-Establecer **mensaje** a *: 2*<br />-Establecer **operación** a *LOBPort.UpdateLOB.Response*|  
|SendResponse2|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *SaveResponse.UpdateLOB.Request*|  

 Después de especificar estas propiedades, están conectados a los puertos y formas de mensaje y se completa la orquestación.  

 Ahora debe compilar la solución de BizTalk e implementarla en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).  

## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el **orquestaciones** panel en la consola de administración de BizTalk Server. Debe usar la consola de administración de BizTalk Server para configurar la aplicación. Para ver un tutorial, vea [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).

 Configuración de una aplicación implica:  

- Selección de un host de la aplicación.  

- Asignación de los puertos que ha creado en la orquestación con puertos físicos en la consola de administración de BizTalk Server. Para esta orquestación, debe:  

  - Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde se colocará los mensajes de solicitud, uno para las operaciones ReadLOB y UpdateLOB. La orquestación de BizTalk usarán los mensajes de solicitud y enviarla a la base de datos de Oracle.  

  - Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk quitará los mensajes de respuesta, uno para cada operación, que contiene la respuesta de la base de datos de Oracle.  

  - Definir un puerto de envío WCF-Custom o WCF-OracleDB físico para enviar mensajes a la base de datos de Oracle. También debe especificar la acción en el puerto de envío. Para obtener información sobre cómo crear puertos de WCF-Custom o WCF-OracleDB, consulte [configurar manualmente un enlace de puerto físico para el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md). Dado que el WCF-Custom o WCF-OracleDB puerto de envío envía y recibe los mensajes sean conformes a más de un esquema y realiza dos operaciones, debe establecer acciones dinámicas para las operaciones. Para obtener más información acerca de las acciones, vea [configurar la acción SOAP para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md). Para esta orquestación, se debe establecer la acción siguiente:  

    ```  
    <BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
      <Operation Name="ReadLOB" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/ReadLOB" />  
      <Operation Name="UpdateLOB" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/UpdateLOB" />  
    </BtsActionMapping>  
    ```  

    > [!NOTE]
    >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde la consola de administración de BizTalk Server para crear puertos de envío (para las llamadas salientes) o la recepción (para las llamadas entrantes). Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).  

## <a name="starting-the-application"></a>Iniciar la aplicación  
 Debe iniciar la aplicación de BizTalk para realizar una operación en la base de datos de Oracle. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md).  

 En esta etapa, asegúrese de que:  

-   El archivo de puerto de recepción para recibir mensajes de solicitud para la orquestación se está ejecutando.  

-   El puerto de envío de archivo para recibir los mensajes de respuesta de la orquestación se está ejecutando.  

-   Puerto o WCF-OracleDB para enviar mensajes a la base de datos se está ejecutando de Oracle de envío personalizada de WCF.  

-   La orquestación de BizTalk para la operación se está ejecutando.  

## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, debe quitar la ubicación de recepción de mensajes en el archivo de solicitud. El esquema para los mensajes de solicitud debe cumplir el esquema para las operaciones que se generó anteriormente. Consulte [esquemas de mensaje para operaciones especiales de LOB](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md) para obtener más información sobre el esquema de mensaje de solicitud para invocar operaciones en tipos de datos LOB mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  

 La orquestación consume los mensajes de solicitud y los envía a la base de datos de Oracle. La respuesta de la base de datos de Oracle se guarda en otra ubicación de archivo definida como parte de la orquestación.  

 Para esta orquestación, primero se quite un mensaje de solicitud para la operación de UpdateLOB para actualizar la columna PHOTO (del tipo de datos BLOB) de la tabla CUSTOMER. El mensaje de solicitud para invocar la actualización de la columna PHOTO para un cliente específico es:  

```  
<UpdateLOB xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER">  
  <LOB_COLUMN>PHOTO</LOB_COLUMN>  
  <FILTER>Name='Mindy Martin'</FILTER>  
  <Stream>YWJjZA==</Stream>  
</UpdateLOB>  
```  

> [!NOTE]
>  La cadena de filtro debe siempre devuelve una fila coincidente en caso contrario, la inicia de adaptador de base de datos de Oracle una XmlReaderParsingException. Además, el valor para el \<Stream\> elemento debe ser del tipo de base64Binary.  

 La respuesta para la operación UpdateLOB es:  

```  
<?xml version="1.0" encoding="utf-8"?>  
<UpdateLOBResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER"></UpdateLOBResponse>  
```  

 Ahora, coloque un mensaje de solicitud para la operación ReadLOB leer los datos que se actualizan con la operación UpdateLOB. El mensaje de solicitud para invocar la operación ReadLOB en la columna PHOTO para un cliente específico es:  

```  
<ReadLOB xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER">  
  <LOB_COLUMN>PHOTO</LOB_COLUMN>  
  <FILTER>NAME='Mindy Martin'</FILTER>  
</ReadLOB>  
```  

> [!NOTE]
>  La cadena de filtro siempre debe capturar una fila coincidente. Si hay más de una fila coincidente, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] solo devuelve la columna LOB para la primera fila (coincidencia).  

 La respuesta para la operación ReadLOB es:  

```  
<?xml version="1.0" encoding="utf-8"?>  
<ReadLOBResponse mlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER">  
  <ReadLOBResult>YWJjZA==</ReadLOBResult>  
</ReadLOBResponse>  
```  

> [!NOTE]
>  La respuesta para la operación ReadLOB puede producir un error al validar el archivo WSDL. Debe realizar ciertas tareas para validar la ReadLOB contra el WSDL. Para obtener más información, consulte [solución de problemas operativos](https://msdn.microsoft.com/library/dd787883.aspx).  

## <a name="possible-exceptions"></a>Posibles excepciones  
 Para obtener información sobre las excepciones puede aparecer al realizar operaciones en la tabla que contiene datos LOB mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [excepciones y control de errores](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md).  

## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez que haya implementado y configurado el proyecto de BizTalk, puede exportar opciones de configuración a un archivo XML llamado el archivo de enlaces. Cuando genere un archivo de enlaces, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear los puertos de envío, recepción, puertos, etc., de la misma orquestación. Para obtener más información acerca de los archivos de enlace, consulte [enlaces del adaptador de base de datos de Oracle reutilizar](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md).  

## <a name="see-also"></a>Vea también  
[Bloques de creación de aplicaciones de desarrollo de BizTalk con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)