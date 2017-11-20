---
title: "Arquitectura del adaptador de envío de SWIFT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e52a5a21-0aa1-4cd9-a2a4-f9df425913a0
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d772203c980495c5aa62266beb060693c1a8ad8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="swift-send-adapter-architecture"></a><span data-ttu-id="52b57-102">Arquitectura del adaptador de envío SWIFT</span><span class="sxs-lookup"><span data-stu-id="52b57-102">SWIFT Send Adapter Architecture</span></span>
<span data-ttu-id="52b57-103">En general, los adaptadores de envío de BizTalk Server se hospedan en el proceso de servicio de BizTalk, Btsntsvc.exe.</span><span class="sxs-lookup"><span data-stu-id="52b57-103">In general, BizTalk Server send adapters are hosted in the BizTalk service process, Btsntsvc.exe.</span></span> <span data-ttu-id="52b57-104">Esto significa que el servidor BizTalk Server administra la duración del adaptador.</span><span class="sxs-lookup"><span data-stu-id="52b57-104">This means that BizTalk Server manages the lifetime of the adapter.</span></span>  
  
 <span data-ttu-id="52b57-105">Hay dos maneras de enviar mensajes a la red SWIFT: (ExchangeRequest) sincrónica y asincrónica (es decir, no está implementado en esta versión).</span><span class="sxs-lookup"><span data-stu-id="52b57-105">There are two ways of sending messages to the SWIFT network: synchronous (ExchangeRequest) and asynchronous (not implemented for this release).</span></span> <span data-ttu-id="52b57-106">En BizTalk Server, el adaptador de envío debe admitir los siguientes patrones de comunicación para interactuar con el motor de mensajería de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="52b57-106">In BizTalk Server, the send adapter should support the following communication patterns to interact with the BizTalk Messaging Engine:</span></span>  
  
-   <span data-ttu-id="52b57-107">Respuesta de petición-respuesta, los mensajes se intercambian en parejas, llamados a los tipos primitivos, con la red SWIFT.</span><span class="sxs-lookup"><span data-stu-id="52b57-107">Solicit response — messages are exchanged in pairs, called the primitives, with the SWIFT network.</span></span> <span data-ttu-id="52b57-108">Los mensajes enviados a SWIFT tendrá una respuesta sea empresarial, confirmación o un error.</span><span class="sxs-lookup"><span data-stu-id="52b57-108">Any messages sent to SWIFT will have a response be it business, acknowledgement or error.</span></span> <span data-ttu-id="52b57-109">El mensaje de respuesta se envía al cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="52b57-109">The response message is submitted back to messagebox.</span></span> <span data-ttu-id="52b57-110">Este modo de funcionamiento se utiliza para la comunicación en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="52b57-110">This mode of operation is used for Real-Time communication.</span></span>  
  
-   <span data-ttu-id="52b57-111">Una manera de envío, el adaptador cuando se configura de una manera opera en el almacén y el modo de reenvío.</span><span class="sxs-lookup"><span data-stu-id="52b57-111">One way send — the adapter when configured in one way operates in store and forward mode.</span></span> <span data-ttu-id="52b57-112">Los mensajes se envían a una cola preconfigurada en lugar de un destinatario.</span><span class="sxs-lookup"><span data-stu-id="52b57-112">The messages are sent to a preconfigured queue as opposed to a receipient.</span></span> <span data-ttu-id="52b57-113">El remitente puede recuperar la respuesta al abrir una sesión con la cola en modo de inserción o extracción.</span><span class="sxs-lookup"><span data-stu-id="52b57-113">The sender can retrieve the response by opening a session with the queue in push or pull mode.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52b57-114">La manera de crear el adaptador afecta al modo en que funciona.</span><span class="sxs-lookup"><span data-stu-id="52b57-114">The way you create the adapter affects the way it operates.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="52b57-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="52b57-115">In This Section</span></span>  
  
-   [<span data-ttu-id="52b57-116">URI del adaptador de envío SWIFT</span><span class="sxs-lookup"><span data-stu-id="52b57-116">SWIFT Send Adapter URI</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-uri.md)  
  
-   [<span data-ttu-id="52b57-117">Envío dinámico del adaptador de envío SWIFT</span><span class="sxs-lookup"><span data-stu-id="52b57-117">SWIFT Send Adapter Dynamic Send</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-dynamic-send.md)  
  
-   [<span data-ttu-id="52b57-118">Inicialización del adaptador de envío SWIFT</span><span class="sxs-lookup"><span data-stu-id="52b57-118">SWIFT Send Adapter Initialization</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-initialization.md)  
  
-   [<span data-ttu-id="52b57-119">Modo sincrónico del adaptador de envío SWIFT</span><span class="sxs-lookup"><span data-stu-id="52b57-119">SWIFT Send Adapter Synchronous Mode</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-synchronous-mode.md)  
  
-   [<span data-ttu-id="52b57-120">Finalización del adaptador de envío SWIFT</span><span class="sxs-lookup"><span data-stu-id="52b57-120">SWIFT Send Adapter Termination</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-termination.md)