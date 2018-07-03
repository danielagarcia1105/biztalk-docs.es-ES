---
title: Ejecutar un servicio de itinerarios | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d86d228-da28-494f-85c7-4225b54f9b98
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a85e5c134e9fbbd2d1b6880fdb9e5cd866bc512
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024386"
---
# <a name="executing-an-itinerary-service"></a>Ejecutar un servicio de itinerarios
Un itinerario ESB puede contener cualquier servicio de itinerarios que puede ser implementadas como orquestación o mensajería para realizar las tareas siguientes:  
  
- Puede recibir el mensaje que contiene el itinerario.  
  
- Puede recuperar el paso del itinerario actual.  
  
- Puede procesar el servicio.  
  
- Puede avanzar el itinerario en el mensaje saliente mediante una llamada a la **por adelantado** método.  
  
- Puede publicar el mensaje procesado en la base de datos de cuadro de mensaje de BizTalk de Microsoft.  
  
  Por ejemplo, una orquestación puede recibir un mensaje que contiene un itinerario mediante la implementación de un filtro definido en la forma de recepciones de activación, tal como se muestra en la figura 1 de [mediante una orquestación como un suscriptor de servicio de itinerarios](../esb-toolkit/using-an-orchestration-as-an-itinerary-service-subscriber.md). Sin embargo, la mensajería es ligeramente diferente: el componente de canalización llama a la **GetItineraryStep** método para determinar si existe un itinerario en un mensaje entrante. También examina las propiedades del mensaje para comprobar si debe procesar.  
  
  ![Orquestación](../esb-toolkit/media/ch4-orchestration.jpg "Ch4 orquestación")  
  
  **Figura 1**  
  
  **Expresión de filtro para una orquestación que participará en un itinerario como suscriptor**  
  
  Después de que el servicio obtiene el mensaje, debe llamar a la **GetItineraryStep** método, que devuelve una instancia de la **ItineraryStep** clase. Las listas siguientes muestran cómo puede llamar a los métodos de la API del itinerario desde una orquestación y un componente de canalización personalizado. El código siguiente ejecuta la **GetItineraryStep** método desde una forma de expresión de orquestación.  
  
```  
  
//XLANGs  
// Retrieve the current itinerary step.  
itinerary = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryWrapper();  
step = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryStepWrapper();  
  
itinerary.Itinerary = Microsoft.Practices.ESB.Itinerary.ItineraryOMFactory.Create(InboundMessage);  
step.ItineraryStep = itinerary.Itinerary.GetItineraryStep(InboundMessage);  
```  
  
 El código siguiente muestra cómo ejecutar el método de servicio de mensajería desde un componente de canalización personalizado.  
  
```csharp  
// Execute messaging step.  
public IBaseMessage Execute(IPipelineContext context, IBaseMessage msg, string resolverString, IItineraryStep step)  
{  
    if (null != step  
    && step.ServiceType == "Messaging"  
    && step.ServiceName == "SomeService")  
    {  
        // If the service name matches the required name, process the message here.  
    }  
    else  
    {  
        // Do not process the message.  
        return pInMsg;  
    }  
}  
```  
  
 La instancia de la **IItineraryStep** clase contiene todos los metadatos para el servicio actual, incluidas las propiedades de ambientales del entorno de ejecución de servicio actual. Dos buenos ejemplos de esto son la **ServiceInstanceID** y actual **MessageDirection** las propiedades de un componente de canalización.  
  
 Después de un servicio llama a la **GetItineraryStep** método, puede recuperar asociada ninguna resoluciones. El **ResolverCollection** propiedad de la **ItineraryStep** clase devuelve una colección de las resoluciones que el servicio puede enumerar a través, como se muestra en el ejemplo siguiente.  
  
```csharp  
Microsoft.Practices.ESB.Itinerary.ResolverCollection resolvers;  
resolvers = step.ItineraryStep.ResolverCollection;  
```  
  
 Cada elemento de la **ResolverCollection** representa una cadena de conexión de resolución que coincide con uno de los tipos admitidos por el marco resolución y adaptadores. Por ejemplo, podría ser un elemento de la colección, como la siguiente lista.  
  
```idl  
BRE:\\policy=GetCanadaPurchaseEndPoint;version=;useMsg=;  
UDDI:\\serverUrl=http://localhost/uddi;serviceName=OrderFileServiceWBindings;  
STATIC:\\TransportLocation=http://localhost/ESB.CanadianServices/SubmitPOService.asmx;  
TargetNamespace=http://globalbank.esb.dynamicresolution.com/canadianservices/;  
XPATH:\\TransportType=; TransportLocation=/*[local-name()='OrderDoc' and namespace-  
uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*  
[local-name()='ID' and namespace-  
uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/'];  
TargetNamespace=/*[local-name()='OrderDoc' and namespace-  
uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*  
[local-name()='customerName' and namespace-  
uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/'];  
```  
  
 El Administrador de resolución en el marco de proveedores de adaptador y la resolución puede resolver los puntos de conexión y establecer las propiedades de punto de conexión del mensaje. Para obtener más información acerca de cómo ocurre esto, consulte [enrutamiento y uso de resolución dinámica](../esb-toolkit/using-dynamic-resolution-and-routing.md).  
  
 Después de que el servicio termina de procesar el mensaje, se debe avanzar el itinerario en el mensaje saliente y volver a publicar el mensaje en la base de datos de cuadro de mensaje. El ejemplo siguiente muestra el proceso de una forma de expresión de orquestación.  
  
```xml  
  
//XLANGs  
// Copy the context to the outbound message.  
OutboundMessage = InboundMessage;  
OutboundMessage(*) = InboundMessage(*);  
  
// Call the method of the ItinerarySerializableWrapper to advance to the next step.  
itinerary.Itinerary.Advance(OutboundMessage, step.ItineraryStep);  
```  
  
 El ejemplo siguiente muestra cómo indicar que [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] motor principal debe adelantar el itinerario para un componente de canalización personalizado.  
  
```csharp  
// Advance Itinerary  
// <summary>  
// Signals that the step should be advanced immediately following execution of the service.  
// </summary>  
// <param name="step">Current step</param>  
// <param name="msg">Current message</param>  
// <returns>True to advance the itinerary.</returns>  
public bool ShouldAdvanceStep(IItineraryStep step, IBaseMessage msg)  
{  
    return true;  
}  
```