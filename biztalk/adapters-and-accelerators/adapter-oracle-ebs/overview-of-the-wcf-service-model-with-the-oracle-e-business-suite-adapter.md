---
title: "Información general sobre el modelo de servicio WCF con el adaptador de Oracle E-Business Suite | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aeeac8a4-a4bc-4963-951c-0c806e232f1e
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f40b22865ca45cbd10823f6c514f75e5965f1df5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="ec370-102">Información general sobre el modelo de servicio WCF con el adaptador de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="ec370-102">Overview of the WCF service model with the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="ec370-103">La [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] expone un sistema de Oracle E-Business Suite como un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="ec370-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] exposes an Oracle E-Business Suite system as a WCF service.</span></span> <span data-ttu-id="ec370-104">Para llevar a cabo operaciones en artefactos de Oracle E-Business Suite, por ejemplo, para invocar un procedimiento almacenado, se invoca una operación en el adaptador, que a su vez, realiza la operación en Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="ec370-104">To perform operations on Oracle E-Business Suite artifacts, for example to invoke a stored procedure, you invoke an operation on the adapter, which, in turn, performs the operation on the Oracle E-Business Suite.</span></span> <span data-ttu-id="ec370-105">El código actúa como un cliente para el servicio WCF presentado por el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ec370-105">Your code acts as a client to the WCF service presented by the adapter.</span></span>  
  
 <span data-ttu-id="ec370-106">En el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo de servicio, el contrato de servicio que existe entre un cliente y un servicio se representa como una interfaz de .NET y las operaciones se representan como métodos en esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="ec370-106">In the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] service model, the service contract that exists between a client and a service is represented as a .NET interface, and operations are represented as methods on this interface.</span></span> <span data-ttu-id="ec370-107">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] y WCF ofrecen herramientas que permiten generar esta interfaz para las operaciones de destino de los metadatos que expone el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ec370-107">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] and WCF provide tools that enable you to generate this interface for targeted operations from the metadata that the adapter exposes.</span></span> <span data-ttu-id="ec370-108">Estas herramientas también crean una clase de cliente WCF que puede usarse para invocar las operaciones que se exponen en la interfaz de servicio.</span><span class="sxs-lookup"><span data-stu-id="ec370-108">These tools also create a WCF client class that can be used to invoke the operations exposed in the service interface.</span></span> <span data-ttu-id="ec370-109">Una aplicación cliente puede llamar a los métodos de la clase de cliente WCF para invocar operaciones en el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ec370-109">A client application can call the methods of the WCF client class to invoke operations on the adapter.</span></span>  
  
 <span data-ttu-id="ec370-110">En la siguiente sección se explica cómo utilizar el modelo de servicio WCF para invocar las operaciones con un cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="ec370-110">The following section explains how to use the WCF service model to invoke operations with a WCF client.</span></span>  
  
## <a name="invoking-operations-on-the-oracle-e-business-suite-with-a-wcf-client"></a><span data-ttu-id="ec370-111">Invocar operaciones en Oracle E-Business Suite con un cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="ec370-111">Invoking Operations on the Oracle E-Business Suite with a WCF Client</span></span>  
 <span data-ttu-id="ec370-112">Para usar el modelo de servicio WCF para invocar operaciones en el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], debe generar primero una clase de cliente WCF para las operaciones de destino.</span><span class="sxs-lookup"><span data-stu-id="ec370-112">To use the WCF service model to invoke operations on the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], you must first generate a WCF client class for the target operations.</span></span> <span data-ttu-id="ec370-113">A continuación, puede crear una instancia de esta clase, un cliente de WCF y llamar a sus métodos para realizar estas operaciones en Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="ec370-113">You can then create an instance of this class, a WCF client, and call its methods to perform these operations on the Oracle E-Business Suite.</span></span>  
  
#### <a name="to-invoke-operations-on-the-oracle-e-business-adapter"></a><span data-ttu-id="ec370-114">Para invocar operaciones en el adaptador de Oracle E-Business</span><span class="sxs-lookup"><span data-stu-id="ec370-114">To invoke operations on the Oracle E-Business adapter</span></span>  
  
1.  <span data-ttu-id="ec370-115">Generar un código de clase y la aplicación auxiliar de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="ec370-115">Generate a WCF client class and helper code.</span></span> <span data-ttu-id="ec370-116">Use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o los metadatos herramienta de utilidad ServiceModel (svcutil.exe) para generar una clase de cliente WCF destinada a artefactos de Oracle E-Business Suite con la que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="ec370-116">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF client class targeted at Oracle E-Business Suite artifacts with which you want to work.</span></span> <span data-ttu-id="ec370-117">Para obtener más información sobre cómo generar un cliente de WCF, vea [generar un cliente de WCF o un contrato de servicio de WCF para Oracle E-Business artefactos de la solución](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="ec370-117">For more information about how to generate a WCF client, see [Generate a WCF Client or a WCF Service Contract for Oracle E-Business Solution Artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
2.  <span data-ttu-id="ec370-118">Cree una instancia de cliente WCF y configurar al cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="ec370-118">Create a WCF client instance and configure the WCF client.</span></span> <span data-ttu-id="ec370-119">Configurar al cliente de WCF implica especificar el enlace y dirección de punto de conexión (conexión URI) que el cliente va a usar.</span><span class="sxs-lookup"><span data-stu-id="ec370-119">Configuring the WCF client involves specifying the binding and endpoint address (connection URI) that the client will use.</span></span> <span data-ttu-id="ec370-120">Puede hacerlo imperativamente en código o mediante declaración en configuración.</span><span class="sxs-lookup"><span data-stu-id="ec370-120">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="ec370-121">El código siguiente crea un cliente WCF que tiene como destino el **interfaz cliente** programa simultáneo en la **cuentas por cobrar** aplicación en Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="ec370-121">The following code creates a WCF client that targets the **Customer Interface** concurrent program in the **Receivables** application in the Oracle E-Business Suite.</span></span> <span data-ttu-id="ec370-122">También establece las credenciales para Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="ec370-122">It also sets the credentials for the Oracle E-Business Suite.</span></span> <span data-ttu-id="ec370-123">El cliente de WCF se inicializa desde la configuración.</span><span class="sxs-lookup"><span data-stu-id="ec370-123">The WCF client is initialized from configuration.</span></span>  
  
    ```  
    ConcurrentPrograms_ARClient client = new ConcurrentPrograms_ARClient("OracleEBSBinding_ConcurrentPrograms_AR"); //picking the binding and address from app.config  
  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="ec370-124">Puede especificar la dirección de enlace y el punto de conexión de cliente en el código o declarar en el archivo de configuración app.config.</span><span class="sxs-lookup"><span data-stu-id="ec370-124">You can either specify the client binding and endpoint address in the code or declare it in the app.config configuration file.</span></span> <span data-ttu-id="ec370-125">El fragmento de código anterior usa el último.</span><span class="sxs-lookup"><span data-stu-id="ec370-125">The preceding code snippet uses the latter.</span></span> <span data-ttu-id="ec370-126">Para obtener más información sobre cómo usar ambos métodos, consulte [configurar un enlace de cliente de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span><span class="sxs-lookup"><span data-stu-id="ec370-126">For more information on how to use either approaches, see [Configure a Client Binding for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span></span>  
  
3.  <span data-ttu-id="ec370-127">Abra al cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="ec370-127">Open the WCF client.</span></span>  
  
    ```  
    client.Open();  
    ```  
  
4.  <span data-ttu-id="ec370-128">Invocar métodos en el cliente WCF que creó en el paso 2 para realizar operaciones en Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="ec370-128">Invoke methods on the WCF client created in step 2 to perform operations on the Oracle E-Business Suite.</span></span> <span data-ttu-id="ec370-129">El código siguiente, se invoca el **interfaz cliente** programa simultáneo en la **cuentas por cobrar** aplicación en Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="ec370-129">The following code invokes the **Customer Interface** concurrent program in the **Receivables** application in the Oracle E-Business Suite.</span></span>  
  
    ```  
    string Result = client.RACUST(null, null, null, description, null, recipro_cust, org_id);  
    ```  
  
     <span data-ttu-id="ec370-130">**RACUST** es el nombre del programa interfaz de cliente simultáneo.</span><span class="sxs-lookup"><span data-stu-id="ec370-130">**RACUST** is the actual name of the Customer Interface concurrent program.</span></span> <span data-ttu-id="ec370-131">**Interfaz de cliente** es el nombre descriptivo del programa simultáneo.</span><span class="sxs-lookup"><span data-stu-id="ec370-131">**Customer Interface** is the friendly name of the concurrent program.</span></span>  
  
5.  <span data-ttu-id="ec370-132">Cierre al cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="ec370-132">Close the WCF client.</span></span>  
  
    ```  
    client.Close();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ec370-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec370-133">See Also</span></span>  
 [<span data-ttu-id="ec370-134">Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="ec370-134">Develop Oracle E-Business Suite Applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)