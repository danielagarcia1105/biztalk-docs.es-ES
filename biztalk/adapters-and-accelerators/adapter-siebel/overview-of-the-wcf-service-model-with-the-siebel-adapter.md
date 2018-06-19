---
title: Información general sobre el modelo de servicio WCF con el adaptador de Siebel | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, invoke operations on the Siebel system with a WCF client
- WCF service model, overview of
ms.assetid: 0e812473-0f50-4972-8b07-ec8edc2ef000
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c638255b103a9c588f22d6ddcb2a75b81619b73
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222116"
---
# <a name="overview-of-the-wcf-service-model-with-the-siebel-adapter"></a><span data-ttu-id="3ec1b-102">Información general sobre el modelo de servicio WCF con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="3ec1b-102">Overview of the WCF service model with the Siebel adapter</span></span>
<span data-ttu-id="3ec1b-103">La [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] expone un sistema Siebel como un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="3ec1b-103">The [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] exposes a Siebel system as a WCF service.</span></span> <span data-ttu-id="3ec1b-104">Para llevar a cabo operaciones en los artefactos del sistema Siebel, por ejemplo, para invocar un método de un servicio de negocios de Siebel, se invoca una operación en el adaptador, que a su vez, realiza la operación en el sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="3ec1b-104">To perform operations on Siebel system artifacts, for example to invoke a method of a Siebel business service, you invoke an operation on the adapter, which, in turn, performs the operation on the Siebel system.</span></span> <span data-ttu-id="3ec1b-105">Por lo tanto, el código actúa como un cliente al servicio de WCF presentado por el adaptador.</span><span class="sxs-lookup"><span data-stu-id="3ec1b-105">Your code therefore acts as a client to the WCF service presented by the adapter.</span></span>  
  
 <span data-ttu-id="3ec1b-106">En el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo de servicio, el contrato de servicio que existe entre un cliente y un servicio se representa como una interfaz de .NET y las operaciones se representan como métodos en esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="3ec1b-106">In the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] service model, the service contract that exists between a client and a service is represented as a .NET interface, and operations are represented as methods on this interface.</span></span> <span data-ttu-id="3ec1b-107">El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] y WCF ofrecen herramientas que permiten generar esta interfaz para las operaciones de destino de los metadatos que expone el adaptador.</span><span class="sxs-lookup"><span data-stu-id="3ec1b-107">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] and WCF provide tools that enable you to generate this interface for targeted operations from the metadata that the adapter exposes.</span></span> <span data-ttu-id="3ec1b-108">Estas herramientas también crean una clase de cliente WCF que puede usarse para invocar las operaciones que se exponen en la interfaz de servicio.</span><span class="sxs-lookup"><span data-stu-id="3ec1b-108">These tools also create a WCF client class that can be used to invoke the operations exposed in the service interface.</span></span> <span data-ttu-id="3ec1b-109">Una aplicación cliente puede llamar a los métodos de la clase de cliente WCF para invocar operaciones en el adaptador.</span><span class="sxs-lookup"><span data-stu-id="3ec1b-109">A client application can call the methods of the WCF client class to invoke operations on the adapter.</span></span>  
  
 <span data-ttu-id="3ec1b-110">En la siguiente sección se explica cómo utilizar el modelo de servicio WCF para invocar las operaciones con un cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="3ec1b-110">The following section explains how to use the WCF service model to invoke operations with a WCF client.</span></span>  
  
## <a name="invoking-operations-on-the-siebel-system-with-a-wcf-client"></a><span data-ttu-id="3ec1b-111">Invocar operaciones en el sistema Siebel con un cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="3ec1b-111">Invoking Operations on the Siebel System with a WCF Client</span></span>  
 <span data-ttu-id="3ec1b-112">Para usar el modelo de servicio WCF para invocar operaciones en el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], debe generar primero una clase de cliente WCF para las operaciones de destino.</span><span class="sxs-lookup"><span data-stu-id="3ec1b-112">To use the WCF service model to invoke operations on the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], you must first generate a WCF client class for the target operations.</span></span> <span data-ttu-id="3ec1b-113">A continuación, puede crear una instancia de esta clase, un cliente de WCF y llamar a sus métodos para realizar estas operaciones en el sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="3ec1b-113">You can then create an instance of this class, a WCF client, and call its methods to perform these operations on the Siebel system.</span></span>  
  
#### <a name="to-invoke-operations-on-the-siebel-adapter"></a><span data-ttu-id="3ec1b-114">Para invocar operaciones en el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="3ec1b-114">To invoke operations on the Siebel adapter</span></span>  
  
1.  <span data-ttu-id="3ec1b-115">Generar un código de clase y la aplicación auxiliar de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="3ec1b-115">Generate a WCF client class and helper code.</span></span> <span data-ttu-id="3ec1b-116">Use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o los metadatos herramienta de utilidad ServiceModel (svcutil.exe) para generar una clase de cliente WCF destinada a los artefactos del sistema Siebel con el que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="3ec1b-116">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF client class targeted at the Siebel system artifacts with which you want to work.</span></span> <span data-ttu-id="3ec1b-117">Para obtener más información sobre cómo generar un cliente de WCF, vea [generar un cliente de WCF o un contrato de servicio WCF para los artefactos de la solución de Siebel](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="3ec1b-117">For more information about how to generate a WCF client, see [Generate a WCF Client or a WCF service contract for Siebel Solution Artifacts](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md).</span></span>  
  
2.  <span data-ttu-id="3ec1b-118">Cree una instancia de cliente WCF y configurar al cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="3ec1b-118">Create a WCF client instance and configure the WCF client.</span></span> <span data-ttu-id="3ec1b-119">Configurar al cliente de WCF implica especificar el enlace y dirección de punto de conexión (conexión URI) que el cliente va a usar.</span><span class="sxs-lookup"><span data-stu-id="3ec1b-119">Configuring the WCF client involves specifying the binding and endpoint address (connection URI) that the client will use.</span></span> <span data-ttu-id="3ec1b-120">Puede hacerlo imperativamente en código o mediante declaración en configuración.</span><span class="sxs-lookup"><span data-stu-id="3ec1b-120">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="3ec1b-121">Para obtener más información sobre cómo configurar el cliente de WCF, vea [configurar un cliente de WCF para un sistema Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md).</span><span class="sxs-lookup"><span data-stu-id="3ec1b-121">For more information about how to configure the WCF client, see [Configure a WCF Client for a Siebel System](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md).</span></span> <span data-ttu-id="3ec1b-122">El código siguiente crea a un cliente WCF que tiene como destino el servicio de negocios de Siebel TimeStamp.</span><span class="sxs-lookup"><span data-stu-id="3ec1b-122">The following code creates a WCF client that targets the Siebel TimeStamp business service.</span></span> <span data-ttu-id="3ec1b-123">También establece las credenciales para el sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="3ec1b-123">It also sets the credentials for the Siebel system.</span></span> <span data-ttu-id="3ec1b-124">El cliente de WCF se inicializa desde la configuración.</span><span class="sxs-lookup"><span data-stu-id="3ec1b-124">The WCF client is initialized from configuration.</span></span>  
  
    ```  
    BusinessServices_TimeStamp_OperationClient client =  
        new BusinessServices_TimeStamp_OperationClient("SiebelBinding_BusinessServices_TimeStamp_Operation");  
  
    client.ClientCredentials.UserName.UserName = "YourUserName";  
    client.ClientCredentials.UserName.Password = "YourPassword";  
    ```  
  
3.  <span data-ttu-id="3ec1b-125">Abra al cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="3ec1b-125">Open the WCF client.</span></span>  
  
    ```  
    client.Open();  
    ```  
  
4.  <span data-ttu-id="3ec1b-126">Invocar métodos en el cliente WCF que creó en el paso 2 para realizar operaciones en el sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="3ec1b-126">Invoke methods on the WCF client created in step 2 to perform operations on the Siebel system.</span></span> <span data-ttu-id="3ec1b-127">El código siguiente, se invoca el **Execute** método del cliente WCF para invocar la **Execute** método del servicio de negocio de marca de tiempo en el sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="3ec1b-127">The following code invokes the **Execute** method of the WCF client to invoke the **Execute** method of the TimeStamp business service on the Siebel system.</span></span>  
  
    ```  
    // Create a parameter to hold the results and then invoke the Execute method of the TimeStamp business service.  
    microsoft.lobservices.siebel._2007._03.BusinessServices.TimeStamp.ExecuteResponseRecord er;  
    er = client.Execute();  
    ```  
  
5.  <span data-ttu-id="3ec1b-128">Cierre al cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="3ec1b-128">Close the WCF client.</span></span>  
  
    ```  
    client.Close();  
    ```  
  
 <span data-ttu-id="3ec1b-129">Para obtener más información sobre cómo invocar métodos de servicio de negocio de Siebel, consulte [invocar métodos de servicio empresarial con el adaptador de Siebel mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-siebel/run-business-service-methods-with-the-siebel-adapter-using-a-wcf-service.md)</span><span class="sxs-lookup"><span data-stu-id="3ec1b-129">For more information about invoking Siebel business service methods, see [Invoke Business Service Methods with the Siebel adapter using the WCF Service Model](../../adapters-and-accelerators/adapter-siebel/run-business-service-methods-with-the-siebel-adapter-using-a-wcf-service.md)</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3ec1b-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ec1b-130">See Also</span></span>  
 [<span data-ttu-id="3ec1b-131">Desarrollar aplicaciones de Siebel mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="3ec1b-131">Develop Siebel Applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)