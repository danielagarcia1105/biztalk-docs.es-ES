---
title: Cómo funciona el ejemplo de rampa de itinerario | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f4f318c-b955-4a3d-88db-c0d324b63b21
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f282e49b8095059b273bd737d6fb38ff97090f5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966069"
---
# <a name="how-the-itinerary-on-ramp-sample-works"></a><span data-ttu-id="a3501-102">Cómo funciona el ejemplo de rampa de itinerario</span><span class="sxs-lookup"><span data-stu-id="a3501-102">How the Itinerary On-Ramp Sample Works</span></span>
<span data-ttu-id="a3501-103">La aplicación compila un conjunto de encabezados SOAP que contienen el itinerario que cree mediante los controles en la ventana de la aplicación cliente, el cliente de prueba de itinerarios de ejemplo carga el archivo de mensaje especificado desde el disco, anexa los encabezados de itinerarios al mensaje, y envía al ESB a través de un itinerario en rampa para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="a3501-103">The sample Itinerary Test Client application builds a set of SOAP headers that contain the itinerary that you create using the controls in the client application window, loads the specified message file from disk, appends the itinerary headers to the message, and submits it to the ESB through an Itinerary on-ramp for processing.</span></span> <span data-ttu-id="a3501-104">Si el itinerario genera una respuesta, la aplicación recopila la respuesta y lo muestra en la ventana de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a3501-104">If the itinerary generates a response, the application collects the response and displays it in the application window.</span></span>  

 <span data-ttu-id="a3501-105">Puede elegir desde varios archivos de configuración de itinerarios de ejemplo para ver escenarios unidireccionales y bidireccionales que utilicen las orquestaciones, mensajería o una combinación de ambos.</span><span class="sxs-lookup"><span data-stu-id="a3501-105">You can choose from several sample itinerary configuration files to see one-way and two-way scenarios that use orchestrations, messaging, or a combination of both.</span></span>  

 <span data-ttu-id="a3501-106">Para ayudarle a comprender cómo el servicio de itinerarios utiliza la información de itinerarios en un mensaje, el siguiente XML muestra el archivo de configuración de itinerarios de ejemplo denominado TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml usado en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="a3501-106">To help you understand how the Itinerary service uses the itinerary information in a message, the following XML shows the sample itinerary configuration file named TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml used in the earlier example.</span></span> <span data-ttu-id="a3501-107">La primera sección de este itinerario especifica tres pasos de la invocación de servicio.</span><span class="sxs-lookup"><span data-stu-id="a3501-107">The first section of this itinerary specifies three service invocation steps.</span></span>  

```xml  
<Itinerary xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" uuid="" beginTime="" completeTime="" state="Pending" isRequestResponse="false" servicecount="0" xmlns="http://schemas.microsoft.biztalk.practices.esb.com/itinerary">  
  <BizTalkSegment interchangeId="" epmRRCorrelationToken="" receiveInstanceId="" messageId="" xmlns="" />  
  <ServiceInstance name="Microsoft.Practices.ESB.Services.Transform" type="Orchestration" state="Pending" position="0" isRequestResponse="false" xmlns="" />  
  <Services xmlns="">  
    <Service uuid="92d3b293-e6d4-44a1-b27d-c42b48aec667" beginTime="" completeTime="" name="Microsoft.Practices.ESB.Services.Transform" type="Orchestration" state="Pending" isRequestResponse="false" position="0" serviceInstanceId="" />  
  </Services>  
  <Services xmlns="">  
    <Service uuid="774488bc-e5b9-4a4e-9ae7-d25cdf23fd1c" beginTime="" completeTime="" name="Microsoft.Practices.ESB.Services.Routing" type="Orchestration" state="Pending" isRequestResponse="false" position="1" serviceInstanceId="" />  
  </Services>  
  <Services xmlns="">  
    <Service uuid="" beginTime="" completeTime="" name="ProcessAndRespond" type="Orchestration" state="Pending" isRequestResponse="true" position="2" serviceInstanceId="" />  
  </Services>  
  ...  
```  

 <span data-ttu-id="a3501-108">Después de la lista de pasos de la invocación de servicio en el itinerario es la sección que contiene los detalles de las resoluciones (representados por cadenas de conexión) que permiten que el servicio de itinerarios buscar o proporcionar información de resolución para cada servicio definido en el itinerario.</span><span class="sxs-lookup"><span data-stu-id="a3501-108">Following the list of service invocation steps in the itinerary is the section containing details of the resolvers (represented by connection strings) that allow the Itinerary service to locate or provide resolution information for each service defined in the itinerary.</span></span>  

```xml  
  ...  
<ResolverGroups xmlns="">  
    <Resolvers serviceId="Microsoft.Practices.ESB.Services.Transform0"><![CDATA[BRE:\\Policy=ResolveMap;Version=1.0;UseMsg=False;]]></Resolvers>  
    <Resolvers serviceId="Microsoft.Practices.ESB.Services.Routing1"><![CDATA[STATIC:\\TransportType=FILE;TransportLocation=C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\OUt\%MessageID%.xml;Action=;EndpointConfig=;JaxRpcResponse=False;MessageExchangePattern=;TargetNamespace=;TransformType=;]]><![CDATA[UDDI3:\\ServerUrl=http://localhost/uddi;SearchQualifiers=andAllKeys;CategorySearch=;BindingKey=uddi:esb:orderfileservicev3.1;]]></Resolvers>  
    <Resolvers serviceId="ProcessAndRespond2" />  
  </ResolverGroups>  
</Itinerary>  
```  

> [!NOTE]
>  <span data-ttu-id="a3501-109">El contenido real de cada **\<solucionadores\>** elemento no contiene los caracteres de espacio en blanco usados para ajustar las líneas en la lista anterior.</span><span class="sxs-lookup"><span data-stu-id="a3501-109">The actual content of each **\<Resolvers\>** element does not contain the white space characters used to wrap the lines in the preceding listing.</span></span>  

 <span data-ttu-id="a3501-110">Los siguientes son los tres pasos definidos en la configuración anterior itinerario:</span><span class="sxs-lookup"><span data-stu-id="a3501-110">The following are the three steps defined in the itinerary preceding configuration:</span></span>  

1. <span data-ttu-id="a3501-111">Ejecutar la orquestación Microsoft.Practices.ESB.Services.Transform para transformar el mensaje con la directiva ResolverMap mediante el motor de reglas de negocios (BRE) de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a3501-111">Execute the Microsoft.Practices.ESB.Services.Transform orchestration to transform the message with the ResolverMap policy using BizTalk Business Rules Engine (BRE).</span></span>  

2. <span data-ttu-id="a3501-112">Ejecutar la orquestación Microsoft.Practices.ESB.Services.Routing para enrutar el mensaje transformado en varias ubicaciones mediante el enrutamiento Microsoft.Practices.ESB.Services.Routing1.</span><span class="sxs-lookup"><span data-stu-id="a3501-112">Execute the Microsoft.Practices.ESB.Services.Routing orchestration to route the transformed message to multiple locations using the routing Microsoft.Practices.ESB.Services.Routing1.</span></span> <span data-ttu-id="a3501-113">El **\<ResolverGroups\>** sección contiene un **\<solucionadores\>** elemento con este identificador, que define las cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="a3501-113">The **\<ResolverGroups\>** section contains a **\<Resolvers\>** element with this identifier, which defines the connection strings.</span></span>  

3. <span data-ttu-id="a3501-114">Ejecutar la orquestación ProcessAndRespond proporcionada con este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a3501-114">Execute the ProcessAndRespond orchestration provided with this sample.</span></span> <span data-ttu-id="a3501-115">La implementación de esta orquestación envía como respuesta una copia del mensaje de solicitud al cliente de prueba de itinerario.</span><span class="sxs-lookup"><span data-stu-id="a3501-115">The implementation of this orchestration sends as the response a copy of the request message back to the Itinerary Test Client.</span></span>  

   <span data-ttu-id="a3501-116">Con la finalización de cada servicio, el servicio avanza el itinerario y promueve el servicio siguiente que se define en el itinerario sea la actual instancia de servicio con su estado establecido en **pendiente**.</span><span class="sxs-lookup"><span data-stu-id="a3501-116">With the completion of each service, the service advances the itinerary and promotes the next service defined in the itinerary to be the current service instance, with its state set to **Pending**.</span></span>  

> [!NOTE]
>  <span data-ttu-id="a3501-117">El ejemplo de rampa de itinerario utiliza resolución dinámica para enviar mensajes a la carpeta de salida.</span><span class="sxs-lookup"><span data-stu-id="a3501-117">The Itinerary On-Ramp sample uses dynamic resolution to send messages to the output folder.</span></span> <span data-ttu-id="a3501-118">Esto es por qué no estática puerto de envío definido para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a3501-118">This is why there is no static send port defined for this sample.</span></span>  

 <span data-ttu-id="a3501-119">La siguiente es la secuencia de eventos que se producen después de que la aplicación de cliente de prueba envía el mensaje:</span><span class="sxs-lookup"><span data-stu-id="a3501-119">The following is the sequence of events that occur after the test client application submits the message:</span></span>  

- <span data-ttu-id="a3501-120">Puerto de recepción de la OnRamp.Itinerary recibe el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a3501-120">The OnRamp.Itinerary receive port receives the message.</span></span>  

- <span data-ttu-id="a3501-121">La canalización ItineraryReceiveXml extrae el itinerario desde el encabezado SOAP, valida y lo procesa previamente, escribe el itinerario como una propiedad de contexto de mensaje en el mensaje entrante y publica el mensaje en la base de datos de cuadro de mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a3501-121">The ItineraryReceiveXml pipeline extracts the itinerary from the SOAP header, validates and pre-processes it, writes the itinerary as a message context property into the inbound message, and publishes the message to the BizTalk Message Box database.</span></span>  

- <span data-ttu-id="a3501-122">Una suscripción para la orquestación de servicio Microsoft.Practices.ESB.Services.Transform desencadena la invocación de esta orquestación.</span><span class="sxs-lookup"><span data-stu-id="a3501-122">A subscription for the Microsoft.Practices.ESB.Services.Transform service orchestration triggers invocation of this orchestration.</span></span> <span data-ttu-id="a3501-123">La orquestación primero recupera el paso del itinerario actual al pasar el mensaje actual como un parámetro, tal como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a3501-123">The orchestration first retrieves the current itinerary step by passing the current message as a parameter, as shown in the following code.</span></span>  

  ```csharp  
  itineraryStep =   itinerary.Itinerary.GetItineraryStep(InboundMessage);  
  ```  

- <span data-ttu-id="a3501-124">El **ItineraryStep** objeto contiene toda la información sobre la instancia de servicio actual para su ejecución, así como cualquier solucionadores asociadas con él.</span><span class="sxs-lookup"><span data-stu-id="a3501-124">The **ItineraryStep** object contains all the information about the current service instance for execution, as well as any resolvers associated with it.</span></span>  

- <span data-ttu-id="a3501-125">El **resolución** objeto se recupera de la **ItineraryStep** instancia y el marco de trabajo de resolución de ESB se utiliza para resolver el nombre completo de la asignación de transformación, tal como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a3501-125">The **Resolver** object is retrieved from the **ItineraryStep** instance and the ESB Resolver Framework is used to resolve the full name of the transformation map, as shown in the following code.</span></span>  

  ```csharp  
  resolverDictionary =   
     Microsoft.Practices.ESB.Resolver.ResolverMgr.Resolve(InboundMessage,  
                                                          resolver);  

  // Set the transform type.  
  transformType = resolverDictionary.Item("Resolver.TransformType");  
  ```  

- <span data-ttu-id="a3501-126">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] marco resolución y adaptadores lo consigue mediante la carga de la resolución adecuada de la memoria caché (en este ejemplo, la resolución de motor de reglas de negocios de BizTalk), que invoca la directiva ResolverMap y rellena el  **ResolverDictionary** objeto.</span><span class="sxs-lookup"><span data-stu-id="a3501-126">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Framework accomplishes this by loading the appropriate resolver from the cache (in this example, the BizTalk Business Rules Engine resolver), which invokes the ResolverMap policy and populates the **ResolverDictionary** object.</span></span>  

- <span data-ttu-id="a3501-127">Después de la orquestación finalice, el código llama a la **AdvanceItinerary** método, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a3501-127">After the orchestration completes, the code calls the **AdvanceItinerary** method, as shown in the following code.</span></span>  

  ```csharp  
  // Call the Itinerary helper to advance to the next step.  
  itinerary.Itinerary.Advance(OutboundMessage, itineraryStep.ItineraryStep);  
  ```  

- <span data-ttu-id="a3501-128">Esto hace avanzar el itinerario actual mediante la actualización de sus propiedades y promover el siguiente servicio definido en el itinerario al ejecutar a continuación.</span><span class="sxs-lookup"><span data-stu-id="a3501-128">This advances the current itinerary by updating its properties and promoting the next service defined in the itinerary as the one to execute next.</span></span> <span data-ttu-id="a3501-129">El método copia el itinerario en el mensaje saliente, lo que el servicio se publica en la base de datos de cuadro de mensaje a través de un puerto de envío de enlace directo.</span><span class="sxs-lookup"><span data-stu-id="a3501-129">The method copies the itinerary into the outbound message, which the service publishes back into the Message Box database through a direct-bound send port.</span></span>  

- <span data-ttu-id="a3501-130">Una suscripción para la orquestación de servicio Microsoft.Practices.ESB.Services.Delivery desencadena la invocación de esta orquestación.</span><span class="sxs-lookup"><span data-stu-id="a3501-130">A subscription for the Microsoft.Practices.ESB.Services.Delivery service orchestration triggers invocation of this orchestration.</span></span> <span data-ttu-id="a3501-131">Esta orquestación sigue un proceso similar al primero, obtener el paso del itinerario actual.</span><span class="sxs-lookup"><span data-stu-id="a3501-131">This orchestration follows a similar process to the first one, obtaining the current Itinerary step.</span></span> <span data-ttu-id="a3501-132">Sin embargo, esta orquestación recorre en iteración una colección de resoluciones devuelto por la **ItineraryStep** instancia.</span><span class="sxs-lookup"><span data-stu-id="a3501-132">However, this orchestration iterates through a collection of resolvers returned by the **ItineraryStep** instance.</span></span> <span data-ttu-id="a3501-133">Para cada servicio de resolución de la colección, se utiliza la orquestación entrega la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] marco resolución y adaptadores para resolver las ubicaciones de transporte y promoverlas como propiedades de contexto en el mensaje saliente, tal como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a3501-133">For each resolver in the collection, the delivery orchestration uses the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Framework to resolve the transport locations and promote them as context properties within the outgoing message, as shown in the following code.</span></span>  

  ```csharp  
  // Move to retrieve the first resolver.  
  resolver = resolvers.Current;  

  // Pass the resolver configuration to the Resolver Manager   
  // for resolution.  
  resolverDictionary =  
     Microsoft.Practices.ESB.Resolver.ResolverMgr.Resolve(InboundMessage,  
                                                          resolver);  

  // Set the transport properties.  
  transportLocation =   
     resolverDictionary.Item("Resolver.TransportLocation");  
  transportType =   
     resolverDictionary.Item("Resolver.TransportType");  

  // Call the Adapter Manager to set all necessary properties.  
  Microsoft.Practices.ESB.Adapter.AdapterMgr.SetEndpoint(  
                                  resolverDictionary, DeliveryMessage);  

  // Set the delivery port address and type.  
  DeliveryPort(Microsoft.XLANGs.BaseTypes.Address) = transportLocation;  
  DeliveryPort(Microsoft.XLANGs.BaseTypes.TransportType) = transportType;  
  ```  

- <span data-ttu-id="a3501-134">Una suscripción para la orquestación ProcessAndRespond desencadena la invocación de esta orquestación debido a una coincidencia de las propiedades de contexto de mensaje definidos para las propiedades de la expresión de filtro.</span><span class="sxs-lookup"><span data-stu-id="a3501-134">A subscription for the ProcessAndRespond orchestration triggers invocation of this orchestration because of a match of the message context properties defined for the filter expression properties.</span></span>  

  ```  
  (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName == :"ProcessAndRespond")   
  && Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState == "Pending")  
  && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType == "Orchestration")  
  ```  

- <span data-ttu-id="a3501-135">La orquestación ProcessAndRespond hace avanzar el itinerario y envía el mensaje de solicitud original al servicio de vía rápida a la aplicación cliente de prueba de itinerario como la respuesta.</span><span class="sxs-lookup"><span data-stu-id="a3501-135">The ProcessAndRespond orchestration advances the itinerary and sends the original request message back to the on-ramp service to the Itinerary Test Client application as the response.</span></span>
