---
title: Arquitectura del adaptador de MSMQ | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, MSMQ adapters
- MSMQ adapters, architecture
ms.assetid: acecc2a4-0670-487e-be39-28a24c8c3f16
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd314b6f835568b6336121478268b84381a288ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263052"
---
# <a name="msmq-adapter-architecture"></a><span data-ttu-id="74c2d-102">Arquitectura del adaptador de MSMQ</span><span class="sxs-lookup"><span data-stu-id="74c2d-102">MSMQ Adapter Architecture</span></span>
<span data-ttu-id="74c2d-103">El adaptador de MSMQ le permite aprovechar las características de Microsoft Message Queuing (también denominado MSMQ) que, por otra parte, no están disponibles en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="74c2d-103">The MSMQ adapter lets you take advantage of Microsoft Message Queuing (also known as MSMQ) features that are otherwise unavailable in BizTalk Server.</span></span>  
  
## <a name="adapter-structure"></a><span data-ttu-id="74c2d-104">Estructura del adaptador</span><span class="sxs-lookup"><span data-stu-id="74c2d-104">Adapter Structure</span></span>  
 <span data-ttu-id="74c2d-105">El adaptador de MSMQ tiene la misma estructura que otros adaptadores de BizTalk y utiliza el marco de trabajo de adaptadores.</span><span class="sxs-lookup"><span data-stu-id="74c2d-105">The MSMQ adapter has the same structure as other BizTalk adapters and uses the Adapter Framework.</span></span> <span data-ttu-id="74c2d-106">Está compuesto por un componente de tiempo de diseño y otro de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="74c2d-106">It is made up of a design-time component and a run-time component.</span></span> <span data-ttu-id="74c2d-107">El componente de tiempo de ejecución, a su vez, contiene los elementos que implementan el transporte de mensaje.</span><span class="sxs-lookup"><span data-stu-id="74c2d-107">The run-time component, in turn, contains the elements that implement the message transport.</span></span>  
  
 <span data-ttu-id="74c2d-108">El componente de tiempo de diseño le permite configurar las propiedades del adaptador para el envío y la recepción.</span><span class="sxs-lookup"><span data-stu-id="74c2d-108">The design-time component lets you configure the adapter properties for sending and receiving.</span></span>  
  
 <span data-ttu-id="74c2d-109">El componente de tiempo de ejecución puede enviar mensajes a una cola definida en tiempo de diseño o recibir mensajes desde una cola designada.</span><span class="sxs-lookup"><span data-stu-id="74c2d-109">The run-time component can send messages to a queue defined at design time or receive messages from a designated queue.</span></span> <span data-ttu-id="74c2d-110">El tiempo de ejecución del adaptador se ejecuta en el mismo proceso que la aplicación de BizTalk Server y no se ejecuta en un host aislado.</span><span class="sxs-lookup"><span data-stu-id="74c2d-110">The adapter runtime runs in the same process as the BizTalk Server application and does not run in an isolated host.</span></span>  
  
 <span data-ttu-id="74c2d-111">La administración de todos los mensajes se basa en el servicio Message Queue Server incluso para colas remotas.</span><span class="sxs-lookup"><span data-stu-id="74c2d-111">All message handling relies on the local Message Queuing service, even for remote queues.</span></span> <span data-ttu-id="74c2d-112">Para colas remotas, el adaptador entrega los mensajes al servicio local de Message Queue Server.</span><span class="sxs-lookup"><span data-stu-id="74c2d-112">For remote queues, the adapter hands messages off to the local Message Queuing service.</span></span> <span data-ttu-id="74c2d-113">Éste, a su vez, envía los mensajes a la cola remota.</span><span class="sxs-lookup"><span data-stu-id="74c2d-113">It, in turn, sends the messages to the remote queue.</span></span>  
  
 <span data-ttu-id="74c2d-114">Para obtener una lista completa de envío y recepción de propiedades de configuración, consulte [cómo configurar un puerto de envío MSMQ](../core/how-to-configure-an-msmq-send-port.md) y [cómo configurar una ubicación de recepción de MSMQ](../core/how-to-configure-an-msmq-receive-location.md).</span><span class="sxs-lookup"><span data-stu-id="74c2d-114">For a complete list of send and receive configuration properties, see [How to Configure an MSMQ Send Port](../core/how-to-configure-an-msmq-send-port.md) and [How to Configure an MSMQ Receive Location](../core/how-to-configure-an-msmq-receive-location.md).</span></span>  
  
 <span data-ttu-id="74c2d-115">Para obtener más información sobre Message Queue Server, vea los temas siguientes disponibles en Microsoft TechNet Library:</span><span class="sxs-lookup"><span data-stu-id="74c2d-115">For more information about Message Queuing, see the following topics available in the Microsoft TechNet Library:</span></span>  
  
-   <span data-ttu-id="74c2d-116">**Guía de diseño de puesta en cola de mensajes** en [http://go.microsoft.com/fwlink/?LinkId=137080](http://go.microsoft.com/fwlink/?LinkId=137080).</span><span class="sxs-lookup"><span data-stu-id="74c2d-116">**Message Queuing Design Guide** at [http://go.microsoft.com/fwlink/?LinkId=137080](http://go.microsoft.com/fwlink/?LinkId=137080).</span></span>  
  
-   <span data-ttu-id="74c2d-117">**Guía de operaciones de puesta en cola de mensajes** en [http://go.microsoft.com/fwlink/?LinkId=137079](http://go.microsoft.com/fwlink/?LinkId=137079).</span><span class="sxs-lookup"><span data-stu-id="74c2d-117">**Message Queuing Operations Guide** at [http://go.microsoft.com/fwlink/?LinkId=137079](http://go.microsoft.com/fwlink/?LinkId=137079).</span></span>  
  
-   <span data-ttu-id="74c2d-118">**Message Queue Server Guía de solución de problemas** en [http://go.microsoft.com/fwlink/?LinkId=137081](http://go.microsoft.com/fwlink/?LinkId=137081).</span><span class="sxs-lookup"><span data-stu-id="74c2d-118">**Message Queuing Troubleshooting Guide** at [http://go.microsoft.com/fwlink/?LinkId=137081](http://go.microsoft.com/fwlink/?LinkId=137081).</span></span>  
  
-   <span data-ttu-id="74c2d-119">**Referencia técnica de puesta en cola de mensajes** en [http://go.microsoft.com/fwlink/?LinkId=137082](http://go.microsoft.com/fwlink/?LinkId=137082).</span><span class="sxs-lookup"><span data-stu-id="74c2d-119">**Message Queuing Technical Reference** at [http://go.microsoft.com/fwlink/?LinkId=137082](http://go.microsoft.com/fwlink/?LinkId=137082).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74c2d-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="74c2d-120">See Also</span></span>  
 [<span data-ttu-id="74c2d-121">¿Qué es el adaptador de MSMQ?</span><span class="sxs-lookup"><span data-stu-id="74c2d-121">What Is the MSMQ Adapter?</span></span>](../core/what-is-the-msmq-adapter.md)