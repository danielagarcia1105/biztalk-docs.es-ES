---
title: Invocar funciones con valores de tabla en SQL Server mediante el modelo de servicio WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48688bcc-36b4-4cc1-b078-17e7a5e1cf8c
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a736a82e57f71568f8718a6e4d41e7b649004120
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224700"
---
# <a name="invoke-table-valued-functions-in-sql-server-by-using-the-wcf-service-model"></a><span data-ttu-id="1f899-102">Invocar funciones con valores de tabla en SQL Server mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="1f899-102">Invoke Table-Valued Functions in SQL Server by Using the WCF Service Model</span></span>
<span data-ttu-id="1f899-103">Puede usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en una aplicación de .NET mediante el modelo de servicio WCF para invocar funciones con valores de tabla en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1f899-103">You can use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in a .NET application using the WCF service model to invoke table-valued functions in SQL Server.</span></span> <span data-ttu-id="1f899-104">El adaptador expone las funciones con valores de tabla como métodos que se pueden invocar directamente en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1f899-104">The adapter exposes the table-valued functions as methods that can be invoked directly on SQL Server.</span></span> <span data-ttu-id="1f899-105">Para obtener más información acerca del modo en que el adaptador admite funciones escalares, consulte [Execute Table-Valued funciones en SQL Server mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/execute-table-valued-functions-in-sql-server-using-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="1f899-105">For more information about how the adapter supports scalar functions, see [Execute Table-Valued Functions in SQL Server using the SQL adapter](../../adapters-and-accelerators/adapter-sql/execute-table-valued-functions-in-sql-server-using-the-sql-adapter.md).</span></span>  
  
 <span data-ttu-id="1f899-106">Este tema muestra cómo invocar la función TVF_EMPLOYEE en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1f899-106">This topic demonstrates how to invoke the TVF_EMPLOYEE function in a SQL Server database.</span></span> <span data-ttu-id="1f899-107">La función TVF_EMPLOYEE toma la designación de un empleado en el **empleado** tabla y devuelve el registro del empleado.</span><span class="sxs-lookup"><span data-stu-id="1f899-107">The TVF_EMPLOYEE function takes the designation of an employee in the **Employee** table and returns the record for the employee.</span></span> <span data-ttu-id="1f899-108">La función TVF_EMPLOYEE y **empleado** tabla se crean al ejecutar el script SQL que se proporciona con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="1f899-108">The TVF_EMPLOYEE function and the **Employee** table are created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="1f899-109">Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1f899-109">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="1f899-110">Acerca de los ejemplos usados en este tema</span><span class="sxs-lookup"><span data-stu-id="1f899-110">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="1f899-111">El ejemplo de este tema, invoca la función con valores de tabla TVF_EMPLOYEE en el **empleado** tabla.</span><span class="sxs-lookup"><span data-stu-id="1f899-111">The example in this topic invoked the TVF_EMPLOYEE table-valued function on the **Employee** table.</span></span> <span data-ttu-id="1f899-112">Función TVF_EMPLOYEE y **empleado** tabla se crean al ejecutar el script SQL que se proporciona con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="1f899-112">TVF_EMPLOYEE function and the **Employee** table are created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="1f899-113">Obtener un ejemplo, **TableFunction_ServiceModel**, que se basa en este tema, también se proporciona con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="1f899-113">A sample, **TableFunction_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span> <span data-ttu-id="1f899-114">Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1f899-114">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="1f899-115">La clase de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="1f899-115">The WCF Client Class</span></span>  
 <span data-ttu-id="1f899-116">El nombre del cliente WCF generado para invocar la función escalar en SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] aparece en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="1f899-116">The name of the WCF client generated for invoking the scalar function in SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="1f899-117">Artefactos de base de datos SQL Server</span><span class="sxs-lookup"><span data-stu-id="1f899-117">SQL Server Database Artifact</span></span>|<span data-ttu-id="1f899-118">Nombre de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="1f899-118">WCF Client Name</span></span>|  
|----------------------------------|---------------------|  
|<span data-ttu-id="1f899-119">Función con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="1f899-119">Table-valued function</span></span>|<span data-ttu-id="1f899-120">Cliente TableValuedFunctions_ [esquema]</span><span class="sxs-lookup"><span data-stu-id="1f899-120">TableValuedFunctions_[SCHEMA]Client</span></span>|  
  
 <span data-ttu-id="1f899-121">[Esquema] = artefactos de la colección de SQL Server; Por ejemplo, dbo.</span><span class="sxs-lookup"><span data-stu-id="1f899-121">[SCHEMA] = Collection of SQL Server artifacts; for example, dbo.</span></span>  
  
### <a name="method-signature-for-invoking-table-valued-functions"></a><span data-ttu-id="1f899-122">Firma de método para llamar a funciones con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="1f899-122">Method Signature for Invoking Table-valued Functions</span></span>  
 <span data-ttu-id="1f899-123">La siguiente tabla muestra las firmas de método para las operaciones básicas en una tabla.</span><span class="sxs-lookup"><span data-stu-id="1f899-123">The following table shows the method signatures for the basic operations on a table.</span></span> <span data-ttu-id="1f899-124">Las firmas son los mismos para una vista, excepto en que el espacio de nombres de vista y el nombre sustituirán a las de la tabla.</span><span class="sxs-lookup"><span data-stu-id="1f899-124">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  
  
|<span data-ttu-id="1f899-125">Operación</span><span class="sxs-lookup"><span data-stu-id="1f899-125">Operation</span></span>|<span data-ttu-id="1f899-126">Firma de método</span><span class="sxs-lookup"><span data-stu-id="1f899-126">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="1f899-127">Nombre de la función con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="1f899-127">Table-valued function name</span></span>|<span data-ttu-id="1f899-128">público [NAMESPACE] [nombre_función] [] [nombre_función] (parámetro1, parámetro2,...\)</span><span class="sxs-lookup"><span data-stu-id="1f899-128">public [NAMESPACE][FUNCTION_NAME][] [FUNCTION_NAME](param1, param2, …\)</span></span>|  
  
 <span data-ttu-id="1f899-129">[NAMESPACE] = el espacio de nombres, por ejemplo, schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE</span><span class="sxs-lookup"><span data-stu-id="1f899-129">[NAMESPACE] = The namespace, for example, schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE</span></span>  
  
 <span data-ttu-id="1f899-130">[Nombre_función] = nombre de la función con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="1f899-130">[FUNCTION_NAME] = Name of the table-valued function.</span></span>  
  
 <span data-ttu-id="1f899-131">Por ejemplo, el código siguiente muestra las firmas de método para generar una clase de cliente WCF para la **TVF_EMPLOYEE** funciones escalares, en el esquema dbo, que toma la designación de empleado como parámetro y devuelve el empleado registro.</span><span class="sxs-lookup"><span data-stu-id="1f899-131">As an example, the following code shows the method signatures for a WCF client class generated for the **TVF_EMPLOYEE** scalar functions, in the dbo schema, which takes the employee designation as a parameter and returns the employee record.</span></span>  
  
```  
public partial class TableValuedFunctions_dboClient : System.ServiceModel.ClientBase<TableValuedFunctions_dbo>, TableValuedFunctions_dbo {      
    public schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE[] TVF_EMPLOYEE(string emp_desig);  
}  
```  
  
 <span data-ttu-id="1f899-132">En este fragmento de código, **TableValuedFunctions_dboClient** es el nombre de la clase WCF en el SqlAdapterBindingClient.cs generado por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f899-132">In this snippet, **TableValuedFunctions_dboClient** is the name of the WCF class in the SqlAdapterBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
### <a name="parameters-for-invoking-table-valued-functions"></a><span data-ttu-id="1f899-133">Parámetros para llamar a funciones con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="1f899-133">Parameters for Invoking Table-valued Functions</span></span>  
 <span data-ttu-id="1f899-134">Los parámetros para los métodos expuestos por el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para invocar una función con valores de tabla son los mismos que los parámetros definidos en la definición de función en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1f899-134">The parameters for the methods exposed by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to invoke a table-valued function are the same as the parameters defined in the function definition in SQL Server.</span></span> <span data-ttu-id="1f899-135">Por ejemplo, el parámetro para invocar una función con valores de tabla de TVF_EMPLOYEE es emp_desig y toma la designación de un empleado.</span><span class="sxs-lookup"><span data-stu-id="1f899-135">For example, the parameter for invoking the TVF_EMPLOYEE table-valued function is emp_desig and takes an employee’s designation.</span></span>  
  
 <span data-ttu-id="1f899-136">Una vez más, el valor devuelto para una función con valores de tabla es igual que el valor devuelto definido en la definición de función en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1f899-136">Again, the return value for a table-valued function is same as the return value defined in the function definition in SQL Server.</span></span> <span data-ttu-id="1f899-137">Por ejemplo, el valor devuelto para la función TVF_EMPLOYEE es una matriz de registros de tipo schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE [].</span><span class="sxs-lookup"><span data-stu-id="1f899-137">For example, the return value for the TVF_EMPLOYEE function is an array of records of type schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE[].</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-table-valued-functions"></a><span data-ttu-id="1f899-138">Creación de un cliente WCF para invocar funciones con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="1f899-138">Creating a WCF Client to Invoke Table-valued Functions</span></span>  
 <span data-ttu-id="1f899-139">El conjunto de acciones necesarias para realizar una operación en SQL Server mediante un cliente de WCF genérico implica un conjunto de tareas que se describen en [información general sobre el modelo de servicio de WCF con el adaptador de SQL](overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="1f899-139">The generic set of actions required to perform an operation on SQL Server using a WCF client involves a set of tasks described in [Overview of the WCF Service Model with the SQL Adapter](overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span></span> <span data-ttu-id="1f899-140">Esta sección describe cómo crear un cliente WCF para invocar la **TVF_EMPLOYEE** función con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="1f899-140">This section describes how to create a WCF client to invoke the **TVF_EMPLOYEE** table-valued function.</span></span>  
  
 
1.  <span data-ttu-id="1f899-141">Crear un proyecto de Visual C# en [!INCLUDE[btsVStudioNoVersion](../../includes/btsVStudioNoVersion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f899-141">Create a Visual C# project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsVStudioNoVersion-md.md)].</span></span> <span data-ttu-id="1f899-142">De este tema, cree una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="1f899-142">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="1f899-143">Generar la clase de cliente WCF para la **TVF_EMPLOYEE** función escalar.</span><span class="sxs-lookup"><span data-stu-id="1f899-143">Generate the WCF client class for the **TVF_EMPLOYEE** scalar function.</span></span> <span data-ttu-id="1f899-144">Para obtener más información acerca de cómo generar una clase de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de SQL Server](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="1f899-144">For more information about generating a WCF client class, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
3.  <span data-ttu-id="1f899-145">En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.Sql` y `Microsoft.ServiceModel.Channels`.</span><span class="sxs-lookup"><span data-stu-id="1f899-145">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4.  <span data-ttu-id="1f899-146">Abra Program.cs y cree a un cliente tal y como se describe en el siguiente fragmento.</span><span class="sxs-lookup"><span data-stu-id="1f899-146">Open the Program.cs and create a client as described in the snippet below.</span></span>  
  
    ```  
  
              TableValuedFunctions_dboClient client = new TableValuedFunctions_dboClient("SqlAdapterBinding_TableValuedFunctions_dbo");  
    client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     <span data-ttu-id="1f899-147">En este fragmento de código, `TableValuedFunctions_dboClient` es el cliente WCF definido en SqlAdapterBindingClient.cs.</span><span class="sxs-lookup"><span data-stu-id="1f899-147">In this snippet, `TableValuedFunctions_dboClient` is the WCF client defined in SqlAdapterBindingClient.cs.</span></span> <span data-ttu-id="1f899-148">Este archivo es generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f899-148">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="1f899-149">`SqlAdapterBinding_TableValuedFunctions_dbo`es el nombre de la configuración de punto de conexión de cliente y se define en el archivo app.config. Este archivo también se genera mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y contiene las propiedades de enlace y otras opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="1f899-149">`SqlAdapterBinding_TableValuedFunctions_dbo` is the name of the client endpoint configuration and is defined in the app.config. This file is also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and contains the binding properties and other configuration settings.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1f899-150">En este fragmento de código, utilice el enlace y dirección de punto de conexión del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="1f899-150">In this snippet, you use the binding and endpoint address from the configuration file.</span></span> <span data-ttu-id="1f899-151">Puede especificar también explícitamente estos valores en el código.</span><span class="sxs-lookup"><span data-stu-id="1f899-151">You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="1f899-152">Para obtener más información sobre las distintas formas de especificar, a continuación, enlace de cliente, consulte [configurar un enlace de cliente para el adaptador de SQL](configure-a-client-binding-for-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="1f899-152">For more information on the different ways of specifying then client binding, see [Configure a Client Binding for the SQL Adapter](configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
5.  <span data-ttu-id="1f899-153">Abra al cliente como se describe en el siguiente fragmento:</span><span class="sxs-lookup"><span data-stu-id="1f899-153">Open the client as described in the snippet below:</span></span>  
  
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
  
6.  <span data-ttu-id="1f899-154">Invocar la **TVF_EMPLOYEE** función para recuperar todos los registros de empleados con la designación "Administrador".</span><span class="sxs-lookup"><span data-stu-id="1f899-154">Invoke the **TVF_EMPLOYEE** function to retrieve all the employee records having the “Manager” designation.</span></span>  
  
    ```  
    Console.WriteLine("Invoking the TVF_EMPLOYEE function");  
    schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE[] emp_details;  
    string emp_designation = "Manager";  
  
    try  
    {  
        emp_details = client.TVF_EMPLOYEE(emp_designation);  
    }  
    catch (Exception e)  
    {  
        Console.WriteLine("Exception: " + e.Message);  
        throw;  
    }  
    Console.WriteLine("The details for the employee with the 'Manager' designation are:");  
    Console.WriteLine("*******************************************************************");  
    for (int i = 0; i < emp_details.Length; i++)  
    {  
        Console.WriteLine("Employee ID        : " + emp_details[i].Employee_ID);  
        Console.WriteLine("Employee Name      : " + emp_details[i].Name);  
        Console.WriteLine("Employee Desigation: " + emp_details[i].Designation);  
        Console.WriteLine("Employee Salary    : " + emp_details[i].Salary);  
        Console.WriteLine();  
    }  
    ```  
  
7.  <span data-ttu-id="1f899-155">Cierre al cliente como se describe en el siguiente fragmento:</span><span class="sxs-lookup"><span data-stu-id="1f899-155">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
8.  <span data-ttu-id="1f899-156">Compile el proyecto y, a continuación, ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="1f899-156">Build the project and then run it.</span></span> <span data-ttu-id="1f899-157">La aplicación muestra el identificador de empleado, el nombre y el salario de todos los empleados con una designación de "Administrador".</span><span class="sxs-lookup"><span data-stu-id="1f899-157">The application displays the employee ID, name, and salary of all the employees with a “Manager” designation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f899-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f899-158">See Also</span></span>  
[<span data-ttu-id="1f899-159">Desarrollar aplicaciones con el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="1f899-159">Develop applications using the WCF Service model</span></span>](develop-sql-applications-using-the-wcf-service-model.md)