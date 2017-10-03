---
title: Las operaciones de ExecuteReader, ExecuteScalar o ExecuteNonQuery en Oracle E-Business Suite | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e2d377d-60a2-45fe-8458-433e6f4f6619
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cff3d58712ca8e926ada18519fcebb5fddc7ea65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="executereader-executescalar-or-executenonquery-operations-in-oracle-e-business-suite"></a>Operaciones de ExecuteReader, ExecuteScalar o ExecuteNonQuery en Oracle E-Business Suite
El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone operaciones genéricas como **ExecuteNonQuery**, **ExecuteReader**, y **ExecuteScalar**. Puede utilizar estas operaciones para ejecutar cualquier instrucción SQL en la base de datos de Oracle. Estas operaciones varían en función del tipo de respuesta que se obtiene de la instrucción SQL. Para obtener más información acerca del modo en que el adaptador admite estas operaciones, vea [soporte técnico para las operaciones de ExecuteScalar, ExecuteReader y ExecuteNonQuery](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).  
  
 En este tema se muestra cómo realizar una **ExecuteReader** operación mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Puede seguir el mismo conjunto de procedimientos que se describen en este tema para realizar **ExecuteNonQuery** y **ExecuteScalar** operaciones.  
  
## <a name="how-to-invoke-executereader-operation-on-oracle-database"></a>Cómo la operación ExecuteReader invocar en la base de datos de Oracle  
 Realizar una operación en una base de datos de Oracle mediante el uso de [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica procedimientos tareas que se describen en [bloques de creación para crear aplicaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md). Para invocar la **ExecuteReader** operación en la base de datos de Oracle, estas tareas son:  
  
1.  Crear un proyecto de BizTalk y genere el esquema para el **ExecuteReader** operación.  
  
2.  Crear mensajes en el proyecto de BizTalk para enviar y recibir mensajes de base de datos de Oracle.  
  
3.  Crear una orquestación para invocar la operación en la base de datos de Oracle.  
  
4.  Compilar e implementar el proyecto de BizTalk.  
  
5.  Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
6.  Inicie la aplicación de BizTalk.  
  
 Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="generating-schema"></a>Generar el esquema  
 En este tema se muestra cómo invocar el **ExecuteReader** operación en una base de datos de Oracle mediante la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. El **ExecuteReader** operación toma cualquier instrucción SQL como un parámetro y devuelve el conjunto de resultados de la operación como una matriz del conjunto de datos. De este tema, se ejecute una instrucción SELECT sobre el uso de la tabla ACCOUNTACTIVITY la **ExecuteReader** operación. La tabla ACCOUNTACTIVITY se crea mediante la ejecución de las secuencias de comandos que se proporciona con los ejemplos. Para obtener más información acerca de la secuencia de comandos, consulte [ejemplos](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).  
  
 Para demostrar cómo invocar **ExecuteReader** operación, se genera el esquema para el **ExecuteReader** operación. Debe crear un proyecto de BizTalk y utilizar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar el esquema. Para obtener más información acerca de cómo generar esquemas, vea [recuperación de metadatos para las operaciones de Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md).  
  
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
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *Execute_Reader.GenericOperation.ExecuteReader*, donde Execute_Reader es el nombre de su proyecto de BizTalk. *GenericOperation* es el esquema generado para el **ExecuteReader** operación.|  
  
6.  Repita el paso 2 para crear un nuevo mensaje. En el **propiedades** panel para el nuevo mensaje, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Escriba `Response`|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *Execute_Reader.GenericOperation.ExecuteReaderResponse*.|  
  
## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para usar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para realizar una operación en la base de datos de Oracle. En esta orquestación, se coloca un mensaje de solicitud en una determinada ubicación de recepción. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] consume este mensaje y pasa a la base de datos de Oracle. La respuesta de base de datos de Oracle se guarda en otra ubicación. Una orquestación típica para invocar operaciones genéricas como **ExecuteReader** contendría:  
  
-   Enviar y recibir formas a fin de enviar y recibir mensajes desde una base de datos de Oracle.  
  
-   Puerto para enviar y recibir mensajes desde una base de datos de Oracle de recepción bidireccional.  
  
-   Un puerto de envío unidireccional para enviar la respuesta de base de datos de Oracle en una carpeta.  
  
 Una orquestación de ejemplo para invocar un **ExecuteReader** operación es similar al siguiente:  
  
 ![Orquestación para invocar la operación ExecuteReader](../../adapters-and-accelerators/adapter-oracle-ebs/media/37b63331-76b7-47a2-b9d3-0c60e165d993.gif "37b63331-76b7-47a2-b9d3-0c60e165d993")  
  
### <a name="adding-message-shapes"></a>Agregar formas de mensaje  
 Debe configurar las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la columna de forma corresponden a los nombres de las formas de mensaje como se muestra en la orquestación just-mencionado.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-Establecer **nombre** a *ReceiveMessage*<br />-Establecer **activar** a *es True*|  
|SendMessage|Send|-Establecer **nombre** a *SendMessage*|  
|ReceiveResponse|Receive|-Establecer **nombre** a *ReceiveResponse*<br />-Establecer **activar** a *False*|  
|SendResponse|Send|-Establecer **nombre** a *SendResponse*|  
  
### <a name="adding-ports"></a>Agregar puertos  
 Para cada uno de los puertos lógicos, configure las propiedades en la tabla siguiente. Los nombres que aparecen en la columna de puerto se corresponden con los nombres de los puertos tal como se muestra en la orquestación.  
  
|Puerto|Propiedades|  
|----------|----------------|  
|MessageIn|-Establecer **identificador** a *MessageIn*<br />-Establecer **tipo** a *MessageInType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *de recepción*|  
|LOBPort|-Establecer **identificador** a *LOBPort*<br />-Establecer **tipo** a *LOBPortType*<br />-Establecer **patrón de comunicación** a *solicitudes y respuestas*<br />-Establecer **dirección de comunicación** a *envío y recepción*|  
|ResponseOut|-Establecer **identificador** a *ResponseOut*<br />-Establecer **tipo** a *ResponseOutType*<br />-Establecer **patrón de comunicación** a *unidireccional*<br />-Establecer **dirección de comunicación** a *enviar*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>Especificar mensajes de las formas de acción y conéctelos a los puertos  
 En la tabla siguiente especifica los valores de propiedad para especificar los mensajes para las formas de acción y vincular los mensajes a los puertos. Los nombres que aparecen en la **forma** columna corresponden a los nombres de las formas de mensaje como se muestra en el diagrama de orquestación anteriormente.  
  
 Después de que estas propiedades se configuran, las formas de mensaje y los puertos que están conectados y la orquestación está completa.  
  
 A continuación, ahora debe compilar la solución de BizTalk e implementarlo en BizTalk Server. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *MessageIn.Exec_Reader.Request*|  
|SendMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *LOBPort.Exec_Reader.Request*|  
|ReceiveResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *LOBPort.Exec_Reader.Response*|  
|SendResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *ResponseOut.Exec_Reader.Request*|  
  
 Después de especificar estas propiedades, las formas de mensaje y los puertos que están conectados y la orquestación está completa.  
  
 Ahora deberá compilar la solución de BizTalk e implementarlo en BizTalk Server. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).  
  
## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el **orquestaciones** panel en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Debe utilizar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para configurar la aplicación. Para obtener un tutorial, vea [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).  
  
 Configuración de una aplicación implica:  
  
-   Selección de un host de la aplicación.  
  
-   Asignación de los puertos que ha creado en la orquestación con puertos físicos en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para que esta orquestación debe:  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde se colocará un mensaje de solicitud. La orquestación de BizTalk consumirá el mensaje de solicitud y enviarla a la base de datos de Oracle.  
  
    -   Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta de la base de datos de Oracle.  
  
    -   Definir un físico WCF-Custom o WCF-OracleEBS puerto de envío para enviar mensajes a la base de datos de Oracle. También debe especificar la acción en el puerto de envío. Para obtener información sobre cómo crear puertos de envío, consulte [configurar manualmente un puerto físico enlazado con el adaptador de Oracle E-Business ](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md).  
  
        > [!IMPORTANT]
        >  Como parte de las operaciones genéricas, si se ejecutan operaciones en los objetos, por ejemplo procedimientos almacenados, funciones, tablas de interfaz o vistas de interfaz, que pertenecen a una aplicación de Oracle E-Business Suite, debe establecer el contexto de la aplicación mediante la especificación las propiedades de enlace necesaria. Para obtener más información acerca de cómo establecer el contexto de la aplicación, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
        >   
        >  Puede establecer el contexto de la aplicación mediante la especificación de las propiedades de enlace o estableciendo el mensaje propiedades de contexto expuestas por la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Para obtener instrucciones sobre cómo establecer las propiedades de enlace, consulte [configurar las propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md). Para obtener instrucciones sobre cómo establecer el contexto de la aplicación mediante las propiedades de contexto de mensaje, consulte [configurar las propiedades contexto de mensaje usando de contexto de aplicación en Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md).  
  
        > [!NOTE]
        >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para crear puertos de envío (para las llamadas salientes) o puertos de recepción (para las llamadas entrantes). Para obtener más información, consulte [configurar un físico puerto de enlace utilizando un archivo de enlace de puerto para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md).  
  
## <a name="starting-the-application"></a>A partir de la aplicación  
 Debe iniciar la aplicación de BizTalk antes de invocar **ExecuteReader** operación en la base de datos de Oracle. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md).  
  
 En esta fase, asegúrese de que:  
  
-   El archivo de puerto de recepción para recibir mensajes de solicitud de ejecución de la orquestación.  
  
-   El puerto de envío de archivo para recibir los mensajes de respuesta de la orquestación se está ejecutando.  
  
-   El WCF-Custom o WCF-OracleEBS puerto de envío para enviar mensajes a Oracle que se está ejecutando la base de datos.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, debe quitar un mensaje de solicitud en el archivo de ubicación de recepción. El esquema del mensaje de solicitud debe ajustarse al esquema para el **ExecuteReader** operación generado anteriormente. Por ejemplo, el mensaje de solicitud para ejecutar una instrucción SELECT con una **ExecuteReader** operación es:  
  
```  
<ExecuteReader xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/">  
  <Query>SELECT * FROM ACCOUNTACTIVITY</Query>  
</ExecuteReader>  
```  
  
 Vea los esquemas de mensaje para ExecuteReader, ExecuteScalar y operaciones de ExecuteNonQuery para obtener más información acerca del esquema de mensaje de solicitud para invocar un **ExecuteReader** operación mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
 La orquestación consume el mensaje y lo envía a la base de datos de Oracle. La respuesta de la base de datos de Oracle se guarda en la otra ubicación de archivo definida como parte de la orquestación. La respuesta para la **ExecuteReader** operación contiene un conjunto de resultados como un conjunto de datos. Por ejemplo, la respuesta de la base de datos de Oracle para el mensaje de solicitud anterior es:  
  
```  
\<?xml version="1.0" encoding="utf-8" ?>   
<ExecuteReaderResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/">  
  <ExecuteReaderResult>  
    \<xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
      \<xs:element msdata:IsDataSet="true" name="NewDataSet">  
        \<xs:complexType>  
          \<xs:sequence>  
            \<xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
              \<xs:complexType>  
                \<xs:sequence>  
                  \<xs:element minOccurs="0" name="TID" type="xs:decimal" />   
                  \<xs:element minOccurs="0" name="ACCOUNT" type="xs:decimal" />   
                  \<xs:element minOccurs="0" name="AMOUNT" type="xs:decimal" />   
                  \<xs:element minOccurs="0" name="DESCRIPTION" type="xs:string" />   
                  \<xs:element minOccurs="0" name="TRANSDATE" type="xs:dateTime" />   
                  \<xs:element minOccurs="0" name="PROCESSED" type="xs:string" />   
                \</xs:sequence>  
              \</xs:complexType>  
            \</xs:element>  
          \</xs:sequence>  
        \</xs:complexType>  
      \</xs:element>  
    \</xs:schema>  
    \<diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
      <NewDataSet xmlns="">  
        <NewTable>  
          <TID>1</TID>   
          <ACCOUNT>100001</ACCOUNT>   
          <AMOUNT>500</AMOUNT>   
          <DESCRIPTION />   
          <TRANSDATE>2008-08-04T13:04:20</TRANSDATE>   
          <PROCESSED>n</PROCESSED>   
        </NewTable>  
        <NewTable>  
          ......  
          ......  
        </NewTable>  
        ......  
        ......  
      </NewDataSet>  
    \</diffgr:diffgram>  
  </ExecuteReaderResult>  
</ExecuteReaderResponse>  
```  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez haya implementado y configurado el proyecto de BizTalk, puede exportar la configuración en un archivo XML denominado archivo de enlace. Después de generar un archivo de enlace, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear elementos como los puertos de envío y puertos de recepción para la misma orquestación. Para obtener más información acerca de los archivos de enlace, vea [reutilizar enlaces del adaptador con Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md).  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)