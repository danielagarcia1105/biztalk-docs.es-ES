---
title: Resolución ESB y marco de proveedores de adaptador | Documentos de Microsoft
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
ms.openlocfilehash: a350ac19ac1fa95ffb8eb6782380bda78a457b75
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
ms.locfileid: "31008439"
---
# <a name="the-resolver-and-adapter-provider-framework"></a><span data-ttu-id="24555-102">La resolución y el marco de proveedores de adaptador</span><span class="sxs-lookup"><span data-stu-id="24555-102">The Resolver and Adapter Provider Framework</span></span>
<span data-ttu-id="24555-103">La resolución y el marco de proveedores de adaptador es compatible con la resolución de itinerario, transformación y punto de conexión y el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="24555-103">The Resolver and Adapter Provider Framework supports itinerary, transformation, and endpoint resolution and routing.</span></span> <span data-ttu-id="24555-104">El marco de trabajo puede resolver los puntos de conexión y establecer las propiedades de salida del adaptador dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="24555-104">The framework can dynamically resolve endpoints and set outbound adapter properties.</span></span> <span data-ttu-id="24555-105">Después de la resolución de una componente resuelve un punto de conexión (por ejemplo, mediante Universal Description, Discovery e integración [UDDI] para buscar un extremo de servicio Web salientes), un componente de proveedor de adaptador establece propiedades específicas del servidor BizTalk Server registrado adaptadores.</span><span class="sxs-lookup"><span data-stu-id="24555-105">After a resolver component resolves an endpoint (for example, using Universal Description, Discovery, and Integration [UDDI] to look up an outbound Web service endpoint), an adapter provider component sets specific properties of registered BizTalk Server adapters.</span></span> <span data-ttu-id="24555-106">Por ejemplo, el proveedor del adaptador de WCF-BasicHttp es responsable de establecer el mensaje de BizTalk específico de propiedades de contexto para el extremo de URI que se va a utilizar el adaptador de BizTalk específico; el proveedor de adaptador FTP es responsable de establecer las propiedades específicas del adaptador de FTP.</span><span class="sxs-lookup"><span data-stu-id="24555-106">For example, the WCF-BasicHttp adapter provider is responsible for setting the BizTalk-specific message context properties for the endpoint URI that will use the specific BizTalk adapter; the FTP adapter provider is responsible for setting the properties specific to the FTP adapter.</span></span>  
  
 <span data-ttu-id="24555-107">Uno de los objetivos de la resolución y el marco de proveedores de adaptador es compatible con la resolución y el enrutamiento en el nivel mensajería, sin requerir el uso de las orquestaciones de BizTalk, o en el nivel de orquestación.</span><span class="sxs-lookup"><span data-stu-id="24555-107">One goal of the Resolver and Adapter Provider Framework is to support resolution and routing at either the messaging level, without requiring the use of BizTalk orchestrations, or at the orchestration level.</span></span> <span data-ttu-id="24555-108">En ambos casos, el marco acoplable proporciona fácil desarrollo, la implementación y el registro de proveedores de adaptador y resoluciones nuevo.</span><span class="sxs-lookup"><span data-stu-id="24555-108">In both cases, the pluggable framework provides easy development, deployment, and registration of new resolvers and adapter providers.</span></span> <span data-ttu-id="24555-109">Todas las resoluciones y proveedores de adaptador implementan interfaces bien definidas y están demanda de carga en tiempo de ejecución a través del registro en los archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="24555-109">All resolvers and adapter providers implement well-defined interfaces and are demand-loaded at run time through registration in the configuration files.</span></span>  
  
 <span data-ttu-id="24555-110">El distribuidor de ESB y ESB distribuidor desensamblar los componentes de canalización usan la resolución y el marco de proveedores de adaptador, pase la cadena de conexión desde el encabezado SOAP de itinerario o la configuración de canalización con el Administrador de resolución.</span><span class="sxs-lookup"><span data-stu-id="24555-110">Both the ESB Dispatcher and ESB Dispatcher Disassemble pipeline components use the Resolver and Adapter Provider Framework by passing the connection string from either the itinerary SOAP header or the pipeline configuration to the Resolver Manager.</span></span>  
  
 <span data-ttu-id="24555-111">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] configuración contiene los detalles de todos los solucionadores y proveedores de adaptador.</span><span class="sxs-lookup"><span data-stu-id="24555-111">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] configuration contains details of all registered resolvers and adapter providers.</span></span> <span data-ttu-id="24555-112">En tiempo de ejecución, los administradores de resolución y administradores de adaptador leer detalles de los proveedores de adaptador y resoluciones registradas desde los archivos de configuración, cargar los ensamblados adecuados y almacenarlos en una caché de nivel del host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="24555-112">At run time, the resolver managers and adapter managers read details of the registered resolvers and adapter providers from the configuration files, load the appropriate assemblies, and store them in a BizTalk host–level cache.</span></span> <span data-ttu-id="24555-113">Esta técnica de almacenamiento en caché elimina la necesidad de repetidas de lectura de archivos de configuración y la carga de ensamblados para cada mensaje enviado.</span><span class="sxs-lookup"><span data-stu-id="24555-113">This caching technique removes the requirement for repeated reading of configuration files and loading of assemblies for every submitted message.</span></span>  
  
 <span data-ttu-id="24555-114">Para obtener más información sobre cómo funciona la resolución y marco de proveedores de adaptador y cómo puede ampliarlo mediante la creación de solucionadores personalizados y los proveedores de adaptador, vea [modificar y extender el Kit de herramientas de ESB de BizTalk](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md).</span><span class="sxs-lookup"><span data-stu-id="24555-114">For more information about how the Resolver and Adapter Provider Framework works and how you can extend it by creating custom resolvers and adapter providers, see [Modifying and Extending the BizTalk ESB Toolkit](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md).</span></span>  
  
## <a name="supported-resolution-mechanisms-resolvers"></a><span data-ttu-id="24555-115">Mecanismos de resolución admitidos (resoluciones)</span><span class="sxs-lookup"><span data-stu-id="24555-115">Supported Resolution Mechanisms (Resolvers)</span></span>  
 <span data-ttu-id="24555-116">El Kit de herramientas de ESB de BizTalk incluye las siguientes resoluciones: **estático, UDDI, UDDI3, XPATH, BRE, BRI, itinerario, itinerario estático** y **LDAP**.</span><span class="sxs-lookup"><span data-stu-id="24555-116">The BizTalk ESB Toolkit includes the following resolvers: **STATIC, UDDI, UDDI3, XPATH, BRE, BRI, ITINERARY, ITINERARY-STATIC** and **LDAP**.</span></span>  
  
 <span data-ttu-id="24555-117">Cadena de conexión de una resolución siempre consta de un **moniker** (como **BRE**) seguido de ":\\\\" y los detalles de conexión o el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="24555-117">A resolver's connection string always consists of a **moniker** (such as **BRE**) followed by ":\\\\" and the connection or processing details.</span></span> <span data-ttu-id="24555-118">El moniker coincide con la definición de la resolución asociada en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="24555-118">The moniker matches the definition of the associated resolver in the configuration file.</span></span> <span data-ttu-id="24555-119">Las propiedades asociadas a cada cadena de conexión son únicas y no todas las propiedades son necesarias.</span><span class="sxs-lookup"><span data-stu-id="24555-119">The properties associated with each connection string are unique, and not all properties are required.</span></span> <span data-ttu-id="24555-120">El esquema para cada uno de los solucionadores puede encontrarse en ESB. Proyecto de Resolvers.Schemas.</span><span class="sxs-lookup"><span data-stu-id="24555-120">The schema for each of the resolvers can be found in the ESB.Resolvers.Schemas project.</span></span>  
  
 <span data-ttu-id="24555-121">Los siguientes son ejemplos de cadenas de conexión:</span><span class="sxs-lookup"><span data-stu-id="24555-121">The following are examples of connection strings:</span></span>  
  
-   <span data-ttu-id="24555-122">**ESTÁTICO**</span><span class="sxs-lookup"><span data-stu-id="24555-122">**STATIC**</span></span>  
  
     <span data-ttu-id="24555-123">ESTÁTICO:\\\TransportType=;</span><span class="sxs-lookup"><span data-stu-id="24555-123">STATIC:\\\TransportType=;</span></span>  
  
     <span data-ttu-id="24555-124">TransportLocation =http://localhost/ESB.CanadianServices/SubmitPOService.asmx;</span><span class="sxs-lookup"><span data-stu-id="24555-124">TransportLocation=http://localhost/ESB.CanadianServices/SubmitPOService.asmx;</span></span>  
  
     <span data-ttu-id="24555-125">Acción =;</span><span class="sxs-lookup"><span data-stu-id="24555-125">Action=;</span></span>  
  
     <span data-ttu-id="24555-126">EndPointConfig =;</span><span class="sxs-lookup"><span data-stu-id="24555-126">EndPointConfig=;</span></span>  
  
     <span data-ttu-id="24555-127">JaxRpcResponse = false;</span><span class="sxs-lookup"><span data-stu-id="24555-127">JaxRpcResponse=false;</span></span>  
  
     <span data-ttu-id="24555-128">MessageExchangePattern=;</span><span class="sxs-lookup"><span data-stu-id="24555-128">MessageExchangePattern=;</span></span>  
  
     <span data-ttu-id="24555-129">TargetNamespace =http://globalbank.esb.dynamicresolution.com/canadianservices/;</span><span class="sxs-lookup"><span data-stu-id="24555-129">TargetNamespace=http://globalbank.esb.dynamicresolution.com/canadianservices/;</span></span>  
  
     <span data-ttu-id="24555-130">TransformType =;</span><span class="sxs-lookup"><span data-stu-id="24555-130">TransformType=;</span></span>  
  
-   <span data-ttu-id="24555-131">**UDDI**</span><span class="sxs-lookup"><span data-stu-id="24555-131">**UDDI**</span></span>  
  
     <span data-ttu-id="24555-132">UDDI:\\\serverUrl=http://localhost:9901/rmengine;</span><span class="sxs-lookup"><span data-stu-id="24555-132">UDDI:\\\serverUrl=http://localhost:9901/rmengine;</span></span>  
  
     <span data-ttu-id="24555-133">serviceName=OrderPurchaseWebService;</span><span class="sxs-lookup"><span data-stu-id="24555-133">serviceName=OrderPurchaseWebService;</span></span>  
  
     <span data-ttu-id="24555-134">serviceProvider = ESB de prácticas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="24555-134">serviceProvider=Microsoft Practices ESB</span></span>  
  
-   <span data-ttu-id="24555-135">**XPATH**</span><span class="sxs-lookup"><span data-stu-id="24555-135">**XPATH**</span></span>  
  
     <span data-ttu-id="24555-136">XPATH:\\\TransportType=;</span><span class="sxs-lookup"><span data-stu-id="24555-136">XPATH:\\\TransportType=;</span></span>  
  
     `TransportLocation=/*[local-name()='OrderDoc' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*[local-name()='ID' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/'];`  
  
     <span data-ttu-id="24555-137">Acción =;</span><span class="sxs-lookup"><span data-stu-id="24555-137">Action=;</span></span>  
  
     <span data-ttu-id="24555-138">EndPointConfig =;</span><span class="sxs-lookup"><span data-stu-id="24555-138">EndPointConfig=;</span></span>  
  
     <span data-ttu-id="24555-139">JaxRpcResponse =;</span><span class="sxs-lookup"><span data-stu-id="24555-139">JaxRpcResponse=;</span></span>  
  
     <span data-ttu-id="24555-140">MessageExchangePattern=;</span><span class="sxs-lookup"><span data-stu-id="24555-140">MessageExchangePattern=;</span></span>  
  
     `TargetNamespace=/*[local-name()='OrderDoc' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*[local-name()='customerName' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/'];`  
  
     <span data-ttu-id="24555-141">TransformType =;</span><span class="sxs-lookup"><span data-stu-id="24555-141">TransformType=;</span></span>  

-   <span data-ttu-id="24555-142">**BRE**</span><span class="sxs-lookup"><span data-stu-id="24555-142">**BRE**</span></span>  
  
     <span data-ttu-id="24555-143">BRE:\\\policy=GetCanadaEndPoint;</span><span class="sxs-lookup"><span data-stu-id="24555-143">BRE:\\\policy=GetCanadaEndPoint;</span></span>  
  
     <span data-ttu-id="24555-144">versión =;</span><span class="sxs-lookup"><span data-stu-id="24555-144">version=;</span></span>  
  
     <span data-ttu-id="24555-145">useMsg =;</span><span class="sxs-lookup"><span data-stu-id="24555-145">useMsg=;</span></span>  
  
-   <span data-ttu-id="24555-146">**BRI**</span><span class="sxs-lookup"><span data-stu-id="24555-146">**BRI**</span></span>  
  
     <span data-ttu-id="24555-147">BRI:\\\policy=ResolveItinerary;</span><span class="sxs-lookup"><span data-stu-id="24555-147">BRI:\\\policy=ResolveItinerary;</span></span>  
  
     <span data-ttu-id="24555-148">versión =;</span><span class="sxs-lookup"><span data-stu-id="24555-148">version=;</span></span>  
  
     <span data-ttu-id="24555-149">useMsg =;</span><span class="sxs-lookup"><span data-stu-id="24555-149">useMsg=;</span></span>  
  
-   <span data-ttu-id="24555-150">**ITINERARIO**</span><span class="sxs-lookup"><span data-stu-id="24555-150">**ITINERARY**</span></span>  
  
     <span data-ttu-id="24555-151">ITINERARIO:\\\name=TwoWayTestItinerary;</span><span class="sxs-lookup"><span data-stu-id="24555-151">ITINERARY:\\\name=TwoWayTestItinerary;</span></span>  
  
     <span data-ttu-id="24555-152">versión =;</span><span class="sxs-lookup"><span data-stu-id="24555-152">version=;</span></span>  
  
-   <span data-ttu-id="24555-153">**ITINERARIO ESTÁTICOS**</span><span class="sxs-lookup"><span data-stu-id="24555-153">**ITINERARY-STATIC**</span></span>  
  
     <span data-ttu-id="24555-154">ITINERARIO estático:\\\name=TwoWayTestItinerary;</span><span class="sxs-lookup"><span data-stu-id="24555-154">ITINERARY-STATIC:\\\name=TwoWayTestItinerary;</span></span>  
  
     <span data-ttu-id="24555-155">versión =;</span><span class="sxs-lookup"><span data-stu-id="24555-155">version=;</span></span>  
  
-   <span data-ttu-id="24555-156">**LDAP**</span><span class="sxs-lookup"><span data-stu-id="24555-156">**LDAP**</span></span>  
  
     <span data-ttu-id="24555-157">LDAP:\\\TransportType=SMTP;</span><span class="sxs-lookup"><span data-stu-id="24555-157">LDAP:\\\TransportType=SMTP;</span></span>  
  
     <span data-ttu-id="24555-158">TransportLocation = {correo}</span><span class="sxs-lookup"><span data-stu-id="24555-158">TransportLocation={mail}</span></span>  
  
     <span data-ttu-id="24555-159">Filtro = (&(objectClass=User) (| () userPrincipalName =yourname@domain.com)));</span><span class="sxs-lookup"><span data-stu-id="24555-159">Filter=(&(objectClass=User)(|(userPrincipalName=yourname@domain.com)));</span></span>  
  
     <span data-ttu-id="24555-160">SearchRoot =;</span><span class="sxs-lookup"><span data-stu-id="24555-160">SearchRoot=;</span></span>  
  
     <span data-ttu-id="24555-161">SearchScope = subárbol;</span><span class="sxs-lookup"><span data-stu-id="24555-161">SearchScope=Subtree;</span></span>  
  
     <span data-ttu-id="24555-162">EndpointConfig = sujeto = mensaje de prueba de itinerario a {mail} &</span><span class="sxs-lookup"><span data-stu-id="24555-162">EndpointConfig=Subject=Itinerary Test Message to {mail}&</span></span> 
  
     <span data-ttu-id="24555-163">SMTPAuthenticate = 0 &</span><span class="sxs-lookup"><span data-stu-id="24555-163">SMTPAuthenticate=0&</span></span>
  
     <span data-ttu-id="24555-164">SMTPHost = 127.0.0.1 &</span><span class="sxs-lookup"><span data-stu-id="24555-164">SMTPHost=127.0.0.1&</span></span>
  
     <span data-ttu-id="24555-165">FROM =test@globalbank.com&</span><span class="sxs-lookup"><span data-stu-id="24555-165">From=test@globalbank.com&</span></span>
  
     <span data-ttu-id="24555-166">DeliveryReceipt = false &</span><span class="sxs-lookup"><span data-stu-id="24555-166">DeliveryReceipt=false&</span></span>
  
     <span data-ttu-id="24555-167">MessagePartsAttachments = 0 &</span><span class="sxs-lookup"><span data-stu-id="24555-167">MessagePartsAttachments=0&</span></span>
  
     <span data-ttu-id="24555-168">ReadReceipt = false;</span><span class="sxs-lookup"><span data-stu-id="24555-168">ReadReceipt=false;</span></span>  
  
     <span data-ttu-id="24555-169">ThrowErrorIfNotFound = false;</span><span class="sxs-lookup"><span data-stu-id="24555-169">ThrowErrorIfNotFound=false;</span></span>  
  
     <span data-ttu-id="24555-170">Acción =;</span><span class="sxs-lookup"><span data-stu-id="24555-170">Action=;</span></span>  
  
     <span data-ttu-id="24555-171">JaxRpcResponse = false;</span><span class="sxs-lookup"><span data-stu-id="24555-171">JaxRpcResponse=false;</span></span>  
  
     <span data-ttu-id="24555-172">MessageExchangePattern=;</span><span class="sxs-lookup"><span data-stu-id="24555-172">MessageExchangePattern=;</span></span>  
  
     <span data-ttu-id="24555-173">TargetNamespace =;</span><span class="sxs-lookup"><span data-stu-id="24555-173">TargetNamespace=;</span></span>  
  
     <span data-ttu-id="24555-174">TransformType =;</span><span class="sxs-lookup"><span data-stu-id="24555-174">TransformType=;</span></span>  
  
 <span data-ttu-id="24555-175">No todos los atributos de la cadena de conexión son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="24555-175">Not all attributes in the connection string are mandatory.</span></span> <span data-ttu-id="24555-176">Además, **EndPointConfig** es un atributo especial que puede rellenar y devolver cualquier resolución.</span><span class="sxs-lookup"><span data-stu-id="24555-176">In addition, **EndPointConfig** is a special attribute that any resolver can populate and return.</span></span> <span data-ttu-id="24555-177">Si lo desea, la resolución puede almacenar los pares de nombre/valor que se corresponden con determinadas propiedades de contexto del adaptador de BizTalk, que a su vez, pueden escribir en el contexto del mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="24555-177">Optionally, the resolver can store the name/value pairs that correspond to specific BizTalk Adapter Context properties, which it can, in turn, write to the context of the BizTalk message.</span></span>  
  
 <span data-ttu-id="24555-178">En este caso, el **ResolverDictionary** instancia que contiene todas las propiedades resueltas devuelto por el proceso de resolución, a continuación, pasa al administrador de adaptador.</span><span class="sxs-lookup"><span data-stu-id="24555-178">In this case, the **ResolverDictionary** instance that contains all the resolved properties returned from the resolution process then passes to the adapter manager.</span></span> <span data-ttu-id="24555-179">El Administrador de adaptador pasa el diccionario con el proveedor de adaptador específico que se establece propiedades para el mensaje de todo el específicas de punto de conexión y adaptador de BizTalk el contexto.</span><span class="sxs-lookup"><span data-stu-id="24555-179">The adapter manager passes the dictionary to the specific adapter provider that will set all the adapter-specific and endpoint-specific BizTalk Context properties for the message.</span></span> <span data-ttu-id="24555-180">Buscan las resoluciones el **EndPointConfig** propiedad, extraer los pares de nombre/valor que se corresponden con sus propiedades de adaptador correspondiente y, a continuación, establecer estos valores en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="24555-180">The resolvers look for the **EndPointConfig** property, extract the name/value pairs that correspond to their respective adapter properties, and then set these values on the message.</span></span>  
  
## <a name="supported-adapter-providers"></a><span data-ttu-id="24555-181">Proveedores compatibles con el adaptador</span><span class="sxs-lookup"><span data-stu-id="24555-181">Supported Adapter Providers</span></span>  
 <span data-ttu-id="24555-182">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye los siguientes proveedores de adaptador integrado: **archivo, FTP, SMTP, MQSeries, WCF-BasicHttp, WCF-WSHttp,** y **WCF-Custom**.</span><span class="sxs-lookup"><span data-stu-id="24555-182">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes the following built-in adapter providers: **FILE, FTP, SMTP,MQSeries, WCF-BasicHttp, WCF-WSHttp,** and **WCF-Custom**.</span></span> <span data-ttu-id="24555-183">El nombre de cada proveedor de adaptador es idéntico al nombre del adaptador asociado (tipo de transporte) en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="24555-183">The name of each adapter provider is identical to the name of the associated adapter (transport type) in BizTalk Server.</span></span>  
  
 <span data-ttu-id="24555-184">Una ventaja fundamental de la resolución y el marco de proveedores de adaptador es que puede ampliarlo mediante la creación y registrar sus propio solucionadores personalizados para resolver la información de extremo y los proveedores de adaptador personalizado para establecer las propiedades específicas de los adaptadores de BizTalk registrados.</span><span class="sxs-lookup"><span data-stu-id="24555-184">A major advantage of the Resolver and Adapter Provider Framework is that you can extend it by creating and registering your own custom resolvers to resolve endpoint information and custom adapter providers to set specific properties of registered BizTalk adapters.</span></span> <span data-ttu-id="24555-185">Para obtener más información, consulte [modificar y extender el Kit de herramientas de ESB de BizTalk](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md).</span><span class="sxs-lookup"><span data-stu-id="24555-185">For more information, see [Modifying and Extending the BizTalk ESB Toolkit](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md).</span></span>
