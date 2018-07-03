---
title: Recibir mensajes fuertemente tipados basados en sondeos cambio de datos desde SQL Server mediante el modelo de servicio WCF | Microsoft Docs
description: Usar una aplicación .NET para configurar el sondeo con tipo o sondeo fuertemente tipado mediante el servicio WCF con el adaptador de WCF-SQL en BizTalk Server
ms.custom: ''
ms.date: 10/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b55eda71-1226-43f2-bc2f-e6b35563210b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adf6f1e322485521504259f24dade00bb33a4539
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012653"
---
# <a name="receive-strongly-typed-polling-based-data-changed-messages-from-sql-server-using-wcf-service-model"></a><span data-ttu-id="0f09c-103">Recibir mensajes fuertemente tipados basados en sondeos cambio de datos desde SQL Server mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="0f09c-103">Receive Strongly-typed Polling-based Data-changed Messages from SQL Server Using WCF Service Model</span></span>
<span data-ttu-id="0f09c-104">Puede configurar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir mensajes de sondeo fuertemente tipado de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0f09c-104">You can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive strongly-typed polling messages from SQL Server.</span></span> <span data-ttu-id="0f09c-105">Puede especificar una instrucción de sondeo que se ejecuta el adaptador para sondear la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0f09c-105">You can specify a polling statement that the adapter executes to poll the database.</span></span> <span data-ttu-id="0f09c-106">La instrucción de sondeo puede ser una instrucción SELECT o un procedimiento almacenado que devuelve un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="0f09c-106">The polling statement can be a SELECT statement or a stored procedure that returns a result set.</span></span> <span data-ttu-id="0f09c-107">Debe usar sondeo fuertemente tipado en un escenario donde desea que reciban un conjunto de resultados fuertemente tipado.</span><span class="sxs-lookup"><span data-stu-id="0f09c-107">You must use strongly-typed polling in a scenario where you want to receive a strongly-typed result set.</span></span> <span data-ttu-id="0f09c-108">Para obtener más información sobre cómo el adaptador admite el sondeo fuertemente tipado, vea [compatibilidad con entrada de sondeo utilizando llamadas](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span><span class="sxs-lookup"><span data-stu-id="0f09c-108">For more information on how the adapter supports strongly-typed polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="0f09c-109">Si desea tener más de un sondeo operación en una sola aplicación, debe especificar un **InboundID** propiedad de conexión como parte de la conexión URI para que sea único.</span><span class="sxs-lookup"><span data-stu-id="0f09c-109">If you want to have more than one polling operation in a single application, you must specify an **InboundID** connection property as part of the connection URI to make it unique.</span></span> <span data-ttu-id="0f09c-110">Especifica el identificador de entrada se agrega al espacio de nombres de operación para que sea único.</span><span class="sxs-lookup"><span data-stu-id="0f09c-110">The inbound ID you specify is added to the operation namespace to make it unique.</span></span>  

## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="0f09c-111">Cómo este tema muestra el sondeo</span><span class="sxs-lookup"><span data-stu-id="0f09c-111">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="0f09c-112">En este tema, para demostrar cómo el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] admite la recepción de datos fuertemente tipados mensajes de cambio, cree una aplicación .NET y generar el contrato de servicio WCF para la **TypedPolling** operación.</span><span class="sxs-lookup"><span data-stu-id="0f09c-112">In this topic, to demonstrate how the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports receiving strongly-typed data change messages, create a .NET application and generate the WCF service contract for the **TypedPolling** operation.</span></span> <span data-ttu-id="0f09c-113">Asegúrese de que se especifique lo siguiente al generar el contrato de servicio WCF:</span><span class="sxs-lookup"><span data-stu-id="0f09c-113">Make sure you specify the following while generating the WCF service contract:</span></span>  

- <span data-ttu-id="0f09c-114">Debe especificar un **InboundID** como parte de la URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="0f09c-114">You must specify an **InboundID** as part of the connection URI.</span></span>  

- <span data-ttu-id="0f09c-115">Debe especificar una instrucción de sondeo para el **PollingStatement** enlaza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="0f09c-115">You must specify a polling statement for the **PollingStatement** binding property.</span></span>  

  <span data-ttu-id="0f09c-116">Además, si desea especificar otro sondeo relacionados con la propiedades de enlace al generar la clase de proxy, especifique el **PolledDataAvailableStatement** como:</span><span class="sxs-lookup"><span data-stu-id="0f09c-116">Additionally, if you want to specify other polling related binding properties while generating the proxy class, specify the **PolledDataAvailableStatement** as:</span></span>  

```  
SELECT COUNT(*) FROM Employee  
```  

 <span data-ttu-id="0f09c-117">El **PolledDataAvailableStatement** debe devolver un conjunto de resultados con la primera celda que contiene un valor positivo.</span><span class="sxs-lookup"><span data-stu-id="0f09c-117">The **PolledDataAvailableStatement** must return a result set with the first cell containing a positive value.</span></span> <span data-ttu-id="0f09c-118">Si la primera celda no contiene un valor positivo, el adaptador no ejecuta la instrucción de sondeo.</span><span class="sxs-lookup"><span data-stu-id="0f09c-118">If the first cell does not contain a positive value, the adapter does not execute the polling statement.</span></span>  

 <span data-ttu-id="0f09c-119">Como parte de la instrucción de sondeo, realice las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="0f09c-119">As part of the polling statement, perform the following operations:</span></span>  

1. <span data-ttu-id="0f09c-120">Seleccione todas las filas de la tabla Employee.</span><span class="sxs-lookup"><span data-stu-id="0f09c-120">Select all the rows from the Employee table.</span></span>  

2. <span data-ttu-id="0f09c-121">Ejecutar un procedimiento almacenado (MOVE_EMP_DATA) para mover todos los registros de la tabla de empleados a una tabla HistorialEmpleados.</span><span class="sxs-lookup"><span data-stu-id="0f09c-121">Execute a stored procedure (MOVE_EMP_DATA) to move all the records from the Employee table to an EmployeeHistory table.</span></span>  

3. <span data-ttu-id="0f09c-122">Ejecutar un procedimiento almacenado (ADD_EMP_DETAILS) para agregar un nuevo registro a la tabla Employee.</span><span class="sxs-lookup"><span data-stu-id="0f09c-122">Execute a stored procedure (ADD_EMP_DETAILS) to add a new record to the Employee table.</span></span> <span data-ttu-id="0f09c-123">Este procedimiento toma el nombre de empleado, designación y salario como parámetros.</span><span class="sxs-lookup"><span data-stu-id="0f09c-123">This procedure takes the employee name, designation, and salary as parameters.</span></span>  

   <span data-ttu-id="0f09c-124">Para llevar a cabo estas operaciones, debe especificar lo siguiente para el **PollingStatement** enlaza la propiedad al generar las clases de aplicación auxiliar de contrato del servicio WCF:</span><span class="sxs-lookup"><span data-stu-id="0f09c-124">To perform these operations, you must specify the following for the **PollingStatement** binding property while generating the WCF service contract and helper classes:</span></span>  

```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  

 <span data-ttu-id="0f09c-125">Después de ejecutar la instrucción de sondeo, se seleccionan todos los registros de la tabla de empleados y se recibe el mensaje de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0f09c-125">After the polling statement is executed, all the records from the Employee table are selected and the message from SQL Server is received.</span></span> <span data-ttu-id="0f09c-126">Después de ejecuta el procedimiento almacenado de MOVE_EMP_DATA por el adaptador, todos los registros se mueven a la tabla HistorialEmpleados.</span><span class="sxs-lookup"><span data-stu-id="0f09c-126">After the MOVE_EMP_DATA stored procedure is executed by the adapter, all the records are moved to the EmployeeHistory table.</span></span> <span data-ttu-id="0f09c-127">A continuación, se ejecuta el procedimiento almacenado de ADD_EMP_DETAILS para agregar un nuevo registro a la tabla Employee.</span><span class="sxs-lookup"><span data-stu-id="0f09c-127">Then, the ADD_EMP_DETAILS stored procedure is executed to add a new record to the Employee table.</span></span> <span data-ttu-id="0f09c-128">La siguiente ejecución de sondeo solo devolverá un único registro.</span><span class="sxs-lookup"><span data-stu-id="0f09c-128">The next polling execution will only return a single record.</span></span> <span data-ttu-id="0f09c-129">Este ciclo continúa hasta que cierre el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="0f09c-129">This cycle continues until you close the service host.</span></span>  

## <a name="configuring-typed-polling-with-the-sql-adapter-binding-properties"></a><span data-ttu-id="0f09c-130">Configuración de sondeo con tipo con el adaptador de SQL, las propiedades de enlace</span><span class="sxs-lookup"><span data-stu-id="0f09c-130">Configuring Typed Polling with the SQL Adapter Binding Properties</span></span>  
 <span data-ttu-id="0f09c-131">La siguiente tabla resume el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] propiedades que usan para configurar el adaptador para recibir mensajes de cambio de datos de enlace.</span><span class="sxs-lookup"><span data-stu-id="0f09c-131">The following table summarizes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding properties that you use to configure the adapter to receive data-change messages.</span></span> <span data-ttu-id="0f09c-132">No sea el **PollingStatement** propiedad de enlace, todas las demás propiedades de enlace enumerados en esta sección son necesarios al ejecutar la aplicación. NET.</span><span class="sxs-lookup"><span data-stu-id="0f09c-132">Other than the **PollingStatement** binding property, all the other binding properties listed in this section are required while running the .NET application.</span></span> <span data-ttu-id="0f09c-133">Debe especificar el **PollingStatement** enlaza la propiedad antes de generar el contrato de servicio WCF **TypedPolling** operación.</span><span class="sxs-lookup"><span data-stu-id="0f09c-133">You must specify the **PollingStatement** binding property before generating the WCF service contract **TypedPolling** operation.</span></span>  


|         <span data-ttu-id="0f09c-134">Propiedad de enlace</span><span class="sxs-lookup"><span data-stu-id="0f09c-134">Binding Property</span></span>         |                                                                                                                                                                                                                                                                                              <span data-ttu-id="0f09c-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="0f09c-135">Description</span></span>                                                                                                                                                                                                                                                                                              |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="0f09c-136">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="0f09c-136">**InboundOperationType**</span></span>     |                                                                                                                                                                                             <span data-ttu-id="0f09c-137">Especifica si desea realizar **sondeo**, **TypedPolling**, o **notificación** operación entrante.</span><span class="sxs-lookup"><span data-stu-id="0f09c-137">Specifies whether you want to perform **Polling**, **TypedPolling**, or **Notification** inbound operation.</span></span> <span data-ttu-id="0f09c-138">El valor predeterminado es **sondeo**.</span><span class="sxs-lookup"><span data-stu-id="0f09c-138">Default is **Polling**.</span></span> <span data-ttu-id="0f09c-139">Para recibir mensajes de sondeo fuertemente tipado, establezca esta opción en **TypedPolling**.</span><span class="sxs-lookup"><span data-stu-id="0f09c-139">To receive strongly-typed polling messages, set this to **TypedPolling**.</span></span>                                                                                                                                                                                             |
| <span data-ttu-id="0f09c-140">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="0f09c-140">**PolledDataAvailableStatement**</span></span> |                                                                                                                                           <span data-ttu-id="0f09c-141">Especifica la instrucción SQL que ejecuta el adaptador para determinar si los datos están disponibles para el sondeo.</span><span class="sxs-lookup"><span data-stu-id="0f09c-141">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="0f09c-142">La instrucción SQL debe devolver un conjunto que consta de filas y columnas de resultados.</span><span class="sxs-lookup"><span data-stu-id="0f09c-142">The SQL statement must return a result set consisting of rows and columns.</span></span> <span data-ttu-id="0f09c-143">Solo si hay una fila, la instrucción SQL especificada para el **PollingStatement** se ejecutará el enlace de propiedad.</span><span class="sxs-lookup"><span data-stu-id="0f09c-143">Only if a row is available, the SQL statement specified for the **PollingStatement** binding property will be executed.</span></span>                                                                                                                                            |
|   <span data-ttu-id="0f09c-144">**PollingIntervalInSeconds**</span><span class="sxs-lookup"><span data-stu-id="0f09c-144">**PollingIntervalInSeconds**</span></span>   |                                                                              <span data-ttu-id="0f09c-145">Especifica el intervalo, en segundos, en el que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejecuta la instrucción especificada para el **PolledDataAvailableStatement** enlaza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="0f09c-145">Specifies the interval, in seconds, at which the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="0f09c-146">El valor predeterminado es 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="0f09c-146">The default is 30 seconds.</span></span> <span data-ttu-id="0f09c-147">El intervalo de sondeo determina el intervalo de tiempo entre sondeos sucesivos.</span><span class="sxs-lookup"><span data-stu-id="0f09c-147">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="0f09c-148">Si la instrucción se ejecuta en el intervalo especificado, el adaptador espera el tiempo restante en el intervalo.</span><span class="sxs-lookup"><span data-stu-id="0f09c-148">If the statement is executed within the specified interval, the adapter waits for the remaining time in the interval.</span></span>                                                                              |
|       <span data-ttu-id="0f09c-149">**PollingStatement**</span><span class="sxs-lookup"><span data-stu-id="0f09c-149">**PollingStatement**</span></span>       | <span data-ttu-id="0f09c-150">Especifica la instrucción SQL para sondear la tabla de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0f09c-150">Specifies the SQL statement to poll the SQL Server database table.</span></span> <span data-ttu-id="0f09c-151">Puede especificar una instrucción SELECT simple o un procedimiento almacenado para la instrucción de sondeo.</span><span class="sxs-lookup"><span data-stu-id="0f09c-151">You can specify a simple SELECT statement or a stored procedure for the polling statement.</span></span> <span data-ttu-id="0f09c-152">El valor predeterminado es null.</span><span class="sxs-lookup"><span data-stu-id="0f09c-152">The default is null.</span></span> <span data-ttu-id="0f09c-153">Debe especificar un valor para **PollingStatement** para habilitar el sondeo.</span><span class="sxs-lookup"><span data-stu-id="0f09c-153">You must specify a value for **PollingStatement** to enable polling.</span></span> <span data-ttu-id="0f09c-154">Se ejecuta la instrucción de sondeo solo si hay datos disponibles para el sondeo, que viene determinado por la **PolledDataAvailableStatement** enlaza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="0f09c-154">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="0f09c-155">Puede especificar cualquier número de instrucciones SQL separadas por punto y coma.</span><span class="sxs-lookup"><span data-stu-id="0f09c-155">You can specify any number of SQL statements separated by a semi-colon.</span></span> <span data-ttu-id="0f09c-156">**Importante:** para **TypedPolling**, debe especificar esta propiedad de enlace antes de generar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="0f09c-156">**Important:**  For **TypedPolling**, you must specify this binding property before generating metadata.</span></span> |
|      <span data-ttu-id="0f09c-157">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="0f09c-157">**PollWhileDataFound**</span></span>      |                                                                                 <span data-ttu-id="0f09c-158">Especifica si el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] pasa por alto el intervalo de sondeo y continuamente se ejecuta la instrucción SQL especificada para el **PolledDataAvailableStatement** enlaza la propiedad, si hay datos disponibles en la tabla que se sondea.</span><span class="sxs-lookup"><span data-stu-id="0f09c-158">Specifies whether the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ignores the polling interval and continuously executes the SQL statement specified for the **PolledDataAvailableStatement** binding property, if data is available in the table being polled.</span></span> <span data-ttu-id="0f09c-159">Si no hay datos disponibles en la tabla, el adaptador vuelve para ejecutar la instrucción SQL en el intervalo de sondeo especificado.</span><span class="sxs-lookup"><span data-stu-id="0f09c-159">If no data is available in the table, the adapter reverts to execute the SQL statement at the specified polling interval.</span></span> <span data-ttu-id="0f09c-160">El valor predeterminado es **false**.</span><span class="sxs-lookup"><span data-stu-id="0f09c-160">Default is **false**.</span></span>                                                                                 |

 <span data-ttu-id="0f09c-161">Para obtener una descripción más completa de estas propiedades, vea [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="0f09c-161">For a more complete description of these properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="0f09c-162">Para obtener una descripción completa de cómo usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para sondear SQL Server, siga leyendo.</span><span class="sxs-lookup"><span data-stu-id="0f09c-162">For a complete description of how to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to poll SQL Server, read further.</span></span>  

## <a name="configure-strongly-typed-polling-in-the-wcf-service-model"></a><span data-ttu-id="0f09c-163">Configuración de sondeo fuertemente tipado en el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="0f09c-163">Configure Strongly-typed Polling in the WCF Service Model</span></span>  
 <span data-ttu-id="0f09c-164">Para recibir el **sondeo** operación cuando se usa el modelo de servicio WCF, debe:</span><span class="sxs-lookup"><span data-stu-id="0f09c-164">To receive the **Polling** operation when you use the WCF service model, you must:</span></span>  

1. <span data-ttu-id="0f09c-165">Generar un contrato de servicio WCF (interfaz) para el **TypedPolling** operación desde los metadatos expuestos por el adaptador.</span><span class="sxs-lookup"><span data-stu-id="0f09c-165">Generate a WCF service contract (interface) for the **TypedPolling** operation from the metadata exposed by the adapter.</span></span> <span data-ttu-id="0f09c-166">Para ello, puede usar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f09c-166">To do this, you could use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span> <span data-ttu-id="0f09c-167">Al generar el contrato de servicio WCF para este ejemplo, asegúrese de que:</span><span class="sxs-lookup"><span data-stu-id="0f09c-167">While generating the WCF service contract for this example, make sure:</span></span>  

   -   <span data-ttu-id="0f09c-168">Especifique el **InboundID** como **empleado**.</span><span class="sxs-lookup"><span data-stu-id="0f09c-168">You specify the **InboundID** as **Employee**.</span></span>  

   -   <span data-ttu-id="0f09c-169">Especifique una instrucción de sondeo para el **PollingStatement** enlaza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="0f09c-169">You specify a polling statement for the **PollingStatement** binding property.</span></span> <span data-ttu-id="0f09c-170">En este ejemplo, especifique la instrucción de sondeo como:</span><span class="sxs-lookup"><span data-stu-id="0f09c-170">For this example, specify the polling statement as:</span></span>  

       ```  
       SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000  
       ```  

2. <span data-ttu-id="0f09c-171">Implementar un servicio WCF desde esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="0f09c-171">Implement a WCF service from this interface.</span></span>  

3. <span data-ttu-id="0f09c-172">Hospedar este servicio WCF mediante un host de servicio (**System.ServiceModel.ServiceHost**).</span><span class="sxs-lookup"><span data-stu-id="0f09c-172">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  

## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="0f09c-173">Acerca de los ejemplos usados en este tema.</span><span class="sxs-lookup"><span data-stu-id="0f09c-173">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="0f09c-174">Los ejemplos de este tema sondean la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="0f09c-174">The examples in this topic poll the Employee table.</span></span> <span data-ttu-id="0f09c-175">El ejemplo también usa el MOVE_EMP_DATA y ADD_EMP_DETAILS procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="0f09c-175">The example also uses the MOVE_EMP_DATA and ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="0f09c-176">Una secuencia de comandos para generar estos artefactos se suministra con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="0f09c-176">A script to generate these artifacts is supplied with the samples.</span></span> <span data-ttu-id="0f09c-177">Para obtener más información acerca de los ejemplos, vea [ejemplos del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="0f09c-177">For more information about the samples, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span> <span data-ttu-id="0f09c-178">Un ejemplo, **TypedPolling_ServiceModel**, que se basa en este tema, también se proporciona con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="0f09c-178">A sample, **TypedPolling_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  

## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="0f09c-179">El contrato de servicio WCF y la clase</span><span class="sxs-lookup"><span data-stu-id="0f09c-179">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="0f09c-180">Puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para crear un contrato de servicio WCF (interfaz) y la compatibilidad con las clases para el **TypedPolling** operación.</span><span class="sxs-lookup"><span data-stu-id="0f09c-180">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **TypedPolling** operation.</span></span> <span data-ttu-id="0f09c-181">Para obtener más información acerca de cómo generar un contrato de servicio WCF, vea [generar un cliente de WCF o un contrato de servicio WCF para artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="0f09c-181">For more information about generating a WCF service contract, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  

### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="0f09c-182">El contrato de servicio WCF (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f09c-182">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="0f09c-183">El código siguiente muestra el contrato de servicio WCF (interfaz) generado para el **TypedPolling** operación.</span><span class="sxs-lookup"><span data-stu-id="0f09c-183">The following code shows the WCF service contract (interface) generated for the **TypedPolling** operation.</span></span>  

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

### <a name="the-message-contracts"></a><span data-ttu-id="0f09c-184">Los contratos de mensaje</span><span class="sxs-lookup"><span data-stu-id="0f09c-184">The Message Contracts</span></span>  
 <span data-ttu-id="0f09c-185">El espacio de nombres de contrato de mensaje se modifica mediante la **InboundID** parámetro en la conexión URI, si se especifica.</span><span class="sxs-lookup"><span data-stu-id="0f09c-185">The message contract namespace is modified by the **InboundID** parameter in the connection URI, if specified.</span></span> <span data-ttu-id="0f09c-186">En este ejemplo, se especifica el identificador de entrada como **empleado**.</span><span class="sxs-lookup"><span data-stu-id="0f09c-186">In this example, you specified the inbound ID as **Employee**.</span></span> <span data-ttu-id="0f09c-187">El mensaje de solicitud devuelve un conjunto de resultados fuertemente tipado.</span><span class="sxs-lookup"><span data-stu-id="0f09c-187">The request message returns a strongly-typed result set.</span></span>  

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

### <a name="wcf-service-class"></a><span data-ttu-id="0f09c-188">Clase de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="0f09c-188">WCF Service Class</span></span>  
 <span data-ttu-id="0f09c-189">El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] también genera un archivo que tiene un código auxiliar para la clase de servicio WCF implementa el contrato de servicio (interfaz).</span><span class="sxs-lookup"><span data-stu-id="0f09c-189">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="0f09c-190">El nombre del archivo es SqlAdapterBindingService.cs.</span><span class="sxs-lookup"><span data-stu-id="0f09c-190">The name of the file is SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="0f09c-191">Puede insertar la lógica para procesar el **TypedPolling** operación directamente en esta clase.</span><span class="sxs-lookup"><span data-stu-id="0f09c-191">You can insert the logic to process the **TypedPolling** operation directly into this class.</span></span> <span data-ttu-id="0f09c-192">El código siguiente muestra la clase de servicio WCF generada por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f09c-192">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  

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

## <a name="receive-strongly-typed-inbound-messages-for-polling-operation"></a><span data-ttu-id="0f09c-193">Recibir los mensajes entrantes fuertemente tipados para la operación de sondeo</span><span class="sxs-lookup"><span data-stu-id="0f09c-193">Receive Strongly-typed Inbound Messages for Polling Operation</span></span>  
 <span data-ttu-id="0f09c-194">Esta sección proporciona instrucciones sobre cómo escribir una aplicación .NET para recibir mensajes de entrada de sondeo fuertemente tipado mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f09c-194">This section provides instructions on how to write a .NET application to receive strongly-typed inbound polling messages using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

1. <span data-ttu-id="0f09c-195">Use la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar un contrato de servicio WCF (interfaz) y clases auxiliares para el **TypedPolling** operación.</span><span class="sxs-lookup"><span data-stu-id="0f09c-195">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **TypedPolling** operation.</span></span> <span data-ttu-id="0f09c-196">Asegúrese de que se especifique lo siguiente al generar el contrato de servicio WCF para este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0f09c-196">Make sure you specify the following while generating the WCF service contract for this example:</span></span>  

   - <span data-ttu-id="0f09c-197">Debe especificar el **InboundID** como **empleado**.</span><span class="sxs-lookup"><span data-stu-id="0f09c-197">You must specify the **InboundID** as **Employee**.</span></span>  

   - <span data-ttu-id="0f09c-198">Debe especificar una instrucción de sondeo para el **PollingStatement** enlaza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="0f09c-198">You must specify a polling statement for the **PollingStatement** binding property.</span></span> <span data-ttu-id="0f09c-199">En este ejemplo, especifique la instrucción de sondeo como:</span><span class="sxs-lookup"><span data-stu-id="0f09c-199">For this example, specify the polling statement as:</span></span>  

     ```  
     SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000  
     ```  

     <span data-ttu-id="0f09c-200">Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF para artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="0f09c-200">For more information, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span> <span data-ttu-id="0f09c-201">También puede especificar las propiedades de enlace al generar las clases auxiliares y de contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="0f09c-201">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="0f09c-202">Esto garantiza que están establecidas correctamente en el archivo de configuración generado.</span><span class="sxs-lookup"><span data-stu-id="0f09c-202">This guarantees that they are properly set in the generated configuration file.</span></span>  

2. <span data-ttu-id="0f09c-203">Implementar un servicio WCF desde las clases auxiliares y la interfaz generada en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="0f09c-203">Implement a WCF service from the interface and helper classes generated in step 1.</span></span> <span data-ttu-id="0f09c-204">El **TypedPolling** método de esta clase puede producir una excepción para anular la transacción de sondeo, si se produce un error de procesamiento de los datos recibidos de la **TypedPolling** operación; de lo contrario el método no devuelve nada.</span><span class="sxs-lookup"><span data-stu-id="0f09c-204">The **TypedPolling** method of this class can throw an exception to abort the polling transaction, if an error is encountered processing the data received from the **TypedPolling** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="0f09c-205">Debe atributo la clase de servicio WCF como sigue:</span><span class="sxs-lookup"><span data-stu-id="0f09c-205">You must attribute the WCF service class as follows:</span></span>  

   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  

    <span data-ttu-id="0f09c-206">Dentro de la **TypedPolling** método, puede implementar la lógica de aplicación directamente.</span><span class="sxs-lookup"><span data-stu-id="0f09c-206">Within the **TypedPolling** method, you can implement your application logic directly.</span></span> <span data-ttu-id="0f09c-207">Esta clase puede encontrarse en SqlAdapterBindingService.cs.</span><span class="sxs-lookup"><span data-stu-id="0f09c-207">This class can be found in SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="0f09c-208">Este código en este ejemplo Sub clases el **SqlAdapterBindingService** clase.</span><span class="sxs-lookup"><span data-stu-id="0f09c-208">This code in this example sub-classes the **SqlAdapterBindingService** class.</span></span> <span data-ttu-id="0f09c-209">En este código, se escribe el mensaje de sondeo recibido como un conjunto de resultados fuertemente tipados a la consola.</span><span class="sxs-lookup"><span data-stu-id="0f09c-209">In this code, the polling message received as a strongly-typed result set is written to the console.</span></span>  

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

3. <span data-ttu-id="0f09c-210">Dado que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no acepta credenciales como parte de la URI de conexión, debe implementar la siguiente clase para pasar las credenciales para la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0f09c-210">Because the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not accept credentials as part of the connection URI, you must implement the following class to pass credentials for the SQL Server database.</span></span> <span data-ttu-id="0f09c-211">En la última parte de la aplicación, se creará instancias de esta clase para pasar las credenciales de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0f09c-211">In the latter part of the application, you will instantiate this class to pass on the SQL Server credentials.</span></span>  

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

4. <span data-ttu-id="0f09c-212">Crear un **SqlAdapterBinding** y configurar la operación de sondeo mediante la especificación de las propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="0f09c-212">Create a **SqlAdapterBinding** and configure the polling operation by specifying the binding properties.</span></span> <span data-ttu-id="0f09c-213">Puede hacerlo explícitamente en el código o mediante declaración en configuración.</span><span class="sxs-lookup"><span data-stu-id="0f09c-213">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="0f09c-214">Como mínimo, debe especificar el **InboundOperationType**, **PolledDataAvailableStatement**, y **PollingStatement**.</span><span class="sxs-lookup"><span data-stu-id="0f09c-214">At a minimum, you must specify the **InboundOperationType**, **PolledDataAvailableStatement**, and **PollingStatement**.</span></span>  

   ```  
   SqlAdapterBinding binding = new SqlAdapterBinding();  
   binding.InboundOperationType = InboundOperation.TypedPolling;  
   binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
   binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
   ```  

5. <span data-ttu-id="0f09c-215">Especifique las credenciales de base de datos de SQL Server creando el **PollingCredentials** clase creada en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="0f09c-215">Specify SQL Server database credentials by instantiating the **PollingCredentials** class you created in Step 3.</span></span>  

   ```  
   PollingCredentials credentials = new PollingCredentials();  
   credentials.UserName.UserName = "<Enter user name here>";  
   credentials.UserName.Password = "<Enter password here>";  
   ```  

6. <span data-ttu-id="0f09c-216">Cree una instancia del servicio WCF que creó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="0f09c-216">Create an instance of the WCF service created in step 2.</span></span>  

   ```  
   // create service instance  
   PollingService service = new PollingService();  
   ```  

7. <span data-ttu-id="0f09c-217">Cree una instancia de **System.ServiceModel.ServiceHost** mediante el servicio de WCF y un URI de conexión de base.</span><span class="sxs-lookup"><span data-stu-id="0f09c-217">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="0f09c-218">El URI de conexión base no puede contener el identificador entrante.</span><span class="sxs-lookup"><span data-stu-id="0f09c-218">The base connection URI cannot contain the inbound ID.</span></span> <span data-ttu-id="0f09c-219">También debe especificar las credenciales aquí.</span><span class="sxs-lookup"><span data-stu-id="0f09c-219">You must also specify the credentials here.</span></span>  

   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
   ServiceHost serviceHost = new ServiceHost(service, baseUri);  
   serviceHost.Description.Behaviors.Add(credentials);  

   ```  

8. <span data-ttu-id="0f09c-220">Agregar un extremo de servicio al host de servicio.</span><span class="sxs-lookup"><span data-stu-id="0f09c-220">Add a service endpoint to the service host.</span></span> <span data-ttu-id="0f09c-221">Para hacerlo:</span><span class="sxs-lookup"><span data-stu-id="0f09c-221">To do this:</span></span>  

   -   <span data-ttu-id="0f09c-222">Utilice el enlace creado en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="0f09c-222">Use the binding created in step 4.</span></span>  

   -   <span data-ttu-id="0f09c-223">Especifique un URI que contiene las credenciales de conexión y, si es necesario, un identificador de entrada.</span><span class="sxs-lookup"><span data-stu-id="0f09c-223">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  

   -   <span data-ttu-id="0f09c-224">Especifique el contrato como "TypedPolling_Employee".</span><span class="sxs-lookup"><span data-stu-id="0f09c-224">Specify the contract as "TypedPolling_Employee".</span></span>  

   ```  
   // Add service endpoint: be sure to specify TypedPolling_Employee as the contract  
   Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?InboundID=Employee");  
   serviceHost.AddServiceEndpoint("TypedPolling_Employee", binding, ConnectionUri);  
   ```  

9. <span data-ttu-id="0f09c-225">Para recibir datos de sondeo, abra el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="0f09c-225">To receive polling data, open the service host.</span></span> <span data-ttu-id="0f09c-226">El adaptador devolverá datos cada vez que la consulta devuelve un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="0f09c-226">The adapter will return data whenever the query returns a result set.</span></span>  

    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  

10. <span data-ttu-id="0f09c-227">Para finalizar el sondeo, cierre el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="0f09c-227">To terminate polling, close the service host.</span></span>  

    > [!IMPORTANT]
    >  <span data-ttu-id="0f09c-228">El adaptador seguirá sondeando hasta que se cierra el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="0f09c-228">The adapter will continue to poll until the service host is closed.</span></span>  

    ```  
    serviceHost.Close();  
    ```  

### <a name="example"></a><span data-ttu-id="0f09c-229">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0f09c-229">Example</span></span>  
 <span data-ttu-id="0f09c-230">El ejemplo siguiente muestra una consulta de sondeo que se ejecuta en la tabla Employee.</span><span class="sxs-lookup"><span data-stu-id="0f09c-230">The following example shows a polling query that executes the Employee table.</span></span> <span data-ttu-id="0f09c-231">La instrucción de sondeo lleva a cabo las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="0f09c-231">The polling statement performs the following tasks:</span></span>  

1. <span data-ttu-id="0f09c-232">Selecciona todos los registros de la tabla Employee.</span><span class="sxs-lookup"><span data-stu-id="0f09c-232">Selects all the records from the Employee table.</span></span>  

2. <span data-ttu-id="0f09c-233">Ejecuta el procedimiento MOVE_EMP_DATA almacenado para mover todos los registros de la tabla Employee a HistorialEmpleados tabla.</span><span class="sxs-lookup"><span data-stu-id="0f09c-233">Executes the MOVE_EMP_DATA stored procedure to move all records from Employee table to EmployeeHistory table.</span></span>  

3. <span data-ttu-id="0f09c-234">Ejecuta el procedimiento almacenado de ADD_EMP_DETAILS para agregar un único registro a la tabla Employee.</span><span class="sxs-lookup"><span data-stu-id="0f09c-234">Executes the ADD_EMP_DETAILS stored procedure to add a single record to the Employee table.</span></span>  

   <span data-ttu-id="0f09c-235">El primer mensaje de sondeo contendrá todos los registros de la tabla Employee.</span><span class="sxs-lookup"><span data-stu-id="0f09c-235">The first polling message will contain all the records from the Employee table.</span></span> <span data-ttu-id="0f09c-236">Los mensajes de sondeo subsiguiente contendrá solo el último registro insertado por el procedimiento almacenado de ADD_EMP_DETAILS.</span><span class="sxs-lookup"><span data-stu-id="0f09c-236">The subsequent polling messages will contain only the last record inserted by the ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="0f09c-237">El adaptador seguirá sondeando hasta que cierre el host de servicio presionando `<RETURN>`.</span><span class="sxs-lookup"><span data-stu-id="0f09c-237">The adapter will continue to poll until you close the service host by pressing `<RETURN>`.</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="0f09c-238">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f09c-238">See Also</span></span>  
 [<span data-ttu-id="0f09c-239">Sondear el servidor SQL mediante el adaptador de SQL con el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="0f09c-239">Poll SQL Server using the SQL Adapter with WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)
