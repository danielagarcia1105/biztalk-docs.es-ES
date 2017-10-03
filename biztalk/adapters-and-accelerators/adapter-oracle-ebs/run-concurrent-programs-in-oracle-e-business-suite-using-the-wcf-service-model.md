---
title: "Invocar programas simultáneos en Oracle E-Business Suite mediante el modelo de servicio WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e227c60f-f6fe-40bf-bf41-2784a4428ad0
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aed2b50eab9612e5a2a610047e41560e1dc24576
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invoke-concurrent-programs-in-oracle-e-business-suite-using-the-wcf-service-model"></a><span data-ttu-id="c10d3-102">Invocar programas simultáneos en Oracle E-Business Suite mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="c10d3-102">Invoke concurrent programs in Oracle E-Business Suite using the WCF service model</span></span>
<span data-ttu-id="c10d3-103">Oracle E-Business Suite expone programas simultáneos que se pueden ejecutar para realizar operaciones específicas en las aplicaciones de Oracle.</span><span class="sxs-lookup"><span data-stu-id="c10d3-103">Oracle E-Business Suite exposes concurrent programs that you can execute to perform specific operations on Oracle applications.</span></span> <span data-ttu-id="c10d3-104">Cada aplicación de Oracle tiene un conjunto de programas simultáneos estándares (que son los mismos en todas las operaciones) y determinados programas simultáneos que son específicos de una aplicación de Oracle.</span><span class="sxs-lookup"><span data-stu-id="c10d3-104">Each Oracle application has a set of standard concurrent programs (that are same across all operations) and certain concurrent programs that are specific to an Oracle application.</span></span> <span data-ttu-id="c10d3-105">La [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone todos los programas simultáneos como las operaciones que los clientes de adaptador pueden invocar.</span><span class="sxs-lookup"><span data-stu-id="c10d3-105">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] exposes all concurrent programs as operations that adapter clients can invoke.</span></span> <span data-ttu-id="c10d3-106">Para obtener más información acerca del modo en que el adaptador admite programas simultáneos, consulte [operaciones en programas simultáneos](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md).</span><span class="sxs-lookup"><span data-stu-id="c10d3-106">For more information about how the adapter supports concurrent programs, see [Operations on Concurrent Programs](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c10d3-107">Para los programas simultáneos que no exponen sus metadatos, el adaptador de Oracle E-Business expone 100 parámetros opcionales para cada uno de estos programas simultáneos.</span><span class="sxs-lookup"><span data-stu-id="c10d3-107">For the concurrent programs that do not expose their metadata, the Oracle E-Business adapter exposes 100 optional parameters for each of these concurrent programs.</span></span> <span data-ttu-id="c10d3-108">Para invocar correctamente estos programas simultáneos, el usuario debe consultar la documentación de Oracle E-Business Suite para averiguar los parámetros de un programa simultáneo que requieren un valor y especifíquelos.</span><span class="sxs-lookup"><span data-stu-id="c10d3-108">To invoke these concurrent programs successfully, the user must consult the Oracle E-Business Suite documentation to figure out the parameters for a concurrent program that require a value, and then specify them.</span></span> <span data-ttu-id="c10d3-109">Un ejemplo de este tipo de programa simultánea es **importación de Journal** (nombre real: **GLLEZL**) en el **contabilidad** aplicación.</span><span class="sxs-lookup"><span data-stu-id="c10d3-109">An example of such a concurrent program is **Journal Import** (actual name: **GLLEZL**) in the **General Ledger** application.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="c10d3-110">Acerca de los ejemplos usados en este tema</span><span class="sxs-lookup"><span data-stu-id="c10d3-110">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="c10d3-111">El ejemplo de este tema, se invoca el **MS_SAMPLE_COPY_EMP_DATA** programa simultáneo, seguido por el **Get_Status** programa simultáneo para conocer el estado del primer programa simultáneo.</span><span class="sxs-lookup"><span data-stu-id="c10d3-111">The example in this topic invokes the **MS_SAMPLE_COPY_EMP_DATA** concurrent program, followed by the **Get_Status** concurrent program to know the status of the first concurrent program.</span></span> <span data-ttu-id="c10d3-112">Estos programas simultáneos se invocan desde el **biblioteca de objetos de aplicación** aplicación.</span><span class="sxs-lookup"><span data-stu-id="c10d3-112">These concurrent programs are invoked from the **Application Object Library** application.</span></span> <span data-ttu-id="c10d3-113">El **MS_SAMPLE_COPY_EMP_DATA** se crea mediante la ejecución de la secuencia de comandos que se proporciona con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="c10d3-113">The **MS_SAMPLE_COPY_EMP_DATA** is created by running the script provided with the samples.</span></span> <span data-ttu-id="c10d3-114">Para obtener más información acerca de los ejemplos, vea [ejemplos para el adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="c10d3-114">For more information about samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="c10d3-115">Obtener un ejemplo, **ConcurrentProgram_ServiceModel**, que se basa en este tema, también se proporciona con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="c10d3-115">A sample, **ConcurrentProgram_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="c10d3-116">La clase de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="c10d3-116">The WCF Client Class</span></span>  
 <span data-ttu-id="c10d3-117">El nombre del cliente WCF que se genera para llamar a los programas simultáneos por el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] aparece en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="c10d3-117">The name of the WCF client generated for invoking the concurrent programs by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="c10d3-118">Artefacto</span><span class="sxs-lookup"><span data-stu-id="c10d3-118">Artifact</span></span>|<span data-ttu-id="c10d3-119">Nombre de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="c10d3-119">WCF Client Name</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="c10d3-120">Programa simultáneo</span><span class="sxs-lookup"><span data-stu-id="c10d3-120">Concurrent Program</span></span>|<span data-ttu-id="c10d3-121">Cliente ConcurrentPrograms_ [APP_NAME]</span><span class="sxs-lookup"><span data-stu-id="c10d3-121">ConcurrentPrograms_[APP_NAME]Client</span></span>|  
  
 <span data-ttu-id="c10d3-122">[APP_NAME] = nombre real de la aplicación de Oracle E-Business Suite; Por ejemplo, buscar.</span><span class="sxs-lookup"><span data-stu-id="c10d3-122">[APP_NAME] = Actual name of the Oracle E-Business Suite application; for example, FND.</span></span>  
  
### <a name="method-signature-for-invoking-concurrent-programs"></a><span data-ttu-id="c10d3-123">Firma de método para invocar programas simultáneos</span><span class="sxs-lookup"><span data-stu-id="c10d3-123">Method Signature for Invoking Concurrent Programs</span></span>  
 <span data-ttu-id="c10d3-124">En la tabla siguiente se muestra la firma del método para los programas simultáneos.</span><span class="sxs-lookup"><span data-stu-id="c10d3-124">The following table shows the method signature for the concurrent programs.</span></span>  
  
|<span data-ttu-id="c10d3-125">Operación</span><span class="sxs-lookup"><span data-stu-id="c10d3-125">Operation</span></span>|<span data-ttu-id="c10d3-126">Firma de método</span><span class="sxs-lookup"><span data-stu-id="c10d3-126">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="c10d3-127">Programa simultáneo</span><span class="sxs-lookup"><span data-stu-id="c10d3-127">Concurrent program</span></span>|<span data-ttu-id="c10d3-128">pública \<tipo de valor devuelto >< Concurrent_program_name > (parámetro 1, el parámetro 2,...)</span><span class="sxs-lookup"><span data-stu-id="c10d3-128">public \<return type> <Concurrent_program_name>(param 1, param 2, …)</span></span>|  
  
 <span data-ttu-id="c10d3-129">Por ejemplo, el código siguiente muestra las firmas de método para generar una clase de cliente WCF para la **MS_SAMPLE_COPY_EMP_DATA** y **Get_Status** programas simultáneos.</span><span class="sxs-lookup"><span data-stu-id="c10d3-129">As an example, the following code shows the method signatures for a WCF client class generated for the **MS_SAMPLE_COPY_EMP_DATA** and **Get_Status** concurrent programs.</span></span>  
  
```  
public partial class ConcurrentPrograms_FNDClient : System.ServiceModel.ClientBase<ConcurrentPrograms_FND>, ConcurrentPrograms_FND {      
  
    public string MS_SAMPLE_COPY_EMP_DATA(schemas.microsoft.com.OracleEBS._2008._05.Options.SetOptions SetOptions,  
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetPrintOptions SetPrintOptions,  
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetRepeatOptions SetRepeatOptions,  
      string Description, string StartTime);  
  
    public bool GetStatusForConcurrentProgram(string RequestId, out string Phase, out string Status,  
      out string DevPhase, out string DevStatus, out string Message);  
}  
```  
  
 <span data-ttu-id="c10d3-130">En este fragmento de código, **ConcurrentPrograms_FNDClient** es el nombre de la clase WCF en el OracleEBSBindingClient.cs generado por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c10d3-130">In this snippet, **ConcurrentPrograms_FNDClient** is the name of the WCF class in the OracleEBSBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="c10d3-131">**MS_SAMPLE_COPY_EMP_DATA** es el nombre del método para invocar el programa simultáneo.</span><span class="sxs-lookup"><span data-stu-id="c10d3-131">**MS_SAMPLE_COPY_EMP_DATA** is the name of the method to invoke the concurrent program.</span></span> <span data-ttu-id="c10d3-132">**GetStatusForConcurrentProgram** es el nombre del método para invocar el programa simultáneo para obtener el estado del primer programa simultáneo.</span><span class="sxs-lookup"><span data-stu-id="c10d3-132">**GetStatusForConcurrentProgram** is the name of the method to invoke the concurrent program to get the status of the first concurrent program.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c10d3-133">**GetStatusForConcurrentProgram** es el nombre real de la **Get_Status** programa simultáneo.</span><span class="sxs-lookup"><span data-stu-id="c10d3-133">**GetStatusForConcurrentProgram** is the actual name of the **Get_Status** concurrent program.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-concurrent-programs"></a><span data-ttu-id="c10d3-134">Creación de un cliente WCF para invocar programas simultáneos</span><span class="sxs-lookup"><span data-stu-id="c10d3-134">Creating a WCF Client to Invoke Concurrent Programs</span></span>  
 <span data-ttu-id="c10d3-135">El conjunto de acciones necesarias para realizar una operación en Oracle E-Business Suite mediante un cliente WCF genérico implica un conjunto de tareas que se describen en [información general sobre el modelo de servicio WCF con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="c10d3-135">The generic set of actions required to perform an operation on Oracle E-Business Suite using a WCF client involves a set of tasks described in [Overview of the WCF service model with the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md).</span></span> <span data-ttu-id="c10d3-136">Esta sección describe cómo crear un cliente WCF para invocar la **MS_SAMPLE_COPY_EMP_DATA** y **Get_Status** programas simultáneos.</span><span class="sxs-lookup"><span data-stu-id="c10d3-136">This section describes how to create a WCF client to invoke the **MS_SAMPLE_COPY_EMP_DATA** and **Get_Status** concurrent programs.</span></span>  
  
#### <a name="to-create-a-wcf-client"></a><span data-ttu-id="c10d3-137">Para crear a un cliente WCF</span><span class="sxs-lookup"><span data-stu-id="c10d3-137">To create a WCF client</span></span>  
  
1.  <span data-ttu-id="c10d3-138">Cree un proyecto de Visual C# en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c10d3-138">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="c10d3-139">De este tema, cree una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="c10d3-139">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="c10d3-140">Generar la clase de cliente WCF para la **MS_SAMPLE_COPY_EMP_DATA** y **Get_Status** programas simultáneos.</span><span class="sxs-lookup"><span data-stu-id="c10d3-140">Generate the WCF client class for the **MS_SAMPLE_COPY_EMP_DATA** and **Get_Status** concurrent programs.</span></span> <span data-ttu-id="c10d3-141">Para obtener más información acerca de cómo generar una clase de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="c10d3-141">For more information about generating a WCF client class, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c10d3-142">Antes de generar la clase de cliente WCF, asegúrese de establecer el **EnableBizTalkCompatibilityMode** enlaza la propiedad en false.</span><span class="sxs-lookup"><span data-stu-id="c10d3-142">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3.  <span data-ttu-id="c10d3-143">En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.OracleEBS` y `Microsoft.ServiceModel.Channels`.</span><span class="sxs-lookup"><span data-stu-id="c10d3-143">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4.  <span data-ttu-id="c10d3-144">Abra el archivo Program.cs y agregue los espacios de nombres siguientes:</span><span class="sxs-lookup"><span data-stu-id="c10d3-144">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `System.ServiceModel`  
  
5.  <span data-ttu-id="c10d3-145">Abra el archivo Program.cs y crear a un cliente, como se describe en el siguiente fragmento.</span><span class="sxs-lookup"><span data-stu-id="c10d3-145">Open the Program.cs file and create a client as described in the snippet below.</span></span>  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
    ConcurrentPrograms_FNDClient client = new ConcurrentPrograms_FNDClient(binding, address);  
    ```  
  
     <span data-ttu-id="c10d3-146">En este fragmento de código, `ConcurrentPrograms_FNDClient` es el cliente WCF definido en OracleEBSBindingClient.cs.</span><span class="sxs-lookup"><span data-stu-id="c10d3-146">In this snippet, `ConcurrentPrograms_FNDClient` is the WCF client defined in OracleEBSBindingClient.cs.</span></span> <span data-ttu-id="c10d3-147">Este archivo es generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c10d3-147">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c10d3-148">En este fragmento, especificar explícitamente la dirección de enlace y el punto de conexión en el código de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c10d3-148">In this snippet, you explicitly specify the binding and endpoint address in your application code.</span></span> <span data-ttu-id="c10d3-149">También puede utilizar estos valores desde el archivo de configuración del aplicación, app.config, también generado el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c10d3-149">You can also use these values from the application configuration file, app.config, also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="c10d3-150">Para obtener más información sobre las distintas formas de especificar el enlace del cliente, consulte [configurar un cliente de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span><span class="sxs-lookup"><span data-stu-id="c10d3-150">For more information on the different ways of specifying client binding, see [Configure a client binding for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span></span>  
  
6.  <span data-ttu-id="c10d3-151">Establezca las credenciales para el cliente.</span><span class="sxs-lookup"><span data-stu-id="c10d3-151">Set the credentials for the client.</span></span>  
  
    ```  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
7.  <span data-ttu-id="c10d3-152">Dado que va a invocar programas simultáneos en una aplicación de Oracle E-Business Suite, debe establecer el contexto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c10d3-152">Because you are invoking concurrent programs in an Oracle E-Business Suite application, you must set the application context.</span></span> <span data-ttu-id="c10d3-153">En este ejemplo, para establecer el contexto de la aplicación, especifique la **OracleUserName**, **OraclePassword**, y **OracleEBSResponsibilityName** propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="c10d3-153">In this example, to set the application context, you specify the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="c10d3-154">Para obtener más información sobre el contexto de la aplicación, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span><span class="sxs-lookup"><span data-stu-id="c10d3-154">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
    ```  
    binding.OracleUserName = "myOracleEBSUserName";  
    binding.OraclePassword = "myOracleEBSPassword";  
    binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
    ```  
  
8.  <span data-ttu-id="c10d3-155">Abra al cliente como se describe en el siguiente fragmento:</span><span class="sxs-lookup"><span data-stu-id="c10d3-155">Open the client as described in the snippet below:</span></span>  
  
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
  
9. <span data-ttu-id="c10d3-156">Invocar la **MS_SAMPLE_COPY_EMP_DATA** y **Get_Status** programas simultáneos.</span><span class="sxs-lookup"><span data-stu-id="c10d3-156">Invoke the **MS_SAMPLE_COPY_EMP_DATA** and **Get_Status** concurrent programs.</span></span>  
  
    ```  
    string RequestID;  
    bool Result;  
    string Phase;  
    string Status;  
    string DevPhase;  
    string DevStatus;  
    string Message;  
  
    try  
    {  
        Console.WriteLine("Invoking the MS_SAMPLE_COPY_EMP_DATA concurrent program");  
        RequestID = client.MS_SAMPLE_COPY_EMP_DATA(null, null, null, null, null);  
        Console.WriteLine("The request ID generated for the concurrent program is : " + RequestID);  
        Console.WriteLine("********************************************************");  
        Console.WriteLine("\nWaiting for 60 seconds for the concurrent program to be complete");  
        System.Threading.Thread.Sleep(60000);  
        Console.WriteLine("\nInvoking the Get_Status concurrent program");  
        Result = client.GetStatusForConcurrentProgram(RequestID, out Phase, out Status, out DevPhase, out DevStatus, out Message);  
        Console.WriteLine("\nResult is  : " + Result);  
        Console.WriteLine("Phase is     : " + Phase);  
        Console.WriteLine("Status is    : " + Status);  
        Console.WriteLine("DevPhase is  : " + DevPhase);  
        Console.WriteLine("DevStatus is : " + DevStatus);  
        Console.WriteLine("Message is   : " + Message);  
        Console.WriteLine("********************************************************");  
        Console.WriteLine("\nHit <RETURN> to end");  
        Console.ReadLine();  
    }  
    catch (Exception ex)  
    {  
        Console.WriteLine("Exception : " + ex);  
        throw;                 
    }  
    ```  
  
10. <span data-ttu-id="c10d3-157">Cierre al cliente como se describe en el siguiente fragmento:</span><span class="sxs-lookup"><span data-stu-id="c10d3-157">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    ```  
  
11. <span data-ttu-id="c10d3-158">Compile el proyecto y, a continuación, ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="c10d3-158">Build the project and then run it.</span></span> <span data-ttu-id="c10d3-159">La aplicación invoca el **MS_SAMPLE_COPY_EMP_DATA** y devuelve un identificador de solicitud.</span><span class="sxs-lookup"><span data-stu-id="c10d3-159">The application invokes the **MS_SAMPLE_COPY_EMP_DATA** and returns a request ID.</span></span> <span data-ttu-id="c10d3-160">El identificador se pasa a continuación el **Get_Status** programa simultánea, lo que finalmente proporciona el estado de la **MS_SAMPLE_COPY_EMP_DATA** programa de columna.</span><span class="sxs-lookup"><span data-stu-id="c10d3-160">The ID is then passed to the **Get_Status** concurrent program, which finally provides the status of the **MS_SAMPLE_COPY_EMP_DATA** column program.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c10d3-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="c10d3-161">See Also</span></span>  
 [<span data-ttu-id="c10d3-162">Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="c10d3-162">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)