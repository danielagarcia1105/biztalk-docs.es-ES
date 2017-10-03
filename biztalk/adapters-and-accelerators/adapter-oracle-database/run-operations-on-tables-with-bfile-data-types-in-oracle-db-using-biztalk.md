---
title: Ejecutar operaciones en tablas con tipos de datos BFILE de base de datos de Oracle mediante BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- operations on tables with BFILE data types, performing by using BizTalk Server
- BFILE data types
ms.assetid: 2e4af5a9-acde-419b-a99c-3eaa0c72daa8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2219b93bfcc767af4eec6d433074a013dba0cca2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="run-operations-on-tables-with-bfile-data-types-in-oracle-database-using-biztalk-server"></a>Ejecutar operaciones en tablas con tipos de datos BFILE de base de datos de Oracle mediante BizTalk Server
El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es compatible con el tipo de datos BFILE en tablas y procedimientos almacenados. Esta sección proporciona información sobre cómo realizar operaciones en tablas que tengan una columna de tipo de datos BFILE. Para obtener más información acerca de cómo los [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite BFILE, consulte [operaciones en tablas con BFILE tipos de datos en la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-with-bfile-data-types-in-oracle-database.md).  
  
## <a name="setting-up-your-oracle-database-server-for-operations-on-bfile"></a>Cómo configurar un servidor de base de datos de Oracle para operaciones con BFILE  
 En esta sección se muestra cómo invocar un procedimiento que inserta un registro en el SCOTT. Tabla CUSTOMERDOC. Esta tabla contiene una columna de tipo de datos BFILE y se crea al ejecutarse los scripts SQL incluidos con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] ejemplos. Para obtener más información sobre los ejemplos y las secuencias de comandos SQL, consulte [ejemplos para el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/samples-for-the-oracle-database-adapter.md).  
  
 Después de ejecutar la secuencia de comandos para crear la tabla CUSTOMERDOC, debe realizar determinadas acciones en el equipo que ejecuta la base de datos de Oracle para habilitar las operaciones en tipos de datos BFILE. Las tareas que se deben realizar en la base de datos de Oracle son:  
  
1.  Cree un directorio C:\MYDIR en el equipo que ejecuta la base de datos de Oracle.  
  
2.  Cree un directorio lógico en la base de datos de Oracle. Esto normalmente requiere un usuario con privilegios SYSDBA. Por ejemplo:  
  
    ```  
    CREATE OR REPLACE DIRECTORY MYDIR AS 'C:\MYDIR';  
    ```  
  
3.  Agregar privilegios al usuario tener acceso al directorio lógico en Oracle. Por ejemplo:  
  
    ```  
    GRANT READ, WRITE ON DIRECTORY MYDIR to SCOTT;  
    ```  
  
4.  Copie los archivos para tener acceso a la ubicación del directorio físico, en el equipo que ejecuta la base de datos de Oracle, asociado con el directorio lógico en Oracle. Crea este directorio en el paso 1.  
  
     Según el ejemplo anterior, copie un archivo, customer_profile.txt en el directorio C:\MYDIR. Este archivo ahora está disponible para las operaciones de BFILE. Para obtener más información sobre cómo realizar operaciones, vea [realizar operaciones en tablas con datos de tipos de objeto grandes por mediante BizTalk Server en la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-large-object-data-types-in-oracle-database.md).  
  
    > [!IMPORTANT]
    >  La operación de ReadLOB se admite en las tablas con el tipo de datos BFILE. NO se admite la operación de UpdateLOB. Sin embargo, los usuarios o bien pueden usar la operación de actualización.  
  
## <a name="how-to-perform-operations-using-bfile-data-types"></a>Cómo realizar operaciones con los tipos de datos BFILE  
 Realizar una operación en una base de datos de Oracle mediante [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica procedimientos tareas que se describen en [bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md). Para invocar un procedimiento que inserta un registro en el SCOTT. Tabla CUSTOMERDOC, estas tareas son:  
  
1.  Cree un proyecto de BizTalk y genere el esquema para el procedimiento almacenado de CREATE_CUSTOMERDOC.  
  
2.  Crear mensajes en el proyecto de BizTalk para enviar y recibir mensajes de la base de datos de Oracle.  
  
3.  Crear una orquestación para invocar la operación en la tabla de base de datos de Oracle o la vista.  
  
4.  Compilar e implementar el proyecto de BizTalk.  
  
5.  Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
6.  Inicie la aplicación de BizTalk.  
  
 Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="sample-based-on-this-topic"></a>Ejemplo basado en este tema  
 Un ejemplo, Operate_BFILE, basado en este tema también se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos para el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/samples-for-the-oracle-database-adapter.md).  
  
## <a name="generating-schema"></a>Generar el esquema  
 En este tema, para demostrar cómo realizar operaciones en una tabla con columnas BFILE, se invoca el procedimiento CREATE_CUSTOMERDOC. Este procedimiento se crea en el esquema de SCOTT\Package\ACCOUNT_PKG mediante la ejecución de los scripts SQL que se proporciona con los ejemplos. Este procedimiento toma el tipo de registro BFILE y agrega un registro en la tabla CUSTOMERDOC. Para obtener más información acerca de los scripts SQL, consulte [ejemplos de esquema](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md).  
  
 Vea [recuperar metadatos para operaciones de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md) para obtener más información sobre cómo generar el esquema.  
  
## <a name="defining-messages-and-message-types"></a>Definición de mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes en la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Debe vincular el esquema generado en el primer paso para los mensajes de la ventana Vista orquestación del proyecto de BizTalk.  
  
 En este tema, debe crear dos mensajes: uno para enviar una solicitud a la base de datos de Oracle y el otro para recibir una respuesta.  
  
 Realice los pasos siguientes para crear mensajes y vincularlas al esquema.  
  
#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vincular al esquema  
  
1.  Abra la ventana Vista orquestación del proyecto de BizTalk, si no está ya abierto. Para ello, haga clic en **vista**, seleccione **otras ventanas**y, a continuación, haga clic en **Vista orquestación**.  
  
2.  En Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
3.  Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  
  
4.  En el **propiedades** panel para **Message_1**, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo de **solicitar**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *BFILE_Operations.OracleDBBindingSchema.CREATE_CUSTOMERDOC*, donde *BFILE_Operations* es el nombre de el proyecto de BizTalk. *OracleDBBindingSchema* es el esquema generado para el procedimiento CREATE_CUSTOMERDOC.|  
  
5.  Repita el paso 2 para crear un nuevo mensaje. En el **propiedades** panel para el nuevo mensaje, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo de **respuesta**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *BFILE_Operations.OracleDBBindingSchema.CREATE_CUSTOMERDOCResponse*.|  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para usar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para ejecutar un procedimiento. En esta orquestación, se coloca un mensaje de solicitud en una determinada ubicación de recepción. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] consume este mensaje y pasa a la base de datos de Oracle a través de ODP. La respuesta de la base de datos de Oracle se guarda en otra ubicación. Contendría una orquestación típica para llevar a cabo operaciones en BFILE columnas en una tabla de base de datos de Oracle:  
  
-   Enviar y recibir formas a fin de enviar mensajes a la base de datos de Oracle y recibir respuestas.  
  
-   Un unidireccional puerto de recepción para recibir mensajes de solicitud para enviar a la base de datos de Oracle.  
  
-   Puerto para enviar mensajes de solicitud con Oracle con la base de datos y reciban respuestas de envío bidireccional.  
  
-   Un puerto de envío unidireccional para enviar las respuestas de base de datos de Oracle en una carpeta.  
  
 Una orquestación de ejemplo es similar al siguiente:  
  
 ![Orquestación para realizar operaciones con BFILE](../../adapters-and-accelerators/adapter-oracle-database/media/5902cf48-0555-4d9a-b902-5208949b6c87.gif "5902cf48-0555-4d9a-b902-5208949b6c87")  
  
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
|FileIn|-Establecer **identificador** a *FileIn*<br />-Establecer **tipo** a *FileInType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *de recepción*|  
|LOBPort|-Establecer **identificador** a *LOBPort*<br />-Establecer **tipo** a *LOBPortType*<br />-Establecer **patrón de comunicación** a *solicitudes y respuestas*<br />-Establecer **dirección de comunicación** a *envío y recepción*|  
|SaveResponse|-Establecer **identificador** a *SaveResponse*<br />-Establecer **tipo** a *SaveResponseType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *enviar*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>Especificar mensajes de las formas de acción y conéctelos a los puertos  
 En la tabla siguiente especifica las propiedades y sus valores que se deben establecer para especificar los mensajes para las formas de acción y vincular los mensajes a los puertos. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación que se ha mencionado anteriormente.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *FileIn.Create_BFILE. Solicitud*|  
|SendMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *LOBPort.Create_BFILE. Solicitud*|  
|ReceiveResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *LOBPort.Create_BFILE. Respuesta*|  
|SendResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *SaveResponse.Create_BFILE. Solicitud*|  
  
 Después de especificar estas propiedades, las formas de mensaje y los puertos que están conectados y la orquestación se completa.  
  
 Ahora debe compilar la solución de BizTalk e implementarlo en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).  
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el **orquestaciones** panel de la consola de administración de BizTalk Server. Debe usar la consola de administración de BizTalk Server para configurar la aplicación. Para obtener un tutorial, vea [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).
  
 Configuración de una aplicación implica:  
  
-   Selección de un host de la aplicación.  
  
-   Asignación de los puertos que ha creado en la orquestación con puertos físicos en la consola de administración de BizTalk Server. Para que esta orquestación debe:  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde se colocará un mensaje de solicitud. La orquestación de BizTalk consumirá el mensaje de solicitud y enviarla a la base de datos de Oracle.  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta de la base de datos de Oracle.  
  
    -   Definir un puerto de envío WCF-Custom o WCF-OracleDB físico para enviar mensajes a la base de datos de Oracle. También debe especificar la acción en el puerto de envío. Para obtener información sobre cómo crear puertos de WCF-Custom o WCF-OracleDB, consulte [configurar manualmente el enlace de puerto físico para el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md).  
  
        > [!NOTE]
        >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde la consola de administración de BizTalk Server para crear puertos de envío (para las llamadas salientes) o puertos de recepción (para las llamadas entrantes). Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).  
  
## <a name="starting-the-application"></a>A partir de la aplicación  
 Debe iniciar la aplicación de BizTalk para invocar el procedimiento que crea un registro en la tabla CUSTOMERDOC. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md).  
  
 En esta fase, asegúrese de que:  
  
-   El archivo de puerto de recepción para recibir mensajes de solicitud de ejecución de la orquestación.  
  
-   El puerto de envío de archivo para recibir los mensajes de respuesta de la orquestación se está ejecutando.  
  
-   El puerto de envío WCF-Custom o WCF-OracleDB para enviar mensajes a la base de datos de Oracle se está ejecutando.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, debe quitar un mensaje de solicitud en el archivo de ubicación de recepción. El esquema del mensaje de solicitud debe ajustarse al esquema para el procedimiento que ha generado anteriormente. Vea [esquemas de mensaje para funciones y procedimientos](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md) para obtener más información acerca del esquema de mensaje de solicitud para invocar el procedimiento mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
 Por ejemplo, el mensaje de solicitud para invocar el procedimiento CREATE_CUSTOMERDOC es:  
  
```  
<CREATE_CUSTOMERDOC xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
  <CNAME>John Smith</CNAME>  
  <CDOC>MYDIR/John_Smith_profile.txt</CDOC>  
</CREATE_CUSTOMERDOC>  
```  
  
> [!NOTE]
>  El archivo de texto, John_Smith_profile.txt debe estar presente en la ubicación del directorio físico asociada al directorio lógico en Oracle. En este ejemplo, el archivo de texto debe estar presente en C:\MYDIR  
  
 La orquestación consume el mensaje y lo envía a la base de datos de Oracle. La respuesta de la base de datos de Oracle se guarda en la otra ubicación de archivo definida como parte de la orquestación. Por ejemplo, la respuesta de la base de datos de Oracle para el mensaje de solicitud anterior es:  
  
```  
\<?xml version="1.0" encoding="utf-8"?>  
<CREATE_CUSTOMERDOCResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG"></CREATE_CUSTOMERDOCResponse>  
```  
  
> [!NOTE]
>  Puede crear una orquestación para leer los datos de tablas que tienen campos de tipo BFILE similar. La secuencia de comandos SQL incluidos con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] crea un ACCOUNT_PKG que contiene un procedimiento GET_CUSTOMERDOC. Puede usar este procedimiento para recuperar datos BFILE del SCOTT. Tabla CUSTOMERDOC.  
>   
>  También se incluye con los ejemplos para obtener un ejemplo, Operate_BFILE, [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Este ejemplo muestra cómo insertar registros en el SCOTT. Tabla CUSTOMERDOC mediante el CREATE_CUSTOMERDOC el procedimiento almacenado (tal y como se describe en este tema.) El ejemplo también muestra cómo leer datos BFILE desde el SCOTT. Tabla CUSTOMERDOC mediante GET_CUSTOMERDOC el procedimiento almacenado.  
  
## <a name="possible-exceptions"></a>Posibles excepciones  
 Para obtener información sobre las excepciones puede surgir mientras se realiza una operación de DML con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [excepciones y control de errores](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md).  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez haya implementado y configurado el proyecto de BizTalk, puede exportar la configuración en un archivo XML denominado archivo de enlaces. Una vez que se genera un archivo de enlaces, puede importar los valores de configuración desde el archivo para que no es necesario crear los puertos de envío, recepción, puertos, etc. para la misma orquestación. Para obtener más información acerca de los archivos de enlace, vea [enlaces del adaptador de base de datos de Oracle reutilizar](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md).  
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)