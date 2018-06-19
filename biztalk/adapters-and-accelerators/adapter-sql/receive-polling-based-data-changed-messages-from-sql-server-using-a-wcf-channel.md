---
title: Recibir mensajes de cambio de datos basado en sondeo de SQL Server mediante el modelo de canal de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0f4af71-fb0c-433d-ba74-48ee6487eb1a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb785631d6fe00ea68f57f943dca11ebd1a84b1d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226396"
---
# <a name="receive-polling-based-data-changed-messages-from-sql-server-by-using-the-wcf-channel-model"></a><span data-ttu-id="ce6e2-102">Recibir mensajes de cambio de datos basado en sondeo de SQL Server mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="ce6e2-102">Receive Polling-based Data-changed Messages from SQL Server by Using the WCF Channel Model</span></span>
<span data-ttu-id="ce6e2-103">Puede configurar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir mensajes de cambio de datos periódicos para SQL Server tablas o vistas.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-103">You can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive periodic data-change messages for SQL Server tables or views.</span></span> <span data-ttu-id="ce6e2-104">Puede especificar una instrucción de sondeo que el adaptador se ejecuta para sondear la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-104">You can specify a polling statement that the adapter executes to poll the database.</span></span> <span data-ttu-id="ce6e2-105">La instrucción de sondeo puede ser una instrucción SELECT o un procedimiento almacenado que devuelve un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-105">The polling statement can be a SELECT statement or a stored procedure that returns a result set.</span></span>  
  
 <span data-ttu-id="ce6e2-106">Para obtener más información sobre cómo el adaptador admite el sondeo, consulte [compatibilidad con entrada de sondeo utilizando llamadas](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span><span class="sxs-lookup"><span data-stu-id="ce6e2-106">For more information on how the adapter supports polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ce6e2-107">Si desea tener más de un sondeo operación en una sola aplicación, debe especificar un **InboundID** propiedad de conexión como parte de la conexión de URI para que sea único.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-107">If you want to have more than one polling operation in a single application, you must specify an **InboundID** connection property as part of the connection URI to make it unique.</span></span> <span data-ttu-id="ce6e2-108">Especifica el identificador de entrada se agrega al espacio de nombres de operación para hacerlo único.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-108">The inbound ID you specify is added to the operation namespace to make it unique.</span></span>  
  
## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="ce6e2-109">Cómo este tema muestra el sondeo</span><span class="sxs-lookup"><span data-stu-id="ce6e2-109">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="ce6e2-110">En este tema, para demostrar cómo [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] admite la recepción de datos de los mensajes de cambio, cree una aplicación .NET para la **sondeo** operación.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-110">In this topic, to demonstrate how the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports receiving data change messages, create a .NET application for the **Polling** operation.</span></span> <span data-ttu-id="ce6e2-111">En este tema, especificar el **PolledDataAvailableStatement** como:</span><span class="sxs-lookup"><span data-stu-id="ce6e2-111">For this topic, specify the **PolledDataAvailableStatement** as:</span></span>  
  
```  
SELECT COUNT(*) FROM Employee  
```  
  
 <span data-ttu-id="ce6e2-112">El **PolledDataAvailableStatement** debe devolver un conjunto de resultados con la primera celda que contiene un valor positivo.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-112">The **PolledDataAvailableStatement** must return a result set with the first cell containing a positive value.</span></span> <span data-ttu-id="ce6e2-113">Si la primera celda no contiene un valor positivo, el adaptador no ejecuta la instrucción de sondeo.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-113">If the first cell does not contain a positive value, the adapter does not execute the polling statement.</span></span>  
  
 <span data-ttu-id="ce6e2-114">Como parte de la instrucción de sondeo, realice las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="ce6e2-114">As part of the polling statement, perform the following operations:</span></span>  
  
1.  <span data-ttu-id="ce6e2-115">Seleccione todas las filas de la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-115">Select all the rows from the Employee table.</span></span>  
  
2.  <span data-ttu-id="ce6e2-116">Ejecutar un procedimiento almacenado (MOVE_EMP_DATA) para mover todos los registros de la tabla de empleados a una tabla HistorialEmpleados.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-116">Execute a stored procedure (MOVE_EMP_DATA) to move all the records from the Employee table to an EmployeeHistory table.</span></span>  
  
3.  <span data-ttu-id="ce6e2-117">Ejecutar un procedimiento almacenado (ADD_EMP_DETAILS) para agregar un nuevo registro a la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-117">Execute a stored procedure (ADD_EMP_DETAILS) to add a new record to the Employee table.</span></span> <span data-ttu-id="ce6e2-118">Este procedimiento toma el nombre de empleado, designación y salario como parámetros.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-118">This procedure takes the employee name, designation, and salary as parameters.</span></span>  
  
 <span data-ttu-id="ce6e2-119">Para llevar a cabo estas operaciones, debe especificar lo siguiente para el **PollingStatement** propiedad de enlace:</span><span class="sxs-lookup"><span data-stu-id="ce6e2-119">To perform these operations, you must specify the following for the **PollingStatement** binding property:</span></span>  
  
```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  
  
 <span data-ttu-id="ce6e2-120">Después de ejecuta la instrucción de sondeo, se seleccionan todos los registros de la tabla de empleados y se recibe el mensaje de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-120">After the polling statement is executed, all the records from the Employee table are selected and the message from SQL Server is received.</span></span> <span data-ttu-id="ce6e2-121">Una vez que se ejecuta el procedimiento almacenado de MOVE_EMP_DATA por el adaptador, todos los registros se mueven a la tabla HistorialEmpleados.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-121">Once the MOVE_EMP_DATA stored procedure is executed by the adapter, all the records are moved to the EmployeeHistory table.</span></span> <span data-ttu-id="ce6e2-122">A continuación, se ejecuta el procedimiento almacenado de ADD_EMP_DETAILS para agregar un nuevo registro a la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-122">Then, the ADD_EMP_DETAILS stored procedure is executed to add a new record to the Employee table.</span></span> <span data-ttu-id="ce6e2-123">La siguiente ejecución de sondeo solo devolverá un único registro.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-123">The next polling execution will only return a single record.</span></span> <span data-ttu-id="ce6e2-124">Este ciclo continúa hasta que se cierra el agente de escucha de canal.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-124">This cycle continues until you close the channel listener.</span></span>  
  
## <a name="configuring-a-polling-query-with-the-sql-adapter-binding-properties"></a><span data-ttu-id="ce6e2-125">Configuración de una consulta de sondeo con el adaptador de SQL propiedades de enlace</span><span class="sxs-lookup"><span data-stu-id="ce6e2-125">Configuring a Polling Query with the SQL Adapter Binding Properties</span></span>  
 <span data-ttu-id="ce6e2-126">La siguiente tabla resume el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] propiedades de enlace que se utiliza para configurar el adaptador para recibir mensajes de cambio de datos.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-126">The following table summarizes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding properties that you use to configure the adapter to receive data-change messages.</span></span> <span data-ttu-id="ce6e2-127">Debe especificar estas propiedades de enlace como parte de la aplicación .NET para el sondeo.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-127">You must specify these binding properties as part of the .NET application for polling.</span></span>  
  
|<span data-ttu-id="ce6e2-128">Propiedad de enlace</span><span class="sxs-lookup"><span data-stu-id="ce6e2-128">Binding Property</span></span>|<span data-ttu-id="ce6e2-129">Description</span><span class="sxs-lookup"><span data-stu-id="ce6e2-129">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="ce6e2-130">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="ce6e2-130">**InboundOperationType**</span></span>|<span data-ttu-id="ce6e2-131">Especifica si desea realizar **sondeo**, **TypedPolling**, o **notificación** operación entrante.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-131">Specifies whether you want to perform **Polling**, **TypedPolling**, or **Notification** inbound operation.</span></span> <span data-ttu-id="ce6e2-132">Valor predeterminado es **sondeo**.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-132">Default is **Polling**.</span></span>|  
|<span data-ttu-id="ce6e2-133">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="ce6e2-133">**PolledDataAvailableStatement**</span></span>|<span data-ttu-id="ce6e2-134">Especifica la instrucción SQL que se ejecuta el adaptador para determinar si los datos están disponibles para el sondeo.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-134">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="ce6e2-135">La instrucción SQL debe devolver un conjunto que consta de filas y columnas de resultados.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-135">The SQL statement must return a result set consisting of rows and columns.</span></span> <span data-ttu-id="ce6e2-136">Solo si una fila está disponible, la instrucción SQL especificada para el **PollingStatement** se va a ejecutar la propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-136">Only if a row is available, the SQL statement specified for the **PollingStatement** binding property will be executed.</span></span>|  
|<span data-ttu-id="ce6e2-137">**PollingIntervalInSeconds**</span><span class="sxs-lookup"><span data-stu-id="ce6e2-137">**PollingIntervalInSeconds**</span></span>|<span data-ttu-id="ce6e2-138">Especifica el intervalo, en segundos, en el que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se ejecuta la instrucción especificada para la **PolledDataAvailableStatement** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-138">Specifies the interval, in seconds, at which the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="ce6e2-139">El valor predeterminado es 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-139">The default is 30 seconds.</span></span> <span data-ttu-id="ce6e2-140">El intervalo de sondeo determina el intervalo de tiempo entre sondeos sucesivos.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-140">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="ce6e2-141">Si la instrucción se ejecuta en el intervalo especificado, el adaptador espera el tiempo restante en el intervalo.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-141">If the statement is executed within the specified interval, the adapter waits for the remaining time in the interval.</span></span>|  
|<span data-ttu-id="ce6e2-142">**PollingStatement**</span><span class="sxs-lookup"><span data-stu-id="ce6e2-142">**PollingStatement**</span></span>|<span data-ttu-id="ce6e2-143">Especifica la instrucción SQL para sondear la tabla de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-143">Specifies the SQL statement to poll the SQL Server database table.</span></span> <span data-ttu-id="ce6e2-144">Puede especificar una instrucción SELECT simple o un procedimiento almacenado para la instrucción de sondeo.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-144">You can specify a simple SELECT statement or a stored procedure for the polling statement.</span></span> <span data-ttu-id="ce6e2-145">El valor predeterminado es null.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-145">The default is null.</span></span> <span data-ttu-id="ce6e2-146">Debe especificar un valor para **PollingStatement** para habilitar el sondeo.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-146">You must specify a value for **PollingStatement** to enable polling.</span></span> <span data-ttu-id="ce6e2-147">Se ejecuta la instrucción de sondeo solo si hay datos disponibles para el sondeo, que viene determinado por la **PolledDataAvailableStatement** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-147">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="ce6e2-148">Puede especificar cualquier número de instrucciones SQL separados por un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-148">You can specify any number of SQL statements separated by a semi-colon.</span></span>|  
|<span data-ttu-id="ce6e2-149">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="ce6e2-149">**PollWhileDataFound**</span></span>|<span data-ttu-id="ce6e2-150">Especifica si el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] pasa por alto el intervalo de sondeo y ejecuta continuamente la instrucción SQL especificada para el **PolledDataAvailableStatement** enlaza la propiedad, si los datos están disponibles en la tabla que se va a sondear.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-150">Specifies whether the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ignores the polling interval and continuously executes the SQL statement specified for the **PolledDataAvailableStatement** binding property, if data is available in the table being polled.</span></span> <span data-ttu-id="ce6e2-151">Si no hay datos disponibles en la tabla, el adaptador vuelve para ejecutar la instrucción SQL en el intervalo de sondeo especificado.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-151">If no data is available in the table, the adapter reverts to execute the SQL statement at the specified polling interval.</span></span> <span data-ttu-id="ce6e2-152">Valor predeterminado es **false**.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-152">Default is **false**.</span></span>|  
  
 <span data-ttu-id="ce6e2-153">Para obtener una descripción más completa de estas propiedades, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="ce6e2-153">For a more complete description of these properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="ce6e2-154">Para obtener una descripción completa de cómo usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para sondear SQL Server, lea el resto de este tema.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-154">For a complete description of how to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to poll SQL Server, read the remainder of this topic.</span></span>  
  
## <a name="consuming-the-polling-request-message"></a><span data-ttu-id="ce6e2-155">Consumir el mensaje de solicitud de sondeo</span><span class="sxs-lookup"><span data-stu-id="ce6e2-155">Consuming the Polling Request Message</span></span>  
 <span data-ttu-id="ce6e2-156">El adaptador invoca el **sondeo** operación en el código para sondear la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-156">The adapter invokes the **Polling** operation on your code to poll the SQL Server database.</span></span> <span data-ttu-id="ce6e2-157">Es decir, el adaptador envía un mensaje de solicitud de sondeo que recibe a través de una forma de canal de IInputChannel.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-157">That is, the adapter sends a Polling request message that you receive over an IInputChannel channel shape.</span></span> <span data-ttu-id="ce6e2-158">El mensaje de solicitud de sondeo contiene el conjunto de resultados de la consulta especificada por la propiedad de enlace de PollingStatement.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-158">The Polling request message contains the result set of the query specified by the PollingStatement binding property.</span></span> <span data-ttu-id="ce6e2-159">Puede utilizar el mensaje de sondeo en uno de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="ce6e2-159">You can consume the Polling message in one of two ways:</span></span>  
  
-   <span data-ttu-id="ce6e2-160">Para consumir el mensaje con el valor del nodo de transmisión por secuencias se debe llamar a la **WriteBodyContents** método en la respuesta del mensaje y lo pasará un **XmlDictionaryWriter** que implementa el valor del nodo de transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-160">To consume the message using node-value streaming you must call the **WriteBodyContents** method on the response message and pass it an **XmlDictionaryWriter** that implements node-value streaming.</span></span>  
  
-   <span data-ttu-id="ce6e2-161">Para consumir el mensaje mediante transmisión por secuencias de nodo que se puede llamar a **GetReaderAtBodyContents** en el mensaje de respuesta para obtener un **XmlReader**.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-161">To consume the message using node streaming you can call **GetReaderAtBodyContents** on the response message to get an **XmlReader**.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="ce6e2-162">Acerca de los ejemplos usados en este tema</span><span class="sxs-lookup"><span data-stu-id="ce6e2-162">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="ce6e2-163">Los ejemplos de este tema sondean la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-163">The examples in this topic poll the Employee table.</span></span> <span data-ttu-id="ce6e2-164">El ejemplo también usa MOVE_EMP_DATA y ADD_EMP_DETAILS procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-164">The example also uses the MOVE_EMP_DATA and ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="ce6e2-165">Una secuencia de comandos para generar estos artefactos se suministra con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-165">A script to generate these artifacts is supplied with the samples.</span></span> <span data-ttu-id="ce6e2-166">Para obtener más información acerca de los ejemplos, vea [ejemplos del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="ce6e2-166">For more information about the samples, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span> <span data-ttu-id="ce6e2-167">Obtener un ejemplo, **Polling_ChannelModel**, que se basa en este tema, también se proporciona con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-167">A sample, **Polling_ChannelModel**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="receiving-inbound-messages-for-polling-operation-using-the-wcf-channel-model"></a><span data-ttu-id="ce6e2-168">Recibir mensajes de entrada para la operación de sondeo con el modelo del canal de WCF</span><span class="sxs-lookup"><span data-stu-id="ce6e2-168">Receiving Inbound Messages for Polling Operation Using the WCF Channel Model</span></span>  
 <span data-ttu-id="ce6e2-169">Esta sección proporciona instrucciones sobre cómo escribir una aplicación de .NET (modelo del canal) para recibir mensajes de sondeo de entrada mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce6e2-169">This section provides instructions on how to write a .NET application (channel model) to receive inbound polling messages using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
#### <a name="to-receive-polling-messages-from-the-sql-adapter"></a><span data-ttu-id="ce6e2-170">Para recibir mensajes de sondeo desde el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="ce6e2-170">To receive polling messages from the SQL adapter</span></span>  
  
1.  <span data-ttu-id="ce6e2-171">Crear un proyecto de Microsoft Visual C# en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce6e2-171">Create a Microsoft Visual C# project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="ce6e2-172">De este tema, cree una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-172">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="ce6e2-173">En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.Sql`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, y `System.Runtime.Serialization`.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-173">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, and `System.Runtime.Serialization`.</span></span>  
  
3.  <span data-ttu-id="ce6e2-174">Abra el archivo Program.cs y agregue los espacios de nombres siguientes:</span><span class="sxs-lookup"><span data-stu-id="ce6e2-174">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.Sql`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Description`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
4.  <span data-ttu-id="ce6e2-175">Especifique un URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-175">Specify a connection URI.</span></span> <span data-ttu-id="ce6e2-176">Para obtener más información acerca de lo URI de conexión del adaptador, vea [crear el URI de conexión de SQL Server](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="ce6e2-176">For more information about the adapter connection URI, see [Create the SQL Server connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
    ```  
    Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
    ```  
  
5.  <span data-ttu-id="ce6e2-177">Cree una instancia de **SqlAdapterBinding** y establezca las propiedades de enlace necesarias para configurar el sondeo.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-177">Create an instance of **SqlAdapterBinding** and set the binding properties required to configure polling.</span></span> <span data-ttu-id="ce6e2-178">Como mínimo debe establecer el **InboundOperationType**, **PolledDataAvailableStatement**, y **PollingStatement** propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-178">At a minimum you must set the **InboundOperationType**, **PolledDataAvailableStatement**, and **PollingStatement** binding properties.</span></span> <span data-ttu-id="ce6e2-179">Para obtener más información sobre el enlace de propiedades que se usan para configurar el sondeo, consulte [compatibilidad con entrada de sondeo utilizando llamadas](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span><span class="sxs-lookup"><span data-stu-id="ce6e2-179">For more information about binding properties used to configure polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  
  
    ```  
    SqlAdapterBinding binding = new SqlAdapterBinding();  
    binding.InboundOperationType = InboundOperation.Polling;  
    binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
    binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
    ```  
  
6.  <span data-ttu-id="ce6e2-180">Crear una colección de parámetros de enlace y establecer las credenciales.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-180">Create a binding parameter collection and set the credentials.</span></span>  
  
    ```  
    ClientCredentials credentials = new ClientCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
  
    BindingParameterCollection bindingParams = new BindingParameterCollection();  
    bindingParams.Add(credentials);  
    ```  
  
7.  <span data-ttu-id="ce6e2-181">Crear un agente de escucha de canal y ábralo.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-181">Create a channel listener and open it.</span></span> <span data-ttu-id="ce6e2-182">Crear el agente de escucha mediante la invocación de **BuildChannelListener < IInputChannel\>**  método en el **SqlAdapterBinding**.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-182">You create the listener by invoking **BuildChannelListener<IInputChannel\>** method on the **SqlAdapterBinding**.</span></span>  
  
    ```  
    IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
    listener.Open();  
    ```  
  
8.  <span data-ttu-id="ce6e2-183">Obtener un **IInputChannel** canal invocando la **AcceptChannel** método en el agente de escucha y ábralo.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-183">Get an **IInputChannel** channel by invoking the **AcceptChannel** method on the listener and open it.</span></span>  
  
    ```  
    IInputChannel channel = listener.AcceptChannel();  
    channel.Open();  
    ```  
  
9. <span data-ttu-id="ce6e2-184">Invocar **recepción** en el canal que se va a obtener el siguiente mensaje POLLINGSTMT desde el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-184">Invoke **Receive** on the channel to get the next POLLINGSTMT message from the adapter.</span></span>  
  
    ```  
    Message message = channel.Receive();  
    ```  
  
10. <span data-ttu-id="ce6e2-185">Consumir el conjunto de resultados devuelto por la operación de POLLINGSTMT.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-185">Consume the result set returned by the POLLINGSTMT operation.</span></span> <span data-ttu-id="ce6e2-186">Puedes utilizar el mensaje mediante un **XmlReader** o un **XmlDictionaryWriter**.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-186">You can consume the message using either an **XmlReader** or an **XmlDictionaryWriter**.</span></span>  
  
    ```  
    XmlReader reader = message.GetReaderAtBodyContents();  
    ```  
  
11. <span data-ttu-id="ce6e2-187">Cierre el canal cuando se hayan completado de procesar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-187">Close the channel when you have completed processing the request.</span></span>  
  
    ```  
    channel.Close()  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ce6e2-188">Debe cerrar el canal cuando haya terminado de procesar la operación de POLLINGSTMT.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-188">You must close the channel after you have finished processing the POLLINGSTMT operation.</span></span> <span data-ttu-id="ce6e2-189">Si no se cierra el canal puede afectar al comportamiento del código.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-189">Failure to close the channel may affect the behavior of your code.</span></span>  
  
12. <span data-ttu-id="ce6e2-190">Cierre el agente de escucha cuando haya terminado de recibir mensajes de cambio de datos.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-190">Close the listener when you are finished receiving data-changed messages.</span></span>  
  
    ```  
    listener.Close()  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ce6e2-191">Cerrando el agente de escucha no cierra los canales creados mediante el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-191">Closing the listener does not close channels created using the listener.</span></span> <span data-ttu-id="ce6e2-192">Debe cerrar explícitamente cada canal que se crea mediante el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-192">You must explicitly close each channel created using the listener.</span></span>  
  
### <a name="example"></a><span data-ttu-id="ce6e2-193">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ce6e2-193">Example</span></span>  
 <span data-ttu-id="ce6e2-194">En el ejemplo siguiente se muestra una consulta de sondeo que se ejecuta la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-194">The following example shows a polling query that executes the Employee table.</span></span> <span data-ttu-id="ce6e2-195">La instrucción de sondeo realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ce6e2-195">The polling statement performs the following tasks:</span></span>  
  
-   <span data-ttu-id="ce6e2-196">Selecciona todos los registros de la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-196">Selects all the records from the Employee table.</span></span>  
  
-   <span data-ttu-id="ce6e2-197">Ejecuta el procedimiento almacenado de MOVE_EMP_DATA para mover todos los registros de la tabla de empleados a la tabla HistorialEmpleados.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-197">Executes the MOVE_EMP_DATA stored procedure to move all records from Employee table to EmployeeHistory table.</span></span>  
  
-   <span data-ttu-id="ce6e2-198">Ejecuta el procedimiento almacenado de ADD_EMP_DETAILS para agregar un único registro a la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-198">Executes the ADD_EMP_DETAILS stored procedure to add a single record to the Employee table.</span></span>  
  
 <span data-ttu-id="ce6e2-199">Los mensajes de sondeo se guardan en `C:\PollingOutput.xml`.</span><span class="sxs-lookup"><span data-stu-id="ce6e2-199">The polling messages are saved at `C:\PollingOutput.xml`.</span></span>  
  
```  
using System;  
using Microsoft.Adapters.Sql;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
  
using System.Xml;  
  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Console.WriteLine("Sample started. This sample will poll 5 times and will perform the following tasks:");  
            Console.WriteLine("Press any key to start polling...");  
            Console.ReadLine();  
            IChannelListener<IInputChannel> listener = null;  
  
            IInputChannel channel = null;  
  
            try  
            {  
                TimeSpan messageTimeout = new TimeSpan(0, 0, 30);  
  
                SqlAdapterBinding binding = new SqlAdapterBinding();  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
                binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
  
                Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
  
                ClientCredentials credentials = new ClientCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  
  
                BindingParameterCollection bindingParams = new BindingParameterCollection();  
                bindingParams.Add(credentials);  
  
                listener = binding.BuildChannelListener<IInputChannel>(ConnectionUri, bindingParams);  
                listener.Open();  
  
                channel = listener.AcceptChannel();  
                channel.Open();  
  
                Console.WriteLine("Channel and Listener opened...");  
                Console.WriteLine("\nWaiting for polled data...");  
                Console.WriteLine("Receive request timeout is {0}", messageTimeout);  
  
                // Poll five times with the specified message timeout   
                // If a timeout occurs polling will be aborted  
                for (int i = 0; i < 5; i++)  
                {  
                    Console.WriteLine("Polling: " + i);  
                    Message message = null;  
                    XmlReader reader = null;  
                    try  
                    {  
                        //Message is received so process the results  
                        message = channel.Receive(messageTimeout);  
                    }  
                    catch (System.TimeoutException toEx)  
                    {  
                        Console.WriteLine("\nNo data for request number {0}: {1}", i + 1, toEx.Message);  
                        continue;  
                    }  
  
                    // Get the query results using an XML reader  
                    try  
                    {  
                        reader = message.GetReaderAtBodyContents();  
                    }  
                    catch (Exception ex)  
                    {  
                        Console.WriteLine("Exception :" + ex);  
                        throw;  
                    }  
  
                    XmlDocument doc = new XmlDocument();  
                    doc.Load(reader);  
                    using (XmlWriter writer = XmlWriter.Create("C:\\PollingOutput.xml"))  
                    {  
                        doc.WriteTo(writer);  
                        Console.WriteLine("The polling response is saved at 'C:\\PollingOutput.xml'");  
                    }  
  
                    // return the cursor  
                    Console.WriteLine();  
  
                    // close the reader  
                    reader.Close();  
  
                    message.Close();  
                }  
                Console.WriteLine("\nPolling done -- hit <RETURN> to finish");  
                Console.ReadLine();  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
            }  
            finally  
            {  
                // IMPORTANT: close the channel and listener to stop polling  
                if (channel != null)  
                {  
                    if (channel.State == CommunicationState.Opened)  
                        channel.Close();  
                    else  
                        channel.Abort();  
                }  
  
                if (listener != null)  
                {  
                    if (listener.State == CommunicationState.Opened)  
                        listener.Close();  
                    else  
                        listener.Abort();  
                }  
            }  
        }  
    }  
}  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="ce6e2-200">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce6e2-200">See Also</span></span>  
[<span data-ttu-id="ce6e2-201">Desarrollar aplicaciones de SQL mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="ce6e2-201">Develop SQL applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)