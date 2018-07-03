---
title: Interactuar mensajes del adaptador para el intercambio empresarial | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3b443b8a-4e56-47f1-8d91-5c807fd54ccc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea8e7d4f4ed8397c88a3cf21280352b446d629c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020156"
---
# <a name="interact-adapter-messages-for-business-exchange"></a><span data-ttu-id="5ca83-102">Interactuar mensajes del adaptador para el intercambio empresarial</span><span class="sxs-lookup"><span data-stu-id="5ca83-102">InterAct Adapter Messages for Business Exchange</span></span>
<span data-ttu-id="5ca83-103">Hay cuatro mensajes en el ciclo de extremo a otro adaptador InterAct.</span><span class="sxs-lookup"><span data-stu-id="5ca83-103">There are four messages in the InterAct adapter end-to-end cycle.</span></span> <span data-ttu-id="5ca83-104">Estos mensajes son primitivos de SWIFTNet.</span><span class="sxs-lookup"><span data-stu-id="5ca83-104">These messages are SWIFTNet primitives.</span></span> <span data-ttu-id="5ca83-105">El primer y último mensajes comprenden los tipos primitivos del lado cliente, SwInt:ExchangeRequest y SwInt:ExchangeResponse.</span><span class="sxs-lookup"><span data-stu-id="5ca83-105">The first and last messages comprise the client-side primitives, SwInt:ExchangeRequest and SwInt:ExchangeResponse.</span></span> <span data-ttu-id="5ca83-106">Los dos mensajes intermedios comprenden los tipos primitivos del lado servidor, SwInt:HandleRequest y SwInt:HandleResponse.</span><span class="sxs-lookup"><span data-stu-id="5ca83-106">The middle two messages comprise the server-side primitives, SwInt:HandleRequest and SwInt:HandleResponse.</span></span>  
  
 <span data-ttu-id="5ca83-107">En este nivel de simplificación, hay seis pasos en el ciclo de mensaje to-end:</span><span class="sxs-lookup"><span data-stu-id="5ca83-107">At this level of simplification, there are six steps in the end-to-end message cycle:</span></span>  
  
1. <span data-ttu-id="5ca83-108">La aplicación cliente prepara el mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="5ca83-108">The client application prepares the request message.</span></span>  
  
2. <span data-ttu-id="5ca83-109">La aplicación cliente pasa el mensaje de solicitud a SWIFTNet.</span><span class="sxs-lookup"><span data-stu-id="5ca83-109">The client application passes the request message to SWIFTNet.</span></span>  
  
3. <span data-ttu-id="5ca83-110">SWIFTNet procesa el mensaje de solicitud y lo envía a la aplicación de servidor.</span><span class="sxs-lookup"><span data-stu-id="5ca83-110">SWIFTNet processes the request message, and sends it to the server application.</span></span>  
  
4. <span data-ttu-id="5ca83-111">La aplicación de servidor recibe el mensaje de solicitud de SWIFTNet.</span><span class="sxs-lookup"><span data-stu-id="5ca83-111">The server application receives the request message from SWIFTNet.</span></span>  
  
5. <span data-ttu-id="5ca83-112">La aplicación de servidor prepara el mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="5ca83-112">The server application prepares the response message.</span></span>  
  
6. <span data-ttu-id="5ca83-113">La aplicación de servidor pasa el mensaje de respuesta a SWIFTNet.</span><span class="sxs-lookup"><span data-stu-id="5ca83-113">The server application passes the response message to SWIFTNet.</span></span>  
  
7. <span data-ttu-id="5ca83-114">SWIFTNet procesa el mensaje de respuesta y lo envía a la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="5ca83-114">SWIFTNet processes the response message, and sends it to the client application.</span></span>  
  
8. <span data-ttu-id="5ca83-115">La aplicación cliente recibe el mensaje de respuesta de SWIFTNet.</span><span class="sxs-lookup"><span data-stu-id="5ca83-115">The client application receives the response message from SWIFTNet.</span></span>  
  
   <span data-ttu-id="5ca83-116">La siguiente ilustración muestra el intercambio de mensajes InterAct.</span><span class="sxs-lookup"><span data-stu-id="5ca83-116">The following figure shows the InterAct message exchange.</span></span>  
  
   <span data-ttu-id="5ca83-117">![Intercambio de mensajes interAct](../../adapters-and-accelerators/fileact-interact/media/12fbebc6-5ab7-4d7f-9f94-4069b22161fa.gif "12fbebc6-5ab7-4d7f-9f94-4069b22161fa")</span><span class="sxs-lookup"><span data-stu-id="5ca83-117">![InterAct message exchange](../../adapters-and-accelerators/fileact-interact/media/12fbebc6-5ab7-4d7f-9f94-4069b22161fa.gif "12fbebc6-5ab7-4d7f-9f94-4069b22161fa")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ca83-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ca83-118">See Also</span></span>  
 <span data-ttu-id="5ca83-119">[Arquitectura de adaptador de interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="5ca83-119">[InterAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="5ca83-120">[Componentes del adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span><span class="sxs-lookup"><span data-stu-id="5ca83-120">[InterAct Adapter Components](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span></span>  
 <span data-ttu-id="5ca83-121">[Aplicación de cliente del adaptador de interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span><span class="sxs-lookup"><span data-stu-id="5ca83-121">[InterAct Adapter Client Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span></span>  
 <span data-ttu-id="5ca83-122">[Aplicación de servidor del adaptador de interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span><span class="sxs-lookup"><span data-stu-id="5ca83-122">[InterAct Adapter Server Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span></span>  
 <span data-ttu-id="5ca83-123">[Interactuar adaptador Store y reenvío](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="5ca83-123">[InterAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="5ca83-124">[Arquitectura de seguridad adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="5ca83-124">[InterAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="5ca83-125">[Entrega confiable de extremo a otro adaptador de interactuar](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span><span class="sxs-lookup"><span data-stu-id="5ca83-125">[InterAct Adapter End-to-End Reliable Delivery](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span></span>  
 <span data-ttu-id="5ca83-126">[Estado del adaptador de interactuar de supervisión](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span><span class="sxs-lookup"><span data-stu-id="5ca83-126">[InterAct Adapter Status Monitoring](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span></span>  
 [<span data-ttu-id="5ca83-127">No rechazo del adaptador de InterAct</span><span class="sxs-lookup"><span data-stu-id="5ca83-127">InterAct Adapter Non-Repudiation</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)