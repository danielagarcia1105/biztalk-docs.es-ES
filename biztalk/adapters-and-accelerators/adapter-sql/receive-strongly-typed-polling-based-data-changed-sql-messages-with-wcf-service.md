---
title: Recibir fuertemente tipado mensajes de cambio de datos basado en sondeo de SQL Server mediante el modelo de servicio WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b55eda71-1226-43f2-bc2f-e6b35563210b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a56ed382f6fa9c106b091b62406feba2dffe704
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-strongly-typed-polling-based-data-changed-messages-from-sql-server-using-wcf-service-model"></a><span data-ttu-id="971b8-102">Recibir fuertemente tipado mensajes de cambio de datos basado en sondeo de SQL Server mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="971b8-102">Receive Strongly-typed Polling-based Data-changed Messages from SQL Server Using WCF Service Model</span></span>
<span data-ttu-id="971b8-103">Puede configurar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir mensajes de sondeo fuertemente tipado de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="971b8-103">You can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive strongly-typed polling messages from SQL Server.</span></span> <span data-ttu-id="971b8-104">Puede especificar una instrucción de sondeo que el adaptador se ejecuta para sondear la base de datos.</span><span class="sxs-lookup"><span data-stu-id="971b8-104">You can specify a polling statement that the adapter executes to poll the database.</span></span> <span data-ttu-id="971b8-105">La instrucción de sondeo puede ser una instrucción SELECT o un procedimiento almacenado que devuelve un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="971b8-105">The polling statement can be a SELECT statement or a stored procedure that returns a result set.</span></span> <span data-ttu-id="971b8-106">Debe utilizar sondeo fuertemente tipado en un escenario donde desea recibir un conjunto de resultados fuertemente tipada.</span><span class="sxs-lookup"><span data-stu-id="971b8-106">You must use strongly-typed polling in a scenario where you want to receive a strongly-typed result set.</span></span> <span data-ttu-id="971b8-107">Para obtener más información sobre cómo el adaptador admite el sondeo fuertemente tipado, consulte [compatibilidad con entrada de sondeo utilizando llamadas](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span><span class="sxs-lookup"><span data-stu-id="971b8-107">For more information on how the adapter supports strongly-typed polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="971b8-108">Si desea tener más de un sondeo operación en una sola aplicación, debe especificar un **InboundID** propiedad de conexión como parte de la conexión de URI para que sea único.</span><span class="sxs-lookup"><span data-stu-id="971b8-108">If you want to have more than one polling operation in a single application, you must specify an **InboundID** connection property as part of the connection URI to make it unique.</span></span> <span data-ttu-id="971b8-109">Especifica el identificador de entrada se agrega al espacio de nombres de operación para hacerlo único.</span><span class="sxs-lookup"><span data-stu-id="971b8-109">The inbound ID you specify is added to the operation namespace to make it unique.</span></span>  
  
## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="971b8-110">Cómo este tema muestra el sondeo</span><span class="sxs-lookup"><span data-stu-id="971b8-110">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="971b8-111">En este tema, para demostrar cómo [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] admite la recepción de datos fuertemente tipados cambiar mensajes, crear una aplicación .NET y generará el contrato de servicio WCF para la **TypedPolling** operación.</span><span class="sxs-lookup"><span data-stu-id="971b8-111">In this topic, to demonstrate how the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports receiving strongly-typed data change messages, create a .NET application and generate the WCF service contract for the **TypedPolling** operation.</span></span> <span data-ttu-id="971b8-112">Asegúrese de que se especifique lo siguiente al generar el contrato de servicio WCF:</span><span class="sxs-lookup"><span data-stu-id="971b8-112">Make sure you specify the following while generating the WCF service contract:</span></span>  
  
-   <span data-ttu-id="971b8-113">Debe especificar un **InboundID** como parte del URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="971b8-113">You must specify an **InboundID** as part of the connection URI.</span></span>  
  
-   <span data-ttu-id="971b8-114">Debe especificar una instrucción de sondeo para la **PollingStatement** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="971b8-114">You must specify a polling statement for the **PollingStatement** binding property.</span></span>  
  
 <span data-ttu-id="971b8-115">Además, si desea especificar otro sondeo relacionados con la propiedades de enlace al generar la clase de proxy, especifique la **PolledDataAvailableStatement** como:</span><span class="sxs-lookup"><span data-stu-id="971b8-115">Additionally, if you want to specify other polling related binding properties while generating the proxy class, specify the **PolledDataAvailableStatement** as:</span></span>  
  
```  
SELECT COUNT(*) FROM Employee  
```  
  
 <span data-ttu-id="971b8-116">El **PolledDataAvailableStatement** debe devolver un conjunto de resultados con la primera celda que contiene un valor positivo.</span><span class="sxs-lookup"><span data-stu-id="971b8-116">The **PolledDataAvailableStatement** must return a result set with the first cell containing a positive value.</span></span> <span data-ttu-id="971b8-117">Si la primera celda no contiene un valor positivo, el adaptador no ejecuta la instrucción de sondeo.</span><span class="sxs-lookup"><span data-stu-id="971b8-117">If the first cell does not contain a positive value, the adapter does not execute the polling statement.</span></span>  
  
 <span data-ttu-id="971b8-118">Como parte de la instrucción de sondeo, realice las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="971b8-118">As part of the polling statement, perform the following operations:</span></span>  
  
1.  <span data-ttu-id="971b8-119">Seleccione todas las filas de la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="971b8-119">Select all the rows from the Employee table.</span></span>  
  
2.  <span data-ttu-id="971b8-120">Ejecutar un procedimiento almacenado (MOVE_EMP_DATA) para mover todos los registros de la tabla de empleados a una tabla HistorialEmpleados.</span><span class="sxs-lookup"><span data-stu-id="971b8-120">Execute a stored procedure (MOVE_EMP_DATA) to move all the records from the Employee table to an EmployeeHistory table.</span></span>  
  
3.  <span data-ttu-id="971b8-121">Ejecutar un procedimiento almacenado (ADD_EMP_DETAILS) para agregar un nuevo registro a la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="971b8-121">Execute a stored procedure (ADD_EMP_DETAILS) to add a new record to the Employee table.</span></span> <span data-ttu-id="971b8-122">Este procedimiento toma el nombre de empleado, designación y salario como parámetros.</span><span class="sxs-lookup"><span data-stu-id="971b8-122">This procedure takes the employee name, designation, and salary as parameters.</span></span>  
  
 <span data-ttu-id="971b8-123">Para llevar a cabo estas operaciones, debe especificar lo siguiente para el **PollingStatement** propiedad de enlace al generar las clases de aplicación auxiliar de contrato del servicio WCF:</span><span class="sxs-lookup"><span data-stu-id="971b8-123">To perform these operations, you must specify the following for the **PollingStatement** binding property while generating the WCF service contract and helper classes:</span></span>  
  
```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  
  
 <span data-ttu-id="971b8-124">Después de ejecuta la instrucción de sondeo, se seleccionan todos los registros de la tabla de empleados y se recibe el mensaje de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="971b8-124">After the polling statement is executed, all the records from the Employee table are selected and the message from SQL Server is received.</span></span> <span data-ttu-id="971b8-125">Después de ejecuta el procedimiento almacenado de MOVE_EMP_DATA por el adaptador, todos los registros se mueven a la tabla HistorialEmpleados.</span><span class="sxs-lookup"><span data-stu-id="971b8-125">After the MOVE_EMP_DATA stored procedure is executed by the adapter, all the records are moved to the EmployeeHistory table.</span></span> <span data-ttu-id="971b8-126">A continuación, se ejecuta el procedimiento almacenado de ADD_EMP_DETAILS para agregar un nuevo registro a la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="971b8-126">Then, the ADD_EMP_DETAILS stored procedure is executed to add a new record to the Employee table.</span></span> <span data-ttu-id="971b8-127">La siguiente ejecución de sondeo solo devolverá un único registro.</span><span class="sxs-lookup"><span data-stu-id="971b8-127">The next polling execution will only return a single record.</span></span> <span data-ttu-id="971b8-128">Este ciclo continúa hasta que se cierra el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="971b8-128">This cycle continues until you close the service host.</span></span>  
  
## <a name="configuring-typed-polling-with-the-sql-adapter-binding-properties"></a><span data-ttu-id="971b8-129">Configuración de sondeo con tipo con el adaptador de SQL propiedades de enlace</span><span class="sxs-lookup"><span data-stu-id="971b8-129">Configuring Typed Polling with the SQL Adapter Binding Properties</span></span>  
 <span data-ttu-id="971b8-130">La siguiente tabla resume el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] propiedades de enlace que se utiliza para configurar el adaptador para recibir mensajes de cambio de datos.</span><span class="sxs-lookup"><span data-stu-id="971b8-130">The following table summarizes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding properties that you use to configure the adapter to receive data-change messages.</span></span> <span data-ttu-id="971b8-131">Distinto de la **PollingStatement** propiedad de enlace, todas las demás propiedades de enlace enumerados en esta sección son necesarios al ejecutar la aplicación. NET.</span><span class="sxs-lookup"><span data-stu-id="971b8-131">Other than the **PollingStatement** binding property, all the other binding properties listed in this section are required while running the .NET application.</span></span> <span data-ttu-id="971b8-132">Debe especificar el **PollingStatement** propiedad de enlace antes de generar el contrato de servicio WCF **TypedPolling** operación.</span><span class="sxs-lookup"><span data-stu-id="971b8-132">You must specify the **PollingStatement** binding property before generating the WCF service contract **TypedPolling** operation.</span></span>  
  
|<span data-ttu-id="971b8-133">Propiedad de enlace</span><span class="sxs-lookup"><span data-stu-id="971b8-133">Binding Property</span></span>|<span data-ttu-id="971b8-134">Description</span><span class="sxs-lookup"><span data-stu-id="971b8-134">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="971b8-135">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="971b8-135">**InboundOperationType**</span></span>|<span data-ttu-id="971b8-136">Especifica si desea realizar **sondeo**, **TypedPolling**, o **notificación** operación entrante.</span><span class="sxs-lookup"><span data-stu-id="971b8-136">Specifies whether you want to perform **Polling**, **TypedPolling**, or **Notification** inbound operation.</span></span> <span data-ttu-id="971b8-137">Valor predeterminado es **sondeo**.</span><span class="sxs-lookup"><span data-stu-id="971b8-137">Default is **Polling**.</span></span> <span data-ttu-id="971b8-138">Para recibir mensajes de sondeo fuertemente tipado, establezca esta propiedad en **TypedPolling**.</span><span class="sxs-lookup"><span data-stu-id="971b8-138">To receive strongly-typed polling messages, set this to **TypedPolling**.</span></span>|  
|<span data-ttu-id="971b8-139">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="971b8-139">**PolledDataAvailableStatement**</span></span>|<span data-ttu-id="971b8-140">Especifica la instrucción SQL que se ejecuta el adaptador para determinar si los datos están disponibles para el sondeo.</span><span class="sxs-lookup"><span data-stu-id="971b8-140">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="971b8-141">La instrucción SQL debe devolver un conjunto que consta de filas y columnas de resultados.</span><span class="sxs-lookup"><span data-stu-id="971b8-141">The SQL statement must return a result set consisting of rows and columns.</span></span> <span data-ttu-id="971b8-142">Solo si una fila está disponible, la instrucción SQL especificada para el **PollingStatement** se va a ejecutar la propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="971b8-142">Only if a row is available, the SQL statement specified for the **PollingStatement** binding property will be executed.</span></span>|  
|<span data-ttu-id="971b8-143">**PollingIntervalInSeconds**</span><span class="sxs-lookup"><span data-stu-id="971b8-143">**PollingIntervalInSeconds**</span></span>|<span data-ttu-id="971b8-144">Especifica el intervalo, en segundos, en el que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se ejecuta la instrucción especificada para la **PolledDataAvailableStatement** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="971b8-144">Specifies the interval, in seconds, at which the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="971b8-145">El valor predeterminado es 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="971b8-145">The default is 30 seconds.</span></span> <span data-ttu-id="971b8-146">El intervalo de sondeo determina el intervalo de tiempo entre sondeos sucesivos.</span><span class="sxs-lookup"><span data-stu-id="971b8-146">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="971b8-147">Si la instrucción se ejecuta en el intervalo especificado, el adaptador espera el tiempo restante en el intervalo.</span><span class="sxs-lookup"><span data-stu-id="971b8-147">If the statement is executed within the specified interval, the adapter waits for the remaining time in the interval.</span></span>|  
|<span data-ttu-id="971b8-148">**PollingStatement**</span><span class="sxs-lookup"><span data-stu-id="971b8-148">**PollingStatement**</span></span>|<span data-ttu-id="971b8-149">Especifica la instrucción SQL para sondear la tabla de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="971b8-149">Specifies the SQL statement to poll the SQL Server database table.</span></span> <span data-ttu-id="971b8-150">Puede especificar una instrucción SELECT simple o un procedimiento almacenado para la instrucción de sondeo.</span><span class="sxs-lookup"><span data-stu-id="971b8-150">You can specify a simple SELECT statement or a stored procedure for the polling statement.</span></span> <span data-ttu-id="971b8-151">El valor predeterminado es null.</span><span class="sxs-lookup"><span data-stu-id="971b8-151">The default is null.</span></span> <span data-ttu-id="971b8-152">Debe especificar un valor para **PollingStatement** para habilitar el sondeo.</span><span class="sxs-lookup"><span data-stu-id="971b8-152">You must specify a value for **PollingStatement** to enable polling.</span></span> <span data-ttu-id="971b8-153">Se ejecuta la instrucción de sondeo solo si hay datos disponibles para el sondeo, que viene determinado por la **PolledDataAvailableStatement** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="971b8-153">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="971b8-154">Puede especificar cualquier número de instrucciones SQL separados por un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="971b8-154">You can specify any number of SQL statements separated by a semi-colon.</span></span> <span data-ttu-id="971b8-155">**Importante:** para **TypedPolling**, debe especificar esta propiedad de enlace antes de generar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="971b8-155">**Important:**  For **TypedPolling**, you must specify this binding property before generating metadata.</span></span>|  
|<span data-ttu-id="971b8-156">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="971b8-156">**PollWhileDataFound**</span></span>|<span data-ttu-id="971b8-157">Especifica si el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] pasa por alto el intervalo de sondeo y ejecuta continuamente la instrucción SQL especificada para el **PolledDataAvailableStatement** enlaza la propiedad, si los datos están disponibles en la tabla que se va a sondear.</span><span class="sxs-lookup"><span data-stu-id="971b8-157">Specifies whether the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ignores the polling interval and continuously executes the SQL statement specified for the **PolledDataAvailableStatement** binding property, if data is available in the table being polled.</span></span> <span data-ttu-id="971b8-158">Si no hay datos disponibles en la tabla, el adaptador vuelve para ejecutar la instrucción SQL en el intervalo de sondeo especificado.</span><span class="sxs-lookup"><span data-stu-id="971b8-158">If no data is available in the table, the adapter reverts to execute the SQL statement at the specified polling interval.</span></span> <span data-ttu-id="971b8-159">Valor predeterminado es **false**.</span><span class="sxs-lookup"><span data-stu-id="971b8-159">Default is **false**.</span></span>|  
  
 <span data-ttu-id="971b8-160">Para obtener una descripción más completa de estas propiedades, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="971b8-160">For a more complete description of these properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="971b8-161">Para obtener una descripción completa de cómo usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para sondear SQL Server, seguir leyendo.</span><span class="sxs-lookup"><span data-stu-id="971b8-161">For a complete description of how to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to poll SQL Server, read further.</span></span>  
  
## <a name="configuring-strongly-typed-polling-in-the-wcf-service-model"></a><span data-ttu-id="971b8-162">Configuración de sondeo fuertemente tipadas en el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="971b8-162">Configuring Strongly-typed Polling in the WCF Service Model</span></span>  
 <span data-ttu-id="971b8-163">Para recibir el **sondeo** operación cuando se usa el modelo de servicio WCF, debe:</span><span class="sxs-lookup"><span data-stu-id="971b8-163">To receive the **Polling** operation when you use the WCF service model, you must:</span></span>  
  
1.  <span data-ttu-id="971b8-164">Generar un contrato de servicio WCF (interfaz) para la **TypedPolling** operación desde los metadatos expuestos por el adaptador.</span><span class="sxs-lookup"><span data-stu-id="971b8-164">Generate a WCF service contract (interface) for the **TypedPolling** operation from the metadata exposed by the adapter.</span></span> <span data-ttu-id="971b8-165">Para ello, puede usar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="971b8-165">To do this, you could use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span> <span data-ttu-id="971b8-166">Al generar el contrato de servicio WCF para este ejemplo, asegúrese de que:</span><span class="sxs-lookup"><span data-stu-id="971b8-166">While generating the WCF service contract for this example, make sure:</span></span>  
  
    -   <span data-ttu-id="971b8-167">Especifique el **InboundID** como **empleado**.</span><span class="sxs-lookup"><span data-stu-id="971b8-167">You specify the **InboundID** as **Employee**.</span></span>  
  
    -   <span data-ttu-id="971b8-168">Especifica una instrucción de sondeo para la **PollingStatement** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="971b8-168">You specify a polling statement for the **PollingStatement** binding property.</span></span> <span data-ttu-id="971b8-169">En este ejemplo, especifique la instrucción de sondeo como:</span><span class="sxs-lookup"><span data-stu-id="971b8-169">For this example, specify the polling statement as:</span></span>  
  
        ```  
        SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000  
        ```  
  
2.  <span data-ttu-id="971b8-170">Implementar un servicio WCF de esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="971b8-170">Implement a WCF service from this interface.</span></span>  
  
3.  <span data-ttu-id="971b8-171">Hospedar este servicio WCF mediante un host de servicio (**System.ServiceModel.ServiceHost**).</span><span class="sxs-lookup"><span data-stu-id="971b8-171">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="971b8-172">Acerca de los ejemplos usados en este tema</span><span class="sxs-lookup"><span data-stu-id="971b8-172">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="971b8-173">Los ejemplos de este tema sondean la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="971b8-173">The examples in this topic poll the Employee table.</span></span> <span data-ttu-id="971b8-174">El ejemplo también usa MOVE_EMP_DATA y ADD_EMP_DETAILS procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="971b8-174">The example also uses the MOVE_EMP_DATA and ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="971b8-175">Una secuencia de comandos para generar estos artefactos se suministra con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="971b8-175">A script to generate these artifacts is supplied with the samples.</span></span> <span data-ttu-id="971b8-176">Para obtener más información acerca de los ejemplos, vea [ejemplos del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="971b8-176">For more information about the samples, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span> <span data-ttu-id="971b8-177">Obtener un ejemplo, **TypedPolling_ServiceModel**, que se basa en este tema, también se proporciona con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="971b8-177">A sample, **TypedPolling_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="971b8-178">El contrato de servicio WCF y la clase</span><span class="sxs-lookup"><span data-stu-id="971b8-178">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="971b8-179">Puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para crear un contrato de servicio WCF (interfaz) y las clases para que admite la **TypedPolling** operación.</span><span class="sxs-lookup"><span data-stu-id="971b8-179">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **TypedPolling** operation.</span></span> <span data-ttu-id="971b8-180">Para obtener más información acerca de cómo generar un contrato de servicio WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="971b8-180">For more information about generating a WCF service contract, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="971b8-181">El contrato de servicio WCF (interfaz)</span><span class="sxs-lookup"><span data-stu-id="971b8-181">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="971b8-182">El código siguiente muestra el contrato de servicio WCF (interfaz) que se genera para la **TypedPolling** operación.</span><span class="sxs-lookup"><span data-stu-id="971b8-182">The following code shows the WCF service contract (interface) generated for the **TypedPolling** operation.</span></span>  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/", ConfigurationName="TypedPolling_Employee")]  
public interface TypedPolling_Employee {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee) of message TypedPolling  
    // does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="TypedPolling")]  
    void TypedPolling(TypedPolling request);  
}  
```  
  
### <a name="the-message-contracts"></a><span data-ttu-id="971b8-183">Los contratos de mensaje</span><span class="sxs-lookup"><span data-stu-id="971b8-183">The Message Contracts</span></span>  
 <span data-ttu-id="971b8-184">El espacio de nombres de contrato de mensaje se modifica mediante la **InboundID** parámetro en el URI, si se especifica de conexión.</span><span class="sxs-lookup"><span data-stu-id="971b8-184">The message contract namespace is modified by the **InboundID** parameter in the connection URI, if specified.</span></span> <span data-ttu-id="971b8-185">En este ejemplo, se especifica el identificador de entrada como **empleado**.</span><span class="sxs-lookup"><span data-stu-id="971b8-185">In this example, you specified the inbound ID as **Employee**.</span></span> <span data-ttu-id="971b8-186">El mensaje de solicitud devuelve un conjunto de resultados fuertemente tipada.</span><span class="sxs-lookup"><span data-stu-id="971b8-186">The request message returns a strongly-typed result set.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="TypedPolling", WrapperNamespace="http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee", IsWrapped=true)]  
public partial class TypedPolling {  
  
[System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee", Order=0)]  
    public schemas.microsoft.com.Sql._2008._05.TypedPolling.Employee.TypedPollingResultSet0[] TypedPollingResultSet0;  
  
[System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee", Order=1)]  
    public schemas.microsoft.com.Sql._2008._05.TypedPolling.Employee.TypedPollingResultSet1[] TypedPollingResultSet1;  
  
    public TypedPolling() {  
    }  
  
    public TypedPolling(schemas.microsoft.com.Sql._2008._05.TypedPolling.Employee.TypedPollingResultSet0[] TypedPollingResultSet0, schemas.microsoft.com.Sql._2008._05.TypedPolling.Employee.TypedPollingResultSet1[] TypedPollingResultSet1) {  
        this.TypedPollingResultSet0 = TypedPollingResultSet0;  
        this.TypedPollingResultSet1 = TypedPollingResultSet1;  
    }  
}  
```  
  
### <a name="wcf-service-class"></a><span data-ttu-id="971b8-187">Clase de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="971b8-187">WCF Service Class</span></span>  
 <span data-ttu-id="971b8-188">El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] también genera un archivo que tiene un código auxiliar para la clase de servicio WCF que implementa el contrato de servicio (interfaz).</span><span class="sxs-lookup"><span data-stu-id="971b8-188">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="971b8-189">El nombre del archivo es SqlAdapterBindingService.cs.</span><span class="sxs-lookup"><span data-stu-id="971b8-189">The name of the file is SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="971b8-190">Puede insertar la lógica para procesar el **TypedPolling** operación directamente en esta clase.</span><span class="sxs-lookup"><span data-stu-id="971b8-190">You can insert the logic to process the **TypedPolling** operation directly into this class.</span></span> <span data-ttu-id="971b8-191">El código siguiente muestra la clase de servicio WCF generada por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="971b8-191">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
```  
namespace SqlAdapterBindingNamespace {  
  
    public class SqlAdapterBindingService : TypedPolling_Employee {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee) of message TypedPolling  
        // does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
        public virtual void TypedPolling(TypedPolling request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-strongly-typed-inbound-messages-for-polling-operation"></a><span data-ttu-id="971b8-192">Recibir mensajes entrantes fuertemente tipados para la operación de sondeo</span><span class="sxs-lookup"><span data-stu-id="971b8-192">Receiving Strongly-typed Inbound Messages for Polling Operation</span></span>  
 <span data-ttu-id="971b8-193">Esta sección proporciona instrucciones sobre cómo escribir una aplicación .NET para recibir mensajes entrantes de sondeo fuertemente tipado mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="971b8-193">This section provides instructions on how to write a .NET application to receive strongly-typed inbound polling messages using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
#### <a name="to-receive-polling-messages-from-the-sql-adapter"></a><span data-ttu-id="971b8-194">Para recibir mensajes de sondeo desde el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="971b8-194">To receive polling messages from the SQL adapter</span></span>  
  
1.  <span data-ttu-id="971b8-195">Use la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar un contrato de servicio WCF (interfaz) y las clases auxiliares para el **TypedPolling** operación.</span><span class="sxs-lookup"><span data-stu-id="971b8-195">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **TypedPolling** operation.</span></span> <span data-ttu-id="971b8-196">Asegúrese de que se especifique lo siguiente al generar el contrato de servicio WCF para este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="971b8-196">Make sure you specify the following while generating the WCF service contract for this example:</span></span>  
  
    -   <span data-ttu-id="971b8-197">Debe especificar el **InboundID** como **empleado**.</span><span class="sxs-lookup"><span data-stu-id="971b8-197">You must specify the **InboundID** as **Employee**.</span></span>  
  
    -   <span data-ttu-id="971b8-198">Debe especificar una instrucción de sondeo para la **PollingStatement** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="971b8-198">You must specify a polling statement for the **PollingStatement** binding property.</span></span> <span data-ttu-id="971b8-199">En este ejemplo, especifique la instrucción de sondeo como:</span><span class="sxs-lookup"><span data-stu-id="971b8-199">For this example, specify the polling statement as:</span></span>  
  
        ```  
        SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000  
        ```  
  
     <span data-ttu-id="971b8-200">Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF de artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="971b8-200">For more information, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span> <span data-ttu-id="971b8-201">También puede especificar las propiedades de enlace al generar las clases de contrato y el Ayudante de servicio.</span><span class="sxs-lookup"><span data-stu-id="971b8-201">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="971b8-202">Esto garantiza que están establecidas correctamente en el archivo de configuración generado.</span><span class="sxs-lookup"><span data-stu-id="971b8-202">This guarantees that they are properly set in the generated configuration file.</span></span>  
  
2.  <span data-ttu-id="971b8-203">Implementar un servicio WCF desde las clases de interfaz y auxiliar generado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="971b8-203">Implement a WCF service from the interface and helper classes generated in step 1.</span></span> <span data-ttu-id="971b8-204">El **TypedPolling** método de esta clase puede producir una excepción para anular la transacción de sondeo, si se produce un error de procesamiento de los datos recibidos de la **TypedPolling** operación; de lo contrario el método no devuelve nada.</span><span class="sxs-lookup"><span data-stu-id="971b8-204">The **TypedPolling** method of this class can throw an exception to abort the polling transaction, if an error is encountered processing the data received from the **TypedPolling** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="971b8-205">La clase de servicio WCF debe atributo como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="971b8-205">You must attribute the WCF service class as follows:</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
     <span data-ttu-id="971b8-206">En el **TypedPolling** método, puede implementar la lógica de aplicación directamente.</span><span class="sxs-lookup"><span data-stu-id="971b8-206">Within the **TypedPolling** method, you can implement your application logic directly.</span></span> <span data-ttu-id="971b8-207">Esta clase se puede encontrar en SqlAdapterBindingService.cs.</span><span class="sxs-lookup"><span data-stu-id="971b8-207">This class can be found in SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="971b8-208">Este código de este ejemplo Sub-clases el **SqlAdapterBindingService** clase.</span><span class="sxs-lookup"><span data-stu-id="971b8-208">This code in this example sub-classes the **SqlAdapterBindingService** class.</span></span> <span data-ttu-id="971b8-209">En este código, se escribe el mensaje de sondeo recibido como un conjunto de resultados fuertemente tipados en la consola.</span><span class="sxs-lookup"><span data-stu-id="971b8-209">In this code, the polling message received as a strongly-typed result set is written to the console.</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
    {  
        public override void TypedPolling(TypedPolling request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("Employee ID\tName\tDesignation\tSalary");  
  
            for (int i = 0; i < request.TypedPollingResultSet0.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
                request.TypedPollingResultSet0[i].Employee_ID,  
                request.TypedPollingResultSet0[i].Name,  
                request.TypedPollingResultSet0[i].Designation,  
                request.TypedPollingResultSet0[i].Salary);  
            }  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("\nHit <RETURN> to stop polling");  
        }  
    }  
    ```  
  
3.  <span data-ttu-id="971b8-210">Dado que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no acepta credenciales como parte del URI de conexión, debe implementar la clase siguiente para pasar las credenciales de la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="971b8-210">Because the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not accept credentials as part of the connection URI, you must implement the following class to pass credentials for the SQL Server database.</span></span> <span data-ttu-id="971b8-211">En la última parte de la aplicación, se creará una instancia de esta clase para pasar las credenciales de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="971b8-211">In the latter part of the application, you will instantiate this class to pass on the SQL Server credentials.</span></span>  
  
    ```  
    class PollingCredentials : ClientCredentials, IServiceBehavior  
    {  
        public void AddBindingParameters(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase, Collection<ServiceEndpoint> endpoints, BindingParameterCollection bindingParameters)  
        {  
            bindingParameters.Add(this);  
        }  
  
        public void ApplyDispatchBehavior(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        public void Validate(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        protected override ClientCredentials CloneCore()  
        {  
            ClientCredentials clone = new PollingCredentials();  
            clone.UserName.UserName = this.UserName.UserName;  
            clone.UserName.Password = this.UserName.Password;  
            return clone;  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="971b8-212">Crear un **SqlAdapterBinding** y configure la operación de sondeo mediante la especificación de las propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="971b8-212">Create a **SqlAdapterBinding** and configure the polling operation by specifying the binding properties.</span></span> <span data-ttu-id="971b8-213">Puede hacerlo explícitamente en el código o mediante declaración en configuración.</span><span class="sxs-lookup"><span data-stu-id="971b8-213">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="971b8-214">Como mínimo, debe especificar el **InboundOperationType**, **PolledDataAvailableStatement**, y **PollingStatement**.</span><span class="sxs-lookup"><span data-stu-id="971b8-214">At a minimum, you must specify the **InboundOperationType**, **PolledDataAvailableStatement**, and **PollingStatement**.</span></span>  
  
    ```  
    SqlAdapterBinding binding = new SqlAdapterBinding();  
    binding.InboundOperationType = InboundOperation.TypedPolling;  
    binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
    binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
    ```  
  
5.  <span data-ttu-id="971b8-215">Especifique las credenciales de base de datos de SQL Server creando el **PollingCredentials** clase creada en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="971b8-215">Specify SQL Server database credentials by instantiating the **PollingCredentials** class you created in Step 3.</span></span>  
  
    ```  
    PollingCredentials credentials = new PollingCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
    ```  
  
6.  <span data-ttu-id="971b8-216">Cree una instancia del servicio WCF que creó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="971b8-216">Create an instance of the WCF service created in step 2.</span></span>  
  
    ```  
    // create service instance  
    PollingService service = new PollingService();  
    ```  
  
7.  <span data-ttu-id="971b8-217">Cree una instancia de **System.ServiceModel.ServiceHost** mediante el servicio WCF y un URI de conexión base.</span><span class="sxs-lookup"><span data-stu-id="971b8-217">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="971b8-218">El URI de conexión base no puede contener el identificador de entrada.</span><span class="sxs-lookup"><span data-stu-id="971b8-218">The base connection URI cannot contain the inbound ID.</span></span> <span data-ttu-id="971b8-219">También debe especificar las credenciales aquí.</span><span class="sxs-lookup"><span data-stu-id="971b8-219">You must also specify the credentials here.</span></span>  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
    ServiceHost serviceHost = new ServiceHost(service, baseUri);  
    serviceHost.Description.Behaviors.Add(credentials);  
  
    ```  
  
8.  <span data-ttu-id="971b8-220">Agregar un extremo de servicio al host de servicio.</span><span class="sxs-lookup"><span data-stu-id="971b8-220">Add a service endpoint to the service host.</span></span> <span data-ttu-id="971b8-221">Para hacerlo:</span><span class="sxs-lookup"><span data-stu-id="971b8-221">To do this:</span></span>  
  
    -   <span data-ttu-id="971b8-222">Utilice el enlace creado en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="971b8-222">Use the binding created in step 4.</span></span>  
  
    -   <span data-ttu-id="971b8-223">Especifica una URI que contiene las credenciales de conexión y, si es necesario, un identificador de entrada.</span><span class="sxs-lookup"><span data-stu-id="971b8-223">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  
  
    -   <span data-ttu-id="971b8-224">Especifique el contrato como "TypedPolling_Employee".</span><span class="sxs-lookup"><span data-stu-id="971b8-224">Specify the contract as "TypedPolling_Employee".</span></span>  
  
    ```  
    // Add service endpoint: be sure to specify TypedPolling_Employee as the contract  
    Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?InboundID=Empliyee");  
    serviceHost.AddServiceEndpoint("TypedPolling_Employee", binding, ConnectionUri);  
    ```  
  
9. <span data-ttu-id="971b8-225">Para recibir datos de sondeo, abra el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="971b8-225">To receive polling data, open the service host.</span></span> <span data-ttu-id="971b8-226">El adaptador devolverá datos cada vez que la consulta devuelve un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="971b8-226">The adapter will return data whenever the query returns a result set.</span></span>  
  
    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  
  
10. <span data-ttu-id="971b8-227">Para finalizar el sondeo, cierre el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="971b8-227">To terminate polling, close the service host.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="971b8-228">El adaptador seguirá sondea hasta que se cierra el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="971b8-228">The adapter will continue to poll until the service host is closed.</span></span>  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a><span data-ttu-id="971b8-229">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="971b8-229">Example</span></span>  
 <span data-ttu-id="971b8-230">En el ejemplo siguiente se muestra una consulta de sondeo que se ejecuta la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="971b8-230">The following example shows a polling query that executes the Employee table.</span></span> <span data-ttu-id="971b8-231">La instrucción de sondeo realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="971b8-231">The polling statement performs the following tasks:</span></span>  
  
1.  <span data-ttu-id="971b8-232">Selecciona todos los registros de la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="971b8-232">Selects all the records from the Employee table.</span></span>  
  
2.  <span data-ttu-id="971b8-233">Ejecuta el procedimiento almacenado de MOVE_EMP_DATA para mover todos los registros de la tabla de empleados a la tabla HistorialEmpleados.</span><span class="sxs-lookup"><span data-stu-id="971b8-233">Executes the MOVE_EMP_DATA stored procedure to move all records from Employee table to EmployeeHistory table.</span></span>  
  
3.  <span data-ttu-id="971b8-234">Ejecuta el procedimiento almacenado de ADD_EMP_DETAILS para agregar un único registro a la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="971b8-234">Executes the ADD_EMP_DETAILS stored procedure to add a single record to the Employee table.</span></span>  
  
 <span data-ttu-id="971b8-235">El primer mensaje de sondeo contendrá todos los registros de la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="971b8-235">The first polling message will contain all the records from the Employee table.</span></span> <span data-ttu-id="971b8-236">Los mensajes de sondeo subsiguiente contendrá solo el último registro insertado por el procedimiento almacenado de ADD_EMP_DETAILS.</span><span class="sxs-lookup"><span data-stu-id="971b8-236">The subsequent polling messages will contain only the last record inserted by the ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="971b8-237">El adaptador seguirá sondea hasta que cierre el host de servicio presionando `<RETURN>`.</span><span class="sxs-lookup"><span data-stu-id="971b8-237">The adapter will continue to poll until you close the service host by pressing `<RETURN>`.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
using Microsoft.Adapters.Sql;  
using Microsoft.ServiceModel.Channels;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Collections.ObjectModel;  
  
namespace TypedPolling_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
    {  
        public override void TypedPolling(TypedPolling request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("Employee ID\tName\tDesignation\tSalary");  
  
            for (int i = 0; i < request.TypedPollingResultSet0.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
                request.TypedPollingResultSet0[i].Employee_ID,  
                request.TypedPollingResultSet0[i].Name,  
                request.TypedPollingResultSet0[i].Designation,  
                request.TypedPollingResultSet0[i].Salary);  
            }  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("\nHit <RETURN> to stop polling");  
        }  
    }  
  
    class PollingCredentials : ClientCredentials, IServiceBehavior  
    {  
        public void AddBindingParameters(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase, Collection<ServiceEndpoint> endpoints, BindingParameterCollection bindingParameters)  
        {  
            bindingParameters.Add(this);  
        }  
  
        public void ApplyDispatchBehavior(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        public void Validate(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        protected override ClientCredentials CloneCore()  
        {  
            ClientCredentials clone = new PollingCredentials();  
            clone.UserName.UserName = this.UserName.UserName;  
            clone.UserName.Password = this.UserName.Password;  
            return clone;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost serviceHost = null;  
            try  
            {  
                Console.WriteLine("Sample started...");  
                Console.WriteLine("Press any key to start polling...");  
                Console.ReadLine();  
  
                SqlAdapterBinding binding = new SqlAdapterBinding();  
                binding.InboundOperationType = InboundOperation.TypedPolling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
                binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
                Console.WriteLine("Binding properties assigned...");  
  
                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?InboundId=Employee");  
  
                // This URI is used to initialize the ServiceHost. It cannot contain  
                // the InboundID; otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
  
                PollingCredentials credentials = new PollingCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  
  
                Console.WriteLine("Opening service host...");  
                PollingService service = new PollingService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("TypedPolling_Employee", binding, ConnectionUri);  
                serviceHost.Open();  
                Console.WriteLine("Service host opened...");  
                Console.WriteLine("Polling started...");  
                Console.ReadLine();  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("Exception :" + e.Message);  
                Console.ReadLine();  
  
                /* If there is an error it will be specified in the inner exception */  
                if (e.InnerException != null)  
                {  
                    Console.WriteLine("InnerException: " + e.InnerException.Message);  
                    Console.ReadLine();  
                }  
            }  
            finally  
            {  
                // IMPORTANT: you must close the ServiceHost to stop polling  
                if (serviceHost.State == CommunicationState.Opened)  
                    serviceHost.Close();  
                else  
                    serviceHost.Abort();  
            }  
        }  
    }  
}  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="971b8-238">Vea también</span><span class="sxs-lookup"><span data-stu-id="971b8-238">See Also</span></span>  
 [<span data-ttu-id="971b8-239">Sondear el servidor SQL mediante el adaptador de SQL con el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="971b8-239">Poll SQL Server using the SQL Adapter with WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)