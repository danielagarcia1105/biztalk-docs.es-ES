---
title: Marco de proveedores de adaptador y la resolución ESB | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb7ea42e-b32c-40a8-b36b-c349f56f6edd
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95134a1f806398f14a5596149eb605e2de20cac2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002805"
---
# <a name="the-resolver-and-adapter-provider-framework"></a><span data-ttu-id="fe697-102">El marco de proveedores de adaptador y resolución</span><span class="sxs-lookup"><span data-stu-id="fe697-102">The Resolver and Adapter Provider Framework</span></span>
<span data-ttu-id="fe697-103">El marco de proveedores de adaptador y la resolución admite itinerario, transformación y punto de conexión de la resolución y enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="fe697-103">The Resolver and Adapter Provider Framework supports itinerary, transformation, and endpoint resolution and routing.</span></span> <span data-ttu-id="fe697-104">El marco de trabajo dinámicamente puede resolver los puntos de conexión y establecer propiedades del adaptador de salida.</span><span class="sxs-lookup"><span data-stu-id="fe697-104">The framework can dynamically resolve endpoints and set outbound adapter properties.</span></span> <span data-ttu-id="fe697-105">Después de la resolución de una componente se resuelve como un punto de conexión (por ejemplo, el uso de Universal Description, Discovery and Integration [UDDI] para buscar un punto de conexión de servicio Web salientes), un componente de proveedor de adaptador establece propiedades específicas de servidor BizTalk Server registrado adaptadores.</span><span class="sxs-lookup"><span data-stu-id="fe697-105">After a resolver component resolves an endpoint (for example, using Universal Description, Discovery, and Integration [UDDI] to look up an outbound Web service endpoint), an adapter provider component sets specific properties of registered BizTalk Server adapters.</span></span> <span data-ttu-id="fe697-106">Por ejemplo, el proveedor del adaptador WCF-BasicHttp es responsable de establecer el mensaje de BizTalk específico de propiedades de contexto para el punto de conexión de URI que se usará el adaptador de BizTalk específico; el proveedor del adaptador FTP es responsable de establecer las propiedades específicas para el adaptador de FTP.</span><span class="sxs-lookup"><span data-stu-id="fe697-106">For example, the WCF-BasicHttp adapter provider is responsible for setting the BizTalk-specific message context properties for the endpoint URI that will use the specific BizTalk adapter; the FTP adapter provider is responsible for setting the properties specific to the FTP adapter.</span></span>  
  
 <span data-ttu-id="fe697-107">Es uno de los objetivos de la resolución y el marco de proveedores de adaptador admitir la resolución y enrutamiento en el nivel mensajería, sin requerir el uso de las orquestaciones de BizTalk, o en el nivel de orquestación.</span><span class="sxs-lookup"><span data-stu-id="fe697-107">One goal of the Resolver and Adapter Provider Framework is to support resolution and routing at either the messaging level, without requiring the use of BizTalk orchestrations, or at the orchestration level.</span></span> <span data-ttu-id="fe697-108">En ambos casos, el marco acoplable proporciona fácil desarrollo, implementación y registro de las resoluciones nuevo y proveedores de adaptador.</span><span class="sxs-lookup"><span data-stu-id="fe697-108">In both cases, the pluggable framework provides easy development, deployment, and registration of new resolvers and adapter providers.</span></span> <span data-ttu-id="fe697-109">Todas las resoluciones y proveedores de adaptador implementan interfaces bien definidas y son de carga a petición en tiempo de ejecución a través del registro en los archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="fe697-109">All resolvers and adapter providers implement well-defined interfaces and are demand-loaded at run time through registration in the configuration files.</span></span>  
  
 <span data-ttu-id="fe697-110">El distribuidor de ESB y desensamblar distribuidor de ESB componentes de canalización usan el marco de proveedores de adaptador y la resolución pasando la cadena de conexión desde el encabezado SOAP del itinerario o la configuración de canalización para el Administrador de solucionador.</span><span class="sxs-lookup"><span data-stu-id="fe697-110">Both the ESB Dispatcher and ESB Dispatcher Disassemble pipeline components use the Resolver and Adapter Provider Framework by passing the connection string from either the itinerary SOAP header or the pipeline configuration to the Resolver Manager.</span></span>  
  
 <span data-ttu-id="fe697-111">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] configuración contiene los detalles de todas las instancias registradas resoluciones y proveedores de adaptador.</span><span class="sxs-lookup"><span data-stu-id="fe697-111">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] configuration contains details of all registered resolvers and adapter providers.</span></span> <span data-ttu-id="fe697-112">En tiempo de ejecución, los administradores de resolución y administradores de adaptador que se leen los archivos de configuración en los detalles de los proveedores de adaptador y resoluciones registradas, cargar los ensamblados adecuados y almacenarlos en una caché de nivel del host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="fe697-112">At run time, the resolver managers and adapter managers read details of the registered resolvers and adapter providers from the configuration files, load the appropriate assemblies, and store them in a BizTalk host–level cache.</span></span> <span data-ttu-id="fe697-113">Esta técnica de almacenamiento en caché elimina el requisito para repetidas de lectura de archivos de configuración y carga de ensamblados para cada mensaje enviado.</span><span class="sxs-lookup"><span data-stu-id="fe697-113">This caching technique removes the requirement for repeated reading of configuration files and loading of assemblies for every submitted message.</span></span>  
  
 <span data-ttu-id="fe697-114">Para obtener más información sobre cómo el marco resolución y adaptadores proveedor funciona y cómo puede ampliarlo mediante la creación de los solucionadores personalizados y proveedores de adaptador, vea [modificación y extensión del Kit de herramientas de BizTalk ESB](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md).</span><span class="sxs-lookup"><span data-stu-id="fe697-114">For more information about how the Resolver and Adapter Provider Framework works and how you can extend it by creating custom resolvers and adapter providers, see [Modifying and Extending the BizTalk ESB Toolkit](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md).</span></span>  
  
## <a name="supported-resolution-mechanisms-resolvers"></a><span data-ttu-id="fe697-115">Resolución admite mecanismos (resoluciones)</span><span class="sxs-lookup"><span data-stu-id="fe697-115">Supported Resolution Mechanisms (Resolvers)</span></span>  
 <span data-ttu-id="fe697-116">El Kit de herramientas de ESB de BizTalk incluye las siguientes resoluciones: **estático, UDDI, UDDI3, XPATH, BRE, BRI, itinerario, itinerario estático** y **LDAP**.</span><span class="sxs-lookup"><span data-stu-id="fe697-116">The BizTalk ESB Toolkit includes the following resolvers: **STATIC, UDDI, UDDI3, XPATH, BRE, BRI, ITINERARY, ITINERARY-STATIC** and **LDAP**.</span></span>  
  
 <span data-ttu-id="fe697-117">Cadena de conexión de una resolución siempre consta de un **moniker** (como **BRE**) seguido de ":\\\\" y los detalles de conexión o procesamiento.</span><span class="sxs-lookup"><span data-stu-id="fe697-117">A resolver's connection string always consists of a **moniker** (such as **BRE**) followed by ":\\\\" and the connection or processing details.</span></span> <span data-ttu-id="fe697-118">El moniker coincide con la definición de la resolución asociada en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="fe697-118">The moniker matches the definition of the associated resolver in the configuration file.</span></span> <span data-ttu-id="fe697-119">Las propiedades asociadas con cada cadena de conexión son únicas y no todas las propiedades que son necesarias.</span><span class="sxs-lookup"><span data-stu-id="fe697-119">The properties associated with each connection string are unique, and not all properties are required.</span></span> <span data-ttu-id="fe697-120">El esquema para cada una de las resoluciones puede encontrarse en el ESB. Proyecto Resolvers.Schemas.</span><span class="sxs-lookup"><span data-stu-id="fe697-120">The schema for each of the resolvers can be found in the ESB.Resolvers.Schemas project.</span></span>  
  
 <span data-ttu-id="fe697-121">Los siguientes son ejemplos de cadenas de conexión:</span><span class="sxs-lookup"><span data-stu-id="fe697-121">The following are examples of connection strings:</span></span>  
  
- <span data-ttu-id="fe697-122">**ESTÁTICO**</span><span class="sxs-lookup"><span data-stu-id="fe697-122">**STATIC**</span></span>  
  
   <span data-ttu-id="fe697-123">ESTÁTICO:\\\TransportType=;</span><span class="sxs-lookup"><span data-stu-id="fe697-123">STATIC:\\\TransportType=;</span></span>  
  
   <span data-ttu-id="fe697-124">TransportLocation =<http://localhost/ESB.CanadianServices/SubmitPOService.asmx>;</span><span class="sxs-lookup"><span data-stu-id="fe697-124">TransportLocation=<http://localhost/ESB.CanadianServices/SubmitPOService.asmx>;</span></span>  
  
   <span data-ttu-id="fe697-125">Acción =;</span><span class="sxs-lookup"><span data-stu-id="fe697-125">Action=;</span></span>  
  
   <span data-ttu-id="fe697-126">EndPointConfig =;</span><span class="sxs-lookup"><span data-stu-id="fe697-126">EndPointConfig=;</span></span>  
  
   <span data-ttu-id="fe697-127">JaxRpcResponse = false.</span><span class="sxs-lookup"><span data-stu-id="fe697-127">JaxRpcResponse=false;</span></span>  
  
   <span data-ttu-id="fe697-128">MessageExchangePattern=;</span><span class="sxs-lookup"><span data-stu-id="fe697-128">MessageExchangePattern=;</span></span>  
  
   <span data-ttu-id="fe697-129">TargetNamespace =<http://globalbank.esb.dynamicresolution.com/canadianservices/>;</span><span class="sxs-lookup"><span data-stu-id="fe697-129">TargetNamespace=<http://globalbank.esb.dynamicresolution.com/canadianservices/>;</span></span>  
  
   <span data-ttu-id="fe697-130">TransformType =;</span><span class="sxs-lookup"><span data-stu-id="fe697-130">TransformType=;</span></span>  
  
- <span data-ttu-id="fe697-131">**UDDI**</span><span class="sxs-lookup"><span data-stu-id="fe697-131">**UDDI**</span></span>  
  
   <span data-ttu-id="fe697-132">UDDI:\\\serverUrl=<http://localhost:9901/rmengine>;</span><span class="sxs-lookup"><span data-stu-id="fe697-132">UDDI:\\\serverUrl=<http://localhost:9901/rmengine>;</span></span>  
  
   <span data-ttu-id="fe697-133">serviceName=OrderPurchaseWebService;</span><span class="sxs-lookup"><span data-stu-id="fe697-133">serviceName=OrderPurchaseWebService;</span></span>  
  
   <span data-ttu-id="fe697-134">serviceProvider = ESB de prácticas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="fe697-134">serviceProvider=Microsoft Practices ESB</span></span>  
  
- <span data-ttu-id="fe697-135">**XPATH**</span><span class="sxs-lookup"><span data-stu-id="fe697-135">**XPATH**</span></span>  
  
   <span data-ttu-id="fe697-136">XPATH:\\\TransportType=;</span><span class="sxs-lookup"><span data-stu-id="fe697-136">XPATH:\\\TransportType=;</span></span>  
  
   `TransportLocation=/*[local-name()='OrderDoc' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*[local-name()='ID' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/'];`  
  
   <span data-ttu-id="fe697-137">Acción =;</span><span class="sxs-lookup"><span data-stu-id="fe697-137">Action=;</span></span>  
  
   <span data-ttu-id="fe697-138">EndPointConfig =;</span><span class="sxs-lookup"><span data-stu-id="fe697-138">EndPointConfig=;</span></span>  
  
   <span data-ttu-id="fe697-139">JaxRpcResponse =;</span><span class="sxs-lookup"><span data-stu-id="fe697-139">JaxRpcResponse=;</span></span>  
  
   <span data-ttu-id="fe697-140">MessageExchangePattern=;</span><span class="sxs-lookup"><span data-stu-id="fe697-140">MessageExchangePattern=;</span></span>  
  
   `TargetNamespace=/*[local-name()='OrderDoc' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*[local-name()='customerName' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/'];`  
  
   <span data-ttu-id="fe697-141">TransformType =;</span><span class="sxs-lookup"><span data-stu-id="fe697-141">TransformType=;</span></span>  

- <span data-ttu-id="fe697-142">**BRE**</span><span class="sxs-lookup"><span data-stu-id="fe697-142">**BRE**</span></span>  
  
   <span data-ttu-id="fe697-143">BRE:\\\policy=GetCanadaEndPoint;</span><span class="sxs-lookup"><span data-stu-id="fe697-143">BRE:\\\policy=GetCanadaEndPoint;</span></span>  
  
   <span data-ttu-id="fe697-144">versión =;</span><span class="sxs-lookup"><span data-stu-id="fe697-144">version=;</span></span>  
  
   <span data-ttu-id="fe697-145">useMsg =;</span><span class="sxs-lookup"><span data-stu-id="fe697-145">useMsg=;</span></span>  
  
- <span data-ttu-id="fe697-146">**BRI**</span><span class="sxs-lookup"><span data-stu-id="fe697-146">**BRI**</span></span>  
  
   <span data-ttu-id="fe697-147">BRI:\\\policy=ResolveItinerary;</span><span class="sxs-lookup"><span data-stu-id="fe697-147">BRI:\\\policy=ResolveItinerary;</span></span>  
  
   <span data-ttu-id="fe697-148">versión =;</span><span class="sxs-lookup"><span data-stu-id="fe697-148">version=;</span></span>  
  
   <span data-ttu-id="fe697-149">useMsg =;</span><span class="sxs-lookup"><span data-stu-id="fe697-149">useMsg=;</span></span>  
  
- <span data-ttu-id="fe697-150">**ITINERARIO**</span><span class="sxs-lookup"><span data-stu-id="fe697-150">**ITINERARY**</span></span>  
  
   <span data-ttu-id="fe697-151">ITINERARIO:\\\name=TwoWayTestItinerary;</span><span class="sxs-lookup"><span data-stu-id="fe697-151">ITINERARY:\\\name=TwoWayTestItinerary;</span></span>  
  
   <span data-ttu-id="fe697-152">versión =;</span><span class="sxs-lookup"><span data-stu-id="fe697-152">version=;</span></span>  
  
- <span data-ttu-id="fe697-153">**ITINERARIO ESTÁTICO**</span><span class="sxs-lookup"><span data-stu-id="fe697-153">**ITINERARY-STATIC**</span></span>  
  
   <span data-ttu-id="fe697-154">ITINERARIO estático:\\\name=TwoWayTestItinerary;</span><span class="sxs-lookup"><span data-stu-id="fe697-154">ITINERARY-STATIC:\\\name=TwoWayTestItinerary;</span></span>  
  
   <span data-ttu-id="fe697-155">versión =;</span><span class="sxs-lookup"><span data-stu-id="fe697-155">version=;</span></span>  
  
- <span data-ttu-id="fe697-156">**LDAP**</span><span class="sxs-lookup"><span data-stu-id="fe697-156">**LDAP**</span></span>  
  
   <span data-ttu-id="fe697-157">LDAP:\\\TransportType=SMTP;</span><span class="sxs-lookup"><span data-stu-id="fe697-157">LDAP:\\\TransportType=SMTP;</span></span>  
  
   <span data-ttu-id="fe697-158">TransportLocation = {correo electrónico de}</span><span class="sxs-lookup"><span data-stu-id="fe697-158">TransportLocation={mail}</span></span>  
  
   <span data-ttu-id="fe697-159">Filtro = (&(objectClass=User) (| () userPrincipalName =yourname@domain.com)));</span><span class="sxs-lookup"><span data-stu-id="fe697-159">Filter=(&(objectClass=User)(|(userPrincipalName=yourname@domain.com)));</span></span>  
  
   <span data-ttu-id="fe697-160">SearchRoot =;</span><span class="sxs-lookup"><span data-stu-id="fe697-160">SearchRoot=;</span></span>  
  
   <span data-ttu-id="fe697-161">SearchScope = subárbol;</span><span class="sxs-lookup"><span data-stu-id="fe697-161">SearchScope=Subtree;</span></span>  
  
   <span data-ttu-id="fe697-162">EndpointConfig = asunto = mensaje de prueba de itinerario para correo electrónico de {} &</span><span class="sxs-lookup"><span data-stu-id="fe697-162">EndpointConfig=Subject=Itinerary Test Message to {mail}&</span></span> 
  
   <span data-ttu-id="fe697-163">SMTPAuthenticate = 0 &</span><span class="sxs-lookup"><span data-stu-id="fe697-163">SMTPAuthenticate=0&</span></span>
  
   <span data-ttu-id="fe697-164">SMTPHost = 127.0.0.1 &</span><span class="sxs-lookup"><span data-stu-id="fe697-164">SMTPHost=127.0.0.1&</span></span>
  
   <span data-ttu-id="fe697-165">FROM =test@globalbank.com&</span><span class="sxs-lookup"><span data-stu-id="fe697-165">From=test@globalbank.com&</span></span>
  
   <span data-ttu-id="fe697-166">DeliveryReceipt = false &</span><span class="sxs-lookup"><span data-stu-id="fe697-166">DeliveryReceipt=false&</span></span>
  
   <span data-ttu-id="fe697-167">MessagePartsAttachments = 0 &</span><span class="sxs-lookup"><span data-stu-id="fe697-167">MessagePartsAttachments=0&</span></span>
  
   <span data-ttu-id="fe697-168">ReadReceipt = false.</span><span class="sxs-lookup"><span data-stu-id="fe697-168">ReadReceipt=false;</span></span>  
  
   <span data-ttu-id="fe697-169">ThrowErrorIfNotFound = false.</span><span class="sxs-lookup"><span data-stu-id="fe697-169">ThrowErrorIfNotFound=false;</span></span>  
  
   <span data-ttu-id="fe697-170">Acción =;</span><span class="sxs-lookup"><span data-stu-id="fe697-170">Action=;</span></span>  
  
   <span data-ttu-id="fe697-171">JaxRpcResponse = false.</span><span class="sxs-lookup"><span data-stu-id="fe697-171">JaxRpcResponse=false;</span></span>  
  
   <span data-ttu-id="fe697-172">MessageExchangePattern=;</span><span class="sxs-lookup"><span data-stu-id="fe697-172">MessageExchangePattern=;</span></span>  
  
   <span data-ttu-id="fe697-173">TargetNamespace =;</span><span class="sxs-lookup"><span data-stu-id="fe697-173">TargetNamespace=;</span></span>  
  
   <span data-ttu-id="fe697-174">TransformType =;</span><span class="sxs-lookup"><span data-stu-id="fe697-174">TransformType=;</span></span>  
  
  <span data-ttu-id="fe697-175">No todos los atributos en la cadena de conexión son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="fe697-175">Not all attributes in the connection string are mandatory.</span></span> <span data-ttu-id="fe697-176">Además, **EndPointConfig** es un atributo especial que puede rellenar y devolver cualquier resolución.</span><span class="sxs-lookup"><span data-stu-id="fe697-176">In addition, **EndPointConfig** is a special attribute that any resolver can populate and return.</span></span> <span data-ttu-id="fe697-177">Opcionalmente, la resolución puede almacenar los pares nombre/valor que se corresponden con determinadas propiedades de contexto del adaptador de BizTalk, que a su vez, pueden escribir en el contexto del mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="fe697-177">Optionally, the resolver can store the name/value pairs that correspond to specific BizTalk Adapter Context properties, which it can, in turn, write to the context of the BizTalk message.</span></span>  
  
  <span data-ttu-id="fe697-178">En este caso, el **ResolverDictionary** instancia que contiene todas las propiedades resueltas devuelto por el proceso de resolución, a continuación, pasa al administrador de adaptador.</span><span class="sxs-lookup"><span data-stu-id="fe697-178">In this case, the **ResolverDictionary** instance that contains all the resolved properties returned from the resolution process then passes to the adapter manager.</span></span> <span data-ttu-id="fe697-179">El Administrador de adaptador pasa el diccionario con el proveedor de adaptador específico que se establece propiedades para el mensaje de todo el específicas del punto de conexión y adaptador de BizTalk el contexto.</span><span class="sxs-lookup"><span data-stu-id="fe697-179">The adapter manager passes the dictionary to the specific adapter provider that will set all the adapter-specific and endpoint-specific BizTalk Context properties for the message.</span></span> <span data-ttu-id="fe697-180">Busque las resoluciones del **EndPointConfig** propiedad, extraer los pares nombre/valor que se corresponden con sus propiedades de adaptador correspondiente y, a continuación, establezca estos valores en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="fe697-180">The resolvers look for the **EndPointConfig** property, extract the name/value pairs that correspond to their respective adapter properties, and then set these values on the message.</span></span>  
  
## <a name="supported-adapter-providers"></a><span data-ttu-id="fe697-181">Proveedores compatibles con el adaptador</span><span class="sxs-lookup"><span data-stu-id="fe697-181">Supported Adapter Providers</span></span>  
 <span data-ttu-id="fe697-182">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye los siguientes proveedores de adaptador integrado: **archivo, FTP, SMTP, MQSeries, WCF-BasicHttp, WCF-WSHttp,** y **WCF-Custom**.</span><span class="sxs-lookup"><span data-stu-id="fe697-182">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes the following built-in adapter providers: **FILE, FTP, SMTP,MQSeries, WCF-BasicHttp, WCF-WSHttp,** and **WCF-Custom**.</span></span> <span data-ttu-id="fe697-183">El nombre de cada proveedor de adaptador es idéntico al nombre del adaptador asociado (tipo de transporte) en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="fe697-183">The name of each adapter provider is identical to the name of the associated adapter (transport type) in BizTalk Server.</span></span>  
  
 <span data-ttu-id="fe697-184">Una ventaja fundamental de la resolución y el marco de proveedores de adaptador es que puede ampliarlo mediante la creación y registro de sus propias resoluciones personalizadas para resolver la información de punto de conexión y los proveedores de adaptador personalizado para establecer propiedades específicas de los adaptadores de BizTalk registrados.</span><span class="sxs-lookup"><span data-stu-id="fe697-184">A major advantage of the Resolver and Adapter Provider Framework is that you can extend it by creating and registering your own custom resolvers to resolve endpoint information and custom adapter providers to set specific properties of registered BizTalk adapters.</span></span> <span data-ttu-id="fe697-185">Para obtener más información, consulte [modificación y extensión del Kit de herramientas de BizTalk ESB](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md).</span><span class="sxs-lookup"><span data-stu-id="fe697-185">For more information, see [Modifying and Extending the BizTalk ESB Toolkit](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md).</span></span>
