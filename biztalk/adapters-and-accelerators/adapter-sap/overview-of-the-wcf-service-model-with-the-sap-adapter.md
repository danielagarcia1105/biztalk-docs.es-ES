---
title: Información general sobre el modelo de servicio WCF con el adaptador SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, overview of using
ms.assetid: 02a4b43e-ade0-4dba-b8f6-074bca7cbe5c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da5b2f7cc8e38eb8afd211a2008c0f740760cd4f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="overview-of-the-wcf-service-model-with-the-sap-adapter"></a><span data-ttu-id="ca100-102">Información general sobre el modelo de servicio WCF con el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="ca100-102">Overview of the WCF service model with the SAP adapter</span></span>
<span data-ttu-id="ca100-103">Cuando se usan operaciones que el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] superficies, el código actúa como un cliente o un servicio para el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ca100-103">When you consume operations that the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] surfaces, your code acts either as a client or a service to the adapter.</span></span>  
  
 <span data-ttu-id="ca100-104">El código actúa como un cliente para invocar los siguientes tipos de operaciones en el sistema SAP:</span><span class="sxs-lookup"><span data-stu-id="ca100-104">Your code acts as a client to invoke the following kinds of operations on the SAP system:</span></span>  
  
-   <span data-ttu-id="ca100-105">La llamada a una función remota (RFC).</span><span class="sxs-lookup"><span data-stu-id="ca100-105">Invoke a Remote Function Call (RFC).</span></span>  
  
-   <span data-ttu-id="ca100-106">Invocar un Transactional Remote Function Call (tRFC).</span><span class="sxs-lookup"><span data-stu-id="ca100-106">Invoke a Transactional Remote Function Call (tRFC).</span></span>  
  
-   <span data-ttu-id="ca100-107">Invocar una interfaz (BAPI) de programación de aplicaciones de negocios.</span><span class="sxs-lookup"><span data-stu-id="ca100-107">Invoke a Business Application Programming Interface (BAPI).</span></span>  
  
-   <span data-ttu-id="ca100-108">Enviar un documento intermedio (IDOC)</span><span class="sxs-lookup"><span data-stu-id="ca100-108">Send an Intermediate Document (IDOC)</span></span>  
  
 <span data-ttu-id="ca100-109">El código actúa como un servicio para recibir los siguientes tipos de operaciones:</span><span class="sxs-lookup"><span data-stu-id="ca100-109">Your code acts as a service to receive the following kinds of operations:</span></span>  
  
-   <span data-ttu-id="ca100-110">Recibir una solicitud de cambio (servidor RFC)</span><span class="sxs-lookup"><span data-stu-id="ca100-110">Receive an RFC (RFC server)</span></span>  
  
-   <span data-ttu-id="ca100-111">Recibir un tRFC (tRFC server)</span><span class="sxs-lookup"><span data-stu-id="ca100-111">Receive a tRFC (tRFC server)</span></span>  
  
-   <span data-ttu-id="ca100-112">Recibir un IDOC.</span><span class="sxs-lookup"><span data-stu-id="ca100-112">Receive an IDOC.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca100-113">Dado que BAPI es métodos expuestos por el sistema SAP en objetos de negocio ubicados en el repositorio de objeto de negocios (BOR), no podrá recibir BAPI.</span><span class="sxs-lookup"><span data-stu-id="ca100-113">Because BAPIs are methods exposed by the SAP system on business objects located in the Business Object Repository (BOR), you cannot receive BAPIs.</span></span>  
  
 <span data-ttu-id="ca100-114">En el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo de servicio, el contrato de servicio que existe entre un cliente y un servicio se representa como una interfaz de .NET y las operaciones se representan como métodos en esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="ca100-114">In the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] service model, the service contract that exists between a client and a service is represented as a .NET interface, and operations are represented as methods on this interface.</span></span> <span data-ttu-id="ca100-115">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] y WCF ofrecen herramientas que permiten generar esta interfaz para las operaciones de destino de los metadatos que expone el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ca100-115">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] and WCF provide tools that enable you to generate this interface for targeted operations from the metadata that the adapter exposes.</span></span> <span data-ttu-id="ca100-116">Estas herramientas también crean una clase de cliente WCF que puede usarse para invocar las operaciones que se exponen en la interfaz de servicio.</span><span class="sxs-lookup"><span data-stu-id="ca100-116">These tools also create a WCF client class that can be used to invoke the operations exposed in the service interface.</span></span> <span data-ttu-id="ca100-117">Una aplicación cliente puede llamar a los métodos de la clase de cliente WCF para invocar operaciones en el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ca100-117">A client application can call the methods of the WCF client class to invoke operations on the adapter.</span></span> <span data-ttu-id="ca100-118">Para implementar un servicio para recibir operaciones desde la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], implemente la interfaz generada para la operación de destino.</span><span class="sxs-lookup"><span data-stu-id="ca100-118">To implement a service to receive operations from the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], you implement the interface generated for the target operation.</span></span>  
  
 <span data-ttu-id="ca100-119">Las siguientes secciones explican cómo utilizar el modelo de servicio WCF para crear código de cliente y el servicio para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca100-119">The following sections explain how to use the WCF service model to create client and service code for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="creating-a-wcf-client-and-invoking-operations-on-sap"></a><span data-ttu-id="ca100-120">Cómo crear a un cliente de WCF e invocar operaciones en SAP</span><span class="sxs-lookup"><span data-stu-id="ca100-120">Creating a WCF Client and Invoking Operations on SAP</span></span>  
 <span data-ttu-id="ca100-121">Para usar el modelo de servicio WCF para invocar operaciones en el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], debe generar primero una clase de cliente WCF para las operaciones de destino.</span><span class="sxs-lookup"><span data-stu-id="ca100-121">To use the WCF service model to invoke operations on the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], you must first generate a WCF client class for the target operations.</span></span> <span data-ttu-id="ca100-122">A continuación, puede crear una instancia de esta clase, un cliente de WCF y llamar a sus métodos para realizar operaciones en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="ca100-122">You can then create an instance of this class, a WCF client, and call its methods to perform operations on the SAP system.</span></span>  
  
#### <a name="to-invoke-operations-on-the-sap-adapter"></a><span data-ttu-id="ca100-123">Para invocar operaciones en el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="ca100-123">To invoke operations on the SAP adapter</span></span>  
  
1.  <span data-ttu-id="ca100-124">Generar un código de clase y la aplicación auxiliar de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="ca100-124">Generate a WCF client class and helper code.</span></span> <span data-ttu-id="ca100-125">Use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o los metadatos herramienta de utilidad ServiceModel (svcutil.exe) para generar una clase de cliente WCF destinada a los artefactos del sistema SAP con el que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="ca100-125">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF client class targeted at the SAP system artifacts with which you want to work.</span></span> <span data-ttu-id="ca100-126">Para obtener más información sobre cómo generar un cliente de WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="ca100-126">For more information about how to generate a WCF client, see [Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
2.  <span data-ttu-id="ca100-127">Cree una instancia de cliente WCF mediante la especificación de un enlace del cliente.</span><span class="sxs-lookup"><span data-stu-id="ca100-127">Create a WCF client instance by specifying a client binding.</span></span> <span data-ttu-id="ca100-128">Especificación de un enlace de cliente implica especificar el enlace y la dirección del extremo que se va a usar el cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="ca100-128">Specifying a client binding involves specifying the binding and endpoint address that the WCF client will use.</span></span> <span data-ttu-id="ca100-129">Puede hacerlo imperativamente en código o mediante declaración en configuración.</span><span class="sxs-lookup"><span data-stu-id="ca100-129">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="ca100-130">Para obtener más información sobre cómo especificar un enlace del cliente, consulte [configurar un enlace para el sistema SAP de cliente](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md).</span><span class="sxs-lookup"><span data-stu-id="ca100-130">For more information about how to specify a client binding, see [Configure a client binding for the SAP system](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md).</span></span> <span data-ttu-id="ca100-131">El código siguiente crea a un cliente WCF que puede usarse para invocar una solicitud de cambio en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="ca100-131">The following code creates a WCF client that can be used to invoke an RFC on the SAP system.</span></span> <span data-ttu-id="ca100-132">También establece las credenciales para el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="ca100-132">It also sets the credentials for the SAP system.</span></span> <span data-ttu-id="ca100-133">El cliente de WCF se inicializa desde la configuración.</span><span class="sxs-lookup"><span data-stu-id="ca100-133">The WCF client is initialized from configuration.</span></span>  
  
    ```  
    RfcClient rfcClient = new RfcClient("SAPBinding_Rfc");  
  
    rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
    rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
    ```  
  
3.  <span data-ttu-id="ca100-134">Abra al cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="ca100-134">Open the WCF client.</span></span>  
  
    ```  
    rfcClient.Open();  
    ```  
  
4.  <span data-ttu-id="ca100-135">Invocar métodos en el cliente WCF que creó en el paso 2 para realizar operaciones en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="ca100-135">Invoke methods on the WCF client created in step 2 to perform operations on the SAP system.</span></span> <span data-ttu-id="ca100-136">El código siguiente, se invoca el **SD_RFC_CUSTOMER_GET** método del cliente WCF para invocar la solicitud de cambio en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="ca100-136">The following code invokes the **SD_RFC_CUSTOMER_GET** method of the WCF client to invoke the RFC on the SAP system.</span></span>  
  
    ```  
    microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[] customers =   
        new microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[0];  
  
    rfcClient.SD_RFC_CUSTOMER_GET(string.Empty, "AB*", ref customers);  
    ```  
  
5.  <span data-ttu-id="ca100-137">Cierre al cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="ca100-137">Close the WCF client.</span></span>  
  
    ```  
    rfcClient.Close();  
  
    ```  
  
## <a name="creating-and-implementing-a-wcf-service-by-using-the-sap-adapter"></a><span data-ttu-id="ca100-138">Creación e implementación de un servicio WCF mediante el adaptador SAP.</span><span class="sxs-lookup"><span data-stu-id="ca100-138">Creating and Implementing a WCF Service by Using the SAP Adapter</span></span>  
 <span data-ttu-id="ca100-139">Para utilizar el modelo de servicio WCF para recibir las operaciones de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], primero debe generar la interfaz de .NET (también denominada el contrato de servicio WCF) que representa el contrato de servicio expuesto por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para la operación.</span><span class="sxs-lookup"><span data-stu-id="ca100-139">To use the WCF service model to receive operations from the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], you must first generate the .NET interface (also called the WCF service contract) that represents the service contract exposed by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] for the operation.</span></span> <span data-ttu-id="ca100-140">Para obtener más información acerca de cómo hacerlo, consulte [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="ca100-140">For more information about how to do this, see [Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
 <span data-ttu-id="ca100-141">A continuación, implementar un servicio WCF mediante la implementación de la interfaz generada.</span><span class="sxs-lookup"><span data-stu-id="ca100-141">You then implement a WCF service by implementing the generated interface.</span></span> <span data-ttu-id="ca100-142">Esta clase contiene la lógica de negocios para procesar la operación y devolver una respuesta al adaptador.</span><span class="sxs-lookup"><span data-stu-id="ca100-142">This class contains the business logic to process the operation and return a response to the adapter.</span></span> <span data-ttu-id="ca100-143">A continuación, usar un host de servicio (**System.ServiceModel.ServiceHost**) para hospedar una instancia de este servicio.</span><span class="sxs-lookup"><span data-stu-id="ca100-143">Then you use a service host (**System.ServiceModel.ServiceHost**) to host an instance of this service.</span></span>  
  
#### <a name="to-create-and-implement-a-wcf-service"></a><span data-ttu-id="ca100-144">Para crear e implementar un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="ca100-144">To create and implement a WCF service</span></span>  
  
1.  <span data-ttu-id="ca100-145">Generar un clases de aplicación auxiliar de contrato del servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="ca100-145">Generate a WCF service contract and helper classes.</span></span> <span data-ttu-id="ca100-146">Use la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o svcutil.exe para generar un contrato de servicio WCF (interfaz) destinado a los artefactos del sistema SAP con el que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="ca100-146">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or svcutil.exe to generate a WCF service contract (interface) targeted at the SAP system artifacts with which you want to work.</span></span> <span data-ttu-id="ca100-147">Para obtener más información sobre cómo generar un cliente de WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="ca100-147">For more information about how to generate a WCF client, see [Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
2.  <span data-ttu-id="ca100-148">Implementar un servicio WCF desde las clases de interfaz y auxiliar generado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="ca100-148">Implement a WCF service from the interface and helper classes generated in step 1.</span></span> <span data-ttu-id="ca100-149">Si se produce un error, los datos para la operación de procesamiento, el método que controla esa operación puede producir una excepción para devolver un error en el sistema SAP; en caso contrario, el método debe devolver una instancia de la clase de respuesta (generado) adecuada para la operación.</span><span class="sxs-lookup"><span data-stu-id="ca100-149">If an error is encountered processing the data for the operation, the method that handles that operation can throw an exception to return a fault to the SAP system; otherwise the method must return an instance of the appropriate (generated) response class for the operation.</span></span> <span data-ttu-id="ca100-150">La clase de servicio WCF debe atributo como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="ca100-150">You must attribute the WCF service class as follows:</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
    1.  <span data-ttu-id="ca100-151">Si ha usado la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar la interfaz, puede implementar la lógica de directamente en el método apropiado en los botones generados **SAPBindingService** clase.</span><span class="sxs-lookup"><span data-stu-id="ca100-151">If you used the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate the interface, you can implement your logic directly in the appropriate method in the generated **SAPBindingService** class.</span></span> <span data-ttu-id="ca100-152">Esta clase se puede encontrar en SAPBindingService.cs.</span><span class="sxs-lookup"><span data-stu-id="ca100-152">This class can be found in SAPBindingService.cs.</span></span> <span data-ttu-id="ca100-153">El siguiente código subclases el **SAPBindingService** clase.</span><span class="sxs-lookup"><span data-stu-id="ca100-153">The following code sub-classes the **SAPBindingService** class.</span></span>  
  
        ```  
        [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single,UseSynchronizationContext = false)]  
        class RfcServerClass : SAPBindingNamespace.SAPBindingService  
        {  
            public override Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request)  
            {  
                // If either parameter is null throw an exception   
                if (request.X == null || request.Y == null)  
                    throw new System.ArgumentNullException();  
  
                // Add the two operands  
                int result = (int) (request.X + request.Y);  
  
                return new Z_RFC_MKD_ADDResponse(result);  
            }  
        }  
        ```  
  
    2.  <span data-ttu-id="ca100-154">Si utiliza svcutil.exe para generar la interfaz, debe crear una clase que implementa la interfaz e implementar la lógica en la appropriatemethod de esta clase.</span><span class="sxs-lookup"><span data-stu-id="ca100-154">If you used svcutil.exe to generate the interface, you must create a class that implements the interface and implement your logic in the appropriatemethod of this class.</span></span>  
  
3.  <span data-ttu-id="ca100-155">Cree una instancia del servicio WCF que creó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="ca100-155">Create an instance of the WCF service created in step 2.</span></span>  
  
    ```  
    // create service instance  
    RfcServerClass rfcServerInstance = new RfcServerClass();  
    ```  
  
4.  <span data-ttu-id="ca100-156">Cree una instancia de **System.ServiceModel.ServiceHost** mediante el servicio WCF y un URI de conexión base.</span><span class="sxs-lookup"><span data-stu-id="ca100-156">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="ca100-157">El URI de conexión base no puede contener userinfoparams o un query_string.</span><span class="sxs-lookup"><span data-stu-id="ca100-157">The base connection URI cannot contain userinfoparams or a query_string.</span></span>  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("sap://a/YourSAPHost/00") };  
    ServiceHost srvHost = new ServiceHost(pollingInstance, baseUri);  
    ```  
  
5.  <span data-ttu-id="ca100-158">Crear un **SAPBinding** y configurarlo para la operación estableciendo sus propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="ca100-158">Create an **SAPBinding** and configure it for the operation by setting its binding properties.</span></span> <span data-ttu-id="ca100-159">Puede hacerlo explícitamente en el código o mediante declaración en configuración.</span><span class="sxs-lookup"><span data-stu-id="ca100-159">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="ca100-160">Como mínimo, debe establecer **AcceptCredentialsInUri** a **true**.</span><span class="sxs-lookup"><span data-stu-id="ca100-160">At a minimum, you must set **AcceptCredentialsInUri** to **true**.</span></span>  
  
    ```  
    // Create and configure a binding for the service endpoint. NOTE: binding  
    // parameters are set here for clarity, but these are already set in the  
    // the generated configuration file  
    SAPBinding binding = new SAPBinding();  
  
    // The credentials are included in the connection URI, so set this property to true  
    binding.AcceptCredentialsInUri = true;  
    ```  
  
6.  <span data-ttu-id="ca100-161">Agregar un extremo de servicio al host de servicio.</span><span class="sxs-lookup"><span data-stu-id="ca100-161">Add a service endpoint to the service host.</span></span> <span data-ttu-id="ca100-162">Para hacerlo:</span><span class="sxs-lookup"><span data-stu-id="ca100-162">To do this:</span></span>  
  
    -   <span data-ttu-id="ca100-163">Utilice el enlace creado en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="ca100-163">Use the binding created in step 5.</span></span>  
  
    -   <span data-ttu-id="ca100-164">Especifica una URI que contiene las credenciales y especifica una conexión de agente de escucha de conexión (puerta de enlace de servicio de puerta de enlace de SAP y el Id. de programa) en el query_string.</span><span class="sxs-lookup"><span data-stu-id="ca100-164">Specify a connection URI that contains credentials and specifies a listener connection (SAP gateway, gateway service and program ID) in the query_string.</span></span> <span data-ttu-id="ca100-165">Para obtener más información sobre el URI de conexión de SAP, consulte [crear la conexión del sistema SAP URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="ca100-165">For more information about the SAP connection URI, see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
    -   <span data-ttu-id="ca100-166">Especifique el contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="ca100-166">Specify the service contract.</span></span> <span data-ttu-id="ca100-167">Este es el nombre de la interfaz que representa el contrato de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="ca100-167">This is the name of the interface that represents the WCF service contract.</span></span> <span data-ttu-id="ca100-168">Para las solicitudes de cambio, es "Rfc".</span><span class="sxs-lookup"><span data-stu-id="ca100-168">For RFCs, it is "Rfc".</span></span>  
  
    ```  
    // Add service endpoint   
    // NOTE: The contract for the service endpoint is "Rfc".  
    //       This is the generated WCF service contract (interface) -- see SAPBindingInterface.cs.  
    Uri serviceUri = new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGW00&ListenerGwHost=YourSapHost&ListenerProgramId=SAPAdapter");  
    srvHost.AddServiceEndpoint("Rfc", binding, serviceUri);  
    ```  
  
7.  <span data-ttu-id="ca100-169">Para la operación de recepción desde el sistema SAP, abra el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="ca100-169">To receive the operation from the SAP system, open the service host.</span></span> <span data-ttu-id="ca100-170">El servicio WCF se invocará cada vez que el sistema SAP, invoca la operación en el Id. de programa y el sistema especificado en el URI del servicio en el paso 6.</span><span class="sxs-lookup"><span data-stu-id="ca100-170">Your WCF service will be invoked whenever the SAP system invokes the operation on the program ID and system specified in the service URI in step 6.</span></span>  
  
    ```  
    // Open the service host to begin receiving the operation.  
    srvHost.Open();  
    ```  
  
8.  <span data-ttu-id="ca100-171">Para dejar de recibir la operación, cierre el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="ca100-171">To stop receiving the operation, close the service host.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ca100-172">El adaptador seguirá recibiendo la operación hasta que se cierra el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="ca100-172">The adapter will continue to receive the operation until the service host is closed.</span></span> <span data-ttu-id="ca100-173">Siempre debería cerrar el host del servicio cuando ya no desea que reciban la operación.</span><span class="sxs-lookup"><span data-stu-id="ca100-173">You should always close the service host when you no longer want to receive the operation.</span></span>  
  
    ```  
    srvHost.Close();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ca100-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca100-174">See Also</span></span>  
[<span data-ttu-id="ca100-175">Desarrollar aplicaciones de SAP mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="ca100-175">Develop SAP applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)