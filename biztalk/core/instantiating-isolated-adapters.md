---
title: Crear instancias de adaptadores aislados | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b8359a3-b098-4bb6-87b4-d3432d2671b1
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e3090252f63221547604a4fdf88388bcbf8296f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="instantiating-isolated-adapters"></a>Crear instancias de adaptadores aislados
Como se ha comentado con anterioridad, BizTalk Server no crea instancias de los adaptadores aislados. En cambio, se crean instancias de ellos y se alojan en otro proceso. Es responsabilidad del adaptador para crear el proxy de transporte, **QueryInterface**, para **IBTTransportProxy**y, a continuación, llame a **IBTTransportProxy**. **RegisterIsolatedReceiver** para registrar con el motor de mensajería.  
  
 El registro requiere que el adaptador pase una de sus ubicaciones de recepción configurada y habilitada al motor de mensajería. Las credenciales del proceso del host del adaptador deben ser miembro del grupo Usuarios de hosts aislados de BizTalk. El uso solo de la suplantación aquí no es suficiente a menos que el usuario sea miembro de ese grupo. Además, se consulta el adaptador para asegurarse de tiene el valor correcto **ClassID** y se está ejecutando en el equipo que se configuró para esa instancia de host. Después de que el adaptador ha registrado correctamente con el proxy de transporte, su configuración se envía a llamando al método Load de la **IPersistPropertyBag** interfaz.  
  
 La ilustración siguiente muestra esta secuencia de llamadas a la API. Las interfaces que se muestran en azul son las que implementa el adaptador.  
  
 ![](../core/media/isolated-adapter-init.gif "Isolated_adapter_init")  
  
 El siguiente fragmento de código muestra las llamadas a la API de registro:  
  
```  
using Microsoft.BizTalk.TransportProxy.Interop;  
using Microsoft.BizTalk.Component.Interop;  
using Microsoft.BizTalk.Message.Interop;  
  
public class MyAdapter : IBTTransport,   
 IBTTransportConfig,   
 IBTTransportControl,   
 IBaseComponent  
{  
...  
private IBTTransportProxy transportProxy;  
  
 public void Register(string uri)  
 {  
 // Create the Transport Proxy...  
 this.transportProxy =   
 (IBTTransportProxy)new BTTransportProxy();  
  
// Register on of the adapters uri’s with the TP  
 this.transportProxy.RegisterIsolatedReceiver(  
 uri,   
 (IBTTransportConfig)this );  
 }  
}  
```  
  
 **Sugerencia para la implementación:** se recomienda que el adaptador realice un recuento del trabajo en curso. El adaptador debe bloquear **Terminate** hasta que llegue a cero el número de mensajes. En el caso de la recepción, este trabajo incluye cualquier solicitud pendiente que no se haya publicado en BizTalk Server. No se enviarán mensajes de respuesta a un adaptador de recepción después de **Terminate** se ha llamado.  
  
 En el caso de los adaptadores de envío, los mensajes que están en curso deben controlarse de forma adecuada. Esto significa que cualquier mensaje entregado correctamente debe eliminarse de la cola privada de mensajes de la aplicación del adaptador para evitar que se envíen más de una vez.  
  
 Después de **Terminate** se llama el motor de mensajería no acepta solicitudes para publicar nuevos mensajes, con excepción de los mensajes de respuesta para los pares petición-respuesta.