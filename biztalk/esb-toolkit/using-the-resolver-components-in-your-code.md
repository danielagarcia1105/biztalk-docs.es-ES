---
title: "Con los componentes de la resolución de su código | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d197cb28-78a9-4c8a-872b-f61ef15e6622
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 220ae4983f2fcbf60f6de02f818095fe5c0c50a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-resolver-components-in-your-code"></a><span data-ttu-id="c13db-102">Con los componentes de resolución en el código</span><span class="sxs-lookup"><span data-stu-id="c13db-102">Using the Resolver Components in Your Code</span></span>
<span data-ttu-id="c13db-103">El siguiente fragmento de código desde el agente de transformación dinámica muestra la funcionalidad de resolución predeterminada just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="c13db-103">The following code fragment from the dynamic transformation agent shows the default just-in-time (JIT) resolution functionality.</span></span> <span data-ttu-id="c13db-104">Puede implementar fácilmente la resolución en su propia aplicación mediante código similar.</span><span class="sxs-lookup"><span data-stu-id="c13db-104">You can easily implement resolution in your own application by using similar code.</span></span>  
  
```  
  
//XLANGs  
itinerary = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryWrapper();  
step = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryStepWrapper();  
  
itinerary.Itinerary = Microsoft.Practices.ESB.Itinerary.ItineraryOMFactory.Create(InboundMessage);  
step.ItineraryStep = itinerary.Itinerary.GetItineraryStep(InboundMessage);  
resolvers = step.ItineraryStep.ResolverCollection;  
resolvers.MoveNext();  
resolver = resolvers.Current;  
  
// Pass the resolver configuration to the Resolver mgr for resolution.  
resolverDictionary = Microsoft.Practices.ESB.Resolver.ResolverMgr.Resolve(InboundMessage, resolver);  
  
// Set the transform type.  
transformType = resolverDictionary.Item("Resolver.TransformType");  
```  
  
 <span data-ttu-id="c13db-105">En la lista anterior, el **resolver** método de la **ResolverMgr** clase devuelve una **diccionario** objeto que contiene todas las propiedades de resolución predeterminado y sus valores resueltos.</span><span class="sxs-lookup"><span data-stu-id="c13db-105">In the preceding listing, the **Resolve** method of the **ResolverMgr** class returns a **Dictionary** object that contains all the default resolution properties and their resolved values.</span></span> <span data-ttu-id="c13db-106">Cualquier resolución personalizada puede agregar propiedades personalizadas a la **diccionario** objeto; hacer esto hace que las propiedades disponibles para cualquier servicio itinerario personalizado.</span><span class="sxs-lookup"><span data-stu-id="c13db-106">Any custom resolver can add custom properties to the **Dictionary** object; doing this makes those properties available to any custom itinerary service.</span></span>  
  
 <span data-ttu-id="c13db-107">La siguiente tabla muestra las propiedades que se pueden rellenar opcionalmente por las resoluciones incluidas en el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c13db-107">The following table shows the properties that can be optionally populated by the resolvers included in the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="c13db-108">Cualquier servicio itinerario puede recuperar estos valores de propiedad mediante la extracción de ellos desde el valor devuelto **diccionario** objeto.</span><span class="sxs-lookup"><span data-stu-id="c13db-108">Any itinerary service can retrieve these property values by extracting them from the returned **Dictionary** object.</span></span>  
  
 <span data-ttu-id="c13db-109">**Propiedades de**:</span><span class="sxs-lookup"><span data-stu-id="c13db-109">**Properties**:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="c13db-110">**Resolver.Action**</span><span class="sxs-lookup"><span data-stu-id="c13db-110">**Resolver.Action**</span></span>|<span data-ttu-id="c13db-111">**Resolver.ActionField**</span><span class="sxs-lookup"><span data-stu-id="c13db-111">**Resolver.ActionField**</span></span>|<span data-ttu-id="c13db-112">**Resolver.DocumentSpecName**</span><span class="sxs-lookup"><span data-stu-id="c13db-112">**Resolver.DocumentSpecName**</span></span>|  
|<span data-ttu-id="c13db-113">**Resolver.Success**</span><span class="sxs-lookup"><span data-stu-id="c13db-113">**Resolver.Success**</span></span>|<span data-ttu-id="c13db-114">**Resolver.EndpointConfig**</span><span class="sxs-lookup"><span data-stu-id="c13db-114">**Resolver.EndpointConfig**</span></span>|<span data-ttu-id="c13db-115">**Resolver.DocumentSpecStrongName**</span><span class="sxs-lookup"><span data-stu-id="c13db-115">**Resolver.DocumentSpecStrongName**</span></span>|  
|<span data-ttu-id="c13db-116">**Resolver.FixJaxRpc**</span><span class="sxs-lookup"><span data-stu-id="c13db-116">**Resolver.FixJaxRpc**</span></span>|<span data-ttu-id="c13db-117">**Resolver.InboundTransportType**</span><span class="sxs-lookup"><span data-stu-id="c13db-117">**Resolver.InboundTransportType**</span></span>|<span data-ttu-id="c13db-118">**Resolver.EpmRRCorrelationToken**</span><span class="sxs-lookup"><span data-stu-id="c13db-118">**Resolver.EpmRRCorrelationToken**</span></span>|  
|<span data-ttu-id="c13db-119">**Resolver.InterchangeId**</span><span class="sxs-lookup"><span data-stu-id="c13db-119">**Resolver.InterchangeId**</span></span>|<span data-ttu-id="c13db-120">**Resolver.IsRequestResponse**</span><span class="sxs-lookup"><span data-stu-id="c13db-120">**Resolver.IsRequestResponse**</span></span>|<span data-ttu-id="c13db-121">**Resolver.InboundTransportLocation**</span><span class="sxs-lookup"><span data-stu-id="c13db-121">**Resolver.InboundTransportLocation**</span></span>|  
|<span data-ttu-id="c13db-122">**Resolver.MessageType**</span><span class="sxs-lookup"><span data-stu-id="c13db-122">**Resolver.MessageType**</span></span>|<span data-ttu-id="c13db-123">**Resolver.MethodName**</span><span class="sxs-lookup"><span data-stu-id="c13db-123">**Resolver.MethodName**</span></span>|<span data-ttu-id="c13db-124">**Resolver.MessageExchangePattern**</span><span class="sxs-lookup"><span data-stu-id="c13db-124">**Resolver.MessageExchangePattern**</span></span>|  
|<span data-ttu-id="c13db-125">**Resolver.ReceivePortName**</span><span class="sxs-lookup"><span data-stu-id="c13db-125">**Resolver.ReceivePortName**</span></span>|<span data-ttu-id="c13db-126">**Resolver.TransportLocation**</span><span class="sxs-lookup"><span data-stu-id="c13db-126">**Resolver.TransportLocation**</span></span>|<span data-ttu-id="c13db-127">**Resolver.OutboundTransportCLSID**</span><span class="sxs-lookup"><span data-stu-id="c13db-127">**Resolver.OutboundTransportCLSID**</span></span>|  
|<span data-ttu-id="c13db-128">**Resolver.TransformType**</span><span class="sxs-lookup"><span data-stu-id="c13db-128">**Resolver.TransformType**</span></span>|<span data-ttu-id="c13db-129">**Resolver.TargetNamespace**</span><span class="sxs-lookup"><span data-stu-id="c13db-129">**Resolver.TargetNamespace**</span></span>|<span data-ttu-id="c13db-130">**Resolver.ReceiveLocationName**</span><span class="sxs-lookup"><span data-stu-id="c13db-130">**Resolver.ReceiveLocationName**</span></span>|  
|<span data-ttu-id="c13db-131">**Resolver.TransportType**</span><span class="sxs-lookup"><span data-stu-id="c13db-131">**Resolver.TransportType**</span></span>|<span data-ttu-id="c13db-132">**Resolver.TransportNamespace**</span><span class="sxs-lookup"><span data-stu-id="c13db-132">**Resolver.TransportNamespace**</span></span>|<span data-ttu-id="c13db-133">**Resolver.WindowUserField**</span><span class="sxs-lookup"><span data-stu-id="c13db-133">**Resolver.WindowUserField**</span></span>|  
|<span data-ttu-id="c13db-134">**Resolver.CacheTimeout**</span><span class="sxs-lookup"><span data-stu-id="c13db-134">**Resolver.CacheTimeout**</span></span>|||  
  
 <span data-ttu-id="c13db-135">Después de la resolución manager devuelve el **diccionario** instancia del objeto, el Administrador de adaptador establece las propiedades de contexto del adaptador de BizTalk específicas del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c13db-135">After the resolver manager returns the **Dictionary** object instance, the adapter manager sets the specific BizTalk Adapter Context properties of the message.</span></span> <span data-ttu-id="c13db-136">El siguiente fragmento de código desde el agente de enrutamiento muestra cómo se puede usar el Administrador de adaptador para establecer las propiedades de punto de conexión del mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="c13db-136">The following code fragment from the routing agent demonstrates how you can use the adapter manager to set the endpoint properties of the outgoing message.</span></span>  
  
```  
  
//XLANGs  
// Set the transport properties.  
transportLocation = resolverDictionary.Item("Resolver.TransportLocation");  
transportType = resolverDictionary.Item("Resolver.TransportType");  
  
// Create the delivery message.  
DeliveryMessage = InboundMessage;  
  
// Call the adapter manager to set all necessary properties on the message.  
Microsoft.Practices.ESB.Adapter.AdapterMgr.SetEndpoint(  
                                resolverDictionary,DeliveryMessage);  
  
// Set the delivery port address.  
DeliveryPort(Microsoft.XLANGs.BaseTypes.Address) = transportLocation;  
DeliveryPort(Microsoft.XLANGs.BaseTypes.TransportType) = transportType;  
```  
  
 <span data-ttu-id="c13db-137">El siguiente fragmento de código desde el agente de enrutamiento muestra cómo utilizar el administrador del adaptador desde dentro de un componente de canalización personalizado para establecer las propiedades de punto de conexión de un mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="c13db-137">The following code fragment from the routing agent demonstrates how to use the adapter manager from within a custom pipeline component to set the endpoint properties of an outgoing message.</span></span>  
  
```csharp  
// Resolve the configuration for routing.  
ResolverDictionary = ResolverMgr.Resolve(info, pInMsg, pContext);  
  
// Call the adapter manager to set all required message properties.  
AdapterMgr.SetEndpoint(ResolverDictionary, pInMsg.Context);  
```