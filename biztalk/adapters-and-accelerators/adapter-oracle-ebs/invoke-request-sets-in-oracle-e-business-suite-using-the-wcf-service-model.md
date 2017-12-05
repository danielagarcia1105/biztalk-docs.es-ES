---
title: Invocar conjuntos de solicitudes en Oracle E-Business Suite mediante el modelo de servicio WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb6ec551-c069-4133-add5-2ba83d20405d
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec243c1d1ed1093241e4dc6120c3703fbf2e4542
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="invoke-request-sets-in-oracle-e-business-suite-using-the-wcf-service-model"></a><span data-ttu-id="59b01-102">Invocar conjuntos de solicitudes en Oracle E-Business Suite mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="59b01-102">Invoke request sets in Oracle E-Business Suite using the WCF service model</span></span>
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]<span data-ttu-id="59b01-103">permite ejecutar conjuntos de solicitudes en Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="59b01-103"> enables you to execute request sets in Oracle E-Business Suite.</span></span> <span data-ttu-id="59b01-104">Solicitar conjuntos se dividen en una o varias fases y cada fase contiene un conjunto de informes y programas simultáneos.</span><span class="sxs-lookup"><span data-stu-id="59b01-104">Request sets are divided into one or more stages, and each stage contains a set of reports and concurrent programs.</span></span> <span data-ttu-id="59b01-105">Para obtener más información acerca del modo en que el adaptador admite los conjuntos de solicitudes, consulte [operaciones en la solicitud establece](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md).</span><span class="sxs-lookup"><span data-stu-id="59b01-105">For more information about how the adapter supports request sets, see [Operations on Request Sets](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="59b01-106">La clase de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="59b01-106">The WCF Client Class</span></span>  
 <span data-ttu-id="59b01-107">El nombre del cliente WCF generado para invocar la solicitud, se establece el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] aparece en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="59b01-107">The name of the WCF client generated for invoking the request sets by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="59b01-108">Artefacto</span><span class="sxs-lookup"><span data-stu-id="59b01-108">Artifact</span></span>|<span data-ttu-id="59b01-109">Nombre de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="59b01-109">WCF Client Name</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="59b01-110">Conjunto de solicitud</span><span class="sxs-lookup"><span data-stu-id="59b01-110">Request Set</span></span>|<span data-ttu-id="59b01-111">Cliente RequestSets_ [APP_NAME]</span><span class="sxs-lookup"><span data-stu-id="59b01-111">RequestSets_[APP_NAME]Client</span></span>|  
  
 <span data-ttu-id="59b01-112">[APP_NAME] = nombre real de la aplicación de Oracle E-Business Suite; Por ejemplo, SQLAP.</span><span class="sxs-lookup"><span data-stu-id="59b01-112">[APP_NAME] = Actual name of the Oracle E-Business Suite application; for example, SQLAP.</span></span>  
  
### <a name="method-signature-for-invoking-request-sets"></a><span data-ttu-id="59b01-113">Firma de método para invocar conjuntos de solicitudes</span><span class="sxs-lookup"><span data-stu-id="59b01-113">Method Signature for Invoking Request Sets</span></span>  
 <span data-ttu-id="59b01-114">En la tabla siguiente se muestra la firma del método de conjuntos de solicitudes.</span><span class="sxs-lookup"><span data-stu-id="59b01-114">The following table shows the method signature for request sets.</span></span>  
  
|<span data-ttu-id="59b01-115">Operación</span><span class="sxs-lookup"><span data-stu-id="59b01-115">Operation</span></span>|<span data-ttu-id="59b01-116">Firma de método</span><span class="sxs-lookup"><span data-stu-id="59b01-116">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="59b01-117">Conjunto de solicitud</span><span class="sxs-lookup"><span data-stu-id="59b01-117">Request Set</span></span>|<span data-ttu-id="59b01-118">pública \<tipo de valor devuelto\> \<nombre del conjunto de solicitud\>(parámetro 1, el parámetro 2,...)</span><span class="sxs-lookup"><span data-stu-id="59b01-118">public \<return type\> \<request set name\>(param 1, param 2, …)</span></span>|  
  
 <span data-ttu-id="59b01-119">Por ejemplo, el código siguiente muestra las firmas de método para generar una clase de cliente WCF para la **reqset_singlestage** solicitar conjunto.</span><span class="sxs-lookup"><span data-stu-id="59b01-119">As an example, the following code shows the method signatures for a WCF client class generated for the **reqset_singlestage** request set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59b01-120">Esto es un conjunto de solicitudes personalizado y podría no estar disponible en la instancia de Oracle E-Business solución.</span><span class="sxs-lookup"><span data-stu-id="59b01-120">This is a custom request set and might not be available on your Oracle E-Business Solution instance.</span></span>  
  
```  
public partial class RequestSets_SQLAPClient : System.ServiceModel.ClientBase<RequestSets_SQLAP>, RequestSets_SQLAP{      
  
    public string REQSTG(  
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetRelClassOptions SetRelClassOptions,  
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetPrintOptions SetPrintOptions,   
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetRepeatOptions SetRepeatOptions,   
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetNlsOptions SetNlsOptions,  
      string StartTime,  
      schemas.microsoft.com.OracleEBS._2008._05.RequestSetStage.SQLAP.REQSTG.set1 set1_set1);  
}  
```  
  
 <span data-ttu-id="59b01-121">En este fragmento de código, **RequestSets_SQLAPClient** es el nombre de la clase WCF en el OracleEBSBindingClient.cs generado por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59b01-121">In this snippet, **RequestSets_SQLAPClient** is the name of the WCF class in the OracleEBSBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="59b01-122">**REQSTG** es el nombre del método para invocar el conjunto de solicitud.</span><span class="sxs-lookup"><span data-stu-id="59b01-122">**REQSTG** is the name of the method to invoke the request set.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-request-sets"></a><span data-ttu-id="59b01-123">Creación de un cliente WCF para invocar conjuntos de solicitudes</span><span class="sxs-lookup"><span data-stu-id="59b01-123">Creating a WCF Client to Invoke Request Sets</span></span>  
 <span data-ttu-id="59b01-124">El conjunto de acciones necesarias para realizar una operación en Oracle E-Business Suite mediante un cliente WCF genérico implica un conjunto de tareas que se describen en [información general sobre el modelo de servicio WCF con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="59b01-124">The generic set of actions required to perform an operation on Oracle E-Business Suite using a WCF client involves a set of tasks described in [Overview of the WCF service model with the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md).</span></span> <span data-ttu-id="59b01-125">Esta sección describe cómo crear un cliente WCF para invocar la **reqset_singlestage** solicitar conjunto.</span><span class="sxs-lookup"><span data-stu-id="59b01-125">This section describes how to create a WCF client to invoke the **reqset_singlestage** request set.</span></span>  
  
#### <a name="to-create-a-wcf-client"></a><span data-ttu-id="59b01-126">Para crear a un cliente WCF</span><span class="sxs-lookup"><span data-stu-id="59b01-126">To create a WCF client</span></span>  
  
1.  <span data-ttu-id="59b01-127">Cree un proyecto de Visual C# en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="59b01-127">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="59b01-128">De este tema, cree una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="59b01-128">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="59b01-129">Generar la clase de cliente WCF para la **reqset_singlestage** solicitar conjunto.</span><span class="sxs-lookup"><span data-stu-id="59b01-129">Generate the WCF client class for the **reqset_singlestage** request set.</span></span> <span data-ttu-id="59b01-130">Para obtener más información acerca de cómo generar una clase de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="59b01-130">For more information about generating a WCF client class, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="59b01-131">Antes de generar la clase de cliente WCF, asegúrese de establecer el **EnableBizTalkCompatibilityMode** enlaza la propiedad en false.</span><span class="sxs-lookup"><span data-stu-id="59b01-131">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3.  <span data-ttu-id="59b01-132">En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.OracleEBS` y `Microsoft.ServiceModel.Channels`.</span><span class="sxs-lookup"><span data-stu-id="59b01-132">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4.  <span data-ttu-id="59b01-133">Abra el archivo Program.cs y agregue los espacios de nombres siguientes:</span><span class="sxs-lookup"><span data-stu-id="59b01-133">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `System.ServiceModel`  
  
5.  <span data-ttu-id="59b01-134">Abra el archivo Program.cs y crear a un cliente, como se describe en el siguiente fragmento.</span><span class="sxs-lookup"><span data-stu-id="59b01-134">Open the Program.cs file and create a client as described in the snippet below.</span></span>  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
    RequestSets_SQLAPClient client = new RequestSets_SQLAPClient(binding, address);  
    ```  
  
     <span data-ttu-id="59b01-135">En este fragmento de código, `RequestSets_SQLAPClient` es el cliente WCF definido en OracleEBSBindingClient.cs.</span><span class="sxs-lookup"><span data-stu-id="59b01-135">In this snippet, `RequestSets_SQLAPClient` is the WCF client defined in OracleEBSBindingClient.cs.</span></span> <span data-ttu-id="59b01-136">Este archivo es generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59b01-136">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="59b01-137">En este fragmento, especificar explícitamente la dirección de enlace y el punto de conexión en el código de aplicación.</span><span class="sxs-lookup"><span data-stu-id="59b01-137">In this snippet, you explicitly specify the binding and endpoint address in your application code.</span></span> <span data-ttu-id="59b01-138">También puede utilizar estos valores desde el archivo de configuración del aplicación, app.config, también generado el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59b01-138">You can also use these values from the application configuration file, app.config, also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="59b01-139">Para obtener más información sobre las distintas maneras de especificar el enlace del cliente, consulte [configurar un cliente de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span><span class="sxs-lookup"><span data-stu-id="59b01-139">For more information about the different ways of specifying client binding, see [Configure a client binding for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span></span>  
  
6.  <span data-ttu-id="59b01-140">Establezca las credenciales para el cliente.</span><span class="sxs-lookup"><span data-stu-id="59b01-140">Set the credentials for the client.</span></span>  
  
    ```  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
7.  <span data-ttu-id="59b01-141">Dado que se están invocando conjuntos de solicitud en una aplicación de Oracle E-Business Suite, debe establecer el contexto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="59b01-141">Because you are invoking request sets in an Oracle E-Business Suite application, you must set the application context.</span></span> <span data-ttu-id="59b01-142">En este ejemplo, para establecer el contexto de la aplicación, especifique la **OracleUserName**, **OraclePassword**, y **OracleEBSResponsibilityName** propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="59b01-142">In this example, to set the application context, you specify the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="59b01-143">Para obtener más información sobre el contexto de la aplicación, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span><span class="sxs-lookup"><span data-stu-id="59b01-143">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
    ```  
    binding.OracleUserName = "myOracleEBSUserName";  
    binding.OraclePassword = "myOracleEBSPassword";  
    binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
    ```  
  
8.  <span data-ttu-id="59b01-144">Abra al cliente como se describe en el siguiente fragmento:</span><span class="sxs-lookup"><span data-stu-id="59b01-144">Open the client as described in the snippet below:</span></span>  
  
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
  
9. <span data-ttu-id="59b01-145">Invocar la **reqset_singlestage** solicitar conjunto.</span><span class="sxs-lookup"><span data-stu-id="59b01-145">Invoke the **reqset_singlestage** request set.</span></span>  
  
    ```  
    string RequestID;  
  
    schemas.microsoft.com.OracleEBS._2008._05.RequestSetStage.SQLAP.REQSTG.set1 param =  
        new schemas.microsoft.com.OracleEBS._2008._05.RequestSetStage.SQLAP.REQSTG.set1();  
  
    param.INSPARAMPROG = new schemas.microsoft.com.OracleEBS._2008._05.RequestSetConcurrentProgram.SQLAP.REQSTG.set1.SQLAP1.INSPARAMPROG();  
    param.INSPARAMPROG.p_id = "123";  
    param.INSPARAMPROG.p_name = "MyName";  
  
    try  
    {  
        Console.WriteLine("Invoking the reqset_singlestage request set");  
        RequestID = client.REQSTG(null, null, null, null, null, param);  
        Console.WriteLine("The request ID generated for the request set is : " + RequestID);  
        Console.WriteLine("*****************************************************************");  
        Console.WriteLine("\nHit <RETURN> to end");  
        Console.ReadLine();  
    }  
    catch (Exception ex)  
    {  
        Console.WriteLine("Exception : " + ex);  
        throw;  
    }  
    ```  
  
10. <span data-ttu-id="59b01-146">Cierre al cliente como se describe en el siguiente fragmento:</span><span class="sxs-lookup"><span data-stu-id="59b01-146">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    ```  
  
11. <span data-ttu-id="59b01-147">Compile el proyecto y, a continuación, ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="59b01-147">Build the project and then run it.</span></span> <span data-ttu-id="59b01-148">La aplicación invoca el **reqset_singlestage** solicitud conjunto y devuelve un identificador de solicitud, que se escribe en la consola.</span><span class="sxs-lookup"><span data-stu-id="59b01-148">The application invokes the **reqset_singlestage** request set and returns a request ID, which is written to the console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59b01-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="59b01-149">See Also</span></span>  
 [<span data-ttu-id="59b01-150">Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="59b01-150">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)