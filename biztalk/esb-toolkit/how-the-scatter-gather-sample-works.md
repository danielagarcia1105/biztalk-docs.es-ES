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
# <a name="how-the-scatter-gather-sample-works"></a>Cómo funciona el ejemplo de dispersión y recopilación
La aplicación de ejemplo compila un conjunto de encabezados SOAP que contiene el itinerario cargado desde el archivo de itinerarios de dispersión y recopilación, carga el archivo de mensaje especificado desde el disco, anexa los encabezados de itinerarios al mensaje y lo envía al ESB a través de una vía rápida para procesamiento. Si el itinerario genera una respuesta, la aplicación recopila esto y lo muestra en la ventana de la aplicación.  
  
 Para ayudarle a comprender cómo el servicio de itinerarios utiliza la información de itinerarios en un mensaje, la lista siguiente muestra el archivo de configuración de itinerarios de ejemplo denominado ScatterGatherItinerary.xml. La primera sección de este itinerario especifica dos pasos de la invocación de servicio.  
  
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
  
 Después de la lista de pasos de la invocación de servicio en el itinerario es la sección que contiene los detalles de las resoluciones y cadenas de conexión que permiten que el servicio de itinerarios buscar cada servicio definido en el itinerario, como se muestra en el siguiente código XML.  
  
```xml  
<ResolverGroups xmlns="">  
 <Resolvers serviceId="ScatterGather0"><![CDATA[BRE:\\policy=ResolveEndPointScatterGather;version=;useMsg=;]]><![CDATA[UDDI3:\\serverUrl=http://localhost/uddi;bindingKey=uddi:esb:purchaseordersubmitorderservicebinding;credentialType=Ntlm]]></Resolvers>  
<Resolvers serviceId="DynamicTest1"><![CDATA[UDDI3:\\serverUrl=http://localhost/uddi;bindingKey=uddi:esb:orderfileservicebinding;credentialType=Ntlm]]>  
</Resolvers>  
  </ResolverGroups>  
```  
  
 En este ejemplo, ejecuta la aplicación SubmitPOService Web servicio dos veces porque ambas cadenas de conexión de la resolución se resuelva en la ubicación de este servicio (http://localhost/ESB.CanadianServices/SubmitPOService.asmx). El contexto del mensaje especifica la orquestación Broker tal como se define el primer servicio de itinerarios para activar, en el ejemplo de la forma siguiente.  
  
```csharp  
(Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName == "ScatterGather")  
     && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState ==   
    "Pending") && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType   
    == "Orchestration")  
```  
  
 La orquestación Broker analiza la configuración de su paso del itinerario y recupera una colección de asociada con el paso del itinerario de resoluciones. Para cada una de estas resoluciones, la orquestación utiliza la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] marco resolución y adaptadores para resolver el punto de conexión de servicio. A continuación, la orquestación de Broker activa número n de orquestaciones ServiceDispatcher asincrónicamente (donde n es el número de resoluciones asociada con el servicio ScatterGather en el itinerario) para enviar el mensaje de solicitud con los siguientes parámetros:  
  
- **TransportLocation**. La resolución rellena este parámetro.  
  
- **TransportType**. La resolución rellena este parámetro.  
  
- **ResolverDictionary**. Este parámetro contiene una colección de hechos de resolución rellenada por la instancia de resolución concreto.  
  
- **InboundMessage**. Este parámetro contiene el mensaje original que contiene el itinerario.  
  
- **ServiceResponsePort**. Este parámetro es el nombre del puerto de autocorrelación respuesta que recibirá las respuestas de las instancias de la orquestación ServiceDispatcher.  
  
  Cada instancia de la orquestación ServiceDispatcher usa la directiva ResolveMapScatterGather para resolver los tipos de asignación de Microsoft BizTalk para el mensaje de solicitud y respuesta, en función de **TransportType** y  **TransportLocation** propiedades. Las instancias de orquestación utilizan los mapas resueltos para transformar el mensaje entrante en el mensaje de solicitud para llamar al servicio Web.  
  
  El Administrador de adaptador ESB establece el transporte de salida en Propiedades de contexto en el mensaje de solicitud, que reenviará al puerto de petición-respuesta entonces BizTalk denominado ServiceRequestPort.  
  
  Cuando recibe un mensaje de respuesta de un servicio, la orquestación ServiceDispatcher usa la información del mapa resuelto para transformar el mensaje de respuesta entrante a un formato canónico. A continuación, la respuesta modificada se ajusta dentro de la envoltura ServiceResponse y lo reenvía a la orquestación de agente a través del puerto de autocorrelación. La orquestación Broker agrega todas las respuestas entrantes y prepara el mensaje de respuesta final mediante GlobalBank.ESB.ScatterGather.Processes.AggregatingPipeline, tal como se muestra en el código siguiente.  
  
```csharp  
AggregatedResponse.Body = null;  
AggregatedResponse(*) = InboundMessage(*);  
Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteSendPipeline(  
    typeof(GlobalBank.ESB.ScatterGather.Processes.AggregatingPipeline),  
    messageAggregator,AggregatedResponse);  
```  
  
 Este código incluye todo el lote de las respuestas dentro de un sobre predefinidos. A continuación, la orquestación Broker hace avanzar el itinerario para el **DynamicTest** paso del itinerario, tal como se muestra en el código siguiente.  
  
```csharp  
// Copy the context and advance the itinerary.  
OutboundMessage = AggregatedResponse.Body;  
OutboundMessage(*) = AggregatedResponse(*);  
// Advance the Itinerary to the next step.  
itinerary.Itinerary.Advance(OutboundMessage, itineraryStep);  
```  
  
 Dado que el atributo de tipo de servicio denominado **DynamicTest** está establecido en **mensajería**, el **ItineraryHelper** clase promociona las propiedades de la resolución en el contexto de la mensaje denominado **OutboundMessage**. La orquestación de agente envía este mensaje a un puerto de enlace directo de BizTalk. BizTalk, a continuación, reenvía el mensaje al puerto de envío dinámico representado por la **ServiceName** suscripción, que es **DynamicTest**. Este puerto de envío serializa la respuesta final agregada a la carpeta \Source\Samples\DynamicResolution\Test\Filedrop\Out.