---
title: "Propiedades de mensajería de confianza con el adaptador de MSMQ | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, properties
- queues, MSMQ adapters
- MSMQ adapters, dead letters
- queues, failures [MSMQ adapters]
- MSMQ adapters, impersonation
- MSMQ adapters, remote queues
- queues
- reliability, MSMQ adapters
- impersonation, MSMQ adapters
- MSMQ adapters, queue failures
- clustering, MSMQ adapters
- queues, remote
- MSMQ adapters, reliability
- MSMQ adapters, clustering
ms.assetid: 34bfe028-b2aa-4816-a437-3679d19dffb2
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49aebf12c86ae72d5dcb224d078c62afefcb8f46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="properties-for-reliable-messaging-with-the-msmq-adapter"></a><span data-ttu-id="fe9ae-102">Propiedades de mensajería de confianza con el adaptador de MSMQ</span><span class="sxs-lookup"><span data-stu-id="fe9ae-102">Properties for Reliable Messaging with the MSMQ Adapter</span></span>
<span data-ttu-id="fe9ae-103">Es posible mejorar la confiabilidad del envío y la recepción de mensajes con el adaptador de MSMQ mediante el modo de configuración de éste.</span><span class="sxs-lookup"><span data-stu-id="fe9ae-103">You can improve the reliability of sending and receiving messages with the MSMQ adapter by the way you configure the MSMQ adapter.</span></span> <span data-ttu-id="fe9ae-104">En este tema se analiza el uso de varias propiedades de configuración para la mensajería confiable.</span><span class="sxs-lookup"><span data-stu-id="fe9ae-104">This topic discusses using several configuration properties for reliable messaging.</span></span>  
  
## <a name="running-msmq-adapter-handlers-within-a-clustered-biztalk-host"></a><span data-ttu-id="fe9ae-105">Ejecutar controladores del adaptador de MSMQ en un host agrupado de BizTalk</span><span class="sxs-lookup"><span data-stu-id="fe9ae-105">Running MSMQ Adapter Handlers Within a Clustered BizTalk Host</span></span>  
 <span data-ttu-id="fe9ae-106">Una forma de garantizar la alta disponibilidad es ejecutar los controladores del adaptador en varias instancias de host de diferentes servidores de BizTalk Server de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="fe9ae-106">One approach to high availability is to run adapter handlers in multiple host instances on different BizTalk servers simultaneously.</span></span> <span data-ttu-id="fe9ae-107">Este enfoque no resulta recomendable para los controladores del adaptador de MSMQ, puesto que MSMQ no admite transacciones de lecturas remotas y el controlador de envío MSMQ mantiene una dependencia en la instancia de ejecución local del servicio MSMQ.</span><span class="sxs-lookup"><span data-stu-id="fe9ae-107">This approach is not recommended for the MSMQ adapter handlers, because MSMQ does not support remote transacted reads and because the MSMQ send handler maintains a dependency on the locally running instance of the MSMQ service.</span></span> <span data-ttu-id="fe9ae-108">Para proporcionar una alta disponibilidad para los controladores de recepción y envío de MSMQ, se recomienda ejecutar los controladores del adaptador de MSMQ en una instancia de host agrupado de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="fe9ae-108">To provide high availability for the MSMQ send and receive handlers it is recommended that you run the MSMQ adapter handlers in a clustered instance of a BizTalk Host.</span></span> <span data-ttu-id="fe9ae-109">Para obtener más información, consulte [consideraciones para ejecutar controladores de adaptador dentro de un Host en clúster](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).</span><span class="sxs-lookup"><span data-stu-id="fe9ae-109">For more information, see [Considerations for Running Adapter Handlers within a Clustered Host](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).</span></span>  
  
## <a name="queue-failure-and-the-dead-letter-queue"></a><span data-ttu-id="fe9ae-110">Error de cola y cola de mensajes con problemas de entrega</span><span class="sxs-lookup"><span data-stu-id="fe9ae-110">Queue Failure and the Dead Letter Queue</span></span>  
 <span data-ttu-id="fe9ae-111">Tras enviar un mensaje correctamente, no habrá ningún error de los mensajes posteriores si la cola de recepción se deshabilita o elimina.</span><span class="sxs-lookup"><span data-stu-id="fe9ae-111">After successfully sending a message, there is no error for subsequent messages if the receiving queue is disabled or deleted.</span></span> <span data-ttu-id="fe9ae-112">Esto podría provocar pérdida de mensajes.</span><span class="sxs-lookup"><span data-stu-id="fe9ae-112">This situation could cause loss of messages.</span></span>  
  
 <span data-ttu-id="fe9ae-113">Establecer el **cola de mensajes no enviados de uso** propiedad de configuración a **True** impide la pérdida de mensajes.</span><span class="sxs-lookup"><span data-stu-id="fe9ae-113">Setting the **Use Dead Letter Queue** configuration property to **True** prevents you from losing messages.</span></span> <span data-ttu-id="fe9ae-114">Si la propiedad se establece como `True` (valor predeterminado), los mensajes que no recibe la cola van a la cola de mensajes con problemas de entrega.</span><span class="sxs-lookup"><span data-stu-id="fe9ae-114">When the property is `True` (the default), messages that the queue does not receive go into the dead letter queue.</span></span>  
  
## <a name="impersonation-and-remote-queues"></a><span data-ttu-id="fe9ae-115">Colas remotas y suplantación</span><span class="sxs-lookup"><span data-stu-id="fe9ae-115">Impersonation and Remote Queues</span></span>  
 <span data-ttu-id="fe9ae-116">También tendrá que configurar el **usar cola de mensajes no enviados** propiedad de configuración a **True** cuando usa las colas remotas.</span><span class="sxs-lookup"><span data-stu-id="fe9ae-116">You also have to set the **Use Dead Letter Queue** configuration property to **True** when you use remote queues.</span></span> <span data-ttu-id="fe9ae-117">Si el adaptador de MSMQ suplanta a un usuario sin permiso para utilizar la cola remota, el mensaje podría perderse.</span><span class="sxs-lookup"><span data-stu-id="fe9ae-117">If the adapter for MSMQ impersonates a user without permission to use the remote queue, the message could be lost.</span></span>  
  
 <span data-ttu-id="fe9ae-118">Cuando la propiedad es **True** y el usuario suplantado no tiene permiso para utilizar la cola remota, el mensaje va a la cola de mensajes no enviados en el equipo local o remoto.</span><span class="sxs-lookup"><span data-stu-id="fe9ae-118">When the property is **True** and the impersonated user does not have permission to use the remote queue, the message goes to the dead letter queue on either the local or remote computer.</span></span> <span data-ttu-id="fe9ae-119">En un envío transaccional, el mensaje va a la cola de mensajes con problemas de entrega del equipo local.</span><span class="sxs-lookup"><span data-stu-id="fe9ae-119">In a transactional send, the message goes to the dead letter queue on the local computer.</span></span> <span data-ttu-id="fe9ae-120">En un envío no transaccional, el mensaje va a la cola de mensajes con problemas de entrega del equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="fe9ae-120">In a non-transactional send, the message goes to the dead letter queue on the remote computer.</span></span>  
  
## <a name="recoverable-and-use-journal-queue-properties"></a><span data-ttu-id="fe9ae-121">Propiedades Recuperable y Usar cola de diario</span><span class="sxs-lookup"><span data-stu-id="fe9ae-121">Recoverable and Use Journal Queue Properties</span></span>  
 <span data-ttu-id="fe9ae-122">Tanto el **recuperables** y **usar cola de diario** propiedades guardan copias de los mensajes enviados.</span><span class="sxs-lookup"><span data-stu-id="fe9ae-122">Both the **Recoverable** and **Use Journal Queue** properties save copies of sent messages.</span></span> <span data-ttu-id="fe9ae-123">Para obtener más información acerca de estas propiedades, vea [cómo configurar una ubicación de recepción de MSMQ](../core/how-to-configure-an-msmq-receive-location.md) y [cómo configurar un puerto de envío MSMQ](../core/how-to-configure-an-msmq-send-port.md).</span><span class="sxs-lookup"><span data-stu-id="fe9ae-123">For more information about these properties, see [How to Configure an MSMQ Receive Location](../core/how-to-configure-an-msmq-receive-location.md) and [How to Configure an MSMQ Send Port](../core/how-to-configure-an-msmq-send-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe9ae-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe9ae-124">See Also</span></span>  
 <span data-ttu-id="fe9ae-125">[Mensajería confiable con el adaptador de MSMQ](../core/reliable-messaging-with-the-msmq-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="fe9ae-125">[Reliable Messaging with the MSMQ Adapter](../core/reliable-messaging-with-the-msmq-adapter.md) </span></span>  
 [<span data-ttu-id="fe9ae-126">Consideraciones para ejecutar controladores del adaptador en un Host en clúster</span><span class="sxs-lookup"><span data-stu-id="fe9ae-126">Considerations for Running Adapter Handlers within a Clustered Host</span></span>](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)