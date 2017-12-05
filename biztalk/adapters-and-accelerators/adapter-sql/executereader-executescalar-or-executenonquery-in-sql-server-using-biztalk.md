---
title: ExecuteReader, ExecuteScalar u operaciones de ExecuteNonQuery en SQL con BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d8def133-cbe1-4648-ae41-6b8ce6640cb3
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c33db07cf497ed232222fe5ccef3e7f69808f97a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="executereader-executescalar-or-executenonquery-operations-in-sql-using-biztalk-server"></a>ExecuteReader, ExecuteScalar u operaciones de ExecuteNonQuery en SQL con BizTalk Server
El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expone las operaciones de SQL Server genéricas como **ExecuteNonQuery**, **ExecuteReader**, y **ExecuteScalar**. Puede utilizar estas operaciones para ejecutar cualquier instrucción SQL en una base de datos de SQL Server. Estas operaciones varían en función del tipo de respuesta que se obtiene de la instrucción SQL. Para obtener más información acerca del modo en que el adaptador admite estas operaciones, vea [soporte técnico para las operaciones de ExecuteScalar, ExecuteReader y ExecuteNonQuery](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).  
  
 En este tema se muestra cómo realizar una **ExecuteReader** operación mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Puede seguir el mismo conjunto de procedimientos que se describen en este tema para realizar **ExecuteNonQuery** y **ExecuteScalar** operaciones.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Crear un [clave de nombre seguro de archivos y obtenga información acerca de las herramientas](prerequisites-to-create-sql-applications-using-the-sql-adapter.md)
  
-   [Configurar MSDTC](configure-msdtc-on-sql-server-and-adapter-client.md) en equipos que ejecutan el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] y SQL Server.
  
## <a name="invoke-the-executereader-operation-on-a-sql-server-database"></a>Invocar la operación ExecuteReader en una base de datos de SQL Server  
 Realizar una operación en una base de datos de SQL Server mediante el uso de [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica procedimientos tareas que se describen en [bloques de creación para desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md). Para invocar la **ExecuteReader** operación en SQL Server, estas tareas son:  
  
1.  Crear un proyecto de BizTalk y genere el esquema para el **ExecuteReader** operación.  
  
2.  Crear mensajes en el proyecto de BizTalk para enviar y recibir mensajes de SQL Server.  
  
3.  Crear una orquestación para invocar la operación en SQL Server.  
  
4.  Compilar e implementar el proyecto de BizTalk.  
  
5.  Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
6.  Inicie la aplicación de BizTalk.  
  
 Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="generate-schema"></a>Generar esquema  
 En este tema se muestra cómo invocar **ExecuteReader** operación en SQL Server mediante la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. El **ExecuteReader** operación toma cualquier instrucción SQL como un parámetro y devuelve el conjunto de resultados de la operación como una matriz del conjunto de datos. Este tema muestra cómo ejecutar el procedimiento almacenado de ADD_EMP_DETAILS mediante la **ExecuteReader** operación. Este procedimiento almacenado agrega un registro a la tabla de empleados y devuelve el identificador del empleado recién agregado. Las tablas y procedimientos almacenados se utilizan en el tema se crean mediante la ejecución de las secuencias de comandos que se proporciona con los ejemplos. Para obtener más información acerca de la secuencia de comandos, consulte [ejemplos del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).  
  
 Para demostrar cómo invocar **ExecuteReader** operación, se genera el esquema para el **ExecuteReader** operación. Debe crear un proyecto de BizTalk y utilizar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar el esquema. Vea [recuperación de metadatos para operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md) para obtener más información acerca de cómo generar esquemas.  
  
## <a name="define-messages-and-message-types"></a>Defina los mensajes y el mensaje tipos  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes de la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Ahora, cree mensajes para la orquestación y vincularlos a los esquemas generados en el paso anterior.  
  
1.  Agregar una orquestación al proyecto de BizTalk. En el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**. Escriba un nombre para la orquestación de BizTalk y, a continuación, haga clic en **agregar**.  
  
2.  Abra la ventana Vista orquestación del proyecto de BizTalk, si no está ya abierto. Para ello, haga clic en **vista**, seleccione **otras ventanas**y, a continuación, haga clic en **Vista orquestación**.  
  
3.  En Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
4.  Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  
  
5.  En el **propiedades** panel para la **Message_1**, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Escriba `Request`|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *Execute_Reader.GenericOperation.ExecuteReader*, donde Execute_Reader es el nombre de su proyecto de BizTalk. *GenericOperation* es el esquema generado para el **ExecuteReader** operación.|  
  
6.  Repita el paso 2 para crear un nuevo mensaje. En el **propiedades** panel para el nuevo mensaje, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Escriba `Response`|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *Execute_Reader.GenericOperation.ExecuteReaderResponse*.|  
  
## <a name="set-up-the-orchestration"></a>Configurar la orquestación  
 Crear una orquestación de BizTalk para usar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para realizar una operación en SQL Server. En esta orquestación, se coloca un mensaje de solicitud en una determinada ubicación de recepción. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] consume este mensaje y lo pasa al SQL Server. La respuesta de SQL Server se guarda en otra ubicación. Debe incluir el envío y recepción formas para enviar mensajes a SQL Server y recibir respuestas, respectivamente. Una orquestación de ejemplo para invocar un **ExecuteReader** operación es similar al siguiente:  
  
 ![Orquestación para invocar la operación ExecuteReader](../../adapters-and-accelerators/adapter-sql/media/2ac8dc12-918a-4077-a95c-f66b1c0ef4f0.gif "2ac8dc12-918a-4077-a95c-f66b1c0ef4f0")  
  
### <a name="add-message-shapes"></a>Agregar formas de mensaje  
 Especifique las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación just-mencionado.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-Establecer **nombre** a *ReceiveMessage*<br />-Establecer **activar** a *es True*|  
|SendMessage|Send|-Establecer **nombre** a *SendMessage*|  
|ReceiveResponse|Receive|-Establecer **nombre** a *ReceiveResponse*<br />-Establecer **activar** a *False*|  
|SendResponse|Send|-Establecer **nombre** a *SendResponse*|  
  
### <a name="add-ports"></a>Agregar puertos  
 Asegúrese de que especifique las siguientes propiedades para cada uno de los puertos lógicos. Los nombres que aparecen en la columna de puerto son los nombres de los puertos, como se muestra en la orquestación.  
  
|Puerto|Propiedades|  
|----------|----------------|  
|MessageIn|-Establecer **identificador** a *MessageIn*<br />-Establecer **tipo** a *MessageInType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *de recepción*|  
|LOBPort|-Establecer **identificador** a *LOBPort*<br />-Establecer **tipo** a *LOBPortType*<br />-Establecer **patrón de comunicación** a *solicitudes y respuestas*<br />-Establecer **dirección de comunicación** a *envío y recepción*|  
|ResponseOut|-Establecer **identificador** a *ResponseOut*<br />-Establecer **tipo** a *ResponseOutType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *enviar*|  
  
### <a name="enter-messages-for-action-shapes-and-connect-them-to-ports"></a>Escriba mensajes para formas de acción y conéctelos a los puertos  
 En la tabla siguiente especifica las propiedades y sus valores que se deben establecer para especificar los mensajes para las formas de acción y vincular los mensajes a los puertos. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación que se ha mencionado anteriormente.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *MessageIn.ExecuteReader.Request*|  
|SendMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *LOBPort.ExecuteReader.Request*|  
|ReceiveResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *LOBPort.ExecuteReader.Response*|  
|SendResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *ResponseOut.ExecuteReader.Request*|  
  
 Después de especificar estas propiedades, las formas de mensaje y los puertos que están conectados y la orquestación está completa.  
  
 Ahora deberá compilar la solución de BizTalk e implementarlo en BizTalk Server. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).
  
## <a name="configure-the-biztalk-application"></a>Configurar la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, la orquestación que creó anteriormente se muestra en el panel de orquestaciones en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Debe utilizar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para configurar la aplicación. Para obtener más información acerca de cómo configurar una aplicación, consulte [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).
  
 Configuración de una aplicación implica:  
  
-   Selección de un host de la aplicación.  
  
-   Asignación de los puertos que ha creado en la orquestación con puertos físicos en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para que esta orquestación debe:  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde se colocará un mensaje de solicitud. La orquestación de BizTalk consumirá el mensaje de solicitud y enviarla a la base de datos de SQL Server.  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta de la base de datos de SQL Server.  
  
    -   Definir un puerto de envío físico de WCF-Custom o WCF-SQL para enviar mensajes a la base de datos de SQL Server. También debe especificar la acción en el puerto de envío. Para obtener información sobre cómo crear puertos, consulte [configurar manualmente un enlace de puerto físico para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md).
  
        > [!NOTE]
        >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para crear puertos de envío (para las llamadas salientes) o puertos de recepción (para las llamadas entrantes). Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto para utilizar el adaptador SQL](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).
  
## <a name="start-the-application"></a>Iniciar la aplicación  
 Iniciar la aplicación de BizTalk para invocar la **ExecuteReader** operación en la base de datos de SQL Server. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md).
  
 En esta fase, asegúrese de que:  
  
-   El archivo de puerto de recepción para recibir mensajes de solicitud de ejecución de la orquestación.  
  
-   El puerto de envío de archivo para recibir los mensajes de respuesta de la orquestación se está ejecutando.  
  
-   El puerto de envío WCF-Custom o WCF-SQL para enviar mensajes a la base de datos de SQL Server se está ejecutando.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="execute-the-operation"></a>Ejecutar la operación.  
 Después de ejecutar la aplicación, debe quitar un mensaje de solicitud en el archivo de ubicación de recepción. El esquema del mensaje de solicitud debe ajustarse al esquema para el **ExecuteReader** operación generado anteriormente. Por ejemplo, el mensaje de solicitud para invocar la ADD_EMP_DETAILS con una **ExecuteReader** operación es:  
  
```  
<ExecuteReader xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">  
  <Query>EXEC ADD_EMP_DETAILS Tom,Manager,100000</Query>  
</ExecuteReader>  
```  
  
 Vea [esquemas de mensaje para las operaciones de ExecuteScalar, ExecuteReader y ExecuteNonQuery](../../adapters-and-accelerators/adapter-sql/executenonquery-executereader-and-executescalar-message-schemas-in-sql.md) para obtener más información acerca del esquema de mensaje de solicitud para invocar un **ExecuteReader** operación mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
> [!NOTE]
>  En la `<Query>` etiqueta, puede especificar varias instrucciones SQL separadas por un punto y coma.  
  
 La orquestación consume el mensaje y lo envía a la base de datos de SQL Server. La respuesta de la base de datos de SQL Server se guarda en la otra ubicación de archivo definida como parte de la orquestación. La respuesta para la **ExecuteReader** operación contiene un conjunto de resultados como una matriz de conjunto de datos. Por ejemplo, la respuesta de la base de datos de SQL Server para el mensaje de solicitud anterior es:  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<ExecuteReaderResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">  
  <ExecuteReaderResult>  
    <DataSet xmlns="http://schemas.datacontract.org/2004/07/System.Data">  
      <xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
        <xs:element msdata:IsDataSet="true" name="NewDataSet">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                <xs:complexType>  
                  <xs:sequence>  
                    <xs:element minOccurs="0" name="Employee_ID" type="xs:int" />   
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
            <Employee_ID>10767</Employee_ID>   
          </NewTable>  
        </NewDataSet>  
      </diffgr:diffgram>  
    </DataSet>  
  </ExecuteReaderResult>  
</ExecuteReaderResponse>  
```  
  
 En la respuesta, 10767 es el identificador del empleado recién creado.  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez haya implementado y configurado el proyecto de BizTalk, puede exportar la configuración en un archivo XML denominado archivo de enlace. Una vez que se genera un archivo de enlace, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear elementos como los puertos de envío y puertos de recepción para la misma orquestación. Para obtener más información acerca de los archivos de enlace, vea [reutilizar enlaces del adaptador](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md).
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)