---
title: Ejecutar la operación SQLEXECUTE en la base de datos de Oracle con BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SQLEXECUTE operation, performing by using BizTalk Server
- SQLEXECUTE operation
ms.assetid: 7fdd1ead-0bf0-46cf-86fc-db513f76f6b3
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 548beb71ff2388957f537cefe052e9209f1cabed
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966893"
---
# <a name="run-sqlexecute-operation-in-oracle-database-using-biztalk-server"></a>Ejecutar la operación SQLEXECUTE en la base de datos de Oracle con BizTalk Server
El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] permite a los clientes ejecutar la instrucción SQL parametrizada en una base de datos de Oracle. Para admitir estas operaciones, la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone una operación SQLEXECUTE. Operación SQLEXECUTE admite un bloque de parámetro de entrada consta de conjuntos de parámetros que permiten ejecutar la misma instrucción SQL una vez para cada conjunto. La operación SQLEXECUTE devuelve los resultados de la instrucción SQL en un conjunto de registros genérico. Para obtener más información acerca de la operación, vea [operación SQLEXECUTE en la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/sqlexecute-operation-in-oracle-database.md). Para obtener información acerca de la estructura del mensaje SOAP para la operación SQLEXECUTE, consulte [esquemas de mensaje para la operación SQLEXECUTE](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md).  
  
## <a name="how-to-perform-a-sqlexecute-operation-on-an-oracle-database"></a>¿Cómo realizar una operación SQLEXECUTE en una base de datos de Oracle?  
 Realizar una operación en una base de datos de Oracle mediante [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica tareas de procedimientos se describe en [bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md). Para llevar a cabo una operación SQLEXECUTE, estas tareas son:  
  
1. Cree un proyecto de BizTalk y genere el esquema para la operación SQLEXECUTE. La operación SQLEXECUTE aparece bajo el nodo raíz (/) en el **seleccionar una categoría** panel en el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].  
  
2. Crear mensajes en el proyecto de BizTalk para enviar y recibir mensajes de la base de datos de Oracle.  
  
3. Crear una orquestación para invocar la operación en la tabla de base de datos de Oracle o la vista.  
  
4. Compile e implemente el proyecto de BizTalk.  
  
5. Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
6. Inicie la aplicación de BizTalk.  
  
   Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="sample-based-on-this-topic"></a>Ejemplo basado en este tema.  
 Un ejemplo, SqlExec, basado en este tema también se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).  
  
## <a name="generating-schema"></a>Generar el esquema  
 En este tema, para demostrar cómo ejecutar una consulta SQL con parámetros, se generará el esquema para la operación SQLEXECUTE disponible en el nodo raíz (/) en el **seleccionar una categoría** panel en el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Consulte [recuperar metadatos para operaciones de base de datos de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md) para obtener más información acerca de cómo generar un esquema.  
  
## <a name="defining-messages-and-message-types"></a>Definición de los mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes en la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Debe vincular el esquema generado en el primer paso para los mensajes desde la ventana Vista orquestación del proyecto de BizTalk.  
  
 Este tema, debe crear dos mensajes: uno para enviar una solicitud a la base de datos de Oracle y el otro para recibir una respuesta.  
  
 Realice los pasos siguientes para crear mensajes y vincularlas al esquema.  
  
#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vínculo a esquema  
  
1.  Abra la ventana Vista orquestación del proyecto de BizTalk, si aún no está abierto. Para ello, haga clic en **vista**, apunte a **Other Windows**y, a continuación, haga clic en **Vista orquestación**.  
  
2.  En la Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
3.  Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  
  
4.  En el **propiedades** panel **Message_1**, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo **solicitar**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *SqlExec.OracleDBBindingSchema.SQLEXECUTE*, donde *SqlExec* es el nombre de su proyecto de BizTalk. *OracleDBBindingSchema* es el esquema generado para la operación SQLEXECUTE.|  
  
5.  Repita el paso 2 para crear un nuevo mensaje. En el **propiedades** panel para el nuevo mensaje, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo **respuesta**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *SqlExec.OracleDBBindingSchema.SQLEXECUTEResponse*.|  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para utilizar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para ejecutar una instancia de SQL con parámetros de consulta mediante la operación SQLEXECUTE. En esta orquestación, se coloca un mensaje de solicitud en una determinada ubicación de recepción. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] consume este mensaje y lo pasa a la base de datos de Oracle a través de ODP. La respuesta de la base de datos de Oracle se guarda en otra ubicación. Contendría una orquestación típica para llevar a cabo la operación SQLEXECUTE en la base de datos de Oracle:  
  
- Enviar y recibir las formas para enviar mensajes a la base de datos de Oracle y recibir respuestas.  
  
- Puerto para recibir mensajes de solicitud para enviar a la base de datos de Oracle de recepción unidireccional.  
  
- Puerto para enviar mensajes de solicitud para Oracle de base de datos y reciban respuestas de envío bidireccional.  
  
- Un puerto de envío unidireccional para enviar las respuestas de base de datos de Oracle en una carpeta.  
  
  Una orquestación de ejemplo para la operación SQLEXECUTE es similar al siguiente:  
  
  ![Orquestación para invocar la operación SQLEXECUTE](../../adapters-and-accelerators/adapter-oracle-database/media/bdb47660-6013-46f7-aa4b-fe5eb83f3a1e.gif "bdb47660-6013-46f7-aa4b-fe5eb83f3a1e")  
  
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
|FileIn|-Establecer **identificador** a *FileIn*<br />-Establecer **tipo** a *FileInType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *de recepción*|  
|LOBPort|-Establecer **identificador** a *LOBPort*<br />-Establecer **tipo** a *LOBPortType*<br />-Establecer **patrón de comunicación** a *de solicitud-respuesta*<br />-Establecer **dirección de comunicación** a *envío y recepción*|  
|SaveResponse|-Establecer **identificador** a *SaveResponse*<br />-Establecer **tipo** a *SaveResponseType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *enviar*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>Especifique los mensajes para las formas Acción y conectarlos a puertos  
 En la tabla siguiente especifica las propiedades y sus valores que se deben establecer para especificar los mensajes para las formas Acción y vincular los mensajes a los puertos. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación que se ha mencionado anteriormente.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *FileIn.SQLEXECUTE.Request*|  
|SendMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *LOBPort.SQLEXECUTE.Request*|  
|ReceiveResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *LOBPort.SQLEXECUTE.Response*|  
|SendResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *SaveResponse.SQLEXECUTE.Request*|  
  
 Después de especificar estas propiedades, están conectados a los puertos y formas de mensaje y se completa la orquestación.  
  
 Ahora debe compilar la solución de BizTalk e implementarla en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).  
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el **orquestaciones** panel en la consola de administración de BizTalk Server. Debe usar la consola de administración de BizTalk Server para configurar la aplicación. Para ver un tutorial, vea [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).
  
 Configuración de una aplicación implica:  
  
- Selección de un host de la aplicación.  
  
- Asignación de los puertos que ha creado en la orquestación con puertos físicos en la consola de administración de BizTalk Server. Para esta orquestación, debe:  
  
  - Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde se colocará un mensaje de solicitud. La orquestación de BizTalk usarán el mensaje de solicitud y enviarla a la base de datos de Oracle.  
  
  - Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta de la base de datos de Oracle.  
  
  - Definir un puerto de envío WCF-Custom o WCF-OracleDB físico para enviar mensajes a la base de datos de Oracle. También debe especificar la acción en el puerto de envío. Para obtener información sobre cómo crear puertos de WCF-Custom o WCF-OracleDB, consulte [configurar manualmente un enlace de puerto físico al adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md).  
  
    > [!NOTE]
    >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde la consola de administración de BizTalk Server para crear puertos de envío (para las llamadas salientes) o la recepción (para las llamadas entrantes). Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).  
  
## <a name="starting-the-application"></a>Iniciar la aplicación  
 Debe iniciar la aplicación de BizTalk para realizar la operación SQLEXECUTE. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md).  
  
 En esta etapa, asegúrese de que:  
  
-   El archivo de puerto de recepción para recibir mensajes de solicitud para la orquestación se está ejecutando.  
  
-   El puerto de envío de archivo para recibir los mensajes de respuesta de la orquestación se está ejecutando.  
  
-   El puerto de envío WCF-Custom o WCF-OracleDB para enviar mensajes a la base de datos de Oracle se está ejecutando.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, debe quitar un mensaje de solicitud en el archivo de ubicación de recepción. El esquema del mensaje de solicitud debe cumplir el esquema para la operación SQLEXECUTE generado anteriormente. La orquestación consume el mensaje y lo envía a la base de datos de Oracle. La respuesta de la base de datos de Oracle se guarda en la otra ubicación de archivo definida como parte de la orquestación. Consulte [esquemas de mensaje para la operación SQLEXECUTE](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md) para obtener más información acerca del esquema de mensaje de solicitud para invocar una operación SQLEXECUTE.  
  
 Dado que la operación SQLEXECUTE no aparece en cualquier artefacto de la base de datos de Oracle, puede usar el mismo esquema para realizar una consulta SQL parametrizada en una vista o ejecutar un procedimiento que funciona en otra tabla.  
  
 Por ejemplo, el siguiente mensaje de solicitud realiza una instrucción SELECT con parámetros en la tabla de cuentas mediante la operación SQLEXECUTE. La tabla de la cuenta se crea bajo el esquema SCOTT ejecutando los scripts SQL que se proporciona con los ejemplos. Para obtener más información acerca de los ejemplos, vea [ejemplos de esquema](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md).  
  
```  
<SQLEXECUTE xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE">  
  <SQLSTATEMENT>select * from ACCOUNT where ACCTID=:num</SQLSTATEMENT>  
  <PARAMETERSCHEMA>num number</PARAMETERSCHEMA>  
  <PARAMETERSET>  
    <PARAMETERDATA xmlns="http://Microsoft.LobServices.OracleDB/2007/03">  
      <PARAMETER>  
        <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">100000</string>  
      </PARAMETER>  
    </PARAMETERDATA>  
  </PARAMETERSET>  
</SQLEXECUTE>  
```  
  
 La respuesta de la base de datos de Oracle para el mensaje de solicitud anterior es:  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<SQLEXECUTEResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE">  
  <SQLEXECUTEResult>  
    <GenRecordRow xmlns="http://Microsoft.LobServices.OracleDB/2007/03">  
      <GenRecordColumn>  
        <GenRecordColumn>  
          <ColumnName>ACCTID</ColumnName>   
          <ColumnValue>100000</ColumnValue>   
          <ColumnType>System.Decimal</ColumnType>   
        </GenRecordColumn>  
        <GenRecordColumn>  
          <ColumnName>NAME</ColumnName>   
          <ColumnValue>Kim Ralls</ColumnValue>   
          <ColumnType>System.String</ColumnType>   
        </GenRecordColumn>  
        <GenRecordColumn>  
          <ColumnName>BALANCE</ColumnName>   
          <ColumnValue>10000</ColumnValue>   
          <ColumnType>System.Decimal</ColumnType>   
        </GenRecordColumn>  
      </GenRecordColumn>  
    </GenRecordRow>  
  </SQLEXECUTEResult>  
</SQLEXECUTEResponse>  
```  
  
## <a name="possible-exceptions"></a>Posibles excepciones  
 Para obtener información sobre las excepciones puede surgir mientras se realiza una operación de DML con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [excepciones y control de errores](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md).  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez que haya implementado y configurado el proyecto de BizTalk, puede exportar opciones de configuración a un archivo XML llamado el archivo de enlaces. Cuando genere un archivo de enlaces, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear los puertos de envío, recepción, puertos, etc., de la misma orquestación. Para obtener más información acerca de los archivos de enlace, consulte [enlaces del adaptador de base de datos de Oracle reutilizar](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md).  
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)