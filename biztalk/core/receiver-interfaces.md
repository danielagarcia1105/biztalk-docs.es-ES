---
title: Interfaces del receptor | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7ab77d4-705a-4b39-8c33-a7532ae6484c
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77b42530d721a6dcee52e082fe46deae9ae06405
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receiver-interfaces"></a><span data-ttu-id="df90d-102">Interfaces del receptor</span><span class="sxs-lookup"><span data-stu-id="df90d-102">Receiver Interfaces</span></span>
<span data-ttu-id="df90d-103">Además de las interfaces de adaptador estándar, adaptadores de recepción necesitan implementar **IBTTransportConfig**.</span><span class="sxs-lookup"><span data-stu-id="df90d-103">In addition to the standard adapter interfaces, receive adapters need to implement **IBTTransportConfig**.</span></span> <span data-ttu-id="df90d-104">Esta es la interfaz en la que el motor de mensajería de BizTalk entrega la configuración de ubicación de recepción al adaptador.</span><span class="sxs-lookup"><span data-stu-id="df90d-104">This is the interface on which the BizTalk Messaging Engine delivers receive location configuration to the adapter.</span></span>  
  
## <a name="request-response-adapters"></a><span data-ttu-id="df90d-105">Adaptadores de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="df90d-105">Request-Response Adapters</span></span>  
 <span data-ttu-id="df90d-106">Es posible que sea necesario que los adaptadores de recepción controlen los mensajes de envío en algunos casos.</span><span class="sxs-lookup"><span data-stu-id="df90d-106">Receive adapters may also need to handle send messages in some cases.</span></span> <span data-ttu-id="df90d-107">A los adaptadores que realizan esto se les conoce como bidireccionales o adaptadores de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="df90d-107">Adapters that do this are usually referred to as two-way, or Request-Response adapters.</span></span> <span data-ttu-id="df90d-108">Para poder enviar mensajes, debe implementar un adaptador de recepción **IBTTransmitter**.</span><span class="sxs-lookup"><span data-stu-id="df90d-108">To be able to send messages, a receive adapter needs to implement **IBTTransmitter**.</span></span>  
  
 <span data-ttu-id="df90d-109">La siguiente ilustración muestra las interfaces implementadas por adaptadores de recepción.</span><span class="sxs-lookup"><span data-stu-id="df90d-109">The following figure shows the interfaces implemented by receive adapters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df90d-110">El **IBTBatchTransmitter** interfaz no es compatible con los adaptadores de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="df90d-110">The **IBTBatchTransmitter** interface is not supported for Request-Response adapters.</span></span>  
  
 ![](../core/media/requestresponseadapters.gif "RequestResponseAdapters")