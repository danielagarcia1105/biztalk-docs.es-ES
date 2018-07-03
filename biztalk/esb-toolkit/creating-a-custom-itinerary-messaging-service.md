---
title: Creación de un servicio de mensajería de itinerarios personalizado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2de44c21-68ca-4cf1-a117-bcb35af1b4a9
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecb6c6976493e05c9df747de4a358df7fff7809f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983925"
---
# <a name="creating-a-custom-itinerary-messaging-service"></a><span data-ttu-id="b866b-102">Creación de un servicio de mensajería de itinerarios personalizado</span><span class="sxs-lookup"><span data-stu-id="b866b-102">Creating a Custom Itinerary Messaging Service</span></span>
<span data-ttu-id="b866b-103">El marco de itinerarios que forma parte de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] admite la ejecución de pasos de itinerarios mediante las clases que implementan la **IMessagingService** interfaz que se ejecutan los servicios de mensajería de itinerarios.</span><span class="sxs-lookup"><span data-stu-id="b866b-103">The itinerary framework that is part of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports execution of itinerary steps using classes implementing the **IMessagingService** interface that execute itinerary messaging services.</span></span> <span data-ttu-id="b866b-104">Puede implementar un servicio de mensajería personalizado cuando desee que el servicio sea responsable de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b866b-104">You can implement a custom messaging service when you want the service to be responsible for the following:</span></span>  
  
- <span data-ttu-id="b866b-105">Validación de mensaje personalizado configurada en el itinerario</span><span class="sxs-lookup"><span data-stu-id="b866b-105">Custom message validation configured in the itinerary</span></span>  
  
- <span data-ttu-id="b866b-106">Transformación de mensaje personalizado configurado en el itinerario</span><span class="sxs-lookup"><span data-stu-id="b866b-106">Custom message transformation configured in the itinerary</span></span>  
  
- <span data-ttu-id="b866b-107">Procesamiento del mensaje personalizado</span><span class="sxs-lookup"><span data-stu-id="b866b-107">Custom processing of the message</span></span>  
  
  <span data-ttu-id="b866b-108">En todos estos casos, un servicio de itinerarios personalizado que implementa actúa como un interceptor y se llama mediante el componente de canalización del distribuidor.</span><span class="sxs-lookup"><span data-stu-id="b866b-108">In all these cases, a custom itinerary service that you implement acts as an interceptor and is called by the Dispatcher pipeline component.</span></span>  
  
  <span data-ttu-id="b866b-109">Servicios personalizados de itinerarios basada en mensajería o servicios de mensajería, implemente todos los **IMessagingService** interfaz.</span><span class="sxs-lookup"><span data-stu-id="b866b-109">Custom messaging-based itinerary services, or messaging services, all implement the **IMessagingService** interface.</span></span> <span data-ttu-id="b866b-110">Esta interfaz expone el **nombre** y **SupportsDisassemble** propiedades y el **Execute** y **ShouldAdvanceStep** métodos.</span><span class="sxs-lookup"><span data-stu-id="b866b-110">This interface exposes the **Name** and **SupportsDisassemble** properties and the **Execute** and **ShouldAdvanceStep** methods.</span></span>  
  
  <span data-ttu-id="b866b-111">El **nombre** propiedad es el nombre del servicio tal y como aparecerá en un itinerario.</span><span class="sxs-lookup"><span data-stu-id="b866b-111">The **Name** property is the name of the service as it will appear in an itinerary.</span></span> <span data-ttu-id="b866b-112">Debe coincidir con el nombre configurado en la configuración de servicios de itinerario en el archivo Esb.config.</span><span class="sxs-lookup"><span data-stu-id="b866b-112">It must match the configured name in the itinerary services configuration in the Esb.config file.</span></span>  
  
  <span data-ttu-id="b866b-113">El **SupportsDisassemble** propiedad indica si el servicio de mensajería personalizado que está creando admite desensamblar y la ejecución de varias resoluciones.</span><span class="sxs-lookup"><span data-stu-id="b866b-113">The **SupportsDisassemble** property indicates whether the custom messaging service you are creating supports disassemble and the execution of multiple resolvers.</span></span>  
  
  <span data-ttu-id="b866b-114">El **ShouldAdvanceStep** método toma el paso del itinerario actual y el mensaje actual y devuelve un valor booleano que indica si el distribuidor debe adelantar el itinerario después de que el servicio se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="b866b-114">The **ShouldAdvanceStep** method takes in the current itinerary step, and the current message, and returns a Boolean value that indicates whether the dispatcher should advance the itinerary after the service executes.</span></span> <span data-ttu-id="b866b-115">En casi todos los casos, este método debe devolver **true**.</span><span class="sxs-lookup"><span data-stu-id="b866b-115">In almost all cases, this method should return **true**.</span></span>  
  
  <span data-ttu-id="b866b-116">El **Execute** método es de máxima importancia para un servicio de mensajería y contiene la lógica que se ejecutará en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b866b-116">The **Execute** method is of greatest importance for a messaging service and contains the logic that will be executed at run time.</span></span> <span data-ttu-id="b866b-117">Que se tarda en el contexto de canalización, el mensaje, la cadena de resolución y el paso del itinerario actual; y devuelve el mensaje actualizado.</span><span class="sxs-lookup"><span data-stu-id="b866b-117">It takes in the pipeline context, the message, the resolver string, and the current itinerary step; and it returns the updated message.</span></span>  
  
  <span data-ttu-id="b866b-118">Una implementación de referencia de la **Execute** método puede encontrarse en el archivo RoutingService.cs del ESB. Proyecto Itinerary.Services, tal como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="b866b-118">A reference implementation of the **Execute** method can be found in the RoutingService.cs file of the ESB.Itinerary.Services project, as shown in the following code.</span></span>  
  
```csharp  
public IBaseMessage ExecuteRoute(IPipelineContext context, IBaseMessage msg, string resolverString)  
        {  
            if (context == null)  
                throw new ArgumentNullException("context");  
            if (msg == null)  
                throw new ArgumentNullException("msg");  
            if (string.IsNullOrEmpty(resolverString))  
                throw new ArgumentException(Properties.Resources.ArgumentStringRequired, "resolverString");  
            try  
            {  
                ResolverInfo info = ResolverMgr.GetResolverInfo(ResolutionType.Endpoint, resolverString);  
                if (!info.Success)  
                    throw new RoutingException(Properties.Resources.ResolverStringInvalid, resolverString);  
  
                // Resolve configuration for routing.  
                Dictionary<string, string> resolverDictionary = ResolverMgr.Resolve(info, msg, context);  
  
                if (string.IsNullOrEmpty(resolverDictionary["Resolver.TransportLocation"]))  
                    throw new RoutingException(Properties.Resources.TransportLocationNotResolved, resolverString);  
  
                AdapterMgr.SetEndpoint(resolverDictionary, msg.Context);  
  
                return msg;  
            }  
            catch (System.Exception ex)  
            {  
                EventLogger.Write(MethodInfo.GetCurrentMethod(), ex);  
                throw;  
            }        
        }  
```  
  
 <span data-ttu-id="b866b-119">**Para implementar un servicio de itinerarios personalizado para la mensajería**</span><span class="sxs-lookup"><span data-stu-id="b866b-119">**To implement a custom itinerary service for messaging**</span></span>  
  
1.  <span data-ttu-id="b866b-120">Crear un ensamblado con una clase que derive de **IMessagingService;** en el **Execute** método, incluir toda la lógica necesaria para realizar modificaciones en el mensaje o en el contexto del mensaje (si existe).</span><span class="sxs-lookup"><span data-stu-id="b866b-120">Create an assembly with a class that derives from **IMessagingService;** in the **Execute** method, include all logic necessary to make modifications to the message or the message context (if any).</span></span>  
  
2.  <span data-ttu-id="b866b-121">Agregue una entrada en el **itineraryServices** sección del archivo Esb.config para el servicio agregando una **\<itineraryService\>** elemento con un GUID como el **Id.**  atributo, el nombre del servicio como el **nombre** atributo, el nombre completo de la clase como el **tipo** atributo, **mensajería**como el **ámbito** atributo y la fase permitida (por ejemplo, **OnRampReceive**, **OnRampSend**, **OffRampSend**, **OffRampReceive**, **AllSend**, **AllReceive**, o **todas**) como el **fase**atributo.</span><span class="sxs-lookup"><span data-stu-id="b866b-121">Add an entry in the **itineraryServices** section of the Esb.config file for your service by adding an **\<itineraryService\>** element with a GUID as the **id** attribute, the name of the service as the **name** attribute, the fully qualified name of the class as the **type** attribute, **Messaging** as the **scope** attribute, and the allowed stage (for example, **OnRampReceive**, **OnRampSend**, **OffRampSend**, **OffRampReceive**, **AllSend**, **AllReceive**, or **All**) as the **stage** attribute.</span></span>  
  
3.  <span data-ttu-id="b866b-122">Registre el nuevo ensamblado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="b866b-122">Register the new assembly in the global assembly cache.</span></span>