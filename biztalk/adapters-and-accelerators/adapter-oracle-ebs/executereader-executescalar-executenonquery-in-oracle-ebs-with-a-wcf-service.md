---
title: Las operaciones de ExecuteReader, ExecuteScalar o ExecuteNonQuery en Oracle E-Business Suite mediante el modelo de servicio WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 54c42db1-9a4d-4003-af69-f75ff48b575a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eaffcdc59cd6093feababc8319c1f9f1964a0d05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217388"
---
# <a name="executereader-executescalar-or-executenonquery-operations-in-oracle-e-business-suite-using-the-wcf-service-model"></a><span data-ttu-id="b9180-102">Operaciones de ExecuteReader, ExecuteScalar o ExecuteNonQuery en Oracle E-Business Suite mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="b9180-102">ExecuteReader, ExecuteScalar, or ExecuteNonQuery operations in Oracle E-Business Suite using the WCF service model</span></span>
<span data-ttu-id="b9180-103">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone operaciones genéricas como **ExecuteNonQuery**, **ExecuteReader**, y **ExecuteScalar**.</span><span class="sxs-lookup"><span data-stu-id="b9180-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] exposes generic operations such as **ExecuteNonQuery**, **ExecuteReader**, and **ExecuteScalar**.</span></span> <span data-ttu-id="b9180-104">Puede utilizar estas operaciones para ejecutar cualquier instrucción en Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="b9180-104">You can use these operations to execute any statement on Oracle E-Business Suite.</span></span> <span data-ttu-id="b9180-105">Estas operaciones varían en función del tipo de respuesta que se obtiene de la instrucción.</span><span class="sxs-lookup"><span data-stu-id="b9180-105">These operations differ based on the kind of response you get for the statement.</span></span> <span data-ttu-id="b9180-106">Para obtener más información acerca del modo en que el adaptador admite estas operaciones, vea [soporte técnico para las operaciones de ExecuteScalar, ExecuteReader y ExecuteNonQuery](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).</span><span class="sxs-lookup"><span data-stu-id="b9180-106">For more information about how the adapter supports these operations, see [Support for ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).</span></span>  
  
 <span data-ttu-id="b9180-107">En este tema se muestra cómo realizar una **ExecuteReader** operación mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] mediante el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="b9180-107">This topic demonstrates how to perform an **ExecuteReader** operation using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] using the WCF service model.</span></span> <span data-ttu-id="b9180-108">Puede seguir el mismo conjunto de procedimientos que se describen en este tema para realizar **ExecuteNonQuery** y **ExecuteScalar** operaciones.</span><span class="sxs-lookup"><span data-stu-id="b9180-108">You can follow the same set of procedures described in this topic to perform **ExecuteNonQuery** and **ExecuteScalar** operations.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="b9180-109">Acerca de los ejemplos usados en este tema</span><span class="sxs-lookup"><span data-stu-id="b9180-109">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="b9180-110">El ejemplo de este tema se realiza una **ExecuteReader** operación que se realiza una operación SELECT en la tabla de interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="b9180-110">The example in this topic performs an **ExecuteReader** operation to perform a SELECT operation on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="b9180-111">La tabla se crea mediante la ejecución de la secuencia de comandos que se proporciona con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="b9180-111">The table is created by running the script provided with the samples.</span></span> <span data-ttu-id="b9180-112">Para obtener más información acerca de los ejemplos, vea [ejemplos para el adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="b9180-112">For more information about samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="b9180-113">Obtener un ejemplo, **ExecuteReader**, que se basa en este tema, también se proporciona con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="b9180-113">A sample, **ExecuteReader**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="b9180-114">La clase de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="b9180-114">The WCF Client Class</span></span>  
 <span data-ttu-id="b9180-115">El nombre del cliente WCF generado para invocar operaciones genéricas (ExecuteNonQuery, ExecuteReader o ExecuteScalar) utilizando el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] aparece en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="b9180-115">The name of the WCF client generated for invoking generic operations (ExecuteNonQuery, ExecuteReader, or ExecuteScalar) using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="b9180-116">Operaciones</span><span class="sxs-lookup"><span data-stu-id="b9180-116">Operations</span></span>|<span data-ttu-id="b9180-117">Nombre de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="b9180-117">WCF Client Name</span></span>|  
|----------------|---------------------|  
|<span data-ttu-id="b9180-118">ExecuteNonQuery, ExecuteReader o ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="b9180-118">ExecuteNonQuery, ExecuteReader, or ExecuteScalar</span></span>|<span data-ttu-id="b9180-119">GenericOperation_Client</span><span class="sxs-lookup"><span data-stu-id="b9180-119">GenericOperation_Client</span></span>|  
  
### <a name="method-signature-for-invoking-generic-operations"></a><span data-ttu-id="b9180-120">Firma de método para invocar operaciones genéricas</span><span class="sxs-lookup"><span data-stu-id="b9180-120">Method Signature for Invoking Generic Operations</span></span>  
 <span data-ttu-id="b9180-121">En la tabla siguiente se muestra la firma para el método expuesto para invocar las operaciones genéricas.</span><span class="sxs-lookup"><span data-stu-id="b9180-121">The following table shows the signature for the method exposed to invoke the generic operations.</span></span>  
  
|<span data-ttu-id="b9180-122">Operación</span><span class="sxs-lookup"><span data-stu-id="b9180-122">Operation</span></span>|<span data-ttu-id="b9180-123">Firma de método</span><span class="sxs-lookup"><span data-stu-id="b9180-123">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="b9180-124">ExecuteNonQuery</span><span class="sxs-lookup"><span data-stu-id="b9180-124">ExecuteNonQuery</span></span>|<span data-ttu-id="b9180-125">int ExecuteNonQuery (cadena de consulta, string [] OutputRefCursorNames, out] System.Data.DataSet OutputRefCursors)</span><span class="sxs-lookup"><span data-stu-id="b9180-125">int ExecuteNonQuery(string Query, string[] OutputRefCursorNames, out System.Data.DataSet[] OutputRefCursors)</span></span>|  
|<span data-ttu-id="b9180-126">ExecuteReader</span><span class="sxs-lookup"><span data-stu-id="b9180-126">ExecuteReader</span></span>|<span data-ttu-id="b9180-127">System.Data.DataSet ExecuteReader(string Query)</span><span class="sxs-lookup"><span data-stu-id="b9180-127">System.Data.DataSet ExecuteReader(string Query)</span></span>|  
|<span data-ttu-id="b9180-128">ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="b9180-128">ExecuteScalar</span></span>|<span data-ttu-id="b9180-129">cadena ExecuteScalar(string Query)</span><span class="sxs-lookup"><span data-stu-id="b9180-129">string ExecuteScalar(string Query)</span></span>|  
  
 <span data-ttu-id="b9180-130">Por ejemplo, la firma para los métodos de operación genérica se muestra en el siguiente fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="b9180-130">As an example, the signature for the generic operation methods is shown in the following code snippet.</span></span>  
  
```  
public partial class GenericOperation_Client : System.ServiceModel.ClientBase<GenericOperation_>, GenericOperation_ {  
  public int ExecuteNonQuery(string Query, string[] OutputRefCursorNames, out System.Data.DataSet[] OutputRefCursors);  
  public System.Data.DataSet ExecuteReader(string Query);  
  public string ExecuteScalar(string Query);  
}  
```  
  
 <span data-ttu-id="b9180-131">En este fragmento de código</span><span class="sxs-lookup"><span data-stu-id="b9180-131">In this snippet,</span></span>  
  
-   <span data-ttu-id="b9180-132">`GenericOperation_Client`es el nombre de la clase.</span><span class="sxs-lookup"><span data-stu-id="b9180-132">`GenericOperation_Client` is the name of the class.</span></span> <span data-ttu-id="b9180-133">Esta clase se utiliza para crear un cliente para invocar la operación genérica, ExecuteReader.</span><span class="sxs-lookup"><span data-stu-id="b9180-133">This class is used to create a client to invoke the generic operation, ExecuteReader.</span></span>  
  
-   <span data-ttu-id="b9180-134">`public System.Data.DataSet ExecuteReader(string Query)`es el método que se invoca para llevar a cabo una instrucción SELECT en la tabla de interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="b9180-134">`public System.Data.DataSet ExecuteReader(string Query)` is the method that you invoke to perform a SELECT statement on the MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-an-executereader-operation"></a><span data-ttu-id="b9180-135">Creación de un cliente WCF para invocar la operación ExecuteReader</span><span class="sxs-lookup"><span data-stu-id="b9180-135">Creating a WCF Client to Invoke an ExecuteReader Operation</span></span>  
 <span data-ttu-id="b9180-136">El conjunto de acciones necesarias para realizar una operación en Oracle E-Business Suite mediante un cliente WCF genérico implica un conjunto de tareas que se describen en [información general sobre el modelo de servicio WCF con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="b9180-136">The generic set of actions required to perform an operation on Oracle E-Business Suite using a WCF client involves a set of tasks described in [Overview of the WCF service model with the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md).</span></span> <span data-ttu-id="b9180-137">Esta sección describe cómo crear un cliente WCF para invocar la **ExecuteReader** operación.</span><span class="sxs-lookup"><span data-stu-id="b9180-137">This section describes how to create a WCF client to invoke the **ExecuteReader** operation.</span></span>  
  
#### <a name="to-create-a-wcf-client-to-invoke-executereader-operation"></a><span data-ttu-id="b9180-138">Para crear un cliente WCF para invocar la operación ExecuteReader</span><span class="sxs-lookup"><span data-stu-id="b9180-138">To create a WCF client to invoke ExecuteReader operation</span></span>  
  
1.  <span data-ttu-id="b9180-139">Cree un proyecto de Visual C# en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b9180-139">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="b9180-140">De este tema, cree una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="b9180-140">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="b9180-141">Generar la clase de cliente WCF para la **ExecuteReader** operación genérica.</span><span class="sxs-lookup"><span data-stu-id="b9180-141">Generate the WCF client class for the **ExecuteReader** generic operation.</span></span> <span data-ttu-id="b9180-142">Esta operación está disponible bajo el nodo raíz cuando se conecta a la Oracle E-Business Suite mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9180-142">This operation is available under the root node when you connect to the Oracle E-Business Suite using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="b9180-143">Para obtener más información acerca de cómo generar una clase de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="b9180-143">For more information about generating a WCF client class, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b9180-144">Antes de generar la clase de cliente WCF, asegúrese de establecer el **EnableBizTalkCompatibilityMode** enlaza la propiedad en false.</span><span class="sxs-lookup"><span data-stu-id="b9180-144">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3.  <span data-ttu-id="b9180-145">En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.OracleEBS` y `Microsoft.ServiceModel.Channels`.</span><span class="sxs-lookup"><span data-stu-id="b9180-145">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4.  <span data-ttu-id="b9180-146">Abra el archivo Program.cs y agregue los espacios de nombres siguientes:</span><span class="sxs-lookup"><span data-stu-id="b9180-146">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `System.ServiceModel`  
  
5.  <span data-ttu-id="b9180-147">En el archivo Program.cs, cree a un cliente tal y como se describe en el siguiente fragmento.</span><span class="sxs-lookup"><span data-stu-id="b9180-147">In the Program.cs file, create a client as described in the snippet below.</span></span>  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    EndpointAddress address = new EndpointAddress("oracleebs://ebs-72-11");  
    GenericOperation_Client client = new GenericOperation_Client(binding, address);  
    ```  
  
     <span data-ttu-id="b9180-148">En este fragmento de código, `GenericOperation_Client` es el cliente WCF definido en OracleEBSBindingClient.cs.</span><span class="sxs-lookup"><span data-stu-id="b9180-148">In this snippet, `GenericOperation_Client` is the WCF client defined in OracleEBSBindingClient.cs.</span></span> <span data-ttu-id="b9180-149">Este archivo es generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9180-149">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b9180-150">En este fragmento, especificar explícitamente la dirección de enlace y el punto de conexión en el código de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b9180-150">In this snippet, you explicitly specify the binding and endpoint address in your application code.</span></span> <span data-ttu-id="b9180-151">Puede utilizar estos valores desde el archivo de configuración del aplicación, app.config, también generado el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9180-151">You can use these values from the application configuration file, app.config, also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="b9180-152">Para obtener más información sobre las distintas maneras de especificar el enlace del cliente, consulte [configurar un cliente de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span><span class="sxs-lookup"><span data-stu-id="b9180-152">For more information about the different ways of specifying client binding, see [Configure a client binding for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span></span>  
  
6.  <span data-ttu-id="b9180-153">Establezca las credenciales para el cliente.</span><span class="sxs-lookup"><span data-stu-id="b9180-153">Set the credentials for the client.</span></span>  
  
    ```  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
7.  <span data-ttu-id="b9180-154">Dado que está realizando una operación en una tabla de interfaz, debe establecer el contexto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b9180-154">Because you are performing an operation on an interface table, you must set the application context.</span></span> <span data-ttu-id="b9180-155">En este ejemplo, para establecer el contexto de la aplicación, especifique la **OracleUserName**, **OraclePassword**, y **OracleEBSResponsibilityName** propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="b9180-155">In this example, to set the application context, you specify the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="b9180-156">Para obtener más información sobre el contexto de la aplicación, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span><span class="sxs-lookup"><span data-stu-id="b9180-156">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
    ```  
    binding.OracleUserName = "myOracleEBSUserName";  
    binding.OraclePassword = "myOracleEBSPassword";  
    binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
    ```  
  
8.  <span data-ttu-id="b9180-157">Abra al cliente como se describe en el siguiente fragmento:</span><span class="sxs-lookup"><span data-stu-id="b9180-157">Open the client as described in the snippet below:</span></span>  
  
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
  
9. <span data-ttu-id="b9180-158">Invocar la **ExecuteReader** operación para realizar la operación de selección en la tabla MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="b9180-158">Invoke the **ExecuteReader** operation for performing the SELECT operation on MS_SAMPLE_EMPLOYEE table.</span></span> <span data-ttu-id="b9180-159">Antes de invocar la operación ExecuteReader, debe agregar el `System.Data` espacio de nombres en el código.</span><span class="sxs-lookup"><span data-stu-id="b9180-159">Before you invoke the ExecuteReader operation, you must add the `System.Data` namespace to your code.</span></span>  
  
    ```  
    string query = "SELECT * FROM MS_SAMPLE_EMPLOYEE";  
    DataSet ds = client.ExecuteReader(query);  
  
    Console.WriteLine("Invoking the SELECT statement using ExecuteReader");  
    Console.WriteLine("*****************************************************");  
    foreach (DataTable tab in ds.Tables)  
    {  
       foreach (DataRow row in tab.Rows)  
       {  
          Console.WriteLine("The details of the employee are: ");  
          for (int i = 0; i < tab.Columns.Count; i++)  
          {  
             Console.WriteLine(row[i]);  
          }  
          Console.WriteLine();  
       }  
    }  
    Console.WriteLine("*****************************************************");  
    Console.ReadLine();  
  
    ```  
  
10. <span data-ttu-id="b9180-160">Cierre al cliente como se describe en el siguiente fragmento:</span><span class="sxs-lookup"><span data-stu-id="b9180-160">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
11. <span data-ttu-id="b9180-161">Compile el proyecto y, a continuación, ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="b9180-161">Build the project and then run it.</span></span> <span data-ttu-id="b9180-162">Todos los registros en la tabla MS_SAMPLE_EMPLOYEE se muestran en la consola.</span><span class="sxs-lookup"><span data-stu-id="b9180-162">All the records in the MS_SAMPLE_EMPLOYEE table are displayed on the console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9180-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9180-163">See Also</span></span>  
 [<span data-ttu-id="b9180-164">Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="b9180-164">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)