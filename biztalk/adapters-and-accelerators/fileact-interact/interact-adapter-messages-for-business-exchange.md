---
title: Interactuar mensajes del adaptador para el intercambio de negocio | Documentos de Microsoft
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
ms.openlocfilehash: d19e10940e6a83c24e9397f0df94d0fc54e4da38
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224604"
---
# <a name="interact-adapter-messages-for-business-exchange"></a><span data-ttu-id="4f98a-102">Interactuar mensajes del adaptador para el intercambio de negocios</span><span class="sxs-lookup"><span data-stu-id="4f98a-102">InterAct Adapter Messages for Business Exchange</span></span>
<span data-ttu-id="4f98a-103">Hay cuatro mensajes en el ciclo de InterAct adaptador-to-end.</span><span class="sxs-lookup"><span data-stu-id="4f98a-103">There are four messages in the InterAct adapter end-to-end cycle.</span></span> <span data-ttu-id="4f98a-104">Estos mensajes son primitivos de SWIFTNet.</span><span class="sxs-lookup"><span data-stu-id="4f98a-104">These messages are SWIFTNet primitives.</span></span> <span data-ttu-id="4f98a-105">El primer y último mensajes forman parte de los tipos primitivos del lado cliente, SwInt:ExchangeRequest y SwInt:ExchangeResponse.</span><span class="sxs-lookup"><span data-stu-id="4f98a-105">The first and last messages comprise the client-side primitives, SwInt:ExchangeRequest and SwInt:ExchangeResponse.</span></span> <span data-ttu-id="4f98a-106">Los dos mensajes intermedios forman parte de los tipos primitivos del lado servidor, SwInt:HandleRequest y SwInt:HandleResponse.</span><span class="sxs-lookup"><span data-stu-id="4f98a-106">The middle two messages comprise the server-side primitives, SwInt:HandleRequest and SwInt:HandleResponse.</span></span>  
  
 <span data-ttu-id="4f98a-107">En este nivel de simplificación, hay seis pasos en el ciclo de mensajes de extremo a extremo:</span><span class="sxs-lookup"><span data-stu-id="4f98a-107">At this level of simplification, there are six steps in the end-to-end message cycle:</span></span>  
  
1.  <span data-ttu-id="4f98a-108">La aplicación cliente prepara el mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="4f98a-108">The client application prepares the request message.</span></span>  
  
2.  <span data-ttu-id="4f98a-109">La aplicación cliente pasa el mensaje de solicitud a SWIFTNet.</span><span class="sxs-lookup"><span data-stu-id="4f98a-109">The client application passes the request message to SWIFTNet.</span></span>  
  
3.  <span data-ttu-id="4f98a-110">SWIFTNet procesa el mensaje de solicitud y lo envía a la aplicación de servidor.</span><span class="sxs-lookup"><span data-stu-id="4f98a-110">SWIFTNet processes the request message, and sends it to the server application.</span></span>  
  
4.  <span data-ttu-id="4f98a-111">La aplicación del servidor recibe el mensaje de solicitud de SWIFTNet.</span><span class="sxs-lookup"><span data-stu-id="4f98a-111">The server application receives the request message from SWIFTNet.</span></span>  
  
5.  <span data-ttu-id="4f98a-112">La aplicación de servidor prepara el mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="4f98a-112">The server application prepares the response message.</span></span>  
  
6.  <span data-ttu-id="4f98a-113">La aplicación de servidor pasa el mensaje de respuesta a SWIFTNet.</span><span class="sxs-lookup"><span data-stu-id="4f98a-113">The server application passes the response message to SWIFTNet.</span></span>  
  
7.  <span data-ttu-id="4f98a-114">SWIFTNet procesa el mensaje de respuesta y lo envía a la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="4f98a-114">SWIFTNet processes the response message, and sends it to the client application.</span></span>  
  
8.  <span data-ttu-id="4f98a-115">La aplicación cliente recibe el mensaje de respuesta de SWIFTNet.</span><span class="sxs-lookup"><span data-stu-id="4f98a-115">The client application receives the response message from SWIFTNet.</span></span>  
  
 <span data-ttu-id="4f98a-116">La siguiente ilustración muestra el intercambio de mensajes de interacción.</span><span class="sxs-lookup"><span data-stu-id="4f98a-116">The following figure shows the InterAct message exchange.</span></span>  
  
 <span data-ttu-id="4f98a-117">![Intercambio de mensajes interAct](../../adapters-and-accelerators/fileact-interact/media/12fbebc6-5ab7-4d7f-9f94-4069b22161fa.gif "12fbebc6-5ab7-4d7f-9f94-4069b22161fa")</span><span class="sxs-lookup"><span data-stu-id="4f98a-117">![InterAct message exchange](../../adapters-and-accelerators/fileact-interact/media/12fbebc6-5ab7-4d7f-9f94-4069b22161fa.gif "12fbebc6-5ab7-4d7f-9f94-4069b22161fa")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f98a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f98a-118">See Also</span></span>  
 <span data-ttu-id="4f98a-119">[Interactuar de arquitectura de adaptador](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="4f98a-119">[InterAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="4f98a-120">[Componentes de adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span><span class="sxs-lookup"><span data-stu-id="4f98a-120">[InterAct Adapter Components](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span></span>  
 <span data-ttu-id="4f98a-121">[Aplicación de cliente de adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span><span class="sxs-lookup"><span data-stu-id="4f98a-121">[InterAct Adapter Client Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span></span>  
 <span data-ttu-id="4f98a-122">[Aplicación de servidor del adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span><span class="sxs-lookup"><span data-stu-id="4f98a-122">[InterAct Adapter Server Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span></span>  
 <span data-ttu-id="4f98a-123">[Interactuar el adaptador de almacenamiento y reenvío](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="4f98a-123">[InterAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="4f98a-124">[Arquitectura de seguridad del adaptador de interactuar](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="4f98a-124">[InterAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="4f98a-125">[Interactuar entrega confiable de adaptador-to-End](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span><span class="sxs-lookup"><span data-stu-id="4f98a-125">[InterAct Adapter End-to-End Reliable Delivery](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span></span>  
 <span data-ttu-id="4f98a-126">[Estado del adaptador de interactuar de supervisión](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span><span class="sxs-lookup"><span data-stu-id="4f98a-126">[InterAct Adapter Status Monitoring](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span></span>  
 [<span data-ttu-id="4f98a-127">Interactuar sin repudio de adaptador</span><span class="sxs-lookup"><span data-stu-id="4f98a-127">InterAct Adapter Non-Repudiation</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)