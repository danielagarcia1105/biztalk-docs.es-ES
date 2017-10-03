---
title: Ejecutar un servicio itinerario | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d86d228-da28-494f-85c7-4225b54f9b98
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4a4dc5c201b26ec33ee5666bc0dbeec8f54ccfc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="executing-an-itinerary-service"></a><span data-ttu-id="d5bf1-102">Ejecutar un servicio itinerario</span><span class="sxs-lookup"><span data-stu-id="d5bf1-102">Executing an Itinerary Service</span></span>
<span data-ttu-id="d5bf1-103">Un itinerario ESB puede contener cualquier servicio itinerario que se puede implementar como orquestación o mensajería para realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d5bf1-103">An ESB itinerary can contain any itinerary service that may be implemented as orchestration or messaging to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="d5bf1-104">Puede recibir el mensaje que contiene el itinerario.</span><span class="sxs-lookup"><span data-stu-id="d5bf1-104">It can receive the message containing the itinerary.</span></span>  
  
-   <span data-ttu-id="d5bf1-105">Puede recuperar el paso actual de itinerarios.</span><span class="sxs-lookup"><span data-stu-id="d5bf1-105">It can retrieve the current itinerary step.</span></span>  
  
-   <span data-ttu-id="d5bf1-106">Puede procesar el servicio.</span><span class="sxs-lookup"><span data-stu-id="d5bf1-106">It can process the service.</span></span>  
  
-   <span data-ttu-id="d5bf1-107">Puede avanzar el itinerario en el mensaje saliente mediante una llamada a la **por adelantado** método.</span><span class="sxs-lookup"><span data-stu-id="d5bf1-107">It can advance the itinerary on the outgoing message by calling the **Advance** method.</span></span>  
  
-   <span data-ttu-id="d5bf1-108">Puede publicar el mensaje procesado en la base de datos de cuadro de mensaje de BizTalk de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d5bf1-108">It can publish the processed message back into the Microsoft BizTalk Message Box database.</span></span>  
  
 <span data-ttu-id="d5bf1-109">Por ejemplo, una orquestación puede recibir un mensaje que contiene un itinerario implementando un filtro definido en la forma recepción activada, como se muestra en la figura 1 de [mediante una orquestación como un suscriptor de servicio de itinerario](../esb-toolkit/using-an-orchestration-as-an-itinerary-service-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="d5bf1-109">For example, an orchestration can receive a message that contains an itinerary by implementing a filter defined on the activated receive shape, as shown in Figure 1 of [Using an Orchestration as an Itinerary Service Subscriber](../esb-toolkit/using-an-orchestration-as-an-itinerary-service-subscriber.md).</span></span> <span data-ttu-id="d5bf1-110">Sin embargo, la mensajería es ligeramente diferente: el componente de canalización llama el **GetItineraryStep** método para determinar si existe un itinerario en un mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="d5bf1-110">However, messaging is slightly different: the pipeline component calls the **GetItineraryStep** method to determine whether an itinerary exists in an incoming message.</span></span> <span data-ttu-id="d5bf1-111">También examina las propiedades del mensaje para comprobar si debe procesar.</span><span class="sxs-lookup"><span data-stu-id="d5bf1-111">It also examines the message properties to check whether it should process it.</span></span>  
  
 <span data-ttu-id="d5bf1-112">![Orquestación](../esb-toolkit/media/ch4-orchestration.jpg "Ch4-Orchestration")</span><span class="sxs-lookup"><span data-stu-id="d5bf1-112">![Orchestration](../esb-toolkit/media/ch4-orchestration.jpg "Ch4-Orchestration")</span></span>  
  
 <span data-ttu-id="d5bf1-113">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="d5bf1-113">**Figure 1**</span></span>  
  
 <span data-ttu-id="d5bf1-114">**Expresión de filtro de ejemplo para una orquestación que vaya a participar en un itinerario como suscriptor**</span><span class="sxs-lookup"><span data-stu-id="d5bf1-114">**Example filter expression for an orchestration that will participate in an itinerary as a subscriber**</span></span>  
  
 <span data-ttu-id="d5bf1-115">Después de que el servicio obtiene el mensaje, debe llamar a la **GetItineraryStep** método, que devuelve una instancia de la **ItineraryStep** clase.</span><span class="sxs-lookup"><span data-stu-id="d5bf1-115">After the service obtains the message, it must call the **GetItineraryStep** method, which returns an instance of the **ItineraryStep** class.</span></span> <span data-ttu-id="d5bf1-116">Listados siguientes muestra cómo puede llamar a los métodos de la API de itinerario desde una orquestación y un componente de canalización personalizado.</span><span class="sxs-lookup"><span data-stu-id="d5bf1-116">The following listings demonstrate how you can call the methods of the itinerary API from both an orchestration and a custom pipeline component.</span></span> <span data-ttu-id="d5bf1-117">El código siguiente ejecuta la **GetItineraryStep** método desde una forma de expresión de orquestación.</span><span class="sxs-lookup"><span data-stu-id="d5bf1-117">The following code executes the **GetItineraryStep** method from an orchestration Expression shape.</span></span>  
  
```  
  
//XLANGs  
// Retrieve the current itinerary step.  
itinerary = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryWrapper();  
step = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryStepWrapper();  
  
itinerary.Itinerary = Microsoft.Practices.ESB.Itinerary.ItineraryOMFactory.Create(InboundMessage);  
step.ItineraryStep = itinerary.Itinerary.GetItineraryStep(InboundMessage);  
```  
  
 <span data-ttu-id="d5bf1-118">El código siguiente muestra cómo ejecutar el método de servicio de mensajería de un componente de canalización personalizado.</span><span class="sxs-lookup"><span data-stu-id="d5bf1-118">The following code shows how to execute the messaging service method from a custom pipeline component.</span></span>  
  
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
  
 <span data-ttu-id="d5bf1-119">La instancia de la **IItineraryStep** clase contiene todos los metadatos para el servicio actual, incluidas las propiedades de ambiente del entorno de ejecución de servicio actual.</span><span class="sxs-lookup"><span data-stu-id="d5bf1-119">The instance of the **IItineraryStep** class contains all the metadata for the current service, including ambient properties of the current service execution environment.</span></span> <span data-ttu-id="d5bf1-120">Dos buenos ejemplos de esto son la **ServiceInstanceID** y actual **MessageDirection** propiedades de un componente de canalización.</span><span class="sxs-lookup"><span data-stu-id="d5bf1-120">Two good examples of this are the **ServiceInstanceID** and the current **MessageDirection** properties for a pipeline component.</span></span>  
  
 <span data-ttu-id="d5bf1-121">Después llama a un servicio el **GetItineraryStep** método, puede recuperar asociada ninguna resoluciones.</span><span class="sxs-lookup"><span data-stu-id="d5bf1-121">After a service calls the **GetItineraryStep** method, it can retrieve any associated resolvers.</span></span> <span data-ttu-id="d5bf1-122">El **ResolverCollection** propiedad de la **ItineraryStep** clase devuelve una colección de resoluciones que el servicio puede enumerar mediante, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d5bf1-122">The **ResolverCollection** property of the **ItineraryStep** class returns a collection of resolvers that the service can enumerate through, as shown in the following example.</span></span>  
  
```csharp  
Microsoft.Practices.ESB.Itinerary.ResolverCollection resolvers;  
resolvers = step.ItineraryStep.ResolverCollection;  
```  
  
 <span data-ttu-id="d5bf1-123">Cada elemento de la **ResolverCollection** representa una cadena de conexión de resolución que coincide con uno de los tipos compatibles con la resolución y el marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d5bf1-123">Each item in the **ResolverCollection** represents a resolver connection string that matches one of the types supported by the Resolver and Adapter Framework.</span></span> <span data-ttu-id="d5bf1-124">Por ejemplo, un elemento de la colección podría verse como la siguiente lista.</span><span class="sxs-lookup"><span data-stu-id="d5bf1-124">For example, an item in the collection could look like the following listing.</span></span>  
  
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
  
 <span data-ttu-id="d5bf1-125">El Administrador de resolución en la resolución y el marco de proveedores de adaptador puede resolver los puntos de conexión y establecer las propiedades de punto de conexión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="d5bf1-125">The resolver manager in the Resolver and Adapter Provider Framework can resolve the endpoints and set the endpoint properties of the message.</span></span> <span data-ttu-id="d5bf1-126">Para obtener más información acerca de cómo se produce esto, consulte [utilizando resolución dinámica y enrutamiento](../esb-toolkit/using-dynamic-resolution-and-routing.md).</span><span class="sxs-lookup"><span data-stu-id="d5bf1-126">For more information about how this occurs, see [Using Dynamic Resolution and Routing](../esb-toolkit/using-dynamic-resolution-and-routing.md).</span></span>  
  
 <span data-ttu-id="d5bf1-127">Después de que el servicio termina de procesar el mensaje, se debe avanzar el itinerario en el mensaje saliente y volver a publicar el mensaje en la base de datos de cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="d5bf1-127">After the service finishes processing the message, it must advance the itinerary on the outgoing message and publish the message back to the Message Box database.</span></span> <span data-ttu-id="d5bf1-128">En el ejemplo siguiente se muestra el proceso de una forma de expresión de orquestación.</span><span class="sxs-lookup"><span data-stu-id="d5bf1-128">The following example shows the process for an orchestration Expression shape.</span></span>  
  
```xml  
  
//XLANGs  
// Copy the context to the outbound message.  
OutboundMessage = InboundMessage;  
OutboundMessage(*) = InboundMessage(*);  
  
// Call the method of the ItinerarySerializableWrapper to advance to the next step.  
itinerary.Itinerary.Advance(OutboundMessage, step.ItineraryStep);  
```  
  
 <span data-ttu-id="d5bf1-129">En el ejemplo siguiente se muestra cómo indicar que [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] motor principal debe adelantar el itinerario para un componente de canalización personalizado.</span><span class="sxs-lookup"><span data-stu-id="d5bf1-129">The following example shows how to indicate that [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core engine should advance itinerary for a custom pipeline component.</span></span>  
  
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