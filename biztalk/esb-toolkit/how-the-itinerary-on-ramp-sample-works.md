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
# <a name="how-the-itinerary-on-ramp-sample-works"></a>Cómo funciona el ejemplo de rampa de itinerario
La aplicación compila un conjunto de encabezados SOAP que contienen el itinerario que cree mediante los controles en la ventana de la aplicación cliente, el cliente de prueba de itinerarios de ejemplo carga el archivo de mensaje especificado desde el disco, anexa los encabezados de itinerarios al mensaje, y envía al ESB a través de un itinerario en rampa para su procesamiento. Si el itinerario genera una respuesta, la aplicación recopila la respuesta y lo muestra en la ventana de la aplicación.  

 Puede elegir desde varios archivos de configuración de itinerarios de ejemplo para ver escenarios unidireccionales y bidireccionales que utilicen las orquestaciones, mensajería o una combinación de ambos.  

 Para ayudarle a comprender cómo el servicio de itinerarios utiliza la información de itinerarios en un mensaje, el siguiente XML muestra el archivo de configuración de itinerarios de ejemplo denominado TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml usado en el ejemplo anterior. La primera sección de este itinerario especifica tres pasos de la invocación de servicio.  

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

 Después de la lista de pasos de la invocación de servicio en el itinerario es la sección que contiene los detalles de las resoluciones (representados por cadenas de conexión) que permiten que el servicio de itinerarios buscar o proporcionar información de resolución para cada servicio definido en el itinerario.  

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
>  El contenido real de cada **\<solucionadores\>** elemento no contiene los caracteres de espacio en blanco usados para ajustar las líneas en la lista anterior.  

 Los siguientes son los tres pasos definidos en la configuración anterior itinerario:  

1. Ejecutar la orquestación Microsoft.Practices.ESB.Services.Transform para transformar el mensaje con la directiva ResolverMap mediante el motor de reglas de negocios (BRE) de BizTalk.  

2. Ejecutar la orquestación Microsoft.Practices.ESB.Services.Routing para enrutar el mensaje transformado en varias ubicaciones mediante el enrutamiento Microsoft.Practices.ESB.Services.Routing1. El **\<ResolverGroups\>** sección contiene un **\<solucionadores\>** elemento con este identificador, que define las cadenas de conexión.  

3. Ejecutar la orquestación ProcessAndRespond proporcionada con este ejemplo. La implementación de esta orquestación envía como respuesta una copia del mensaje de solicitud al cliente de prueba de itinerario.  

   Con la finalización de cada servicio, el servicio avanza el itinerario y promueve el servicio siguiente que se define en el itinerario sea la actual instancia de servicio con su estado establecido en **pendiente**.  

> [!NOTE]
>  El ejemplo de rampa de itinerario utiliza resolución dinámica para enviar mensajes a la carpeta de salida. Esto es por qué no estática puerto de envío definido para este ejemplo.  

 La siguiente es la secuencia de eventos que se producen después de que la aplicación de cliente de prueba envía el mensaje:  

- Puerto de recepción de la OnRamp.Itinerary recibe el mensaje.  

- La canalización ItineraryReceiveXml extrae el itinerario desde el encabezado SOAP, valida y lo procesa previamente, escribe el itinerario como una propiedad de contexto de mensaje en el mensaje entrante y publica el mensaje en la base de datos de cuadro de mensaje de BizTalk.  

- Una suscripción para la orquestación de servicio Microsoft.Practices.ESB.Services.Transform desencadena la invocación de esta orquestación. La orquestación primero recupera el paso del itinerario actual al pasar el mensaje actual como un parámetro, tal como se muestra en el código siguiente.  

  ```csharp  
  itineraryStep =   itinerary.Itinerary.GetItineraryStep(InboundMessage);  
  ```  

- El **ItineraryStep** objeto contiene toda la información sobre la instancia de servicio actual para su ejecución, así como cualquier solucionadores asociadas con él.  

- El **resolución** objeto se recupera de la **ItineraryStep** instancia y el marco de trabajo de resolución de ESB se utiliza para resolver el nombre completo de la asignación de transformación, tal como se muestra en el código siguiente.  

  ```csharp  
  resolverDictionary =   
     Microsoft.Practices.ESB.Resolver.ResolverMgr.Resolve(InboundMessage,  
                                                          resolver);  

  // Set the transform type.  
  transformType = resolverDictionary.Item("Resolver.TransformType");  
  ```  

- El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] marco resolución y adaptadores lo consigue mediante la carga de la resolución adecuada de la memoria caché (en este ejemplo, la resolución de motor de reglas de negocios de BizTalk), que invoca la directiva ResolverMap y rellena el  **ResolverDictionary** objeto.  

- Después de la orquestación finalice, el código llama a la **AdvanceItinerary** método, como se muestra en el código siguiente.  

  ```csharp  
  // Call the Itinerary helper to advance to the next step.  
  itinerary.Itinerary.Advance(OutboundMessage, itineraryStep.ItineraryStep);  
  ```  

- Esto hace avanzar el itinerario actual mediante la actualización de sus propiedades y promover el siguiente servicio definido en el itinerario al ejecutar a continuación. El método copia el itinerario en el mensaje saliente, lo que el servicio se publica en la base de datos de cuadro de mensaje a través de un puerto de envío de enlace directo.  

- Una suscripción para la orquestación de servicio Microsoft.Practices.ESB.Services.Delivery desencadena la invocación de esta orquestación. Esta orquestación sigue un proceso similar al primero, obtener el paso del itinerario actual. Sin embargo, esta orquestación recorre en iteración una colección de resoluciones devuelto por la **ItineraryStep** instancia. Para cada servicio de resolución de la colección, se utiliza la orquestación entrega la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] marco resolución y adaptadores para resolver las ubicaciones de transporte y promoverlas como propiedades de contexto en el mensaje saliente, tal como se muestra en el código siguiente.  

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

- Una suscripción para la orquestación ProcessAndRespond desencadena la invocación de esta orquestación debido a una coincidencia de las propiedades de contexto de mensaje definidos para las propiedades de la expresión de filtro.  

  ```  
  (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName == :"ProcessAndRespond")   
  && Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState == "Pending")  
  && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType == "Orchestration")  
  ```  

- La orquestación ProcessAndRespond hace avanzar el itinerario y envía el mensaje de solicitud original al servicio de vía rápida a la aplicación cliente de prueba de itinerario como la respuesta.
