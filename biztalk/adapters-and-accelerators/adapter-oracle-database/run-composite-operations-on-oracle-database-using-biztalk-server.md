---
title: Ejecutar operaciones compuestas en la base de datos de Oracle con BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf47d95e-cdf1-4c9b-a15a-7cf123d0ea6d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9213a280412e0b9d771c94092709cae2666a025b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005917"
---
# <a name="run-composite-operations-on-oracle-database-using-biztalk-server"></a>Ejecutar operaciones compuestas en la base de datos de Oracle con BizTalk Server
El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] permite a los clientes del adaptador realizar operaciones compuestas en la base de datos de Oracle. Puede incluir una operación compuesta:  

- Insertar, actualizar, eliminar y seleccione las operaciones en tablas y vistas.  

- Procedimientos almacenados y funciones, dentro o fuera de un paquete.  

  Una operación compuesta solo puede tener cualquier número de estas operaciones, en cualquier orden. Por ejemplo, puede tener dos inserciones seguidas de una eliminación y, finalmente, la ejecución de un procedimiento almacenado. Además, puede tener diferentes operaciones destinadas a la base de datos diferentes tablas o vistas. Para obtener más información acerca de cómo el adaptador admite operaciones compuestas, vea [realizar operaciones compuestas en la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-in-oracle-database.md). Para obtener información acerca de la estructura del mensaje SOAP para operaciones compuestas, vea [esquemas de mensaje para la operación compuesta](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md).  

## <a name="how-to-perform-composite-operations-on-oracle-database"></a>¿Cómo realizar operaciones compuestas en la base de datos de Oracle?  
 Realizar una operación en la base de datos de Oracle mediante [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica tareas de procedimientos se describe en [bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md). Para llevar a cabo operaciones compuestas en la base de datos de Oracle, estas tareas son:  

1. Crear un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y genere el esquema para todas las operaciones que desea invocar.  

2. Crear manualmente un archivo de esquema que incluya referencias a todos los esquemas que generó en el paso anterior.  

3. Crear mensajes en el proyecto de BizTalk para enviar y recibir mensajes de base de datos de Oracle. Estos mensajes deben cumplir el esquema de solicitud y respuesta que ha creado en el paso anterior.  

4. Crear una orquestación para invocar la operación compuesta en la base de datos de Oracle.  

5. Compile e implemente el proyecto de BizTalk.  

6. Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  

7. Inicie la aplicación de BizTalk.  

   Este tema proporciona instrucciones sobre cómo realizar estas tareas.  

## <a name="generating-schema"></a>Generar el esquema  
 En este tema, para demostrar cómo realizar operaciones compuestas, se llevará a cabo las siguientes tareas en el mismo orden:  

- Insertar registros en la tabla ACCOUNTACTIVITY.  

- Recuperar todos los registros de la tabla ACCOUNTACTIVITY al invocar el procedimiento GET_ALL_ACTIVITY dentro del paquete ACCOUNT_PKG.  

- Eliminar el registro de la tabla ACCOUNTACTIVITY.  

  Ejecute los scripts proporcionados con los ejemplos para crear la tabla ACCOUNTACTIVITY. Para obtener más información acerca de los ejemplos, vea [ejemplos de esquema](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md).  

  Debe crear un proyecto de BizTalk y utilice el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar el esquema. Consulte [recuperar metadatos para operaciones de base de datos de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md) para obtener más información acerca de cómo generar esquemas.  

## <a name="creating-a-composite-schema-definition"></a>Creación de una definición de esquema compuesto  
 Ahora debe crear un esquema compuesto en el [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] proyecto de BizTalk que se hace referencia a los esquemas creados para las operaciones individuales. Realice los pasos siguientes para crear una definición de esquema compuesto.  

#### <a name="to-add-a-composite-schema-definition"></a>Para agregar una definición de esquema compuesto  

1. Agregar un archivo de esquema al proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. Haga clic en el nombre de la solución, elija **agregar**y, a continuación, haga clic en **nuevo elemento**. En el **Agregar nuevo elemento** cuadro de diálogo desde el **categorías** cuadro, haga clic en **archivos de esquema**. Desde el **plantillas** cuadro, haga clic en **esquema**. Especifique un nombre para el archivo de esquema y haga clic en **Aceptar**.  

    En este ejemplo, especifique el nombre de archivo de esquema como `CompositeSchema.xsd`.  

2. Agregar referencias para el esquema generado para las distintas operaciones que desee realizar. En este ejemplo, los distintos esquemas generados para las operaciones son:  

   - OracleDBBinding.xsd, para las operaciones Insert y Delete en la tabla ACCOUNTACTIVITY.  

   - OracleDBBinding2.xsd, para el procedimiento GET_ALL_ACTIVITY.  

     Para agregar referencias:  

   1.  Haga clic en la raíz **\<esquema\>** nodo en el CompositeSchema.xsd y haga clic en **propiedades**.  

   2.  En el **propiedad** cuadro, haga clic en el botón de puntos suspensivos **(...)**  contra la **importaciones** propiedad.  

        ![Importar definiciones de esquema](../../adapters-and-accelerators/adapter-oracle-database/media/d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca.gif "d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca")  

   3.  En el **importaciones** cuadro de diálogo desde el **importar un esquema nuevo como** lista, seleccione **XSD Import**y, a continuación, haga clic en **agregar**.  

   4.  En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nodo de nombre del proyecto de BizTalk, expanda **esquemas**y, a continuación, seleccione el esquema que desea importar. En este ejemplo, seleccione < BizTalk_project_name >. OracleDBBinding.xsd. Haga clic en **Aceptar**.  

        Repita este paso para importar < BizTalk_project_name >. OracleDBBinding2.xsd demasiado.  

   5.  En el **importaciones** cuadro de diálogo, haga clic en **Aceptar**.  

3. Agregue dos nodos secundarios del nodo de esquema raíz. Un nodo secundario corresponde al esquema de solicitud para realizar la operación compuesta. El otro nodo secundario corresponde al esquema de respuesta. El nodo que se corresponde con el esquema de solicitud puede tener cualquier nombre. El nodo que se corresponde con el esquema de respuesta se debe llamar a < request_schema_node > respuesta. En este ejemplo, se llamará el nodo de esquema de solicitud como **solicitud**. Por lo tanto, el nodo de esquema de respuesta se denomina **RequestResponse**.  

   > [!NOTE]
   >  De forma predeterminada, un **raíz** nodo también se agrega a un nuevo archivo de esquema. Puede cambiar el nombre del **raíz** nodo **solicitar**. Para cambiar el nombre de un nodo, haga clic en el nombre de nodo y haga clic en **cambiar el nombre**.  

    Para agregar un nodo bajo el **\<esquema\>** nodo:  

   1.  Haga clic en el **\<esquema\>** nodo, seleccione **Insertar nodo de esquema**y haga clic en **registro secundario**.  

   2.  Cambiar el nombre del nuevo nodo a **RequestResponse**.  

4. Agregar nodos secundarios bajo el **solicitud** nodo que se corresponden con el esquema de solicitud para cada operación que llevará a cabo como parte de la operación compuesta. En este ejemplo, debe agregar los nodos secundarios correspondientes a la siguiente:  

   -   Insertar y eliminar operaciones en la tabla ACCOUNTACTIVITY.  

   -   Procedimiento GET_ALL_ACTIVITY.  

   > [!IMPORTANT]
   >  Debe agregar los nodos en el mismo orden en el que desea realizar las operaciones. Por ejemplo, si desea insertar un registro, a continuación, ejecutar un procedimiento almacenado y, a continuación, elimine un registro en primer lugar debe agregar un nodo para la operación de inserción, seguido de un nodo para el procedimiento almacenado y, finalmente, un nodo para la operación de eliminación.  

    Para agregar nodos secundarios a la **solicitar** nodo:  

   1.  Haga clic en el **solicitar** nodo, seleccione **Insertar nodo de esquema**y, a continuación, haga clic en **registro secundario**.  

        ![Insertar nodos secundarios para un esquema](../../adapters-and-accelerators/adapter-oracle-database/media/58992131-13a6-45c3-9513-5c0995091fae.gif "58992131-13a6-45c3-9513-5c0995091fae")  

   2.  Cambie el nombre del registro para que correspondan a un esquema de solicitud para una operación que se realiza como parte de la operación compuesta. Por ejemplo, cambie el nombre del nodo para "Insert".  

   3.  Mapa del **insertar** nodo con el esquema de solicitud para la operación de inserción en la tabla ACCOUNTACTIVITY. Para ello, haga clic en el **insertar** nodo y haga clic en **propiedades**. En el **propiedades** cuadro, desde el **Data Structure Type** lista, seleccione **Insert (referencia)**.  

        ![Asignar nodos secundarios al esquema de solicitud](../../adapters-and-accelerators/adapter-oracle-database/media/b4ebd3c7-14e5-4c37-abd7-83f0b4db4c9e.gif "b4ebd3c7-14e5-4c37-abd7-83f0b4db4c9e")  

   4.  Repita estos pasos para agregar nodos para los esquemas de solicitud para el procedimiento almacenado de GET_ALL_ACTIVITY y la operación de eliminación. Especifique los nombres de nodo y asignarlas al esquema correspondiente, tal como se mencionó en la tabla siguiente.  

       |Nombre de nodo|Asigna al esquema|  
       |---------------|----------------------|  
       |GET_ALL_ACTIVITY|GET_ALL_ACTIVITY (referencia)|  
       |DELETE|Delete (referencia)|  

5. Agregar nodos secundarios bajo el **RequestResponse** nodo que se corresponden con el esquema de respuesta para cada operación que llevará a cabo como parte de la operación compuesta. En este ejemplo, debe agregar los nodos secundarios correspondientes a la siguiente:  

   -   Insertar y eliminar operaciones en la tabla ACCOUNTACTIVITY.  

   -   GET_ALL_ACTIVITY el procedimiento almacenado.  

   > [!IMPORTANT]
   >  Debe agregar los nodos secundarios en el mismo orden que los nodos secundarios bajo el **solicitar** nodo.  

    Para agregar nodos secundarios a la **RequestResponse** nodo:  

   1.  Haga clic en el **RequestResponse** nodo, seleccione **Insertar nodo de esquema**y haga clic en **registro secundario**.  

   2.  Cambie el nombre del registro para que correspondan a un esquema de respuesta para una operación que se realiza como parte de la operación compuesta. Por ejemplo, cambie el nombre del nodo para "InsertResponse".  

   3.  Mapa del **InsertResponse** nodo con el esquema de respuesta para la operación de inserción en la tabla ACCOUNTACTIVITY. Para ello, haga clic en el **InsertResponse** nodo y haga clic en **propiedades**. En el **propiedades** cuadro, desde el **Data Structure Type** lista, seleccione **InsertResponse (referencia)**.  

   4.  Repita estos pasos para agregar nodos para los esquemas de respuesta para el procedimiento almacenado de GET_ALL_ACTIVITY y la operación de eliminación. Especifique los nombres de nodo y asignarlas al esquema correspondiente, tal como se mencionó en la tabla siguiente.  

       |Nombre de nodo|Asigna al esquema|  
       |---------------|----------------------|  
       |GET_ALL_ACTIVITYResponse|GET_ALL_ACTIVITYResponse (referencia)|  
       |DeleteResponse|DeleteResponse (referencia)|  

6. Guardar el **CompositeSchema.xsd** archivo.  

## <a name="defining-messages-and-message-types"></a>Definición de los mensajes y tipos de mensaje  
 El esquema compuesto que creó en el último paso describe los "tipos" necesarios para los mensajes en una orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Ahora debe crear mensajes para la orquestación y vincularlos a esquema que ha creado en el paso anterior.  

#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vínculo a esquema  

1. Agregar una orquestación al proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. Desde el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**. Escriba un nombre para la orquestación de BizTalk y, a continuación, haga clic en **agregar**.  

2. Abra la ventana Vista orquestación del proyecto de BizTalk, si aún no está abierto. Para ello, haga clic en **vista**, apunte a **Other Windows**y, a continuación, haga clic en **Vista orquestación**.  

3. En la Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  

4. Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  

5. En el **propiedades** panel para el **Message_1**, realice lo siguiente:  


   |   Use   |                                                                                                                  Para                                                                                                                   |
   |--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  Identificador  |                                                                                                                Escriba `Request`                                                                                                                 |
   | Tipo de mensaje | En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *Composite_Op.CompositeSchema.Request*, donde Composite_Op es el nombre de su proyecto de BizTalk. CompositeSchema es el esquema que ha creado manualmente para las operaciones compuestas. |


6. Repita el paso 2 para crear un nuevo mensaje. En el **propiedades** panel para el nuevo mensaje, haga lo siguiente:  

   |Use|Para|  
   |--------------|----------------|  
   |Identificador|Escriba `Response`|  
   |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y, a continuación, seleccione *Composite_Op.CompositeSchema.RequestResponse*.|  

## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para utilizar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para llevar a cabo operaciones compuestas en la base de datos de Oracle. En esta orquestación, se coloca un mensaje de solicitud en una determinada ubicación de recepción. El mensaje de solicitud debe ajustarse al esquema compuesto que creó anteriormente. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] consume este mensaje y lo pasa por base de datos de Oracle. La respuesta de la base de datos de Oracle se guarda en otra ubicación. Debe incluir el envío y recepción de formas para enviar mensajes a la base de datos de Oracle y recibir respuestas, respectivamente. Una orquestación básica para realizar operaciones compuestas es similar al siguiente:  

 ![Orquestación para efectuar operaciones compuestas](../../adapters-and-accelerators/adapter-oracle-database/media/4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb.gif "4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb")  

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
|ReceiveMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *MessageIn.CompositeOp.Request*|  
|SendMessage|-Establecer **mensaje** a *de solicitud*<br />-Establecer **operación** a *LOBPort.CompositeOp.Request*|  
|ReceiveResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *LOBPort.CompositeOp.Response*|  
|SendResponse|-Establecer **mensaje** a *respuesta*<br />-Establecer **operación** a *ResponseOut.CompositeOp.Request*|  

 Después de especificar estas propiedades, están conectados a los puertos y formas de mensaje y se completa la orquestación.  

 Ahora debe compilar la solución de BizTalk e implementarla en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).  

## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el panel orquestaciones, en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Debe usar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para configurar la aplicación. Para ver un tutorial, vea [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).

 Configuración de una aplicación implica:  

- Selección de un host de la aplicación.  

- Asignación de los puertos que ha creado en la orquestación con puertos físicos en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para esta orquestación, debe:  

  - Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde se colocará un mensaje de solicitud. La orquestación de BizTalk usarán el mensaje de solicitud y enviarla a la base de datos de Oracle.  

  - Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta de la base de datos de Oracle.  

  - Definir un puerto de envío WCF-Custom o WCF-OracleDB físico para enviar mensajes a la base de datos de Oracle. Dado que las operaciones que son es como parte de la operación compuesta se ejecutan en una sola transacción, asegúrese de que el **UseAmbientTransaction** enlaza la propiedad se establece en **True**.  

     También debe especificar la acción en el puerto de envío. La acción para una operación compuesta es "<http://Microsoft.LobServices.OracleDB/2007/03/CompositeOperation”>. Para obtener información sobre cómo crear los puertos, consulte [configurar manualmente un enlace de puerto físico para el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md). Para obtener más información sobre cómo especificar acciones para los puertos, consulte [configurar la acción SOAP para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md).  

    > [!NOTE]
    >  Generar el esquema mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] también crea un archivo de enlace que contiene información sobre los puertos y las acciones que se establecerá para esos puertos. Puede importar este archivo de enlace desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para crear puertos de envío (para las llamadas salientes) o la recepción (para las llamadas entrantes). Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md). Si importa este archivo de enlace, se establece la acción en el puerto de envío a una acción dinámica relacionadas con todas las operaciones que seleccionó en el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] al generar el esquema. Para una operación compuesta, debe reemplazar la acción dinámica con "<http://Microsoft.LobServices.OracleDB/2007/03/CompositeOperation”>.  

## <a name="starting-the-application"></a>Iniciar la aplicación  
 Debe iniciar la aplicación de BizTalk para realizar operaciones compuestas en la base de datos de Oracle. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md).  

 En esta etapa, asegúrese de que:  

-   El archivo de puerto de recepción para recibir mensajes de solicitud para la orquestación se está ejecutando.  

-   El puerto de envío de archivo para recibir los mensajes de respuesta de la orquestación se está ejecutando.  

-   El puerto de envío WCF-Custom o WCF-OracleDB para enviar mensajes a la base de datos de Oracle se está ejecutando.  

-   La orquestación de BizTalk para la operación se está ejecutando.  

## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, debe quitar un mensaje de solicitud en el archivo de ubicación de recepción. El esquema del mensaje de solicitud debe cumplir el esquema para las operaciones compuestas que creó anteriormente. Por ejemplo, un mensaje de solicitud que inserta un registro en la tabla ACCOUNTACTIVITY, invoca el procedimiento almacenado de GET_ALL_ACTIVITY y elimina un registro de la tabla ACCOUNTACTIVITY es:  

```  
<Request xmlns="http://Composite_Op.CompositeSchema">  
  <Insert xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY">  
    <RECORDSET>  
      <ACCOUNTACTIVITYRECORDINSERT>  
        <TID>1</TID>  
        <ACCOUNT>100001</ACCOUNT>  
        <AMOUNT>1500</AMOUNT>  
        <DESCRIPTION></DESCRIPTION>  
        <TRANSDATE>2008-06-21T15:52:19</TRANSDATE>  
        <PROCESSED>n</PROCESSED>  
      </ACCOUNTACTIVITYRECORDINSERT >  
    </RECORDSET>  
  </Insert>  
  <GET_ALL_ACTIVITY xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG"/>  
  <Delete xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY">  
    <FILTER>WHERE AMOUNT = 1500</FILTER>  
  </Delete>  
</Request>  
```  

 El mensaje de solicitud anterior primero inserta un registro y, a continuación, invoca el procedimiento GET_ALL_ACTIVITY para obtener todos los registros en la tabla ACCOUNTACTIVITY. A continuación, se elimina el registro insertado mediante la especificación de una cláusula de filtro. Consulte [esquemas de mensaje para la operación compuesta](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md) para obtener más información sobre el esquema de mensaje de solicitud para realizar operaciones compuestas en Oracle database mediante la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  

 La orquestación consume el mensaje y lo envía a la base de datos de Oracle. La respuesta de la base de datos de Oracle se guarda en la otra ubicación de archivo definida como parte de la orquestación. Por ejemplo, la respuesta de la base de datos de Oracle para el mensaje de solicitud anterior es similar al siguiente:  

```  
<?xml version="1.0" encoding="utf-8" ?>   
<RequestResponse xmlns="http://Composite_Op.CompositeSchema">  
  <InsertResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOOT/Table/ACCOUNTACTIVITY">  
    <InsertResult>1</InsertResult>   
  </InsertResponse>  
  <GET_ALL_ACTIVITYResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
    <ALLRECS>  
      <xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
        <xs:element msdata:IsDataSet="true" name="NewDataSet">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                <xs:complexType>  
                  <xs:sequence>  
                    <xs:element minOccurs="0" name="TID" type="xs:decimal" />   
                    <xs:element minOccurs="0" name="ACCOUNT" type="xs:decimal" />   
                    <xs:element minOccurs="0" name="AMOUNT" type="xs:decimal" />   
                    <xs:element minOccurs="0" name="DESCRIPTION" type="xs:string" />   
                    <xs:element minOccurs="0" name="TRANSDATE" type="xs:dateTime" />   
                    <xs:element minOccurs="0" name="PROCESSED" type="xs:string" />   
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
            ......   
            ......   
          </NewTable>  
          ......  
          ......  
          <NewTable>  
            <TID>10</TID>   
            <ACCOUNT>100001</ACCOUNT>   
            <AMOUNT>1000</AMOUNT>   
            <TRANSDATE>2008-07-28T21:39:57</TRANSDATE>   
            <PROCESSED>n</PROCESSED>   
          </NewTable>  
        </NewDataSet>  
      </diffgr:diffgram>  
    </ALLRECS>  
  </GET_ALL_ACTIVITYResponse>  
  <DeleteResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY">  
    <DeleteResult>1</DeleteResult>   
  </DeleteResponse>  
</RequestResponse>  
```  

 La respuesta anterior contiene varios conjuntos de resultados correspondiente a las diferentes operaciones realizadas como parte de la operación compuesta. Por ejemplo, el `InsertResult` elemento contiene '1', que indica el número de filas insertadas por la operación de inserción. De forma similar, la `DeleteResult` elemento contiene '1', que indica el número de filas eliminadas por la operación de eliminación.  

> [!IMPORTANT]
>  Si experimenta problemas de tiempo de espera mientras se ejecuta una operación compuesta podría ser porque el número de conexiones es menor que el número de operaciones en una operación compuesta que implican:  
> 
> - Procedimientos almacenados que contengan BFILE, BLOB, CLOB, NCLOB y REF CURSOR como OUT o IN OUT parámetros.  
>   -   Operación de selección.  
> 
>   Para resolver este problema, debe asegurarse de que, si hay un número de "n" de estas operaciones en una operación compuesta, el valor especificado para el **MinPoolSize** enlaza la propiedad es "n + 1" o superior. Para obtener más información sobre la **MinPoolSize** enlaza la propiedad, vea [trabajar con propiedades de enlace](https://msdn.microsoft.com/library/dd788467.aspx).  

## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez que haya implementado y configurado el proyecto de BizTalk, puede exportar opciones de configuración a un archivo XML llamado el archivo de enlace. Cuando genere un archivo de enlace, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear elementos como puertos de envío y recepción para la misma orquestación. Para obtener más información acerca de los archivos de enlace, consulte [enlaces del adaptador de base de datos de Oracle reutilizar](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md).  

## <a name="see-also"></a>Vea también  
[Bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)