---
title: Crear un servicio de mensajería itinerarios personalizado | Documentos de Microsoft
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
ms.openlocfilehash: 5f08168e69e26d56cb39fb5c05cc53c3cbb51202
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973738"
---
# <a name="creating-a-custom-itinerary-messaging-service"></a>Crear un servicio de mensajería itinerario personalizado
El marco de trabajo itinerario que forma parte de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] admite la ejecución de pasos itinerarios con las clases que implementan la **IMessagingService** interfaz que se ejecutan los servicios de mensajería itinerarios. Puede implementar un servicio de mensajería personalizado cuando desee que el servicio sea responsable de lo siguiente:  
  
-   Validación personalizada del mensaje configurado en el itinerario  
  
-   Transformación de mensaje personalizado configurado en el itinerario  
  
-   Procesamiento personalizado del mensaje  
  
 En todos estos casos, un servicio de itinerarios personalizado que implementa actúa como un interceptor y es llamado por el componente de canalización de distribuidor.  
  
 Servicios itinerarios basado en mensajería personalizados o servicios de mensajería, implemente todos los **IMessagingService** interfaz. Esta interfaz expone el **nombre** y **SupportsDisassemble** propiedades y la **Execute** y **ShouldAdvanceStep** métodos.  
  
 El **nombre** propiedad es el nombre del servicio tal y como aparecerá en un itinerario. Debe coincidir con el nombre configurado en la configuración de servicios de itinerario en el archivo Esb.config.  
  
 El **SupportsDisassemble** propiedad indica si el servicio de mensajería personalizado que se va a crear es compatible con desensamblar y la ejecución de varias resoluciones.  
  
 El **ShouldAdvanceStep** método toma en el paso de itinerarios actual y el mensaje actual y devuelve un valor booleano que indica si el distribuidor debe adelantar el itinerario cuando se ejecuta el servicio. En casi todos casos, este método debe devolver **true**.  
  
 El **Execute** método es de importancia máxima para un servicio de mensajería y contiene la lógica que se ejecutará en tiempo de ejecución. Que se tarda en el contexto de canalización, el mensaje, la cadena de resolución y el paso actual de itinerarios; y devuelve el mensaje actualizado.  
  
 Una implementación de referencia de la **Execute** método puede encontrarse en el archivo RoutingService.cs de ESB. Proyecto Itinerary.Services, tal como se muestra en el código siguiente.  
  
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
  
 **Para implementar un servicio personalizado de itinerarios para la mensajería de**  
  
1.  Crear un ensamblado con una clase que deriva de **IMessagingService;** en el **Execute** método, incluir toda la lógica necesaria para realizar modificaciones en el mensaje o el contexto del mensaje (si existe).  
  
2.  Agregue una entrada en el **itineraryServices** sección del archivo Esb.config para el servicio mediante la adición de un  **\<itineraryService\>**  elemento con un GUID como el **Id.**  de atributo, el nombre del servicio como el **nombre** de atributo, el nombre completo de la clase como el **tipo** atributo, **mensajería**como el **ámbito** atributo y en la fase permitida (por ejemplo, **OnRampReceive**, **OnRampSend**, **OffRampSend**, **OffRampReceive**, **AllSend**, **AllReceive**, o **todos los**) como el **fase**atributo.  
  
3.  Registrar el nuevo ensamblado en la caché global de ensamblados.