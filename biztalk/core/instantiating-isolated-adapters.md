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
# <a name="instantiating-isolated-adapters"></a><span data-ttu-id="24c7f-102">Crear instancias de adaptadores aislados</span><span class="sxs-lookup"><span data-stu-id="24c7f-102">Instantiating Isolated Adapters</span></span>
<span data-ttu-id="24c7f-103">Como se ha comentado con anterioridad, BizTalk Server no crea instancias de los adaptadores aislados.</span><span class="sxs-lookup"><span data-stu-id="24c7f-103">As discussed earlier, isolated adapters are not instantiated by BizTalk Server.</span></span> <span data-ttu-id="24c7f-104">En cambio, se crean instancias de ellos y se alojan en otro proceso.</span><span class="sxs-lookup"><span data-stu-id="24c7f-104">Rather, they are instantiated and hosted in another process.</span></span> <span data-ttu-id="24c7f-105">Es responsabilidad del adaptador para crear el proxy de transporte, **QueryInterface**, para **IBTTransportProxy**y, a continuación, llame a **IBTTransportProxy**. **RegisterIsolatedReceiver** para registrar con el motor de mensajería.</span><span class="sxs-lookup"><span data-stu-id="24c7f-105">It is the responsibility of the adapter to create its transport proxy, **QueryInterface**, for **IBTTransportProxy**, and then call **IBTTransportProxy**.**RegisterIsolatedReceiver** to register with the Messaging Engine.</span></span>  
  
 <span data-ttu-id="24c7f-106">El registro requiere que el adaptador pase una de sus ubicaciones de recepción configurada y habilitada al motor de mensajería.</span><span class="sxs-lookup"><span data-stu-id="24c7f-106">Registration requires that the adapter pass one of its configured and enabled receive locations to the Messaging Engine.</span></span> <span data-ttu-id="24c7f-107">Las credenciales del proceso del host del adaptador deben ser miembro del grupo Usuarios de hosts aislados de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="24c7f-107">The adapter's host process credentials must be a member of the BizTalk Isolated Host Users group.</span></span> <span data-ttu-id="24c7f-108">El uso solo de la suplantación aquí no es suficiente a menos que el usuario sea miembro de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="24c7f-108">Simply using impersonation here is insufficient unless the user is a member of that group.</span></span> <span data-ttu-id="24c7f-109">Además, se consulta el adaptador para asegurarse de tiene el valor correcto **ClassID** y se está ejecutando en el equipo que se configuró para esa instancia de host.</span><span class="sxs-lookup"><span data-stu-id="24c7f-109">In addition, the adapter is queried to ensure it has the correct **ClassID** and is running on the computer that was configured for that host instance.</span></span> <span data-ttu-id="24c7f-110">Después de que el adaptador ha registrado correctamente con el proxy de transporte, su configuración se envía a llamando al método Load de la **IPersistPropertyBag** interfaz.</span><span class="sxs-lookup"><span data-stu-id="24c7f-110">After the adapter has successfully registered with its transport proxy, its configuration is sent to it using by calling the Load method of the **IPersistPropertyBag** interface.</span></span>  
  
 <span data-ttu-id="24c7f-111">La ilustración siguiente muestra esta secuencia de llamadas a la API.</span><span class="sxs-lookup"><span data-stu-id="24c7f-111">The following figure illustrates this sequence of API calls.</span></span> <span data-ttu-id="24c7f-112">Las interfaces que se muestran en azul son las que implementa el adaptador.</span><span class="sxs-lookup"><span data-stu-id="24c7f-112">The interfaces in blue are implemented by the adapter.</span></span>  
  
 ![](../core/media/isolated-adapter-init.gif "Isolated_adapter_init")  
  
 <span data-ttu-id="24c7f-113">El siguiente fragmento de código muestra las llamadas a la API de registro:</span><span class="sxs-lookup"><span data-stu-id="24c7f-113">The following code fragment illustrates the registration API calls:</span></span>  
  
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
  
 <span data-ttu-id="24c7f-114">**Sugerencia para la implementación:** se recomienda que el adaptador realice un recuento del trabajo en curso.</span><span class="sxs-lookup"><span data-stu-id="24c7f-114">**Implementation Tip:** We recommend that the adapter keep a count of the work in progress.</span></span> <span data-ttu-id="24c7f-115">El adaptador debe bloquear **Terminate** hasta que llegue a cero el número de mensajes.</span><span class="sxs-lookup"><span data-stu-id="24c7f-115">The adapter should block **Terminate** until the message count has reached zero.</span></span> <span data-ttu-id="24c7f-116">En el caso de la recepción, este trabajo incluye cualquier solicitud pendiente que no se haya publicado en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="24c7f-116">On the receive side this work includes any outstanding requests that have not been published to BizTalk Server.</span></span> <span data-ttu-id="24c7f-117">No se enviarán mensajes de respuesta a un adaptador de recepción después de **Terminate** se ha llamado.</span><span class="sxs-lookup"><span data-stu-id="24c7f-117">Response messages are not delivered to a receive adapter after **Terminate** has been called.</span></span>  
  
 <span data-ttu-id="24c7f-118">En el caso de los adaptadores de envío, los mensajes que están en curso deben controlarse de forma adecuada.</span><span class="sxs-lookup"><span data-stu-id="24c7f-118">For send adapters, messages that are in progress should be handled appropriately.</span></span> <span data-ttu-id="24c7f-119">Esto significa que cualquier mensaje entregado correctamente debe eliminarse de la cola privada de mensajes de la aplicación del adaptador para evitar que se envíen más de una vez.</span><span class="sxs-lookup"><span data-stu-id="24c7f-119">This means any message that was successfully delivered should be deleted from the adapter's private application message queue to prevent messages from being sent more than once.</span></span>  
  
 <span data-ttu-id="24c7f-120">Después de **Terminate** se llama el motor de mensajería no acepta solicitudes para publicar nuevos mensajes, con excepción de los mensajes de respuesta para los pares petición-respuesta.</span><span class="sxs-lookup"><span data-stu-id="24c7f-120">After **Terminate** is called the Messaging Engine does not accept requests to publish new messages, with the exception of response messages for solicit-response pairs.</span></span>