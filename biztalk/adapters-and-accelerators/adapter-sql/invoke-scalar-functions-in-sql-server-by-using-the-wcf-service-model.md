---
title: Invocar funciones escalares en SQL Server mediante el modelo de servicio WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a331e275-3c81-41a8-9ba1-3a801ebc259a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a04904f1170644498d49670104a842b4c8f9dd2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="invoke-scalar-functions-in-sql-server-by-using-the-wcf-service-model"></a><span data-ttu-id="f2b5e-102">Invocar funciones escalares en SQL Server mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="f2b5e-102">Invoke Scalar Functions in SQL Server by Using the WCF Service Model</span></span>
<span data-ttu-id="f2b5e-103">Puede usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en una aplicación de .NET mediante el modelo de servicio WCF para invocar funciones escalares en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-103">You can use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in a .NET application using the WCF service model to invoke scalar functions in SQL Server.</span></span> <span data-ttu-id="f2b5e-104">El adaptador expone las funciones escalares como métodos que se pueden invocar directamente en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-104">The adapter exposes the scalar functions as methods that can be invoked directly on SQL Server.</span></span> <span data-ttu-id="f2b5e-105">Para obtener más información acerca del modo en que el adaptador admite funciones escalares, consulte [ejecutar funciones escalares en SQL Server mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/execute-scalar-functions-in-sql-server-using-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="f2b5e-105">For more information about how the adapter supports scalar functions, see [Execute Scalar Functions in SQL Server using the SQL adapter](../../adapters-and-accelerators/adapter-sql/execute-scalar-functions-in-sql-server-using-the-sql-adapter.md).</span></span>  
  
## <a name="how-this-topic-demonstrates-invoking-scalar-functions-using-the-wcf-service-model"></a><span data-ttu-id="f2b5e-106">Cómo en este tema se muestra cómo invocar funciones escalares mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="f2b5e-106">How This Topic Demonstrates Invoking Scalar Functions Using the WCF Service Model</span></span>  
 <span data-ttu-id="f2b5e-107">Este tema muestra cómo invocar la función GET_EMP_ID en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-107">This topic demonstrates how to invoke the GET_EMP_ID function in a SQL Server database.</span></span> <span data-ttu-id="f2b5e-108">La función GET_EMP_ID toma la designación de un empleado en el **empleado** tabla y devuelve el identificador de empleado correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-108">The GET_EMP_ID function takes the designation of an employee in the **Employee** table and returns the corresponding employee ID.</span></span> <span data-ttu-id="f2b5e-109">La función GET_EMP_ID y **empleado** tabla se crean al ejecutar el script SQL que se proporciona con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-109">The GET_EMP_ID function and the **Employee** table are created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="f2b5e-110">Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f2b5e-110">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="f2b5e-111">Acerca de los ejemplos usados en este tema</span><span class="sxs-lookup"><span data-stu-id="f2b5e-111">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="f2b5e-112">El ejemplo de este tema, invoca la función escalar GET_EMP_ID en la tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-112">The example in this topic invoked the GET_EMP_ID scalar function on the Employee table.</span></span> <span data-ttu-id="f2b5e-113">La función GET_EMP_ID y **empleado** tabla se crean al ejecutar el script SQL que se proporciona con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-113">The GET_EMP_ID function and the **Employee** table are created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="f2b5e-114">Obtener un ejemplo, **ScalarFunction_ServiceModel**, que se basa en este tema, también se proporciona con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-114">A sample, **ScalarFunction_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span> <span data-ttu-id="f2b5e-115">Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f2b5e-115">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="f2b5e-116">La clase de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="f2b5e-116">The WCF Client Class</span></span>  
 <span data-ttu-id="f2b5e-117">El nombre del cliente WCF generado para invocar la función escalar en SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] aparece en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-117">The name of the WCF client generated for invoking the scalar function in SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="f2b5e-118">Artefactos de base de datos SQL Server</span><span class="sxs-lookup"><span data-stu-id="f2b5e-118">SQL Server Database Artifact</span></span>|<span data-ttu-id="f2b5e-119">Nombre de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="f2b5e-119">WCF Client Name</span></span>|  
|----------------------------------|---------------------|  
|<span data-ttu-id="f2b5e-120">Función escalar</span><span class="sxs-lookup"><span data-stu-id="f2b5e-120">Scalar function</span></span>|<span data-ttu-id="f2b5e-121">Cliente ScalarFunctions_ [esquema]</span><span class="sxs-lookup"><span data-stu-id="f2b5e-121">ScalarFunctions_[SCHEMA]Client</span></span>|  
  
 <span data-ttu-id="f2b5e-122">[Esquema] = artefactos de la colección de SQL Server; Por ejemplo, dbo.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-122">[SCHEMA] = Collection of SQL Server artifacts; for example, dbo.</span></span>  
  
### <a name="method-signature-for-invoking-scalar-functions"></a><span data-ttu-id="f2b5e-123">Firma de método para invocar funciones escalares</span><span class="sxs-lookup"><span data-stu-id="f2b5e-123">Method Signature for Invoking Scalar Functions</span></span>  
 <span data-ttu-id="f2b5e-124">La siguiente tabla muestra las firmas de método para las operaciones básicas en una tabla.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-124">The following table shows the method signatures for the basic operations on a table.</span></span> <span data-ttu-id="f2b5e-125">Las firmas son los mismos para una vista, excepto en que el espacio de nombres de vista y el nombre sustituirán a las de la tabla.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-125">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  
  
|<span data-ttu-id="f2b5e-126">Operación</span><span class="sxs-lookup"><span data-stu-id="f2b5e-126">Operation</span></span>|<span data-ttu-id="f2b5e-127">Firma de método</span><span class="sxs-lookup"><span data-stu-id="f2b5e-127">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="f2b5e-128">Nombre de la función escalar</span><span class="sxs-lookup"><span data-stu-id="f2b5e-128">Scalar function name</span></span>|<span data-ttu-id="f2b5e-129">pública *< return_type >**< scalar_function_name >*(parámetro1, parámetro2,...)</span><span class="sxs-lookup"><span data-stu-id="f2b5e-129">public *<return_type>**<scalar_function_name>*(param1, param2, …)</span></span>|  
  
 <span data-ttu-id="f2b5e-130">\<*retrun_type* \> = tipo de valor devuelto definido en la definición de función</span><span class="sxs-lookup"><span data-stu-id="f2b5e-130">\<*retrun_type*\> = Return type defined in the function definition</span></span>  
  
 <span data-ttu-id="f2b5e-131">\<*scalar_function_name* \> = nombre de la función escalar.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-131">\<*scalar_function_name*\> = Name of the scalar function.</span></span>  
  
 <span data-ttu-id="f2b5e-132">Por ejemplo, el código siguiente muestra las firmas de método para generar una clase de cliente WCF para la **GET_EMP_ID** funciones escalares, en el esquema dbo, que toma la designación de empleado como parámetro y devuelve un empleado (Id. valor entero).</span><span class="sxs-lookup"><span data-stu-id="f2b5e-132">As an example, the following code shows the method signatures for a WCF client class generated for the **GET_EMP_ID** scalar functions, in the dbo schema, which takes the employee designation as a parameter and returns an employee ID (integer).</span></span>  
  
```  
public partial class ScalarFunctions_dboClient : System.ServiceModel.ClientBase<ScalarFunctions_dbo>, ScalarFunctions_dbo {      
    public System.Nullable<int> GET_EMP_ID(string emp_desig);  
}  
```  
  
 <span data-ttu-id="f2b5e-133">En este fragmento de código, **ScalarFunctions_dboClient** es el nombre de la clase WCF en el SqlAdapterBindingClient.cs generado por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2b5e-133">In this snippet, **ScalarFunctions_dboClient** is the name of the WCF class in the SqlAdapterBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
### <a name="parameters-for-invoking-scalar-functions"></a><span data-ttu-id="f2b5e-134">Parámetros para invocar funciones escalares</span><span class="sxs-lookup"><span data-stu-id="f2b5e-134">Parameters for Invoking Scalar Functions</span></span>  
 <span data-ttu-id="f2b5e-135">Los parámetros para los métodos expuestos por el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para invocar un valor escalar, función son los mismos que los parámetros definidos en la definición de función escalar en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-135">The parameters for the methods exposed by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to invoke a scalar function are the same as the parameters defined in the scalar function definition in SQL Server.</span></span> <span data-ttu-id="f2b5e-136">Por ejemplo, el parámetro para invocar la función escalar GET_EMP_ID es emp_desig y toma la designación de un empleado.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-136">For example, the parameter for invoking the GET_EMP_ID scalar function is emp_desig and takes an employee’s designation.</span></span>  
  
 <span data-ttu-id="f2b5e-137">Una vez más, el valor devuelto para una función escalar es igual que el valor devuelto definido en la definición de función escalar en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-137">Again, the return value for a scalar function is same as the return value defined in the scalar function definition in SQL Server.</span></span> <span data-ttu-id="f2b5e-138">Por ejemplo, el valor devuelto para la función GET_EMP_ID es el identificador de un empleado de tipo entero.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-138">For example, the return value for the GET_EMP_ID function is an employee’s ID of type integer.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-scalar-functions"></a><span data-ttu-id="f2b5e-139">Creación de un cliente WCF para invocar funciones escalares</span><span class="sxs-lookup"><span data-stu-id="f2b5e-139">Creating a WCF Client to Invoke Scalar Functions</span></span>  
 <span data-ttu-id="f2b5e-140">El conjunto de acciones necesarias para realizar una operación en SQL Server mediante un cliente de WCF genérico implica un conjunto de tareas que se describen en [información general sobre el modelo de servicio de WCF con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="f2b5e-140">The generic set of actions required to perform an operation on SQL Server using a WCF client involves a set of tasks described in [Overview of the WCF Service Model with the SQL Adapter](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span></span> <span data-ttu-id="f2b5e-141">Esta sección describe cómo crear un cliente WCF para invocar la **GET_EMP_ID** función escalar.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-141">This section describes how to create a WCF client to invoke the **GET_EMP_ID** scalar function.</span></span>  
  
#### <a name="to-create-a-wcf-client"></a><span data-ttu-id="f2b5e-142">Para crear a un cliente WCF</span><span class="sxs-lookup"><span data-stu-id="f2b5e-142">To create a WCF client</span></span>  
  
1.  <span data-ttu-id="f2b5e-143">Crear un proyecto de Visual C# en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2b5e-143">Create a Visual C# project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="f2b5e-144">De este tema, cree una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-144">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="f2b5e-145">Generar la clase de cliente WCF para la **GET_EMP_ID** función escalar.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-145">Generate the WCF client class for the **GET_EMP_ID** scalar function.</span></span> <span data-ttu-id="f2b5e-146">Para obtener más información acerca de cómo generar una clase de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="f2b5e-146">For more information about generating a WCF client class, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
3.  <span data-ttu-id="f2b5e-147">En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.Sql` y `Microsoft.ServiceModel.Channels`.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-147">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4.  <span data-ttu-id="f2b5e-148">Abra Program.cs y cree a un cliente tal y como se describe en el siguiente fragmento.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-148">Open the Program.cs and create a client as described in the snippet below.</span></span>  
  
    ```  
  
              ScalarFunctions_dboClient client = new ScalarFunctions_dboClient("SqlAdapterBinding_ScalarFunctions_dbo");  
    client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     <span data-ttu-id="f2b5e-149">En este fragmento de código, `ScalarFunctions_dboClient` es el cliente WCF definido en SqlAdapterBindingClient.cs.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-149">In this snippet, `ScalarFunctions_dboClient` is the WCF client defined in SqlAdapterBindingClient.cs.</span></span> <span data-ttu-id="f2b5e-150">Este archivo es generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2b5e-150">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="f2b5e-151">`SqlAdapterBinding_ScalarFunctions_dbo`es el nombre de la configuración de punto de conexión de cliente y se define en el archivo app.config. Este archivo también se genera mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y contiene las propiedades de enlace y otras opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-151">`SqlAdapterBinding_ScalarFunctions_dbo` is the name of the client endpoint configuration and is defined in the app.config. This file is also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and contains the binding properties and other configuration settings.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f2b5e-152">En este fragmento de código, utilice el enlace y dirección de punto de conexión del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-152">In this snippet, you use the binding and endpoint address from the configuration file.</span></span> <span data-ttu-id="f2b5e-153">Puede especificar también explícitamente estos valores en el código.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-153">You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="f2b5e-154">Para obtener más información sobre las distintas formas de especificar, a continuación, enlace de cliente, consulte [configurar un enlace de cliente para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="f2b5e-154">For more information on the different ways of specifying then client binding, see [Configure  a Client Binding for the SQL Adapter](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
5.  <span data-ttu-id="f2b5e-155">Abra al cliente como se describe en el siguiente fragmento:</span><span class="sxs-lookup"><span data-stu-id="f2b5e-155">Open the client as described in the snippet below:</span></span>  
  
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
  
6.  <span data-ttu-id="f2b5e-156">Invocar la **GET_EMP_ID** función para recuperar el identificador de un empleado con la designación como "Administrador".</span><span class="sxs-lookup"><span data-stu-id="f2b5e-156">Invoke the **GET_EMP_ID** function to retrieve the ID for an employee with the designation as “Manager”.</span></span>  
  
    ```  
    Console.WriteLine("Invoking the GET_EMP_ID function");  
    string emp_designation = "Manager";  
    try  
    {  
          System.Nullable<int> emp_id = client.GET_EMP_ID(emp_designation);  
          Console.WriteLine("The Employee ID for the employee with 'Manager' designation is:" + emp_id);  
    }  
    catch (Exception e)  
    {  
          Console.WriteLine("Exception: " + e.Message);  
          throw;  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="f2b5e-157">Por simplicidad, la **empleado** tabla tiene solo un empleado con la designación de "Administrador".</span><span class="sxs-lookup"><span data-stu-id="f2b5e-157">For the sake of simplicity, the **Employee** table has only one employee with “Manager” designation.</span></span> <span data-ttu-id="f2b5e-158">Si la tabla de destino tiene más empleados con la designación del mismo, debe definir la función en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-158">If your target table has more employees with the same designation, you must define the function accordingly.</span></span>  
  
7.  <span data-ttu-id="f2b5e-159">Cierre al cliente como se describe en el siguiente fragmento:</span><span class="sxs-lookup"><span data-stu-id="f2b5e-159">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
8.  <span data-ttu-id="f2b5e-160">Compile el proyecto y, a continuación, ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="f2b5e-160">Build the project and then run it.</span></span> <span data-ttu-id="f2b5e-161">La aplicación muestra el identificador de empleado del empleado con la designación de "Administrador".</span><span class="sxs-lookup"><span data-stu-id="f2b5e-161">The application displays the employee ID of the employee with the designation of “Manager”.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2b5e-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2b5e-162">See Also</span></span>  
[<span data-ttu-id="f2b5e-163">Desarrollar aplicaciones con el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="f2b5e-163">Develop applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)