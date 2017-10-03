---
title: "Cómo funciona el ejemplo de dispersión y recopilación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ccfacb7-4fd2-4a1a-bece-27eedd86bbe9
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1221c038fa2e59636092c5cb49c6cbc40053708
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-the-scatter-gather-sample-works"></a>Cómo funciona el ejemplo de dispersión y recopilación
La aplicación de ejemplo crea un conjunto de encabezados SOAP que contiene el itinerario cargado desde el archivo itinerario de dispersión y recopilación, carga el archivo de mensaje especificado desde el disco, anexa los encabezados itinerarios para el mensaje y lo envía al ESB a través de en rampa para procesamiento. Si el itinerario genera una respuesta, la aplicación recopila esto y lo muestra en la ventana de la aplicación.  
  
 Para ayudarle a comprender cómo el servicio de itinerario utiliza la información de itinerario en un mensaje, la siguiente lista muestra el archivo de configuración itinerarios de ejemplo denominado ScatterGatherItinerary.xml. La primera sección de este itinerario especifica dos pasos de invocación de servicio.  
  
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
  
 Después de la lista de pasos de la invocación de servicio en el itinerario es la sección que contiene los detalles de las resoluciones y cadenas de conexión que permite que el servicio de itinerario buscar cada servicio definido en el itinerario, tal y como se muestra en el siguiente código XML.  
  
```xml  
<ResolverGroups xmlns="">  
 <Resolvers serviceId="ScatterGather0"><![CDATA[BRE:\\policy=ResolveEndPointScatterGather;version=;useMsg=;]]><![CDATA[UDDI3:\\serverUrl=http://localhost/uddi;bindingKey=uddi:esb:purchaseordersubmitorderservicebinding;credentialType=Ntlm]]></Resolvers>  
<Resolvers serviceId="DynamicTest1"><![CDATA[UDDI3:\\serverUrl=http://localhost/uddi;bindingKey=uddi:esb:orderfileservicebinding;credentialType=Ntlm]]>  
</Resolvers>  
  </ResolverGroups>  
```  
  
 En este ejemplo, ejecuta la aplicación SubmitPOService Web servicio dos veces porque ambas cadenas de conexión de resolución resolver en la ubicación de este servicio (http://localhost/ESB.CanadianServices/SubmitPOService.asmx). El contexto del mensaje especifica la orquestación Broker tal como se define el primer servicio itinerario para activar, en el ejemplo de la forma siguiente.  
  
```csharp  
(Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName == "ScatterGather")  
     && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState ==   
    "Pending") && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType   
    == "Orchestration")  
```  
  
 La orquestación de Broker analiza la configuración de su paso itinerario y recupera una colección de resoluciones asociado con el paso de itinerarios. Para cada uno de estos solucionadores, la orquestación utiliza la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] resolución y marco de trabajo para resolver el extremo de servicio. La orquestación de agente, a continuación, activa n número de orquestaciones ServiceDispatcher de forma asincrónica (donde n es el número de resoluciones asociado al servicio ScatterGather en el itinerario) para enviar el mensaje de solicitud con los siguientes parámetros:  
  
-   **TransportLocation**. La resolución rellena este parámetro.  
  
-   **TransportType**. La resolución rellena este parámetro.  
  
-   **ResolverDictionary**. Este parámetro contiene una colección de hechos de resolución rellenado con la instancia de la resolución concretos.  
  
-   **InboundMessage**. Este parámetro contiene el mensaje original que contiene el itinerario.  
  
-   **ServiceResponsePort**. Este parámetro es el nombre del puerto de respuesta autocorrelación que va a recibir las respuestas de las instancias de la orquestación ServiceDispatcher.  
  
 Cada instancia de la orquestación ServiceDispatcher usa la directiva ResolveMapScatterGather para resolver los tipos de asignación de Microsoft BizTalk para el mensaje de solicitud y respuesta, en función de **TransportType** y  **TransportLocation** propiedades. Las instancias de orquestación utilizan los mapas resueltos para transformar el mensaje entrante en el mensaje de solicitud para llamar al servicio Web.  
  
 El Administrador de adaptador de ESB establece propiedades de contexto del transporte de salida en el mensaje de solicitud, que BizTalk, a continuación, reenvía al puerto de petición-respuesta denominado ServiceRequestPort.  
  
 Cuando recibe un mensaje de respuesta de un servicio, la orquestación ServiceDispatcher usa la información del mapa resuelto para transformar el mensaje de respuesta entrante a un formato canónico. A continuación, ajusta la respuesta modificada dentro sobre ServiceResponse y lo reenvía a la orquestación de agente a través del puerto de autocorrelación. La orquestación de Broker agrega todas las respuestas entrantes y prepara el mensaje de respuesta final mediante GlobalBank.ESB.ScatterGather.Processes.AggregatingPipeline, tal como se muestra en el código siguiente.  
  
```csharp  
AggregatedResponse.Body = null;  
AggregatedResponse(*) = InboundMessage(*);  
Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteSendPipeline(  
    typeof(GlobalBank.ESB.ScatterGather.Processes.AggregatingPipeline),  
    messageAggregator,AggregatedResponse);  
```  
  
 Este código ajusta todo el lote de las respuestas dentro de un sobre predefinidos. La orquestación de agente, a continuación, hace avanzar el itinerario para el **DynamicTest** paso itinerario, tal como se muestra en el código siguiente.  
  
```csharp  
// Copy the context and advance the itinerary.  
OutboundMessage = AggregatedResponse.Body;  
OutboundMessage(*) = AggregatedResponse(*);  
// Advance the Itinerary to the next step.  
itinerary.Itinerary.Advance(OutboundMessage, itineraryStep);  
```  
  
 Dado que el atributo de tipo de servicio denominado **DynamicTest** está establecido en **mensajería**, el **ItineraryHelper** clase promociona las propiedades de la resolución en el contexto de la mensaje con el nombre **OutboundMessage**. La orquestación de agente envía este mensaje a un puerto de enlace directo de BizTalk. BizTalk, a continuación, reenvía el mensaje al puerto de envío dinámico representado por la **ServiceName** suscripción, que es **DynamicTest**. Este puerto de envío, serializa la respuesta final agregada a la carpeta \Source\Samples\DynamicResolution\Test\Filedrop\Out.