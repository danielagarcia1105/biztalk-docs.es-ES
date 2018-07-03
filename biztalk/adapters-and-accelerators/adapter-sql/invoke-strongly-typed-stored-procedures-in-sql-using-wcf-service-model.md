---
title: Invocar fuertemente tipado procedimientos almacenados en SQL mediante el modelo de servicio de WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d56df5f6-b046-4fe4-a5b4-b29906093beb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b88cae88a01ea3f04da3b3672153da7d00ea7633
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966821"
---
# <a name="invoke-strongly-typed-stored-procedures-in-sql-using-wcf-service-model"></a><span data-ttu-id="97a77-102">Invocar fuertemente tipado procedimientos almacenados en SQL mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="97a77-102">Invoke Strongly-typed Stored Procedures in SQL using WCF Service Model</span></span>
<span data-ttu-id="97a77-103">Al invocar un procedimiento que aparece bajo el **Strongly-Typed procedimientos** nodo en el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], el resultado es en forma de un conjunto de resultados fuertemente tipado.</span><span class="sxs-lookup"><span data-stu-id="97a77-103">When you invoke a procedure listed under the **Strongly-Typed Procedures** node in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], the output is in the form of a strongly-typed result set.</span></span> <span data-ttu-id="97a77-104">Este tema proporciona instrucciones sobre cómo crear un cliente WCF para invocar procedimientos almacenados en SQL Server que devuelven un conjunto de resultados fuertemente tipado.</span><span class="sxs-lookup"><span data-stu-id="97a77-104">This topic provides instructions on how to create a WCF client to invoke stored procedures in SQL Server that return a strongly-typed result set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="97a77-105">Si va a realizar la operación en tablas con columnas de tipos definidos por el usuario, asegúrese de que se hace referencia a [operaciones en tablas y vistas con tipos definidos por el usuario](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) antes de empezar a desarrollar su aplicación.</span><span class="sxs-lookup"><span data-stu-id="97a77-105">If you are performing operation on tables that have columns of user-defined types, make sure you refer to [Operations on Tables and Views with User-Defined Types](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) before you start developing your application.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="97a77-106">Acerca de los ejemplos usados en este tema.</span><span class="sxs-lookup"><span data-stu-id="97a77-106">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="97a77-107">El ejemplo de este tema usa el procedimiento almacenado de GET_EMP_DETAILS.</span><span class="sxs-lookup"><span data-stu-id="97a77-107">The example in this topic uses the GET_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="97a77-108">Este procedimiento almacenado toma un identificador de empleado como parámetro de entrada y devuelve todas las columnas correspondientes para el empleado con ese identificador.</span><span class="sxs-lookup"><span data-stu-id="97a77-108">This stored procedure takes an employee ID as an input parameter and returns all the corresponding columns for the employee with that ID.</span></span> <span data-ttu-id="97a77-109">El procedimiento almacenado de GET_EMP_DETAILS se crea mediante la ejecución de la secuencia de comandos SQL con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="97a77-109">The GET_EMP_DETAILS stored procedure is created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="97a77-110">Para obtener más información acerca de los ejemplos, vea [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span><span class="sxs-lookup"><span data-stu-id="97a77-110">For more information about samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span> <span data-ttu-id="97a77-111">Un ejemplo, **Execute_TypedStoredProcedure**, que se basa en este tema, también se proporciona con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="97a77-111">A sample, **Execute_TypedStoredProcedure**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="97a77-112">La clase de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="97a77-112">The WCF Client Class</span></span>  
 <span data-ttu-id="97a77-113">El nombre del cliente WCF generado para invocar procedimientos almacenados en el **Strongly-Typed procedimientos** nodo mediante la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] aparece en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="97a77-113">The name of the WCF client generated for invoking stored procedures under the **Strongly-Typed Procedures** node using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="97a77-114">Artefactos de base de datos SQL Server</span><span class="sxs-lookup"><span data-stu-id="97a77-114">SQL Server Database Artifact</span></span>|<span data-ttu-id="97a77-115">Nombre de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="97a77-115">WCF Client Name</span></span>|  
|----------------------------------|---------------------|  
|<span data-ttu-id="97a77-116">Procedimiento (bajo la **Strongly-Typed procedimientos** nodo)</span><span class="sxs-lookup"><span data-stu-id="97a77-116">Procedure (under the **Strongly-Typed Procedures** node)</span></span>|<span data-ttu-id="97a77-117">TypedProcedures_ cliente [esquema]</span><span class="sxs-lookup"><span data-stu-id="97a77-117">TypedProcedures_[schema]Client</span></span>|  
  
 <span data-ttu-id="97a77-118">[] es el esquema al que pertenece el procedimiento; Por ejemplo, "dbo".</span><span class="sxs-lookup"><span data-stu-id="97a77-118">[schema] is the schema to which the procedure belongs; for example “dbo”.</span></span>  
  
### <a name="method-signature-for-invoking-stored-procedures"></a><span data-ttu-id="97a77-119">Firma de método para invocar procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="97a77-119">Method Signature for Invoking Stored Procedures</span></span>  
 <span data-ttu-id="97a77-120">En la tabla siguiente se muestra la firma del método que se exponen para invocar los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="97a77-120">The following table shows the signature for the method exposed to invoke the stored procedures.</span></span>  
  
|<span data-ttu-id="97a77-121">Operación</span><span class="sxs-lookup"><span data-stu-id="97a77-121">Operation</span></span>|<span data-ttu-id="97a77-122">Firma de método</span><span class="sxs-lookup"><span data-stu-id="97a77-122">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="97a77-123">Nombre del procedimiento</span><span class="sxs-lookup"><span data-stu-id="97a77-123">Procedure name</span></span>|<span data-ttu-id="97a77-124">[PROC_NS] [nombre_procedimiento] (param1, param2...\)</span><span class="sxs-lookup"><span data-stu-id="97a77-124">[PROC_NS] [procedure_name](param1, param2, …\)</span></span>|  
  
 <span data-ttu-id="97a77-125">[PROC_NS] es el espacio de nombres de procedimiento; Por ejemplo schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0]</span><span class="sxs-lookup"><span data-stu-id="97a77-125">[PROC_NS] is the procedure namespace; for example schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[]</span></span>  
  
 <span data-ttu-id="97a77-126">[procedure_name] es el nombre del procedimiento; Por ejemplo GET_EMP_DETAILS</span><span class="sxs-lookup"><span data-stu-id="97a77-126">[procedure_name] is the name of the procedure; for example GET_EMP_DETAILS</span></span>  
  
 <span data-ttu-id="97a77-127">Por ejemplo, la firma del método invocar el procedimiento GET_EMP_DETAILS se muestra en el siguiente fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="97a77-127">As an example, the signature for the method to invoke the GET_EMP_DETAILS procedure is shown in the following code snippet.</span></span>  
  
```  
public partial class TypedProcedures_dboClient : System.ServiceModel.ClientBase<TypedProcedures_dbo>, TypedProcedures_dbo{  
public schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[]   
  GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue);  
}  
```  
  
 <span data-ttu-id="97a77-128">En este fragmento de código</span><span class="sxs-lookup"><span data-stu-id="97a77-128">In this snippet,</span></span>  
  
-   <span data-ttu-id="97a77-129">`TypedProcedures_dboClient` es el nombre de la clase.</span><span class="sxs-lookup"><span data-stu-id="97a77-129">`TypedProcedures_dboClient` is the name of the class.</span></span> <span data-ttu-id="97a77-130">En este ejemplo, utiliza esta clase para crear un cliente para invocar el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="97a77-130">In this example, you use this class to create a client to invoke the stored procedure.</span></span>  
  
-   <span data-ttu-id="97a77-131">`public schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[] GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue)` es el método que invoque en este ejemplo para invocar el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="97a77-131">`public schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[] GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue)` is the method that you invoke in this example to invoke the stored procedure.</span></span> <span data-ttu-id="97a77-132">Este procedimiento almacenado toma un identificador de empleado y devuelve un conjunto de resultados fuertemente tipado.</span><span class="sxs-lookup"><span data-stu-id="97a77-132">This stored procedure takes an employee ID and returns a strongly-typed result set.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-a-stored-procedure-in-sql-server"></a><span data-ttu-id="97a77-133">Creación de un cliente WCF para invocar un procedimiento almacenado en SQL Server</span><span class="sxs-lookup"><span data-stu-id="97a77-133">Creating a WCF Client to Invoke a Stored Procedure in SQL Server</span></span>  
 <span data-ttu-id="97a77-134">El conjunto genérico de las acciones necesarias para realizar una operación en SQL Server mediante un cliente de WCF implica un conjunto de tareas que se describen en [general del modelo de servicio WCF con el adaptador de SQL](overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="97a77-134">The generic set of actions required to perform an operation on SQL Server using a WCF client involves a set of tasks described in [Overview of the WCF Service Model with the SQL Adapter](overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span></span> <span data-ttu-id="97a77-135">En concreto, esta sección describe cómo crear a un cliente WCF que invoca un procedimiento almacenado, el conjunto de resultados para que está fuertemente tipada.</span><span class="sxs-lookup"><span data-stu-id="97a77-135">This section specifically describes how to create a WCF client that invokes a stored procedure, the result set for which is strongly-typed.</span></span> <span data-ttu-id="97a77-136">En este tema, por ejemplo, se invoca el procedimiento almacenado de GET_EMP_DETAILS.</span><span class="sxs-lookup"><span data-stu-id="97a77-136">In this topic, as an example, you invoke the GET_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="97a77-137">Este procedimiento almacenado se crea al ejecutar el script SQL proporcionado con cada ejemplo.</span><span class="sxs-lookup"><span data-stu-id="97a77-137">This stored procedure is created by running the SQL script provided with each sample.</span></span>  
  
1. <span data-ttu-id="97a77-138">Cree un proyecto de Visual C# en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="97a77-138">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="97a77-139">Este tema, cree una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="97a77-139">For this topic, create a console application.</span></span>  
  
2. <span data-ttu-id="97a77-140">Generar la clase de cliente WCF para el procedimiento almacenado de GET_EMP_DETAILS.</span><span class="sxs-lookup"><span data-stu-id="97a77-140">Generate the WCF client class for the GET_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="97a77-141">Asegúrese de seleccionar el procedimiento en el **Strongly-Typed procedimientos** nodo.</span><span class="sxs-lookup"><span data-stu-id="97a77-141">Make sure you select the procedure under the **Strongly-Typed Procedures** node.</span></span> <span data-ttu-id="97a77-142">Para obtener más información acerca de cómo generar una clase de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF para artefactos de SQL Server](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="97a77-142">For more information about generating a WCF client class, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="97a77-143">Antes de generar la clase de cliente WCF, asegúrese de establecer el **EnableBizTalkCompatibilityMode** enlaza la propiedad en false.</span><span class="sxs-lookup"><span data-stu-id="97a77-143">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3. <span data-ttu-id="97a77-144">En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.Sql` y `Microsoft.ServiceModel.Channels`.</span><span class="sxs-lookup"><span data-stu-id="97a77-144">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4. <span data-ttu-id="97a77-145">Abra el archivo Program.cs y cree a un cliente como se describe en el siguiente fragmento.</span><span class="sxs-lookup"><span data-stu-id="97a77-145">Open the Program.cs file and create a client as described in the snippet below.</span></span>  
  
   ```  
  
             TypedProcedures_dboClient client = new TypedProcedures_dboClient("SqlAdapterBinding_TypedProcedures_dbo");  
   client.ClientCredentials.UserName.UserName = "<Enter username here>";  
   client.ClientCredentials.UserName.Password = "<Enter username here>";  
   ```  
  
    <span data-ttu-id="97a77-146">En este fragmento de código, `TypedProcedures_dboClient` es el cliente WCF definido en SqlAdapterBindingClient.cs.</span><span class="sxs-lookup"><span data-stu-id="97a77-146">In this snippet, `TypedProcedures_dboClient` is the WCF client defined in SqlAdapterBindingClient.cs.</span></span> <span data-ttu-id="97a77-147">Este archivo es generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97a77-147">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="97a77-148">`SqlAdapterBinding_TypedProcedures_dbo` es el nombre de la configuración de punto de conexión de cliente y se define en el archivo app.config. Este archivo también se genera mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y contiene las propiedades de enlace y otras opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="97a77-148">`SqlAdapterBinding_TypedProcedures_dbo` is the name of the client endpoint configuration and is defined in the app.config. This file is also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and contains the binding properties and other configuration settings.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="97a77-149">En este fragmento de código, utilice el enlace y dirección de punto de conexión del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="97a77-149">In this snippet, you use the binding and endpoint address from the configuration file.</span></span> <span data-ttu-id="97a77-150">Puede especificar también explícitamente estos valores en el código.</span><span class="sxs-lookup"><span data-stu-id="97a77-150">You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="97a77-151">Para obtener más información sobre las diferentes maneras de especificar el enlace del cliente, consulte [configurar un enlace de cliente para el adaptador de SQL](configure-a-client-binding-for-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="97a77-151">For more information on the different ways of specifying client binding, see [Configure a Client Binding for the SQL Adapter](configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
5. <span data-ttu-id="97a77-152">Abra al cliente como se describe en el siguiente fragmento:</span><span class="sxs-lookup"><span data-stu-id="97a77-152">Open the client as described in the snippet below:</span></span>  
  
   ```  
   try  
   {  
      Console.WriteLine("Opening Client...");  
      client.Open();  
   }  
   catch (Exception ex)  
   {  
      Console.WriteLine("Exception: " + ex.Message);  
      throw;  
   }  
   ```  
  
6. <span data-ttu-id="97a77-153">Invocar el procedimiento GET_EMP_DETAILS almacenados como se describe en el siguiente fragmento.</span><span class="sxs-lookup"><span data-stu-id="97a77-153">Invoke the GET_EMP_DETAILS stored procedure as described in the snippet below.</span></span>  
  
   ```  
   // Create array of type as specified in the method signature  
   schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[] resultSet =  
      new schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[1];  
   int returnCode;  
  
   try  
   {  
      Console.WriteLine("Calling a stored procedure...");  
      resultSet = client.GET_EMP_DETAILS(10001, out returnCode);  //Invoke the stored procedure  
   }  
   catch (Exception ex)  
   {  
      Console.WriteLine("Exception: " + ex.Message);  
      throw;  
   }  
   Console.WriteLine("The details for the employee with ID '10001' are:");  
   Console.WriteLine("*************************************************");  
  
   for (int i = 0; i < resultSet.Length; i++)  
      {  
         Console.WriteLine("Employee Name        : " + resultSet[i].Name);  
         Console.WriteLine("Employee Designation : " + resultSet[i].Designation);  
         Console.WriteLine("Employee Salary      : " + resultSet[i].Salary);  
      }  
  
   Console.WriteLine("*************************************************");  
  
   ```  
  
7. <span data-ttu-id="97a77-154">Cierre al cliente como se describe en el siguiente fragmento:</span><span class="sxs-lookup"><span data-stu-id="97a77-154">Close the client as described in the snippet below:</span></span>  
  
   ```  
   client.Close();  
   Console.WriteLine("Press any key to exit...");  
   Console.ReadLine();  
   ```  
  
8. <span data-ttu-id="97a77-155">Compile el proyecto y, a continuación, ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="97a77-155">Build the project and then run it.</span></span> <span data-ttu-id="97a77-156">El nombre, designación y salario para el identificador de empleado, se muestran en la consola.</span><span class="sxs-lookup"><span data-stu-id="97a77-156">The name, designation, and salary for the employee ID, are displayed on the console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97a77-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="97a77-157">See Also</span></span>  
[<span data-ttu-id="97a77-158">Desarrollar aplicaciones con el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="97a77-158">Develop applications using the WCF Service model</span></span>](develop-sql-applications-using-the-wcf-service-model.md)