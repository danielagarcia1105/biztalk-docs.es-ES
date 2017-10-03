---
title: "Estado del adaptador de interactuar supervisión | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2bbc6a45-8d3a-444e-b760-aef0dfa7218a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32cf2f197508c0cd703a05780804c6bc880b5f32
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="interact-adapter-status-monitoring"></a><span data-ttu-id="b325d-102">Estado del adaptador de interactuar de supervisión</span><span class="sxs-lookup"><span data-stu-id="b325d-102">InterAct Adapter Status Monitoring</span></span>
<span data-ttu-id="b325d-103">Vínculo de SWIFTNet (SNL-C) mantiene el estado local sobre SWIFTNet almacén y reenvíos sesiones (SnF) adquiridas en ese SNL.</span><span class="sxs-lookup"><span data-stu-id="b325d-103">SWIFTNet Link (SNL-C) retains a local status about SWIFTNet store and forward (SnF) sessions acquired on that SNL.</span></span> <span data-ttu-id="b325d-104">Para obtener la información acerca de la sesión, utilice SwCall() con el tipo primitivo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b325d-104">To get the information about the session, use SwCall() with the following primitive:</span></span>  
  
 <span data-ttu-id="b325d-105">![Obtener información de sesión](../../adapters-and-accelerators/fileact-interact/media/b7feb4b4-de92-4bb9-bcfe-363a127d0ed2.gif "b7feb4b4-de92-4bb9-bcfe-363a127d0ed2")</span><span class="sxs-lookup"><span data-stu-id="b325d-105">![Getting session information](../../adapters-and-accelerators/fileact-interact/media/b7feb4b4-de92-4bb9-bcfe-363a127d0ed2.gif "b7feb4b4-de92-4bb9-bcfe-363a127d0ed2")</span></span>  
  
 <span data-ttu-id="b325d-106">Tenga en cuenta que no son necesarios para proporcionar un AuthorizationContext.</span><span class="sxs-lookup"><span data-stu-id="b325d-106">Notice that you are not required to provide an AuthorizationContext.</span></span> <span data-ttu-id="b325d-107">Se devuelve la información que se ve el SNL local, como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="b325d-107">The information seen by the local SNL is returned, as shown in the following figure.</span></span>  
  
 <span data-ttu-id="b325d-108">![Información de estado de sesión](../../adapters-and-accelerators/fileact-interact/media/afd46393-a11d-4b4a-a66b-eba5f049f306.gif "afd46393-a11d-4b4a-a66b-eba5f049f306")</span><span class="sxs-lookup"><span data-stu-id="b325d-108">![Session status information](../../adapters-and-accelerators/fileact-interact/media/afd46393-a11d-4b4a-a66b-eba5f049f306.gif "afd46393-a11d-4b4a-a66b-eba5f049f306")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b325d-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="b325d-109">See Also</span></span>  
 <span data-ttu-id="b325d-110">[Interactuar de arquitectura de adaptador](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="b325d-110">[InterAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="b325d-111">[Componentes de adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span><span class="sxs-lookup"><span data-stu-id="b325d-111">[InterAct Adapter Components](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span></span>  
 <span data-ttu-id="b325d-112">[Interactuar mensajes del adaptador para el intercambio de negocios](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span><span class="sxs-lookup"><span data-stu-id="b325d-112">[InterAct Adapter Messages for Business Exchange](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span></span>  
 <span data-ttu-id="b325d-113">[Aplicación de cliente de adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span><span class="sxs-lookup"><span data-stu-id="b325d-113">[InterAct Adapter Client Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span></span>  
 <span data-ttu-id="b325d-114">[Aplicación de servidor del adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span><span class="sxs-lookup"><span data-stu-id="b325d-114">[InterAct Adapter Server Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span></span>  
 <span data-ttu-id="b325d-115">[Interactuar el adaptador de almacenamiento y reenvío](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="b325d-115">[InterAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="b325d-116">[Arquitectura de seguridad del adaptador de interactuar](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="b325d-116">[InterAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="b325d-117">[Interactuar entrega confiable de adaptador-to-End](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span><span class="sxs-lookup"><span data-stu-id="b325d-117">[InterAct Adapter End-to-End Reliable Delivery](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span></span>  
 [<span data-ttu-id="b325d-118">Interactuar sin repudio de adaptador</span><span class="sxs-lookup"><span data-stu-id="b325d-118">InterAct Adapter Non-Repudiation</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)