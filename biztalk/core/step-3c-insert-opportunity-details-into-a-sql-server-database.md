---
title: 'Paso 3c: Insertar detalles de oportunidades en una base de datos SQL Server | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f6f9bbe-6f25-4393-8f92-aeeba9736acf
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33d0055c05e0c9af9f4dddc4a7275c01ff49d779
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22280092"
---
# <a name="step-3c-insert-opportunity-details-into-a-sql-server-database"></a><span data-ttu-id="f1bff-102">Paso 3c: Insertar detalles de oportunidades en una base de datos SQL Server</span><span class="sxs-lookup"><span data-stu-id="f1bff-102">Step 3c: Insert Opportunity Details into a SQL Server Database</span></span>
<span data-ttu-id="f1bff-103">Hasta ahora, hemos compilado la orquestación para enviar una consulta a Salesforce y recibir una respuesta.</span><span class="sxs-lookup"><span data-stu-id="f1bff-103">By now we have built the orchestration to send a query to Salesforce and receive a response.</span></span> <span data-ttu-id="f1bff-104">En esta sección, actualizaremos esa orquestación para insertar la respuesta de Salesforce en una **OrderDetails** tabla en una base de datos de SQL Server local, **pedidos**.</span><span class="sxs-lookup"><span data-stu-id="f1bff-104">In this section, we’ll update that orchestration to insert the response from Salesforce into an **OrderDetails** table in an on-premise SQL Server database, **Orders**.</span></span> <span data-ttu-id="f1bff-105">Para lograrlo, realizaremos los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="f1bff-105">To achieve this, we’ll perform the following broad set of steps:</span></span>  
  
-   <span data-ttu-id="f1bff-106">Crear un **OrderDetails** de tabla en una **pedidos** base de datos en una base de datos de SQL Server local.</span><span class="sxs-lookup"><span data-stu-id="f1bff-106">Create an **OrderDetails** table in an **Orders** database in an on-premise SQL Server database.</span></span>  
  
-   <span data-ttu-id="f1bff-107">Use la [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] disponibles con [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] para generar el esquema para la operación de inserción en el **OrderDetails** tabla.</span><span class="sxs-lookup"><span data-stu-id="f1bff-107">Use the [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] available with [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] to generate the schema for the Insert operation on the **OrderDetails** table.</span></span>  
  
-   <span data-ttu-id="f1bff-108">Crear una asignación para transformar el mensaje de respuesta de Salesforce al mensaje para insertar en **OrderDetails** tabla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f1bff-108">Create a map to transform the Salesforce response message to the message for inserting into **OrderDetails** table in SQL Server.</span></span>  
  
-   <span data-ttu-id="f1bff-109">Actualizar la orquestación para usar la transformación para insertar el mensaje de respuesta en el **OrderDetails** tabla.</span><span class="sxs-lookup"><span data-stu-id="f1bff-109">Update the orchestration to use the transform to insert the response message into the **OrderDetails** table.</span></span>  
  
## <a name="create-sql-server-database-and-table"></a><span data-ttu-id="f1bff-110">Crear la base de datos y la tabla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f1bff-110">Create SQL Server Database and Table</span></span>  
  
#### <a name="to-create-the-database-and-table"></a><span data-ttu-id="f1bff-111">Para crear la base de datos y la tabla</span><span class="sxs-lookup"><span data-stu-id="f1bff-111">To create the database and table</span></span>  
  
1.  <span data-ttu-id="f1bff-112">Abra SQL Server Management Studio y conéctese como administrador.</span><span class="sxs-lookup"><span data-stu-id="f1bff-112">Open SQL Server Management Studio and connect as an administrator.</span></span>  
  
2.  <span data-ttu-id="f1bff-113">Haga clic en el **bases de datos** nodo y haga clic en **nueva base de datos**.</span><span class="sxs-lookup"><span data-stu-id="f1bff-113">Right-click the **Databases** node and click **New Database**.</span></span> <span data-ttu-id="f1bff-114">Especifique el nombre de la base de datos como `Orders` y especificar otros detalles para crear una nueva base de datos.</span><span class="sxs-lookup"><span data-stu-id="f1bff-114">Specify the database name as `Orders` and specify other details to create a new database.</span></span>  
  
3.  <span data-ttu-id="f1bff-115">Abra un editor de consultas y ejecute la consulta siguiente para crear un **OrderDetails** tabla el **pedidos** base de datos:</span><span class="sxs-lookup"><span data-stu-id="f1bff-115">Open a query editor and run the following query to create an **OrderDetails** table in the **Orders** database:</span></span>  
  
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
  
## <a name="create-schema-for-insert-operation-on-orderdetails-table"></a><span data-ttu-id="f1bff-116">Crear un esquema para la operación de inserción en la tabla OrderDetails</span><span class="sxs-lookup"><span data-stu-id="f1bff-116">Create Schema for Insert Operation on OrderDetails Table</span></span>  
 <span data-ttu-id="f1bff-117">Instalar [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] proporciona un [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] que se puede utilizar dentro de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proyecto para generar el esquema para la operación de inserción en el **OrderDetails** tabla.</span><span class="sxs-lookup"><span data-stu-id="f1bff-117">Installing [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] provides a [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] that can be used within a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project to generate the schema for the Insert operation on the **OrderDetails** table.</span></span> <span data-ttu-id="f1bff-118">Esta sección proporciona los pasos que deben seguirse para crear el esquema del mensaje.</span><span class="sxs-lookup"><span data-stu-id="f1bff-118">This section provides steps to follow to create the message schema.</span></span>  
  
#### <a name="to-create-the-schema-for-insert-operation"></a><span data-ttu-id="f1bff-119">Para crear el esquema para la operación de inserción</span><span class="sxs-lookup"><span data-stu-id="f1bff-119">To create the schema for Insert operation</span></span>  
  
1.  <span data-ttu-id="f1bff-120">Haga clic en el **BtsSalesforceIntegration** , seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="f1bff-120">Right-click the **BtsSalesforceIntegration** project, point to **Add**, and then click **Add Generated Items**.</span></span> <span data-ttu-id="f1bff-121">En el **agregar elementos generados** cuadro de diálogo, haga clic en **Consume Adapter Service**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="f1bff-121">In the **Add Generated Items** dialog box, click **Consume Adapter Service**, and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="f1bff-122">En el [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)], en el, seleccione una lista desplegable de enlace, haga clic en **sqlBinding**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="f1bff-122">In the [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)], from the Select a binding drop-down, click **sqlBinding**, and then click **Configure**.</span></span>  
  
3.  <span data-ttu-id="f1bff-123">En el **configurar el adaptador** cuadro de diálogo **seguridad** ficha, para **tipo de credencial de cliente**, seleccione **Windows** usar ventanas autenticación para conectarse a la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f1bff-123">In the **Configure Adapter** dialog box, under **Security** tab, for **Client credential type**, select **Windows** to use Windows authentication to connect to SQL Server database.</span></span>  
  
4.  <span data-ttu-id="f1bff-124">En el **configurar el adaptador de** cuadro de diálogo **propiedades de URI** ficha, para **Initial Catalog** especifique el nombre de base de datos (Orders) al que conectarse.</span><span class="sxs-lookup"><span data-stu-id="f1bff-124">In the **Configure Adapter** dialog box, under **URI Properties** tab, for **Initial Catalog** specify the database name (Orders) to connect to.</span></span> <span data-ttu-id="f1bff-125">Para **Server** especificar el nombre del equipo donde está instalado SQL Server que se va a conectar.</span><span class="sxs-lookup"><span data-stu-id="f1bff-125">For **Server** specify the computer name where SQL Server you are connecting to is installed.</span></span> <span data-ttu-id="f1bff-126">Si la base de datos de SQL Server se encuentra en el mismo equipo que el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proyecto, puede poner solo un punto (**.**).</span><span class="sxs-lookup"><span data-stu-id="f1bff-126">If the SQL Server database is on the same computer as the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project, you can just put a period (**.**).</span></span> <span data-ttu-id="f1bff-127">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f1bff-127">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="f1bff-128">En el [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] haga clic en **conectar**.</span><span class="sxs-lookup"><span data-stu-id="f1bff-128">In the [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] click **Connect**.</span></span> <span data-ttu-id="f1bff-129">Una vez establecida la conexión, seleccione el tipo de contrato **Client (Outbound operations)**.</span><span class="sxs-lookup"><span data-stu-id="f1bff-129">After the connection is established, select the contract type as **Client(Outbound operations)**.</span></span> <span data-ttu-id="f1bff-130">En el **seleccione una categoría de** , expanda **tablas**, haga clic en **OrderDetails** de tabla y, en el panel derecho, haga clic en **insertar** y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f1bff-130">Under the **Select a category** box, expand **Tables**, click **OrderDetails** table, and in the right pane click **Insert** and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="f1bff-131">Especifique un **prefijo de nombre de archivo** si desea que los esquemas generados con un identificador de prefijo.</span><span class="sxs-lookup"><span data-stu-id="f1bff-131">Specify a **Filename Prefix** if you want to prefix the generated schemas with an identifier.</span></span> <span data-ttu-id="f1bff-132">Para este tutorial, especifique el prefijo como **InsertOrders** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f1bff-132">For this tutorial, let’s specify the prefix as **InsertOrders** and then click **OK**.</span></span>  
  
     <span data-ttu-id="f1bff-133">Se agrega un grupo de esquemas al proyecto.</span><span class="sxs-lookup"><span data-stu-id="f1bff-133">A bunch of schemas are added to the project.</span></span> <span data-ttu-id="f1bff-134">El esquema que se va a utilizar para insertar mensajes en el **OrderDetails** tabla es **InsertOrdersTableOperation.dbo.OrderDetails.xsd**.</span><span class="sxs-lookup"><span data-stu-id="f1bff-134">The schema that we’ll use for inserting messages into the **OrderDetails** table is **InsertOrdersTableOperation.dbo.OrderDetails.xsd**.</span></span>  
  
## <a name="map-salesforce-response-and-insert-schemas"></a><span data-ttu-id="f1bff-135">Asignar una respuesta de Salesforce y esquemas de inserción</span><span class="sxs-lookup"><span data-stu-id="f1bff-135">Map Salesforce Response and Insert Schemas</span></span>  
 <span data-ttu-id="f1bff-136">Ahora que tenemos ambos esquemas (respuesta de Salesforce e inserción en **OrderDetails**), debemos asignar el esquema de respuesta de Salesforce en el esquema de inserción para **OrderDetails** para que el mensaje de respuesta de Salesforce se pueden insertar en la tabla de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f1bff-136">Now that we have both the schemas (response from Salesforce and inserting into **OrderDetails**), we must map the response schema from Salesforce into the insert schema for **OrderDetails** so that the response message from Salesforce can be inserted in the SQL Server database table.</span></span>  
  
#### <a name="to-map-the-schemas"></a><span data-ttu-id="f1bff-137">Para asignar los esquemas</span><span class="sxs-lookup"><span data-stu-id="f1bff-137">To map the schemas</span></span>  
  
1.  <span data-ttu-id="f1bff-138">Haga clic en el **BtsSalesforceIntegration** , seleccione **agregar**, haga clic en **nuevo elemento**y, a continuación, haga clic en **mapa**.</span><span class="sxs-lookup"><span data-stu-id="f1bff-138">Right-click the **BtsSalesforceIntegration** project, point to **Add**, click **New Item**, and then click **Map**.</span></span> <span data-ttu-id="f1bff-139">Especifique el nombre de asignación `QueryResult_Orders.btm` y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="f1bff-139">Specify the map name as `QueryResult_Orders.btm` and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="f1bff-140">En la superficie del mapa, para el esquema de origen, seleccione **QueryResult** y para el esquema de destino, seleccione **InsertOrdersTableOperation.dbo.OrderDetails.xsd** y, a continuación, dentro de ese, la  **Insertar** nodo.</span><span class="sxs-lookup"><span data-stu-id="f1bff-140">On the map surface, for the source schema, select **QueryResult** and for the destination schema, select **InsertOrdersTableOperation.dbo.OrderDetails.xsd** and then within that, the **Insert** node.</span></span>  
  
3.  <span data-ttu-id="f1bff-141">Asigne los dos esquemas como se muestra en la siguiente captura de pantalla:</span><span class="sxs-lookup"><span data-stu-id="f1bff-141">Map the two schemas as shown in the following screenshot:</span></span>  
  
     <span data-ttu-id="f1bff-142">![Asignar la respuesta de Salesforce al esquema de inserción](../core/media/bts-sf-map-response-insert.jpg "BTS_SF_Map_Response_Insert")</span><span class="sxs-lookup"><span data-stu-id="f1bff-142">![Map Salesforce response to Insert schema](../core/media/bts-sf-map-response-insert.jpg "BTS_SF_Map_Response_Insert")</span></span>  
  
     <span data-ttu-id="f1bff-143">Tenga en cuenta que el mapa utiliza un **bucle** functoid entre el **registros** y **OrderDetails** vínculo.</span><span class="sxs-lookup"><span data-stu-id="f1bff-143">Notice that the map uses a **Looping** functoid between the **records** and the **OrderDetails** link.</span></span> <span data-ttu-id="f1bff-144">Esto garantiza que uno o más de uno nodos dentro de **registros** se asignan a apariciones similar de nodos que hay bajo la **OrderDetails**.</span><span class="sxs-lookup"><span data-stu-id="f1bff-144">This ensures that all one or more than one occurrences of nodes under **records** are mapped to similar occurrences of nodes under the **OrderDetails**.</span></span>  
  
4.  <span data-ttu-id="f1bff-145">Guarde los cambios de la asignación.</span><span class="sxs-lookup"><span data-stu-id="f1bff-145">Save changes to the map.</span></span>  
  
## <a name="update-the-orchestration-to-insert-messages-into-sql-server"></a><span data-ttu-id="f1bff-146">Actualizar la orquestación para insertar mensajes en SQL Server</span><span class="sxs-lookup"><span data-stu-id="f1bff-146">Update the Orchestration to Insert Messages into SQL Server</span></span>  
 <span data-ttu-id="f1bff-147">En esta sección, usaremos la asignación de la orquestación para transformar el mensaje de respuesta de Salesforce en un mensaje para insertar detalles de pedidos en una tabla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f1bff-147">In this section, we’ll use the map in the orchestration to transform the Salesforce response message into a message for inserting order details in a SQL Server table.</span></span> <span data-ttu-id="f1bff-148">Agregaremos también un puerto para enviar el mensaje a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f1bff-148">We’ll also add a port to send that message to SQL Server.</span></span>  
  
#### <a name="to-update-the-orchestration"></a><span data-ttu-id="f1bff-149">Para actualizar la orquestación</span><span class="sxs-lookup"><span data-stu-id="f1bff-149">To update the orchestration</span></span>  
  
1.  <span data-ttu-id="f1bff-150">Cree una variable de mensaje para el esquema de inserción.</span><span class="sxs-lookup"><span data-stu-id="f1bff-150">Create a message variable for the insert schema.</span></span> <span data-ttu-id="f1bff-151">Desde la Vista orquestación, haga clic en el **mensajes** nodo y, a continuación, haga clic en **nuevo mensaje**.</span><span class="sxs-lookup"><span data-stu-id="f1bff-151">From the orchestration view, right-click the **Messages** node, and then click **New Message**.</span></span> <span data-ttu-id="f1bff-152">Establece el nombre del mensaje como **InsertOrders** y tipo de mensaje **BtsSalesforceIntegration.InsertOrdersTableOperation_dbo_OrderDetails.Insert**.</span><span class="sxs-lookup"><span data-stu-id="f1bff-152">Set the message name as **InsertOrders** and message type as **BtsSalesforceIntegration.InsertOrdersTableOperation_dbo_OrderDetails.Insert**.</span></span>  
  
2.  <span data-ttu-id="f1bff-153">Agregar una forma construir mensaje después de la **ReceiveQueryResult** forma.</span><span class="sxs-lookup"><span data-stu-id="f1bff-153">Add a Construct Message shape after the **ReceiveQueryResult** shape.</span></span> <span data-ttu-id="f1bff-154">Establecer el nombre de la forma en `ConstructOrders` y establezca el **mensajes construidos** propiedad **InsertOrders**.</span><span class="sxs-lookup"><span data-stu-id="f1bff-154">Set the name of the shape to `ConstructOrders` and set the **Messages Constructed** property to **InsertOrders**.</span></span>  
  
3.  <span data-ttu-id="f1bff-155">En el **ConstructOrders** forma, agregue un **transformar** forma.</span><span class="sxs-lookup"><span data-stu-id="f1bff-155">Within the **ConstructOrders** shape, add a **Transform** shape.</span></span> <span data-ttu-id="f1bff-156">Haga doble clic en la forma Transformar para abrir el cuadro de diálogo Configuración de Transformación.</span><span class="sxs-lookup"><span data-stu-id="f1bff-156">Double-click the Transform shape to open the Transform Configuration dialog box.</span></span> <span data-ttu-id="f1bff-157">En el cuadro de diálogo, seleccione la **mapa existente** opción y, a continuación, en la lista desplegable seleccione **BtsSalesforceIntegration.QueryResult_Orders**.</span><span class="sxs-lookup"><span data-stu-id="f1bff-157">In the dialog box, select the **Existing Map** option, and then from the drop-down select **BtsSalesforceIntegration.QueryResult_Orders**.</span></span> <span data-ttu-id="f1bff-158">Establecer **origen** a **QueryResultMsg**, **destino** a **InsertOrders**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f1bff-158">Set **Source** to **QueryResultMsg**, **Destination** to **InsertOrders**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="f1bff-159">Después de la **ConstructOrders** forma, agregue una forma de envío.</span><span class="sxs-lookup"><span data-stu-id="f1bff-159">After the **ConstructOrders** shape, add a Send shape.</span></span> <span data-ttu-id="f1bff-160">Nombre de la forma `SendOrders` y establezca el tipo de mensaje **InsertOrders**.</span><span class="sxs-lookup"><span data-stu-id="f1bff-160">Name the shape `SendOrders` and set the message type as **InsertOrders**.</span></span>  
  
5.  <span data-ttu-id="f1bff-161">Agregue un puerto para insertar los detalles de pedidos en Salesforce.</span><span class="sxs-lookup"><span data-stu-id="f1bff-161">Add a port to insert order details into Salesforce.</span></span> <span data-ttu-id="f1bff-162">En el Asistente para configuración de puertos, seleccione las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f1bff-162">In the Port Configuration wizard, select the following options:</span></span>  
  
    -   <span data-ttu-id="f1bff-163">Especifique el nombre de puerto `SendToSQL`.</span><span class="sxs-lookup"><span data-stu-id="f1bff-163">Specify the port name as `SendToSQL`.</span></span>  
  
    -   <span data-ttu-id="f1bff-164">Seleccione la opción Crear un nuevo tipo de puerto.</span><span class="sxs-lookup"><span data-stu-id="f1bff-164">Select the option to create a new port type.</span></span>  
  
    -   <span data-ttu-id="f1bff-165">Establecer **patrón de comunicación** a *unidireccional*.</span><span class="sxs-lookup"><span data-stu-id="f1bff-165">Set **Communication Pattern** to *One-Way*.</span></span>  
  
    -   <span data-ttu-id="f1bff-166">Establecer **dirección de puerto de comunicación** a *siempre enviaré los mensajes en este puerto* y establecer **enlace de puerto** a *especificar más tarde*.</span><span class="sxs-lookup"><span data-stu-id="f1bff-166">Set **Port direction of communication** to *I’ll always be sending messages on this port* and set **Port binding** to *Specify later*.</span></span>  
  
     <span data-ttu-id="f1bff-167">Conectar el **solicitar** operación del puerto a la **SendOrders** forma para completar la orquestación de envío.</span><span class="sxs-lookup"><span data-stu-id="f1bff-167">Connect the **Request** operation of port to the **SendOrders** Send shape to complete the orchestration.</span></span> <span data-ttu-id="f1bff-168">La siguiente captura de pantalla muestra la orquestación completa, de un extremo a otro.</span><span class="sxs-lookup"><span data-stu-id="f1bff-168">The following screenshot depicts the completed orchestration, end-to-end.</span></span>  
  
     <span data-ttu-id="f1bff-169">![Orchesration completa para la integración de Salesforce](../core/media/bts-sf-complete-orch.jpg "BTS_SF_Complete_Orch")</span><span class="sxs-lookup"><span data-stu-id="f1bff-169">![Complete orchesration for Salesforce integration](../core/media/bts-sf-complete-orch.jpg "BTS_SF_Complete_Orch")</span></span>  
  
     <span data-ttu-id="f1bff-170">Agregue un archivo de clave de nombre seguro al proyecto y guarde los cambios del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f1bff-170">Add a strong name key file to the project and save changes to the project.</span></span>  
  
 <span data-ttu-id="f1bff-171">Con los pasos de este tema, hemos completado la orquestación para recibir una notificación de oportunidad de Salesforce, consultar a Salesforce para obtener más detalles de la oportunidad e insertar después la respuesta de la consulta en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f1bff-171">With the steps in this topic, we have completed the orchestration, to receive an opportunity notification from Salesforce, query Salesforce for more details about the opportunity, and then insert the query response into a SQL Server database.</span></span> <span data-ttu-id="f1bff-172">En los temas siguientes, crearemos otros componentes clave de la solución que se usan para autenticarse en Salesforce y procesar la respuesta de Salesforce en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f1bff-172">In the subsequent topics, we’ll build some other key components of the solution that are used to authenticate with Salesforce and process Salesforce response within BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1bff-173">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1bff-173">See Also</span></span>  
 [<span data-ttu-id="f1bff-174">Paso 3: Crear la solución de BizTalk Server en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f1bff-174">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)