---
title: Invocar débilmente tipada los procedimientos almacenados de SQL mediante el modelo de servicio de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aaf74a40-4c03-4a4a-9b91-c21babe154fa
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ec0b8b8d022b4e96a6df4d7c0d49d8176f6cd1a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225068"
---
# <a name="invoke-weakly-typed-stored-procedures-in-sql-using-the-wcf-service-model"></a><span data-ttu-id="3335e-102">Invocar débilmente tipada los procedimientos almacenados de SQL mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="3335e-102">Invoke Weakly-typed Stored Procedures in SQL using the WCF Service Model</span></span>
<span data-ttu-id="3335e-103">Cuando se invoca un procedimiento que se muestra en el **procedimientos** nodo en el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], el resultado es en forma de una matriz de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="3335e-103">When you invoke a procedure listed under the **Procedures** node in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], the output is in the form of a DataSet array.</span></span> <span data-ttu-id="3335e-104">Este tema proporciona instrucciones sobre cómo crear un cliente WCF para invocar un procedimiento almacenado en SQL Server que devuelve una matriz de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="3335e-104">This topic provides instructions on how to create a WCF client to invoke a stored procedure in SQL Server that returns a DataSet array.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3335e-105">Si va a realizar la operación en tablas con columnas de tipos definidos por el usuario, asegúrese de que hace referencia a [operaciones en tablas y vistas con tipos definidos por el usuario mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) antes de empezar a desarrollar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3335e-105">If you are performing operation on tables that have columns of user-defined types, make sure you refer to [Operations on Tables and Views with User-Defined Types using the SQL adapter](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) before you start developing your application.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="3335e-106">Acerca de los ejemplos usados en este tema</span><span class="sxs-lookup"><span data-stu-id="3335e-106">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="3335e-107">El ejemplo de este tema utiliza el procedimiento almacenado de GET_EMP_DETAILS.</span><span class="sxs-lookup"><span data-stu-id="3335e-107">The example in this topic uses the GET_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="3335e-108">Este procedimiento almacenado toma un identificador de empleado como parámetro de entrada y devuelve todas las columnas correspondientes del empleado con ese identificador.</span><span class="sxs-lookup"><span data-stu-id="3335e-108">This stored procedure takes an employee ID as an input parameter and returns all the corresponding columns for the employee with that ID.</span></span> <span data-ttu-id="3335e-109">El procedimiento almacenado de GET_EMP_DETAILS se crea al ejecutar el script SQL que se proporciona con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="3335e-109">The GET_EMP_DETAILS stored procedure is created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="3335e-110">Para obtener más información acerca de los ejemplos, vea [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3335e-110">For more information about samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span> <span data-ttu-id="3335e-111">Obtener un ejemplo, **Execute_StoredProc**, que se basa en este tema, también se proporciona con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="3335e-111">A sample, **Execute_StoredProc**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="3335e-112">La clase de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="3335e-112">The WCF Client Class</span></span>  
 <span data-ttu-id="3335e-113">El nombre del cliente WCF que se genera para llamar a procedimientos almacenados en el **procedimientos** nodo mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] aparece en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="3335e-113">The name of the WCF client generated for invoking stored procedures under the **Procedures** node using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="3335e-114">Artefactos de base de datos SQL Server</span><span class="sxs-lookup"><span data-stu-id="3335e-114">SQL Server Database Artifact</span></span>|<span data-ttu-id="3335e-115">Nombre de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="3335e-115">WCF Client Name</span></span>|  
|----------------------------------|---------------------|  
|<span data-ttu-id="3335e-116">Procedimiento (bajo la **procedimientos** nodo)</span><span class="sxs-lookup"><span data-stu-id="3335e-116">Procedure (under the **Procedures** node)</span></span>|<span data-ttu-id="3335e-117">Procedures_ cliente [esquema]</span><span class="sxs-lookup"><span data-stu-id="3335e-117">Procedures_[schema]Client</span></span>|  
  
 <span data-ttu-id="3335e-118">[] es el esquema al que pertenece el procedimiento; Por ejemplo, "dbo".</span><span class="sxs-lookup"><span data-stu-id="3335e-118">[schema] is the schema to which the procedure belongs; for example “dbo”.</span></span>  
  
### <a name="method-signature-for-invoking-stored-procedures"></a><span data-ttu-id="3335e-119">Firma de método para llamar a procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="3335e-119">Method Signature for Invoking Stored Procedures</span></span>  
 <span data-ttu-id="3335e-120">En la tabla siguiente se muestra la firma para el método expuesto para invocar los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="3335e-120">The following table shows the signature for the method exposed to invoke the stored procedures.</span></span>  
  
|<span data-ttu-id="3335e-121">Operación</span><span class="sxs-lookup"><span data-stu-id="3335e-121">Operation</span></span>|<span data-ttu-id="3335e-122">Firma de método</span><span class="sxs-lookup"><span data-stu-id="3335e-122">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="3335e-123">Nombre del procedimiento</span><span class="sxs-lookup"><span data-stu-id="3335e-123">Procedure name</span></span>|<span data-ttu-id="3335e-124">[] System.Data.DataSet [procedure_name] (parámetro1, parámetro2,...\)</span><span class="sxs-lookup"><span data-stu-id="3335e-124">System.Data.DataSet[] [procedure_name](param1, param2, …\)</span></span>|  
  
 <span data-ttu-id="3335e-125">[procedure_name] es el nombre del procedimiento; Por ejemplo GET_EMP_DETAILS</span><span class="sxs-lookup"><span data-stu-id="3335e-125">[procedure_name] is the name of the procedure; for example GET_EMP_DETAILS</span></span>  
  
 <span data-ttu-id="3335e-126">Por ejemplo, la firma del método invocar el procedimiento GET_EMP_DETAILS se muestra en el siguiente fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="3335e-126">As an example, the signature for the method to invoke the GET_EMP_DETAILS procedure is shown in the following code snippet.</span></span>  
  
```  
public partial class Procedures_dboClient : System.ServiceModel.ClientBase<Procedures_dbo>, Procedures_dbo {  
  public System.Data.DataSet[] GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue);  
}  
```  
  
 <span data-ttu-id="3335e-127">En este fragmento de código</span><span class="sxs-lookup"><span data-stu-id="3335e-127">In this snippet,</span></span>  
  
-   <span data-ttu-id="3335e-128">`Procedures_dboClient`es el nombre de la clase de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="3335e-128">`Procedures_dboClient` is the name of the WCF client class.</span></span> <span data-ttu-id="3335e-129">En este ejemplo, utilice esta clase para crear un cliente para invocar el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="3335e-129">In this example, you use this class to create a client to invoke the stored procedure.</span></span>  
  
-   <span data-ttu-id="3335e-130">`public System.Data.DataSet[] GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue)`es el método que se invoca en este ejemplo para invocar el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="3335e-130">`public System.Data.DataSet[] GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue)` is the method that you invoke in this example to invoke the stored procedure.</span></span> <span data-ttu-id="3335e-131">Este procedimiento almacenado toma un identificador de empleado y devuelve una matriz de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="3335e-131">This stored procedure takes an employee ID and returns a DataSet array.</span></span>  
  
## <a name="create-a-wcf-client-to-invoke-a-stored-procedure-in-sql-server"></a><span data-ttu-id="3335e-132">Crear un cliente WCF para invocar un procedimiento almacenado en SQL Server</span><span class="sxs-lookup"><span data-stu-id="3335e-132">Create a WCF Client to Invoke a Stored Procedure in SQL Server</span></span>  
 <span data-ttu-id="3335e-133">El conjunto de acciones necesarias para realizar una operación en SQL Server mediante un cliente de WCF genérico implica un conjunto de tareas que se describen en [información general sobre el modelo de servicio de WCF con el adaptador](overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="3335e-133">The generic set of actions required to perform an operation on SQL Server using a WCF client involves a set of tasks described in [Overview of the WCF Service Model with the Adapter](overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span></span> <span data-ttu-id="3335e-134">Esta sección describe específicamente cómo crear a un cliente WCF que invoca un procedimiento almacenado, el conjunto de resultados para que es una matriz de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="3335e-134">This section specifically describes how to create a WCF client that invokes a stored procedure, the result set for which is a DataSet array.</span></span> <span data-ttu-id="3335e-135">En este tema, por ejemplo, se invoca el procedimiento almacenado de GET_EMP_DETAILS.</span><span class="sxs-lookup"><span data-stu-id="3335e-135">In this topic, as an example, you invoke the GET_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="3335e-136">Este procedimiento almacenado se crea mediante la ejecución de la secuencia de comandos SQL proporcionado con cada ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3335e-136">This stored procedure is created by running the SQL script provided with each sample.</span></span>  
  
  
1.  <span data-ttu-id="3335e-137">Cree un proyecto de Visual C# en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3335e-137">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="3335e-138">De este tema, cree una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="3335e-138">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="3335e-139">Genere la clase de cliente WCF para el procedimiento almacenado de GET_EMP_DETAILS.</span><span class="sxs-lookup"><span data-stu-id="3335e-139">Generate the WCF client class for the GET_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="3335e-140">Asegúrese de seleccionar el procedimiento bajo el **procedimientos** nodo.</span><span class="sxs-lookup"><span data-stu-id="3335e-140">Make sure you select the procedure under the **Procedures** node.</span></span> <span data-ttu-id="3335e-141">Para obtener más información acerca de cómo generar una clase de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de SQL Server](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="3335e-141">For more information about generating a WCF client class, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3335e-142">Antes de generar la clase de cliente WCF, asegúrese de establecer el **EnableBizTalkCompatibilityMode** enlaza la propiedad en false.</span><span class="sxs-lookup"><span data-stu-id="3335e-142">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3.  <span data-ttu-id="3335e-143">En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.Sql` y `Microsoft.ServiceModel.Channels`.</span><span class="sxs-lookup"><span data-stu-id="3335e-143">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4.  <span data-ttu-id="3335e-144">Abra el archivo Program.cs y crear a un cliente, como se describe en el siguiente fragmento.</span><span class="sxs-lookup"><span data-stu-id="3335e-144">Open the Program.cs file and create a client as described in the snippet below.</span></span>  
  
    ```  
  
              Procedures_dboClient client = new Procedures_dboClient("SqlAdapterBinding_Procedures_dbo");  
  
    client.ClientCredentials.UserName.UserName = "<Enter username here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     <span data-ttu-id="3335e-145">En este fragmento de código, `Procedures_dboClient` es el cliente WCF definido en SqlAdapterBindingClient.cs.</span><span class="sxs-lookup"><span data-stu-id="3335e-145">In this snippet, `Procedures_dboClient` is the WCF client defined in SqlAdapterBindingClient.cs.</span></span> <span data-ttu-id="3335e-146">Este archivo es generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3335e-146">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="3335e-147">`SqlAdapterBinding_Procedures_dbo`es el nombre de la configuración de punto de conexión de cliente y se define en el archivo app.config. Este archivo también se genera mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y contiene las propiedades de enlace y otras opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="3335e-147">`SqlAdapterBinding_Procedures_dbo` is the name of the client endpoint configuration and is defined in the app.config. This file is also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and contains the binding properties and other configuration settings.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3335e-148">En este fragmento de código, utilice el enlace y dirección de punto de conexión del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="3335e-148">In this snippet, you use the binding and endpoint address from the configuration file.</span></span> <span data-ttu-id="3335e-149">Puede especificar también explícitamente estos valores en el código.</span><span class="sxs-lookup"><span data-stu-id="3335e-149">You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="3335e-150">Para obtener más información sobre las distintas formas de especificar el enlace del cliente, consulte [configurar un enlace de cliente para el adaptador de SQL](configure-a-client-binding-for-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="3335e-150">For more information on the different ways of specifying client binding, see [Configure a Client Binding for the SQL Adapter](configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
5.  <span data-ttu-id="3335e-151">Abra al cliente como se describe en el siguiente fragmento:</span><span class="sxs-lookup"><span data-stu-id="3335e-151">Open the client as described in the snippet below:</span></span>  
  
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
  
6.  <span data-ttu-id="3335e-152">Invocar el procedimiento almacenado de GET_EMP_DETAILS.</span><span class="sxs-lookup"><span data-stu-id="3335e-152">Invoke the GET_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="3335e-153">Antes de invocar el procedimiento GET_EMP_DETAILS, debe agregar el `System.Data` espacio de nombres en el código.</span><span class="sxs-lookup"><span data-stu-id="3335e-153">Before you invoke the GET_EMP_DETAILS procedure, you must add the `System.Data` namespace to your code.</span></span>  
  
    ```  
    DataSet[] dataArray;  
    int returnCode;  
  
    try  
    {  
       Console.WriteLine("Calling a stored procedure...");  
       dataArray = client.GET_EMP_DETAILS(10001, out returnCode);  //Invoke the stored procedure  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
    Console.WriteLine("The details for the employee with ID '10001' are:");  
    Console.WriteLine("*************************************************");  
  
    foreach (DataSet dataSet in dataArray)  
    {  
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
    }  
    Console.WriteLine("*************************************************");  
  
    ```  
  
7.  <span data-ttu-id="3335e-154">Cierre al cliente como se describe en el siguiente fragmento:</span><span class="sxs-lookup"><span data-stu-id="3335e-154">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
8.  <span data-ttu-id="3335e-155">Compile el proyecto y, a continuación, ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="3335e-155">Build the project and then run it.</span></span> <span data-ttu-id="3335e-156">Los detalles del empleado, para qué pr</span><span class="sxs-lookup"><span data-stu-id="3335e-156">The details for the employee, for which you pr</span></span>
9.  <span data-ttu-id="3335e-157">ovided el identificador, se muestran en la consola.</span><span class="sxs-lookup"><span data-stu-id="3335e-157">ovided the ID, are displayed on the console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3335e-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="3335e-158">See Also</span></span>  
[<span data-ttu-id="3335e-159">Desarrollar aplicaciones con el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="3335e-159">Develop applications using the WCF Service model</span></span>](develop-sql-applications-using-the-wcf-service-model.md)