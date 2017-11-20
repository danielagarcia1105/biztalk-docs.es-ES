---
title: Las operaciones de ExecuteReader, ExecuteScalar o ExecuteNonQuery en SQL mediante el modelo de servicio de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 62f166af-b657-491b-b20d-1ae7886f27ce
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f886463e2b38b358e5f6a9da8b7e67aabdc9c3ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="executereader-executescalar-or-executenonquery-operations-in-sql-using-wcf-service-model"></a><span data-ttu-id="a4d93-102">Operaciones de ExecuteReader, ExecuteScalar o ExecuteNonQuery en SQL mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="a4d93-102">ExecuteReader, ExecuteScalar, or ExecuteNonQuery operations in SQL using WCF Service Model</span></span>
<span data-ttu-id="a4d93-103">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expone las operaciones de SQL Server genéricas como **ExecuteNonQuery**, **ExecuteReader**, y **ExecuteScalar**.</span><span class="sxs-lookup"><span data-stu-id="a4d93-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] exposes generic SQL Server operations such as **ExecuteNonQuery**, **ExecuteReader**, and **ExecuteScalar**.</span></span> <span data-ttu-id="a4d93-104">Puede utilizar estas operaciones para ejecutar cualquier instrucción SQL en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a4d93-104">You can use these operations to execute any SQL statement on a SQL Server database.</span></span> <span data-ttu-id="a4d93-105">Estas operaciones varían en función del tipo de respuesta que se obtiene de la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="a4d93-105">These operations differ based on the kind of response you get for the SQL statement.</span></span> <span data-ttu-id="a4d93-106">Para obtener más información acerca del modo en que el adaptador admite estas operaciones, vea [soporte técnico para las operaciones de ExecuteScalar, ExecuteReader y ExecuteNonQuery](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).</span><span class="sxs-lookup"><span data-stu-id="a4d93-106">For more information about how the adapter supports these operations, see [Support for ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).</span></span>  
  
 <span data-ttu-id="a4d93-107">En este tema se muestra cómo realizar una **ExecuteReader** operación mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] mediante el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="a4d93-107">This topic demonstrates how to perform an **ExecuteReader** operation using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] using the WCF service model.</span></span> <span data-ttu-id="a4d93-108">Puede seguir el mismo conjunto de procedimientos que se describen en este tema para realizar **ExecuteNonQuery** y **ExecuteScalar** operaciones.</span><span class="sxs-lookup"><span data-stu-id="a4d93-108">You can follow the same set of procedures described in this topic to perform **ExecuteNonQuery** and **ExecuteScalar** operations.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="a4d93-109">Acerca de los ejemplos usados en este tema</span><span class="sxs-lookup"><span data-stu-id="a4d93-109">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="a4d93-110">El ejemplo de este tema usa el **ExecuteReader** operación para ejecutar el ADD_EMP_DETAILS procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="a4d93-110">The example in this topic uses the **ExecuteReader** operation to execute the ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="a4d93-111">Este procedimiento almacenado agrega un registro a la tabla de empleados y devuelve el identificador de empleado para el registro.</span><span class="sxs-lookup"><span data-stu-id="a4d93-111">This stored procedure adds a record to the Employee table and returns the employee ID for the record.</span></span> <span data-ttu-id="a4d93-112">El procedimiento almacenado de ADD_EMP_DETAILS se crea al ejecutar el script SQL que se proporciona con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="a4d93-112">The ADD_EMP_DETAILS stored procedure is created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="a4d93-113">Para obtener más información acerca de los ejemplos, vea [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a4d93-113">For more information about samples, see [Adapter samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span> <span data-ttu-id="a4d93-114">Obtener un ejemplo, **Execute_Reader**, que se basa en este tema, también se proporciona con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="a4d93-114">A sample, **Execute_Reader**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="a4d93-115">La clase de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="a4d93-115">The WCF Client Class</span></span>  
 <span data-ttu-id="a4d93-116">El nombre del cliente WCF generado para invocar operaciones genéricas (ExecuteNonQuery, ExecuteReader o ExecuteScalar) utilizando el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] aparece en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="a4d93-116">The name of the WCF client generated for invoking generic operations (ExecuteNonQuery, ExecuteReader, or ExecuteScalar) using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="a4d93-117">Operaciones</span><span class="sxs-lookup"><span data-stu-id="a4d93-117">Operations</span></span>|<span data-ttu-id="a4d93-118">Nombre de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="a4d93-118">WCF Client Name</span></span>|  
|----------------|---------------------|  
|<span data-ttu-id="a4d93-119">ExecuteNonQuery, ExecuteReader o ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="a4d93-119">ExecuteNonQuery, ExecuteReader, or ExecuteScalar</span></span>|<span data-ttu-id="a4d93-120">GenericTableOpClient</span><span class="sxs-lookup"><span data-stu-id="a4d93-120">GenericTableOpClient</span></span>|  
  
### <a name="method-signature-for-invoking-generic-operations"></a><span data-ttu-id="a4d93-121">Firma de método para invocar operaciones genéricas</span><span class="sxs-lookup"><span data-stu-id="a4d93-121">Method Signature for Invoking Generic Operations</span></span>  
 <span data-ttu-id="a4d93-122">En la tabla siguiente se muestra la firma para el método expuesto para invocar las operaciones genéricas.</span><span class="sxs-lookup"><span data-stu-id="a4d93-122">The following table shows the signature for the method exposed to invoke the generic operations.</span></span>  
  
|<span data-ttu-id="a4d93-123">Operación</span><span class="sxs-lookup"><span data-stu-id="a4d93-123">Operation</span></span>|<span data-ttu-id="a4d93-124">Firma de método</span><span class="sxs-lookup"><span data-stu-id="a4d93-124">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="a4d93-125">ExecuteNonQuery</span><span class="sxs-lookup"><span data-stu-id="a4d93-125">ExecuteNonQuery</span></span>|<span data-ttu-id="a4d93-126">int ExecuteNonQuery (cadena de consulta)</span><span class="sxs-lookup"><span data-stu-id="a4d93-126">int ExecuteNonQuery(string Query)</span></span>|  
|<span data-ttu-id="a4d93-127">ExecuteReader</span><span class="sxs-lookup"><span data-stu-id="a4d93-127">ExecuteReader</span></span>|<span data-ttu-id="a4d93-128">[] De System.Data.DataSet ExecuteReader (cadena de consulta)</span><span class="sxs-lookup"><span data-stu-id="a4d93-128">System.Data.DataSet[] ExecuteReader(string Query)</span></span>|  
|<span data-ttu-id="a4d93-129">ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="a4d93-129">ExecuteScalar</span></span>|<span data-ttu-id="a4d93-130">cadena ExecuteScalar(string Query)</span><span class="sxs-lookup"><span data-stu-id="a4d93-130">string ExecuteScalar(string Query)</span></span>|  
  
 <span data-ttu-id="a4d93-131">Por ejemplo, la firma para los métodos de operación genérica se muestra en el siguiente fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="a4d93-131">As an example, the signature for the generic operation methods is shown in the following code snippet.</span></span>  
  
```  
public partial class GenericTableOpClient : System.ServiceModel.ClientBase<GenericTableOp>, GenericTableOp {  
  public int ExecuteNonQuery(string Query);  
  public System.Data.DataSet[] ExecuteReader(string Query);  
  public string ExecuteScalar(string Query);  
}  
```  
  
 <span data-ttu-id="a4d93-132">En este fragmento de código</span><span class="sxs-lookup"><span data-stu-id="a4d93-132">In this snippet,</span></span>  
  
-   <span data-ttu-id="a4d93-133">`GenericTableOpClient`es el nombre de la clase.</span><span class="sxs-lookup"><span data-stu-id="a4d93-133">`GenericTableOpClient` is the name of the class.</span></span> <span data-ttu-id="a4d93-134">En este ejemplo, utilice esta clase para crear un cliente para invocar la operación genérica, ExecuteReader.</span><span class="sxs-lookup"><span data-stu-id="a4d93-134">In this example, you use this class to create a client to invoke the generic operation, ExecuteReader.</span></span>  
  
-   <span data-ttu-id="a4d93-135">`public System.Data.DataSet[] ExecuteReader(string Query)`es el método que se invoca en este ejemplo para invocar la ADD_EMP_DETAILS procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="a4d93-135">`public System.Data.DataSet[] ExecuteReader(string Query)` is the method that you invoke in this example to invoke the ADD_EMP_DETAILS stored procedure.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-an-executereader-operation"></a><span data-ttu-id="a4d93-136">Creación de un cliente WCF para invocar la operación ExecuteReader</span><span class="sxs-lookup"><span data-stu-id="a4d93-136">Creating a WCF Client to Invoke an ExecuteReader Operation</span></span>  
 <span data-ttu-id="a4d93-137">El conjunto de acciones necesarias para realizar una operación en SQL Server mediante un cliente de WCF genérico implica un conjunto de tareas que se describen en [información general del modelo del canal WCF con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="a4d93-137">The generic set of actions required to perform an operation on SQL Server using a WCF client involves a set of tasks described in [Overview of the WCF channel model with the SQL adapter](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md).</span></span> <span data-ttu-id="a4d93-138">En concreto, en esta sección describe cómo crear un cliente WCF que invoca un **ExecuteReader** operación para ejecutar el ADD_EMP_DETAILS procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="a4d93-138">This section specifically describes how to create a WCF client that invokes an **ExecuteReader** operation to execute the ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="a4d93-139">Este procedimiento almacenado se crea mediante la ejecución de la secuencia de comandos SQL proporcionado con cada ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a4d93-139">This stored procedure is created by running the SQL script provided with each sample.</span></span>  
  
#### <a name="to-create-a-wcf-client-to-invoke-executereader-operation"></a><span data-ttu-id="a4d93-140">Para crear un cliente WCF para invocar la operación ExecuteReader</span><span class="sxs-lookup"><span data-stu-id="a4d93-140">To create a WCF client to invoke ExecuteReader operation</span></span>  
  
1.  <span data-ttu-id="a4d93-141">Cree un proyecto de Visual C# en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a4d93-141">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="a4d93-142">De este tema, cree una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="a4d93-142">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="a4d93-143">Generar la clase de cliente WCF para la **ExecuteReader** operación genérica.</span><span class="sxs-lookup"><span data-stu-id="a4d93-143">Generate the WCF client class for the **ExecuteReader** generic operation.</span></span> <span data-ttu-id="a4d93-144">Esta operación está disponible bajo el nodo raíz cuando se conecta a la base de datos de SQL Server mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4d93-144">This operation is available under the root node when you connect to the SQL Server database using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="a4d93-145">Para obtener más información acerca de cómo generar una clase de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="a4d93-145">For more information about generating a WCF client class, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a4d93-146">Antes de generar la clase de cliente WCF, asegúrese de establecer el **EnableBizTalkCompatibilityMode** enlaza la propiedad en false.</span><span class="sxs-lookup"><span data-stu-id="a4d93-146">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3.  <span data-ttu-id="a4d93-147">En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.Sql` y `Microsoft.ServiceModel.Channels`.</span><span class="sxs-lookup"><span data-stu-id="a4d93-147">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4.  <span data-ttu-id="a4d93-148">Abra el archivo Program.cs y crear a un cliente, como se describe en el siguiente fragmento.</span><span class="sxs-lookup"><span data-stu-id="a4d93-148">Open the Program.cs file and create a client as described in the snippet below.</span></span>  
  
    ```  
  
            GenericTableOpClient client = new GenericTableOpClient("SqlAdapterBinding_GenericTableOp");  
    client.ClientCredentials.UserName.UserName = "<Enter username here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     <span data-ttu-id="a4d93-149">En este fragmento de código, `GenericTableOpClient` es el cliente WCF definido en SqlAdapterBindingClient.cs.</span><span class="sxs-lookup"><span data-stu-id="a4d93-149">In this snippet, `GenericTableOpClient` is the WCF client defined in SqlAdapterBindingClient.cs.</span></span> <span data-ttu-id="a4d93-150">Este archivo es generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4d93-150">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="a4d93-151">`SqlAdapterBinding_GenericTableOp`es el nombre de la configuración de punto de conexión de cliente y se define en el archivo app.config. Este archivo también se genera mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y contiene las propiedades de enlace y otras opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="a4d93-151">`SqlAdapterBinding_GenericTableOp` is the name of the client endpoint configuration and is defined in the app.config. This file is also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and contains the binding properties and other configuration settings.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a4d93-152">En este fragmento de código, utilice el enlace y dirección de punto de conexión del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a4d93-152">In this snippet, you use the binding and endpoint address from the configuration file.</span></span> <span data-ttu-id="a4d93-153">Puede especificar también explícitamente estos valores en el código.</span><span class="sxs-lookup"><span data-stu-id="a4d93-153">You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="a4d93-154">Para obtener más información sobre las distintas formas de especificar el enlace del cliente, consulte [configurar un enlace de cliente para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="a4d93-154">For more information on the different ways of specifying client binding, see [Configure a Client Binding for the SQL Adapter](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
5.  <span data-ttu-id="a4d93-155">Abra al cliente como se describe en el siguiente fragmento:</span><span class="sxs-lookup"><span data-stu-id="a4d93-155">Open the client as described in the snippet below:</span></span>  
  
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
  
6.  <span data-ttu-id="a4d93-156">Invocar la **ExecuteReader** operación para el ADD_EMP_DETAILS de procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="a4d93-156">Invoke the **ExecuteReader** operation for the ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="a4d93-157">Antes de invocar la operación ExecuteReader, debe agregar el `System.Data` espacio de nombres en el código.</span><span class="sxs-lookup"><span data-stu-id="a4d93-157">Before you invoke the ExecuteReader operation, you must add the `System.Data` namespace to your code.</span></span>  
  
    ```  
    string query = "EXEC ADD_EMP_DETAILS 'Tom Smith', 'Manager', 500000";  
    DataSet[] dsArray = client.ExecuteReader(query);  
  
    Console.WriteLine("Invoking the ADD_EMP_DETAILS stored procedure using ExecuteReader");  
    Console.WriteLine("*****************************************************");  
    foreach (DataSet dataSet in dsArray)  
    {  
       foreach (DataTable tab in dsArray[0].Tables)  
       {  
           foreach (DataRow row in tab.Rows)  
           {  
              for (int i = 0; i < tab.Columns.Count; i++)  
              {  
                 Console.WriteLine("The ID for the newly added employee is : " + row[i]);  
              }  
           }  
        }  
    }  
    Console.WriteLine("*****************************************************");  
  
    ```  
  
7.  <span data-ttu-id="a4d93-158">Cierre al cliente como se describe en el siguiente fragmento:</span><span class="sxs-lookup"><span data-stu-id="a4d93-158">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
8.  <span data-ttu-id="a4d93-159">Compile el proyecto y, a continuación, ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="a4d93-159">Build the project and then run it.</span></span> <span data-ttu-id="a4d93-160">El identificador de empleado del empleado recién insertado se muestra en la consola.</span><span class="sxs-lookup"><span data-stu-id="a4d93-160">The employee ID of the newly inserted employee is displayed on the console.</span></span>