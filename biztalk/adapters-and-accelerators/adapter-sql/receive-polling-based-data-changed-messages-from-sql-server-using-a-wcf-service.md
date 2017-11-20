---
title: Recibir mensajes de cambio de datos basado en sondeo de SQL Server mediante el modelo de servicio WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8713dd38-65ff-4d89-b23b-a93c06c5ff22
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ff5ca099733a59fc5aa64c9ebbe261375f1a488
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-polling-based-data-changed-messages-from-sql-server-using-the-wcf-service-model"></a><span data-ttu-id="1903b-102">Recibir mensajes de cambio de datos basado en sondeo de SQL Server mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="1903b-102">Receive Polling-based Data-changed Messages from SQL Server Using the WCF Service Model</span></span>
<span data-ttu-id="1903b-103">Puede configurar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir mensajes de cambio de datos periódicos para SQL Server tablas o vistas.</span><span class="sxs-lookup"><span data-stu-id="1903b-103">You can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive periodic data-change messages for SQL Server tables or views.</span></span> <span data-ttu-id="1903b-104">Puede especificar una instrucción de sondeo que el adaptador se ejecuta para sondear la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1903b-104">You can specify a polling statement that the adapter executes to poll the database.</span></span> <span data-ttu-id="1903b-105">La instrucción de sondeo puede ser una instrucción SELECT o un procedimiento almacenado que devuelve un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="1903b-105">The polling statement can be a SELECT statement or a stored procedure that returns a result set.</span></span>  
  
 <span data-ttu-id="1903b-106">Para obtener más información sobre cómo el adaptador admite el sondeo, consulte [sondeo en SQL Server mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/polling-in-sql-server-using-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="1903b-106">For more information on how the adapter supports polling, see [Polling in SQL Server using the SQL adapter](../../adapters-and-accelerators/adapter-sql/polling-in-sql-server-using-the-sql-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1903b-107">Este tema muestra cómo utilizar el **sondeo** operación usar los mensajes de sondeo de entrada.</span><span class="sxs-lookup"><span data-stu-id="1903b-107">This topic demonstrates how to use the **Polling** inbound operation to use polling messages.</span></span> <span data-ttu-id="1903b-108">El mensaje para la operación de sondeo no es fuertemente tipada.</span><span class="sxs-lookup"><span data-stu-id="1903b-108">The message for the Polling operation is not strongly-typed.</span></span> <span data-ttu-id="1903b-109">Si desea obtener el mensaje de sondeo fuertemente tipado, debe utilizar el **TypedPolling** operación.</span><span class="sxs-lookup"><span data-stu-id="1903b-109">If you want to get strongly-typed polling message, you must use the **TypedPolling** operation.</span></span> <span data-ttu-id="1903b-110">También debe utilizar el **TypedPolling** operación tener varias operaciones de sondeo en una sola aplicación.</span><span class="sxs-lookup"><span data-stu-id="1903b-110">You must also use the **TypedPolling** operation to have multiple polling operations in a single application.</span></span> <span data-ttu-id="1903b-111">Para obtener instrucciones sobre cómo realizar **TypedPolling** operación, vea [recibir fuertemente tipada basado en sondeo mensajes de cambio de datos de modelo de servicio de WCF de uso de SQL Server](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-sql-messages-with-wcf-service.md).</span><span class="sxs-lookup"><span data-stu-id="1903b-111">For instructions on how to perform **TypedPolling** operation, see [Receive Strongly-typed Polling-based Data-changed Messages from SQL Server Using WCF Service Model](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-sql-messages-with-wcf-service.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1903b-112">Si desea tener más de un sondeo operación en una sola aplicación, debe especificar un **InboundID** propiedad de conexión como parte de la conexión de URI para que sea único.</span><span class="sxs-lookup"><span data-stu-id="1903b-112">If you want to have more than one polling operation in a single application, you must specify an **InboundID** connection property as part of the connection URI to make it unique.</span></span> <span data-ttu-id="1903b-113">Especifica el identificador de entrada se agrega al espacio de nombres de operación para hacerlo único.</span><span class="sxs-lookup"><span data-stu-id="1903b-113">The inbound ID you specify is added to the operation namespace to make it unique.</span></span>  
  
## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="1903b-114">Cómo este tema muestra el sondeo</span><span class="sxs-lookup"><span data-stu-id="1903b-114">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="1903b-115">En este tema, para demostrar cómo [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] admite la recepción de datos de los mensajes de cambio, crear una aplicación .NET y generará el contrato de servicio WCF para la **sondeo** operación.</span><span class="sxs-lookup"><span data-stu-id="1903b-115">In this topic, to demonstrate how the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports receiving data change messages, create a .NET application and generate the WCF service contract for the **Polling** operation.</span></span> <span data-ttu-id="1903b-116">Si desea especificar el sondeo relacionados con propiedades de enlace al generar el contrato de servicio WCF, especifique la **PolledDataAvailableStatement** como:</span><span class="sxs-lookup"><span data-stu-id="1903b-116">If you want to specify the polling related binding properties while generating the WCF service contract, specify the **PolledDataAvailableStatement** as:</span></span>  
  
```  
SELECT COUNT(*) FROM Employee  
```  
  
 <span data-ttu-id="1903b-117">El **PolledDataAvailableStatement** debe devolver un conjunto de resultados con la primera celda que contiene un valor positivo.</span><span class="sxs-lookup"><span data-stu-id="1903b-117">The **PolledDataAvailableStatement** must return a result set with the first cell containing a positive value.</span></span> <span data-ttu-id="1903b-118">Si la primera celda no contiene un valor positivo, el adaptador no ejecuta la instrucción de sondeo.</span><span class="sxs-lookup"><span data-stu-id="1903b-118">If the first cell does not contain a positive value, the adapter does not execute the polling statement.</span></span>  
  
 <span data-ttu-id="1903b-119">Como parte de la instrucción de sondeo, realice las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="1903b-119">As part of the polling statement, perform the following operations:</span></span>  
  
1.  <span data-ttu-id="1903b-120">Seleccione todas las filas de la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="1903b-120">Select all the rows from the Employee table.</span></span>  
  
2.  <span data-ttu-id="1903b-121">Ejecutar un procedimiento almacenado (MOVE_EMP_DATA) para mover todos los registros de la tabla de empleados a una tabla HistorialEmpleados.</span><span class="sxs-lookup"><span data-stu-id="1903b-121">Execute a stored procedure (MOVE_EMP_DATA) to move all the records from the Employee table to an EmployeeHistory table.</span></span>  
  
3.  <span data-ttu-id="1903b-122">Ejecutar un procedimiento almacenado (ADD_EMP_DETAILS) para agregar un nuevo registro a la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="1903b-122">Execute a stored procedure (ADD_EMP_DETAILS) to add a new record to the Employee table.</span></span> <span data-ttu-id="1903b-123">Este procedimiento toma el nombre de empleado, designación y salario como parámetros.</span><span class="sxs-lookup"><span data-stu-id="1903b-123">This procedure takes the employee name, designation, and salary as parameters.</span></span>  
  
 <span data-ttu-id="1903b-124">Para llevar a cabo estas operaciones, debe especificar lo siguiente para el **PollingStatement** propiedad de enlace:</span><span class="sxs-lookup"><span data-stu-id="1903b-124">To perform these operations, you must specify the following for the **PollingStatement** binding property:</span></span>  
  
```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  
  
 <span data-ttu-id="1903b-125">Después de ejecuta la instrucción de sondeo, se seleccionan todos los registros de la tabla de empleados y se recibe el mensaje de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1903b-125">After the polling statement is executed, all the records from the Employee table are selected and the message from SQL Server is received.</span></span> <span data-ttu-id="1903b-126">Después de ejecuta el procedimiento almacenado de MOVE_EMP_DATA por el adaptador, todos los registros se mueven a la tabla HistorialEmpleados.</span><span class="sxs-lookup"><span data-stu-id="1903b-126">After the MOVE_EMP_DATA stored procedure is executed by the adapter, all the records are moved to the EmployeeHistory table.</span></span> <span data-ttu-id="1903b-127">A continuación, se ejecuta el procedimiento almacenado de ADD_EMP_DETAILS para agregar un nuevo registro a la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="1903b-127">Then, the ADD_EMP_DETAILS stored procedure is executed to add a new record to the Employee table.</span></span> <span data-ttu-id="1903b-128">La siguiente ejecución de sondeo solo devolverá un único registro.</span><span class="sxs-lookup"><span data-stu-id="1903b-128">The next polling execution will only return a single record.</span></span> <span data-ttu-id="1903b-129">Este ciclo continúa hasta que se cierra el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="1903b-129">This cycle continues until you close the service host.</span></span>  
  
## <a name="configuring-a-polling-query-with-the-sql-adapter-binding-properties"></a><span data-ttu-id="1903b-130">Configuración de una consulta de sondeo con el adaptador de SQL propiedades de enlace</span><span class="sxs-lookup"><span data-stu-id="1903b-130">Configuring a Polling Query with the SQL Adapter Binding Properties</span></span>  
 <span data-ttu-id="1903b-131">La siguiente tabla resume el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] propiedades de enlace que se utiliza para configurar el adaptador para recibir mensajes de cambio de datos.</span><span class="sxs-lookup"><span data-stu-id="1903b-131">The following table summarizes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding properties that you use to configure the adapter to receive data-change messages.</span></span> <span data-ttu-id="1903b-132">Debe especificar estas propiedades de enlace como parte de la aplicación .NET para el sondeo.</span><span class="sxs-lookup"><span data-stu-id="1903b-132">You must specify these binding properties as part of the .NET application for polling.</span></span>  
  
|<span data-ttu-id="1903b-133">Propiedad de enlace</span><span class="sxs-lookup"><span data-stu-id="1903b-133">Binding Property</span></span>|<span data-ttu-id="1903b-134">Description</span><span class="sxs-lookup"><span data-stu-id="1903b-134">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="1903b-135">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="1903b-135">**InboundOperationType**</span></span>|<span data-ttu-id="1903b-136">Especifica si desea realizar **sondeo**, **TypedPolling**, o **notificación** operación entrante.</span><span class="sxs-lookup"><span data-stu-id="1903b-136">Specifies whether you want to perform **Polling**, **TypedPolling**, or **Notification** inbound operation.</span></span> <span data-ttu-id="1903b-137">Valor predeterminado es **sondeo**.</span><span class="sxs-lookup"><span data-stu-id="1903b-137">Default is **Polling**.</span></span>|  
|<span data-ttu-id="1903b-138">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="1903b-138">**PolledDataAvailableStatement**</span></span>|<span data-ttu-id="1903b-139">Especifica la instrucción SQL que se ejecuta el adaptador para determinar si los datos están disponibles para el sondeo.</span><span class="sxs-lookup"><span data-stu-id="1903b-139">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="1903b-140">La instrucción SQL debe devolver un conjunto que consta de filas y columnas de resultados.</span><span class="sxs-lookup"><span data-stu-id="1903b-140">The SQL statement must return a result set consisting of rows and columns.</span></span> <span data-ttu-id="1903b-141">Solo si una fila está disponible, la instrucción SQL especificada para el **PollingStatement** se va a ejecutar la propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="1903b-141">Only if a row is available, the SQL statement specified for the **PollingStatement** binding property will be executed.</span></span>|  
|<span data-ttu-id="1903b-142">**PollingIntervalInSeconds**</span><span class="sxs-lookup"><span data-stu-id="1903b-142">**PollingIntervalInSeconds**</span></span>|<span data-ttu-id="1903b-143">Especifica el intervalo, en segundos, en el que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se ejecuta la instrucción especificada para la **PolledDataAvailableStatement** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="1903b-143">Specifies the interval, in seconds, at which the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="1903b-144">El valor predeterminado es 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="1903b-144">The default is 30 seconds.</span></span> <span data-ttu-id="1903b-145">El intervalo de sondeo determina el intervalo de tiempo entre sondeos sucesivos.</span><span class="sxs-lookup"><span data-stu-id="1903b-145">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="1903b-146">Si la instrucción se ejecuta en el intervalo especificado, el adaptador espera el tiempo restante en el intervalo.</span><span class="sxs-lookup"><span data-stu-id="1903b-146">If the statement is executed within the specified interval, the adapter waits for the remaining time in the interval.</span></span>|  
|<span data-ttu-id="1903b-147">**PollingStatement**</span><span class="sxs-lookup"><span data-stu-id="1903b-147">**PollingStatement**</span></span>|<span data-ttu-id="1903b-148">Especifica la instrucción SQL para sondear la tabla de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1903b-148">Specifies the SQL statement to poll the SQL Server database table.</span></span> <span data-ttu-id="1903b-149">Puede especificar una instrucción SELECT simple o un procedimiento almacenado para la instrucción de sondeo.</span><span class="sxs-lookup"><span data-stu-id="1903b-149">You can specify a simple SELECT statement or a stored procedure for the polling statement.</span></span> <span data-ttu-id="1903b-150">El valor predeterminado es null.</span><span class="sxs-lookup"><span data-stu-id="1903b-150">The default is null.</span></span> <span data-ttu-id="1903b-151">Debe especificar un valor para **PollingStatement** para habilitar el sondeo.</span><span class="sxs-lookup"><span data-stu-id="1903b-151">You must specify a value for **PollingStatement** to enable polling.</span></span> <span data-ttu-id="1903b-152">Se ejecuta la instrucción de sondeo solo si hay datos disponibles para el sondeo, que viene determinado por la **PolledDataAvailableStatement** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="1903b-152">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="1903b-153">Puede especificar cualquier número de instrucciones SQL separados por un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="1903b-153">You can specify any number of SQL statements separated by a semi-colon.</span></span>|  
|<span data-ttu-id="1903b-154">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="1903b-154">**PollWhileDataFound**</span></span>|<span data-ttu-id="1903b-155">Especifica si el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] pasa por alto el intervalo de sondeo y ejecuta continuamente la instrucción SQL especificada para el **PolledDataAvailableStatement** enlaza la propiedad, si los datos están disponibles en la tabla que se va a sondear.</span><span class="sxs-lookup"><span data-stu-id="1903b-155">Specifies whether the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ignores the polling interval and continuously executes the SQL statement specified for the **PolledDataAvailableStatement** binding property, if data is available in the table being polled.</span></span> <span data-ttu-id="1903b-156">Si no hay datos disponibles en la tabla, el adaptador vuelve para ejecutar la instrucción SQL en el intervalo de sondeo especificado.</span><span class="sxs-lookup"><span data-stu-id="1903b-156">If no data is available in the table, the adapter reverts to execute the SQL statement at the specified polling interval.</span></span> <span data-ttu-id="1903b-157">Valor predeterminado es **false**.</span><span class="sxs-lookup"><span data-stu-id="1903b-157">Default is **false**.</span></span>|  
  
 <span data-ttu-id="1903b-158">Para obtener una descripción más completa de estas propiedades, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="1903b-158">For a more complete description of these properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="1903b-159">Para obtener una descripción completa de cómo usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para sondear SQL Server, seguir leyendo.</span><span class="sxs-lookup"><span data-stu-id="1903b-159">For a complete description of how to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to poll SQL Server, read further.</span></span>  
  
## <a name="configuring-polling-in-the-wcf-service-model"></a><span data-ttu-id="1903b-160">Configuración de sondeo en el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="1903b-160">Configuring Polling in the WCF Service Model</span></span>  
 <span data-ttu-id="1903b-161">Para recibir el **sondeo** operación cuando se usa el modelo de servicio WCF, debe:</span><span class="sxs-lookup"><span data-stu-id="1903b-161">To receive the **Polling** operation when you use the WCF service model, you must:</span></span>  
  
1.  <span data-ttu-id="1903b-162">Generar un contrato de servicio WCF (interfaz) para la **sondeo** operación desde los metadatos expuestos por el adaptador.</span><span class="sxs-lookup"><span data-stu-id="1903b-162">Generate a WCF service contract (interface) for the **Polling** operation from the metadata exposed by the adapter.</span></span> <span data-ttu-id="1903b-163">Para ello, puede usar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1903b-163">To do this, you could use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span>  
  
2.  <span data-ttu-id="1903b-164">Implementar un servicio WCF de esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="1903b-164">Implement a WCF service from this interface.</span></span>  
  
3.  <span data-ttu-id="1903b-165">Hospedar este servicio WCF mediante un host de servicio (**System.ServiceModel.ServiceHost**).</span><span class="sxs-lookup"><span data-stu-id="1903b-165">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="1903b-166">Acerca de los ejemplos usados en este tema</span><span class="sxs-lookup"><span data-stu-id="1903b-166">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="1903b-167">Los ejemplos de este tema sondean la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="1903b-167">The examples in this topic poll the Employee table.</span></span> <span data-ttu-id="1903b-168">El ejemplo también usa MOVE_EMP_DATA y ADD_EMP_DETAILS procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="1903b-168">The example also uses the MOVE_EMP_DATA and ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="1903b-169">Una secuencia de comandos para generar estos artefactos se suministra con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="1903b-169">A script to generate these artifacts is supplied with the samples.</span></span> <span data-ttu-id="1903b-170">Para obtener más información acerca de los ejemplos, vea [ejemplos del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="1903b-170">For more information about the samples, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span> <span data-ttu-id="1903b-171">Obtener un ejemplo, **Polling_ServiceModel**, que se basa en este tema, también se proporciona con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="1903b-171">A sample, **Polling_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="1903b-172">El contrato de servicio WCF y la clase</span><span class="sxs-lookup"><span data-stu-id="1903b-172">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="1903b-173">Puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para crear un contrato de servicio WCF (interfaz) y las clases para que admite la **sondeo** operación.</span><span class="sxs-lookup"><span data-stu-id="1903b-173">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **Polling** operation.</span></span> <span data-ttu-id="1903b-174">Para obtener más información acerca de cómo generar un contrato de servicio WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="1903b-174">For more information about generating a WCF service contract, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="1903b-175">El contrato de servicio WCF (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1903b-175">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="1903b-176">El código siguiente muestra el contrato de servicio WCF (interfaz) que se genera para la **sondeo** operación.</span><span class="sxs-lookup"><span data-stu-id="1903b-176">The following code shows the WCF service contract (interface) generated for the **Polling** operation.</span></span>  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/", ConfigurationName="PollingOperation")]  
public interface PollingOperation {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/Polling/) of message Polling  
    // does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="Polling")]  
    [System.ServiceModel.XmlSerializerFormatAttribute()]  
    void Polling(Polling request);  
}  
```  
  
### <a name="the-message-contracts"></a><span data-ttu-id="1903b-177">Los contratos de mensaje</span><span class="sxs-lookup"><span data-stu-id="1903b-177">The Message Contracts</span></span>  
 <span data-ttu-id="1903b-178">El espacio de nombres de contrato de mensaje se modifica mediante la **InboundID** parámetro en el URI, si se especifica de conexión.</span><span class="sxs-lookup"><span data-stu-id="1903b-178">The message contract namespace is modified by the **InboundID** parameter in the connection URI, if specified.</span></span> <span data-ttu-id="1903b-179">En este ejemplo, no se especificó un identificador de entrada en el URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="1903b-179">In this example, you did not specify an inbound ID in the connection URI.</span></span> <span data-ttu-id="1903b-180">El mensaje de solicitud devuelve un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="1903b-180">The request message returns a DataSet.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Polling", WrapperNamespace="http://schemas.microsoft.com/Sql/2008/05/Polling/", IsWrapped=true)]  
public partial class Polling {  
  
[System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/Polling/", Order=0)]  
    [System.Xml.Serialization.XmlArrayAttribute(IsNullable=true)]  
    [System.Xml.Serialization.XmlArrayItemAttribute("DataSet", Namespace="http://schemas.datacontract.org/2004/07/System.Data", IsNullable=false)]  
    public System.Data.DataSet[] PolledData;  
  
    public Polling() {  
    }  
  
    public Polling(System.Data.DataSet[] PolledData) {  
        this.PolledData = PolledData;  
    }  
}  
```  
  
### <a name="wcf-service-class"></a><span data-ttu-id="1903b-181">Clase de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="1903b-181">WCF Service Class</span></span>  
 <span data-ttu-id="1903b-182">El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] también genera un archivo que tiene un código auxiliar para la clase de servicio WCF que implementa el contrato de servicio (interfaz).</span><span class="sxs-lookup"><span data-stu-id="1903b-182">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="1903b-183">El nombre del archivo es SqlAdapterBindingService.cs.</span><span class="sxs-lookup"><span data-stu-id="1903b-183">The name of the file is SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="1903b-184">Puede insertar la lógica para procesar el **sondeo** operación directamente en esta clase.</span><span class="sxs-lookup"><span data-stu-id="1903b-184">You can insert the logic to process the **Polling** operation directly into this class.</span></span> <span data-ttu-id="1903b-185">El código siguiente muestra la clase de servicio WCF generada por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1903b-185">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
```  
namespace SqlAdapterBindingNamespace {  
  
    public class SqlAdapterBindingService : PollingOperation {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/Polling/) of message Polling   
        // does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
        public virtual void Polling(Polling request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-inbound-messages-for-polling-operation"></a><span data-ttu-id="1903b-186">Recibir mensajes de entrada para la operación de sondeo</span><span class="sxs-lookup"><span data-stu-id="1903b-186">Receiving Inbound Messages for Polling Operation</span></span>  
 <span data-ttu-id="1903b-187">Esta sección proporciona instrucciones sobre cómo escribir una aplicación .NET para recibir mensajes de sondeo de entrada mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1903b-187">This section provides instructions on how to write a .NET application to receive inbound polling messages using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
#### <a name="to-receive-polling-messages-from-the-sql-adapter"></a><span data-ttu-id="1903b-188">Para recibir mensajes de sondeo desde el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="1903b-188">To receive polling messages from the SQL adapter</span></span>  
  
1.  <span data-ttu-id="1903b-189">Use la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar un contrato de servicio WCF (interfaz) y las clases auxiliares para el **sondeo** operación.</span><span class="sxs-lookup"><span data-stu-id="1903b-189">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **Polling** operation.</span></span> <span data-ttu-id="1903b-190">Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF de artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="1903b-190">For more information, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span> <span data-ttu-id="1903b-191">También puede especificar las propiedades de enlace al generar las clases de contrato y el Ayudante de servicio.</span><span class="sxs-lookup"><span data-stu-id="1903b-191">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="1903b-192">Esto garantiza que están establecidas correctamente en el archivo de configuración generado.</span><span class="sxs-lookup"><span data-stu-id="1903b-192">This guarantees that they are properly set in the generated configuration file.</span></span>  
  
2.  <span data-ttu-id="1903b-193">Implementar un servicio WCF desde las clases de interfaz y auxiliar generado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="1903b-193">Implement a WCF service from the interface and helper classes generated in step 1.</span></span> <span data-ttu-id="1903b-194">El **sondeo** método de esta clase puede producir una excepción para anular la transacción de sondeo, si se produce un error de procesamiento de los datos recibidos de la **sondeo** operación; en caso contrario, el método no no devuelve nada.</span><span class="sxs-lookup"><span data-stu-id="1903b-194">The **Polling** method of this class can throw an exception to abort the polling transaction, if an error is encountered processing the data received from the **Polling** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="1903b-195">La clase de servicio WCF debe atributo como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="1903b-195">You must attribute the WCF service class as follows:</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
     <span data-ttu-id="1903b-196">En el **sondeo** método, puede implementar la lógica de aplicación directamente.</span><span class="sxs-lookup"><span data-stu-id="1903b-196">Within the **Polling** method, you can implement your application logic directly.</span></span> <span data-ttu-id="1903b-197">Esta clase se puede encontrar en SqlAdapterBindingService.cs.</span><span class="sxs-lookup"><span data-stu-id="1903b-197">This class can be found in SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="1903b-198">Este código de este ejemplo Sub-clases el **SqlAdapterBindingService** clase.</span><span class="sxs-lookup"><span data-stu-id="1903b-198">This code in this example sub-classes the **SqlAdapterBindingService** class.</span></span> <span data-ttu-id="1903b-199">En este código, el mensaje de sondeo recibido como un conjunto de datos se escribe en la consola.</span><span class="sxs-lookup"><span data-stu-id="1903b-199">In this code, the polling message received as a DataSet is written to the console.</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
    {  
  
    public override void Polling(Polling request)  
    {  
        Console.WriteLine("\nNew Polling Records Received");  
        Console.WriteLine("*************************************************");  
        DataSet[] dataArray = request.PolledData;  
        foreach (DataTable tab in dataArray[0].Tables)  
        {  
            foreach (DataRow row in tab.Rows)  
            {  
                for (int i = 0; i < tab.Columns.Count; i++)  
                {  
                    Console.WriteLine(row[i]);  
                }  
            }  
        }  
        Console.WriteLine("*************************************************");  
        Console.WriteLine("\nHit <RETURN> to stop polling");  
        }  
    }  
    ```  
  
3.  <span data-ttu-id="1903b-200">Dado que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no acepta credenciales como parte del URI de conexión, debe implementar la clase siguiente para pasar las credenciales de la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1903b-200">Because the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not accept credentials as part of the connection URI, you must implement the following class to pass credentials for the SQL Server database.</span></span> <span data-ttu-id="1903b-201">En la última parte de la aplicación, se creará una instancia de esta clase para pasar las credenciales de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1903b-201">In the latter part of the application, you will instantiate this class to pass on the SQL Server credentials.</span></span>  
  
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
  
4.  <span data-ttu-id="1903b-202">Crear un **SqlAdapterBinding** y configure la operación de sondeo mediante la especificación de las propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="1903b-202">Create a **SqlAdapterBinding** and configure the polling operation by specifying the binding properties.</span></span> <span data-ttu-id="1903b-203">Puede hacerlo explícitamente en el código o mediante declaración en configuración.</span><span class="sxs-lookup"><span data-stu-id="1903b-203">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="1903b-204">Como mínimo, debe especificar el **InboundOperationType**, **PolledDataAvailableStatement**, y **PollingStatement**.</span><span class="sxs-lookup"><span data-stu-id="1903b-204">At a minimum, you must specify the **InboundOperationType**, **PolledDataAvailableStatement**, and **PollingStatement**.</span></span>  
  
    ```  
    SqlAdapterBinding binding = new SqlAdapterBinding();  
    binding.InboundOperationType = InboundOperation.Polling;  
    binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
    binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
    ```  
  
5.  <span data-ttu-id="1903b-205">Especifique las credenciales de base de datos de SQL Server creando el **PollingCredentials** clase creada en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="1903b-205">Specify SQL Server database credentials by instantiating the **PollingCredentials** class you created in Step 3.</span></span>  
  
    ```  
    PollingCredentials credentials = new PollingCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
    ```  
  
6.  <span data-ttu-id="1903b-206">Cree una instancia del servicio WCF que creó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="1903b-206">Create an instance of the WCF service created in step 2.</span></span>  
  
    ```  
    // create service instance  
    PollingService service = new PollingService();  
    ```  
  
7.  <span data-ttu-id="1903b-207">Cree una instancia de **System.ServiceModel.ServiceHost** mediante el servicio WCF y un URI de conexión base.</span><span class="sxs-lookup"><span data-stu-id="1903b-207">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="1903b-208">El URI de conexión base no puede contener el identificador de entrada, si se especifica.</span><span class="sxs-lookup"><span data-stu-id="1903b-208">The base connection URI cannot contain the inbound ID, if specified.</span></span> <span data-ttu-id="1903b-209">También debe especificar las credenciales aquí.</span><span class="sxs-lookup"><span data-stu-id="1903b-209">You should also specify the credentials here.</span></span>  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
    ServiceHost serviceHost = new ServiceHost(service, baseUri);  
    serviceHost.Description.Behaviors.Add(credentials);  
  
    ```  
  
8.  <span data-ttu-id="1903b-210">Agregar un extremo de servicio al host de servicio.</span><span class="sxs-lookup"><span data-stu-id="1903b-210">Add a service endpoint to the service host.</span></span> <span data-ttu-id="1903b-211">Para hacerlo:</span><span class="sxs-lookup"><span data-stu-id="1903b-211">To do this:</span></span>  
  
    -   <span data-ttu-id="1903b-212">Utilice el enlace creado en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="1903b-212">Use the binding created in step 4.</span></span>  
  
    -   <span data-ttu-id="1903b-213">Especifica una URI que contiene las credenciales de conexión y, si es necesario, un identificador de entrada.</span><span class="sxs-lookup"><span data-stu-id="1903b-213">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  
  
    -   <span data-ttu-id="1903b-214">Especifique el contrato como "PollingOperation".</span><span class="sxs-lookup"><span data-stu-id="1903b-214">Specify the contract as "PollingOperation".</span></span>  
  
    ```  
    // Add service endpoint: be sure to specify PollingOperation as the contract  
    Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
    serviceHost.AddServiceEndpoint("PollingOperation", binding, ConnectionUri);  
    ```  
  
9. <span data-ttu-id="1903b-215">Para recibir datos de sondeo, abra el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="1903b-215">To receive polling data, open the service host.</span></span> <span data-ttu-id="1903b-216">El adaptador devolverá datos cada vez que la consulta devuelve un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="1903b-216">The adapter will return data whenever the query returns a result set.</span></span>  
  
    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  
  
10. <span data-ttu-id="1903b-217">Para finalizar el sondeo, cierre el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="1903b-217">To terminate polling, close the service host.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="1903b-218">El adaptador seguirá sondea hasta que se cierra el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="1903b-218">The adapter will continue to poll until the service host is closed.</span></span>  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a><span data-ttu-id="1903b-219">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1903b-219">Example</span></span>  
 <span data-ttu-id="1903b-220">En el ejemplo siguiente se muestra una consulta de sondeo que se ejecuta la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="1903b-220">The following example shows a polling query that executes the Employee table.</span></span> <span data-ttu-id="1903b-221">La instrucción de sondeo realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="1903b-221">The polling statement performs the following tasks:</span></span>  
  
1.  <span data-ttu-id="1903b-222">Selecciona todos los registros de la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="1903b-222">Selects all the records from the Employee table.</span></span>  
  
2.  <span data-ttu-id="1903b-223">Ejecuta el procedimiento almacenado de MOVE_EMP_DATA para mover todos los registros de la tabla de empleados a la tabla HistorialEmpleados.</span><span class="sxs-lookup"><span data-stu-id="1903b-223">Executes the MOVE_EMP_DATA stored procedure to move all records from Employee table to EmployeeHistory table.</span></span>  
  
3.  <span data-ttu-id="1903b-224">Ejecuta el procedimiento almacenado de ADD_EMP_DETAILS para agregar un único registro a la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="1903b-224">Executes the ADD_EMP_DETAILS stored procedure to add a single record to the Employee table.</span></span>  
  
 <span data-ttu-id="1903b-225">El primer mensaje de sondeo contendrá todos los registros de la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="1903b-225">The first polling message will contain all the records from the Employee table.</span></span> <span data-ttu-id="1903b-226">Los mensajes de sondeo subsiguiente contendrá solo el último registro insertado por el procedimiento almacenado de ADD_EMP_DETAILS.</span><span class="sxs-lookup"><span data-stu-id="1903b-226">The subsequent polling messages will contain only the last record inserted by the ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="1903b-227">El adaptador seguirá sondea hasta que cierre el host de servicio presionando `<RETURN>`.</span><span class="sxs-lookup"><span data-stu-id="1903b-227">The adapter will continue to poll until you close the service host by pressing `<RETURN>`.</span></span>  
  
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
using System.Data;  
  
namespace Polling_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
    {  
  
        public override void Polling(Polling request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            DataSet[] dataArray = request.PolledData;  
            foreach (DataTable tab in dataArray[0].Tables)  
            {  
                foreach (DataRow row in tab.Rows)  
                {  
                    for (int i = 0; i < tab.Columns.Count; i++)  
                    {  
                        Console.WriteLine(row[i]);  
                    }  
                }  
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
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
                binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
                Console.WriteLine("Binding properties assigned...");  
  
                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId (if any) that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
  
                // This URI is used to initialize the ServiceHost. It cannot contain  
                // a query_string (InboundID); otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
  
                PollingCredentials credentials = new PollingCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  
  
                Console.WriteLine("Opening service host...");  
                PollingService service = new PollingService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("PollingOperation", binding, ConnectionUri);  
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
  
## <a name="see-also"></a><span data-ttu-id="1903b-228">Vea también</span><span class="sxs-lookup"><span data-stu-id="1903b-228">See Also</span></span>  
 [<span data-ttu-id="1903b-229">Sondear el servidor SQL mediante el adaptador de SQL con el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="1903b-229">Poll SQL Server using the SQL Adapter with WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)