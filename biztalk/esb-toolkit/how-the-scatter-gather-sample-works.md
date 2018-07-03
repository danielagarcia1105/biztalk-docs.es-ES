---
title: Cómo funciona el ejemplo de dispersión y recopilación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ccfacb7-4fd2-4a1a-bece-27eedd86bbe9
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c675f2c6a9f558be597f7765ec936daf0a5a2dde
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001103"
---
# <a name="how-the-scatter-gather-sample-works"></a><span data-ttu-id="741c0-102">Cómo funciona el ejemplo de dispersión y recopilación</span><span class="sxs-lookup"><span data-stu-id="741c0-102">How the Scatter-Gather Sample Works</span></span>
<span data-ttu-id="741c0-103">La aplicación de ejemplo compila un conjunto de encabezados SOAP que contiene el itinerario cargado desde el archivo de itinerarios de dispersión y recopilación, carga el archivo de mensaje especificado desde el disco, anexa los encabezados de itinerarios al mensaje y lo envía al ESB a través de una vía rápida para procesamiento.</span><span class="sxs-lookup"><span data-stu-id="741c0-103">The sample application builds a set of SOAP headers containing the itinerary loaded from the Scatter-Gather itinerary file, loads the specified message file from disk, appends the itinerary headers to the message, and submits it to the ESB through an on-ramp for processing.</span></span> <span data-ttu-id="741c0-104">Si el itinerario genera una respuesta, la aplicación recopila esto y lo muestra en la ventana de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="741c0-104">If the itinerary generates a response, the application collects this and displays it in the application window.</span></span>  
  
 <span data-ttu-id="741c0-105">Para ayudarle a comprender cómo el servicio de itinerarios utiliza la información de itinerarios en un mensaje, la lista siguiente muestra el archivo de configuración de itinerarios de ejemplo denominado ScatterGatherItinerary.xml.</span><span class="sxs-lookup"><span data-stu-id="741c0-105">To help you understand how the Itinerary service uses the itinerary information in a message, the following listing shows the sample itinerary configuration file named ScatterGatherItinerary.xml.</span></span> <span data-ttu-id="741c0-106">La primera sección de este itinerario especifica dos pasos de la invocación de servicio.</span><span class="sxs-lookup"><span data-stu-id="741c0-106">The first section of this itinerary specifies two service invocation steps.</span></span>  
  
```xml  
<Itinerary xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"   
    xmlns:xsd="http://www.w3.org/2001/XMLSchema" uuid="" beginTime=""   
    completeTime="" state="Pending" isRequestResponse="false"   
    xmlns="http://schemas.microsoft.biztalk.practices.esb.com/itinerary">  
  <ServiceInstance uuid="" name="ScatterGather" type="Orchestration"  
                   state="Pending" position="0"   
                   isRequestResponse="false" xmlns="" />  
  <Services xmlns="">  
    <Service uuid="" beginTime="" completeTime="" name="ScatterGather"  
             type="Orchestration" state="Pending" isRequestResponse="false"  
             position="0" serviceInstanceId="" />  
  </Services>  
  <Services xmlns="">  
    <Service uuid="" beginTime="" completeTime="" name="DynamicTest"  
             type="Messaging" state="Pending" isRequestResponse="false"  
             position="1" serviceInstanceId="" />  
  </Services>  
</Itinerary>  
...  
```  
  
 <span data-ttu-id="741c0-107">Después de la lista de pasos de la invocación de servicio en el itinerario es la sección que contiene los detalles de las resoluciones y cadenas de conexión que permiten que el servicio de itinerarios buscar cada servicio definido en el itinerario, como se muestra en el siguiente código XML.</span><span class="sxs-lookup"><span data-stu-id="741c0-107">Following the list of service invocation steps in the itinerary is the section containing details of the resolvers and connection strings that allow the Itinerary service to locate each service defined in the itinerary, as shown in the following XML.</span></span>  
  
```xml  
<ResolverGroups xmlns="">  
 <Resolvers serviceId="ScatterGather0"><![CDATA[BRE:\\policy=ResolveEndPointScatterGather;version=;useMsg=;]]><![CDATA[UDDI3:\\serverUrl=http://localhost/uddi;bindingKey=uddi:esb:purchaseordersubmitorderservicebinding;credentialType=Ntlm]]></Resolvers>  
<Resolvers serviceId="DynamicTest1"><![CDATA[UDDI3:\\serverUrl=http://localhost/uddi;bindingKey=uddi:esb:orderfileservicebinding;credentialType=Ntlm]]>  
</Resolvers>  
  </ResolverGroups>  
```  
  
 <span data-ttu-id="741c0-108">En este ejemplo, ejecuta la aplicación SubmitPOService Web servicio dos veces porque ambas cadenas de conexión de la resolución se resuelva en la ubicación de este servicio (http://localhost/ESB.CanadianServices/SubmitPOService.asmx).</span><span class="sxs-lookup"><span data-stu-id="741c0-108">In this example, the application executes the SubmitPOService Web service twice because both resolver connection strings resolve to the location of this service (http://localhost/ESB.CanadianServices/SubmitPOService.asmx).</span></span> <span data-ttu-id="741c0-109">El contexto del mensaje especifica la orquestación Broker tal como se define el primer servicio de itinerarios para activar, en el ejemplo de la forma siguiente.</span><span class="sxs-lookup"><span data-stu-id="741c0-109">The message context specifies the Broker orchestration as the first itinerary service to activate, defined in the sample as the following.</span></span>  
  
```csharp  
(Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName == "ScatterGather")  
     && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState ==   
    "Pending") && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType   
    == "Orchestration")  
```  
  
 <span data-ttu-id="741c0-110">La orquestación Broker analiza la configuración de su paso del itinerario y recupera una colección de asociada con el paso del itinerario de resoluciones.</span><span class="sxs-lookup"><span data-stu-id="741c0-110">The Broker orchestration analyzes the settings for its itinerary step and retrieves a collection of resolvers associated with the itinerary step.</span></span> <span data-ttu-id="741c0-111">Para cada una de estas resoluciones, la orquestación utiliza la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] marco resolución y adaptadores para resolver el punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="741c0-111">For each of these resolvers, the orchestration uses the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Framework to resolve the service endpoint.</span></span> <span data-ttu-id="741c0-112">A continuación, la orquestación de Broker activa número n de orquestaciones ServiceDispatcher asincrónicamente (donde n es el número de resoluciones asociada con el servicio ScatterGather en el itinerario) para enviar el mensaje de solicitud con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="741c0-112">The Broker orchestration then activates n number of ServiceDispatcher orchestrations asynchronously (where n is the number of resolvers associated with the ScatterGather service in the itinerary) to dispatch the request message with following parameters:</span></span>  
  
- <span data-ttu-id="741c0-113">**TransportLocation**.</span><span class="sxs-lookup"><span data-stu-id="741c0-113">**TransportLocation**.</span></span> <span data-ttu-id="741c0-114">La resolución rellena este parámetro.</span><span class="sxs-lookup"><span data-stu-id="741c0-114">The resolver populates this parameter.</span></span>  
  
- <span data-ttu-id="741c0-115">**TransportType**.</span><span class="sxs-lookup"><span data-stu-id="741c0-115">**TransportType**.</span></span> <span data-ttu-id="741c0-116">La resolución rellena este parámetro.</span><span class="sxs-lookup"><span data-stu-id="741c0-116">The resolver populates this parameter.</span></span>  
  
- <span data-ttu-id="741c0-117">**ResolverDictionary**.</span><span class="sxs-lookup"><span data-stu-id="741c0-117">**ResolverDictionary**.</span></span> <span data-ttu-id="741c0-118">Este parámetro contiene una colección de hechos de resolución rellenada por la instancia de resolución concreto.</span><span class="sxs-lookup"><span data-stu-id="741c0-118">This parameter contains a collection of resolver facts populated by the concrete resolver instance.</span></span>  
  
- <span data-ttu-id="741c0-119">**InboundMessage**.</span><span class="sxs-lookup"><span data-stu-id="741c0-119">**InboundMessage**.</span></span> <span data-ttu-id="741c0-120">Este parámetro contiene el mensaje original que contiene el itinerario.</span><span class="sxs-lookup"><span data-stu-id="741c0-120">This parameter contains the original message that contains the itinerary.</span></span>  
  
- <span data-ttu-id="741c0-121">**ServiceResponsePort**.</span><span class="sxs-lookup"><span data-stu-id="741c0-121">**ServiceResponsePort**.</span></span> <span data-ttu-id="741c0-122">Este parámetro es el nombre del puerto de autocorrelación respuesta que recibirá las respuestas de las instancias de la orquestación ServiceDispatcher.</span><span class="sxs-lookup"><span data-stu-id="741c0-122">This parameter is the name of the self-correlating response port that will receive responses from the instances of the ServiceDispatcher orchestration.</span></span>  
  
  <span data-ttu-id="741c0-123">Cada instancia de la orquestación ServiceDispatcher usa la directiva ResolveMapScatterGather para resolver los tipos de asignación de Microsoft BizTalk para el mensaje de solicitud y respuesta, en función de **TransportType** y  **TransportLocation** propiedades.</span><span class="sxs-lookup"><span data-stu-id="741c0-123">Each instance of the ServiceDispatcher orchestration uses the ResolveMapScatterGather policy to resolve the Microsoft BizTalk map types for the request and response message, based on **TransportType** and **TransportLocation** properties.</span></span> <span data-ttu-id="741c0-124">Las instancias de orquestación utilizan los mapas resueltos para transformar el mensaje entrante en el mensaje de solicitud para llamar al servicio Web.</span><span class="sxs-lookup"><span data-stu-id="741c0-124">The orchestration instances use the resolved maps to transform the inbound message into the request message for the Web service call.</span></span>  
  
  <span data-ttu-id="741c0-125">El Administrador de adaptador ESB establece el transporte de salida en Propiedades de contexto en el mensaje de solicitud, que reenviará al puerto de petición-respuesta entonces BizTalk denominado ServiceRequestPort.</span><span class="sxs-lookup"><span data-stu-id="741c0-125">The ESB Adapter Manager sets the outbound transport context properties on the request message, which BizTalk then forwards to the solicit-response port named ServiceRequestPort.</span></span>  
  
  <span data-ttu-id="741c0-126">Cuando recibe un mensaje de respuesta de un servicio, la orquestación ServiceDispatcher usa la información del mapa resuelto para transformar el mensaje de respuesta entrante a un formato canónico.</span><span class="sxs-lookup"><span data-stu-id="741c0-126">When it receives a response message from a service, the ServiceDispatcher orchestration uses the resolved map information to transform the inbound response message to a canonical format.</span></span> <span data-ttu-id="741c0-127">A continuación, la respuesta modificada se ajusta dentro de la envoltura ServiceResponse y lo reenvía a la orquestación de agente a través del puerto de autocorrelación.</span><span class="sxs-lookup"><span data-stu-id="741c0-127">It then wraps the modified response within the ServiceResponse envelope and forwards it to the Broker orchestration through the self-correlating port.</span></span> <span data-ttu-id="741c0-128">La orquestación Broker agrega todas las respuestas entrantes y prepara el mensaje de respuesta final mediante GlobalBank.ESB.ScatterGather.Processes.AggregatingPipeline, tal como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="741c0-128">The Broker orchestration aggregates all incoming responses and prepares the final response message using GlobalBank.ESB.ScatterGather.Processes.AggregatingPipeline, as shown in the following code.</span></span>  
  
```csharp  
AggregatedResponse.Body = null;  
AggregatedResponse(*) = InboundMessage(*);  
Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteSendPipeline(  
    typeof(GlobalBank.ESB.ScatterGather.Processes.AggregatingPipeline),  
    messageAggregator,AggregatedResponse);  
```  
  
 <span data-ttu-id="741c0-129">Este código incluye todo el lote de las respuestas dentro de un sobre predefinidos.</span><span class="sxs-lookup"><span data-stu-id="741c0-129">This code wraps the entire batch of responses within a predefined envelope.</span></span> <span data-ttu-id="741c0-130">A continuación, la orquestación Broker hace avanzar el itinerario para el **DynamicTest** paso del itinerario, tal como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="741c0-130">The Broker orchestration then advances the itinerary to the **DynamicTest** itinerary step, as shown in the following code.</span></span>  
  
```csharp  
// Copy the context and advance the itinerary.  
OutboundMessage = AggregatedResponse.Body;  
OutboundMessage(*) = AggregatedResponse(*);  
// Advance the Itinerary to the next step.  
itinerary.Itinerary.Advance(OutboundMessage, itineraryStep);  
```  
  
 <span data-ttu-id="741c0-131">Dado que el atributo de tipo de servicio denominado **DynamicTest** está establecido en **mensajería**, el **ItineraryHelper** clase promociona las propiedades de la resolución en el contexto de la mensaje denominado **OutboundMessage**.</span><span class="sxs-lookup"><span data-stu-id="741c0-131">Because the service type attribute named **DynamicTest** is set to **Messaging**, the **ItineraryHelper** class promotes the resolver properties into the context of the message named **OutboundMessage**.</span></span> <span data-ttu-id="741c0-132">La orquestación de agente envía este mensaje a un puerto de enlace directo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="741c0-132">The Broker orchestration sends this message to a BizTalk direct-bound port.</span></span> <span data-ttu-id="741c0-133">BizTalk, a continuación, reenvía el mensaje al puerto de envío dinámico representado por la **ServiceName** suscripción, que es **DynamicTest**.</span><span class="sxs-lookup"><span data-stu-id="741c0-133">BizTalk then forwards the message to the dynamic send port represented by the **ServiceName** subscription, which is **DynamicTest**.</span></span> <span data-ttu-id="741c0-134">Este puerto de envío serializa la respuesta final agregada a la carpeta \Source\Samples\DynamicResolution\Test\Filedrop\Out.</span><span class="sxs-lookup"><span data-stu-id="741c0-134">This send port serializes the final aggregated response to the \Source\Samples\DynamicResolution\Test\Filedrop\Out folder.</span></span>