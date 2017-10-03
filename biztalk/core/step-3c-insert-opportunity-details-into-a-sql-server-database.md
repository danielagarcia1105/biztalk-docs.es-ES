---
title: 'Paso 3c: Insertar detalles de oportunidades en una base de datos SQL Server | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f6f9bbe-6f25-4393-8f92-aeeba9736acf
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33d0055c05e0c9af9f4dddc4a7275c01ff49d779
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3c-insert-opportunity-details-into-a-sql-server-database"></a>Paso 3c: Insertar detalles de oportunidades en una base de datos SQL Server
Hasta ahora, hemos compilado la orquestación para enviar una consulta a Salesforce y recibir una respuesta. En esta sección, actualizaremos esa orquestación para insertar la respuesta de Salesforce en una **OrderDetails** tabla en una base de datos de SQL Server local, **pedidos**. Para lograrlo, realizaremos los siguientes pasos:  
  
-   Crear un **OrderDetails** de tabla en una **pedidos** base de datos en una base de datos de SQL Server local.  
  
-   Use la [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] disponibles con [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] para generar el esquema para la operación de inserción en el **OrderDetails** tabla.  
  
-   Crear una asignación para transformar el mensaje de respuesta de Salesforce al mensaje para insertar en **OrderDetails** tabla de SQL Server.  
  
-   Actualizar la orquestación para usar la transformación para insertar el mensaje de respuesta en el **OrderDetails** tabla.  
  
## <a name="create-sql-server-database-and-table"></a>Crear la base de datos y la tabla de SQL Server  
  
#### <a name="to-create-the-database-and-table"></a>Para crear la base de datos y la tabla  
  
1.  Abra SQL Server Management Studio y conéctese como administrador.  
  
2.  Haga clic en el **bases de datos** nodo y haga clic en **nueva base de datos**. Especifique el nombre de la base de datos como `Orders` y especificar otros detalles para crear una nueva base de datos.  
  
3.  Abra un editor de consultas y ejecute la consulta siguiente para crear un **OrderDetails** tabla el **pedidos** base de datos:  
  
    ```  
    USE [Orders]  
    GO  
    /****** Object:  Table [dbo].[OrderDetails]    Script Date: 07-12-2012 22:15:47 ******/  
    SET ANSI_NULLS ON  
    GO  
    SET QUOTED_IDENTIFIER ON  
    GO  
    SET ANSI_PADDING ON  
    GO  
    CREATE TABLE [dbo].[OrderDetails]([ID] [int] IDENTITY(1,1) NOT NULL,  
    [TITLE] [varchar](200) NULL,  
    [ProductName] [varchar](200) NULL,  
    [Quantity] [float] NULL,  
    [Amount] [float] NULL,  
    PRIMARY KEY CLUSTERED   
    (  
    [ID] ASC  
    )WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]  
    GO  
    SET ANSI_PADDING OFF  
    GO  
    ```  
  
## <a name="create-schema-for-insert-operation-on-orderdetails-table"></a>Crear un esquema para la operación de inserción en la tabla OrderDetails  
 Instalar [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] proporciona un [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] que se puede utilizar dentro de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proyecto para generar el esquema para la operación de inserción en el **OrderDetails** tabla. Esta sección proporciona los pasos que deben seguirse para crear el esquema del mensaje.  
  
#### <a name="to-create-the-schema-for-insert-operation"></a>Para crear el esquema para la operación de inserción  
  
1.  Haga clic en el **BtsSalesforceIntegration** , seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**. En el **agregar elementos generados** cuadro de diálogo, haga clic en **Consume Adapter Service**y, a continuación, haga clic en **agregar**.  
  
2.  En el [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)], en el, seleccione una lista desplegable de enlace, haga clic en **sqlBinding**y, a continuación, haga clic en **configurar**.  
  
3.  En el **configurar el adaptador** cuadro de diálogo **seguridad** ficha, para **tipo de credencial de cliente**, seleccione **Windows** usar ventanas autenticación para conectarse a la base de datos de SQL Server.  
  
4.  En el **configurar el adaptador de** cuadro de diálogo **propiedades de URI** ficha, para **Initial Catalog** especifique el nombre de base de datos (Orders) al que conectarse. Para **Server** especificar el nombre del equipo donde está instalado SQL Server que se va a conectar. Si la base de datos de SQL Server se encuentra en el mismo equipo que el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proyecto, puede poner solo un punto (**.**). Haga clic en **Aceptar**.  
  
5.  En el [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] haga clic en **conectar**. Una vez establecida la conexión, seleccione el tipo de contrato **Client (Outbound operations)**. En el **seleccione una categoría de** , expanda **tablas**, haga clic en **OrderDetails** de tabla y, en el panel derecho, haga clic en **insertar** y, a continuación, haga clic en **Agregar**.  
  
6.  Especifique un **prefijo de nombre de archivo** si desea que los esquemas generados con un identificador de prefijo. Para este tutorial, especifique el prefijo como **InsertOrders** y, a continuación, haga clic en **Aceptar**.  
  
     Se agrega un grupo de esquemas al proyecto. El esquema que se va a utilizar para insertar mensajes en el **OrderDetails** tabla es **InsertOrdersTableOperation.dbo.OrderDetails.xsd**.  
  
## <a name="map-salesforce-response-and-insert-schemas"></a>Asignar una respuesta de Salesforce y esquemas de inserción  
 Ahora que tenemos ambos esquemas (respuesta de Salesforce e inserción en **OrderDetails**), debemos asignar el esquema de respuesta de Salesforce en el esquema de inserción para **OrderDetails** para que el mensaje de respuesta de Salesforce se pueden insertar en la tabla de base de datos de SQL Server.  
  
#### <a name="to-map-the-schemas"></a>Para asignar los esquemas  
  
1.  Haga clic en el **BtsSalesforceIntegration** , seleccione **agregar**, haga clic en **nuevo elemento**y, a continuación, haga clic en **mapa**. Especifique el nombre de asignación `QueryResult_Orders.btm` y, a continuación, haga clic en **agregar**.  
  
2.  En la superficie del mapa, para el esquema de origen, seleccione **QueryResult** y para el esquema de destino, seleccione **InsertOrdersTableOperation.dbo.OrderDetails.xsd** y, a continuación, dentro de ese, la  **Insertar** nodo.  
  
3.  Asigne los dos esquemas como se muestra en la siguiente captura de pantalla:  
  
     ![Asignar la respuesta de Salesforce al esquema de inserción](../core/media/bts-sf-map-response-insert.jpg "BTS_SF_Map_Response_Insert")  
  
     Tenga en cuenta que el mapa utiliza un **bucle** functoid entre el **registros** y **OrderDetails** vínculo. Esto garantiza que uno o más de uno nodos dentro de **registros** se asignan a apariciones similar de nodos que hay bajo la **OrderDetails**.  
  
4.  Guarde los cambios de la asignación.  
  
## <a name="update-the-orchestration-to-insert-messages-into-sql-server"></a>Actualizar la orquestación para insertar mensajes en SQL Server  
 En esta sección, usaremos la asignación de la orquestación para transformar el mensaje de respuesta de Salesforce en un mensaje para insertar detalles de pedidos en una tabla de SQL Server. Agregaremos también un puerto para enviar el mensaje a SQL Server.  
  
#### <a name="to-update-the-orchestration"></a>Para actualizar la orquestación  
  
1.  Cree una variable de mensaje para el esquema de inserción. Desde la Vista orquestación, haga clic en el **mensajes** nodo y, a continuación, haga clic en **nuevo mensaje**. Establece el nombre del mensaje como **InsertOrders** y tipo de mensaje **BtsSalesforceIntegration.InsertOrdersTableOperation_dbo_OrderDetails.Insert**.  
  
2.  Agregar una forma construir mensaje después de la **ReceiveQueryResult** forma. Establecer el nombre de la forma en `ConstructOrders` y establezca el **mensajes construidos** propiedad **InsertOrders**.  
  
3.  En el **ConstructOrders** forma, agregue un **transformar** forma. Haga doble clic en la forma Transformar para abrir el cuadro de diálogo Configuración de Transformación. En el cuadro de diálogo, seleccione la **mapa existente** opción y, a continuación, en la lista desplegable seleccione **BtsSalesforceIntegration.QueryResult_Orders**. Establecer **origen** a **QueryResultMsg**, **destino** a **InsertOrders**y, a continuación, haga clic en **Aceptar**.  
  
4.  Después de la **ConstructOrders** forma, agregue una forma de envío. Nombre de la forma `SendOrders` y establezca el tipo de mensaje **InsertOrders**.  
  
5.  Agregue un puerto para insertar los detalles de pedidos en Salesforce. En el Asistente para configuración de puertos, seleccione las siguientes opciones:  
  
    -   Especifique el nombre de puerto `SendToSQL`.  
  
    -   Seleccione la opción Crear un nuevo tipo de puerto.  
  
    -   Establecer **patrón de comunicación** a *unidireccional*.  
  
    -   Establecer **dirección de puerto de comunicación** a *siempre enviaré los mensajes en este puerto* y establecer **enlace de puerto** a *especificar más tarde*.  
  
     Conectar el **solicitar** operación del puerto a la **SendOrders** forma para completar la orquestación de envío. La siguiente captura de pantalla muestra la orquestación completa, de un extremo a otro.  
  
     ![Orchesration completa para la integración de Salesforce](../core/media/bts-sf-complete-orch.jpg "BTS_SF_Complete_Orch")  
  
     Agregue un archivo de clave de nombre seguro al proyecto y guarde los cambios del proyecto.  
  
 Con los pasos de este tema, hemos completado la orquestación para recibir una notificación de oportunidad de Salesforce, consultar a Salesforce para obtener más detalles de la oportunidad e insertar después la respuesta de la consulta en una base de datos de SQL Server. En los temas siguientes, crearemos otros componentes clave de la solución que se usan para autenticarse en Salesforce y procesar la respuesta de Salesforce en BizTalk Server.  
  
## <a name="see-also"></a>Vea también  
 [Paso 3: Crear la solución de BizTalk Server en Visual Studio](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)