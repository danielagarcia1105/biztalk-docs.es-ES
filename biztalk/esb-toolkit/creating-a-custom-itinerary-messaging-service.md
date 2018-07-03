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
# <a name="creating-a-custom-itinerary-messaging-service"></a>Creación de un servicio de mensajería de itinerarios personalizado
El marco de itinerarios que forma parte de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] admite la ejecución de pasos de itinerarios mediante las clases que implementan la **IMessagingService** interfaz que se ejecutan los servicios de mensajería de itinerarios. Puede implementar un servicio de mensajería personalizado cuando desee que el servicio sea responsable de lo siguiente:  
  
- Validación de mensaje personalizado configurada en el itinerario  
  
- Transformación de mensaje personalizado configurado en el itinerario  
  
- Procesamiento del mensaje personalizado  
  
  En todos estos casos, un servicio de itinerarios personalizado que implementa actúa como un interceptor y se llama mediante el componente de canalización del distribuidor.  
  
  Servicios personalizados de itinerarios basada en mensajería o servicios de mensajería, implemente todos los **IMessagingService** interfaz. Esta interfaz expone el **nombre** y **SupportsDisassemble** propiedades y el **Execute** y **ShouldAdvanceStep** métodos.  
  
  El **nombre** propiedad es el nombre del servicio tal y como aparecerá en un itinerario. Debe coincidir con el nombre configurado en la configuración de servicios de itinerario en el archivo Esb.config.  
  
  El **SupportsDisassemble** propiedad indica si el servicio de mensajería personalizado que está creando admite desensamblar y la ejecución de varias resoluciones.  
  
  El **ShouldAdvanceStep** método toma el paso del itinerario actual y el mensaje actual y devuelve un valor booleano que indica si el distribuidor debe adelantar el itinerario después de que el servicio se ejecuta. En casi todos los casos, este método debe devolver **true**.  
  
  El **Execute** método es de máxima importancia para un servicio de mensajería y contiene la lógica que se ejecutará en tiempo de ejecución. Que se tarda en el contexto de canalización, el mensaje, la cadena de resolución y el paso del itinerario actual; y devuelve el mensaje actualizado.  
  
  Una implementación de referencia de la **Execute** método puede encontrarse en el archivo RoutingService.cs del ESB. Proyecto Itinerary.Services, tal como se muestra en el código siguiente.  
  
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
  
 **Para implementar un servicio de itinerarios personalizado para la mensajería**  
  
1.  Crear un ensamblado con una clase que derive de **IMessagingService;** en el **Execute** método, incluir toda la lógica necesaria para realizar modificaciones en el mensaje o en el contexto del mensaje (si existe).  
  
2.  Agregue una entrada en el **itineraryServices** sección del archivo Esb.config para el servicio agregando una **\<itineraryService\>** elemento con un GUID como el **Id.**  atributo, el nombre del servicio como el **nombre** atributo, el nombre completo de la clase como el **tipo** atributo, **mensajería**como el **ámbito** atributo y la fase permitida (por ejemplo, **OnRampReceive**, **OnRampSend**, **OffRampSend**, **OffRampReceive**, **AllSend**, **AllReceive**, o **todas**) como el **fase**atributo.  
  
3.  Registre el nuevo ensamblado en la caché global de ensamblados.