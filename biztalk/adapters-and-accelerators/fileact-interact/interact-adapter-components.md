---
title: Componentes de adaptador interAct | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aad60b57-4cc8-44b9-98f5-e5a2ba3a41e2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e909e49713377172d01540f4c8e660756d68ed72
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224692"
---
# <a name="interact-adapter-components"></a><span data-ttu-id="62f14-102">Componentes de adaptador interAct</span><span class="sxs-lookup"><span data-stu-id="62f14-102">InterAct Adapter Components</span></span>
<span data-ttu-id="62f14-103">El adaptador de InterAct tiene un cliente y un componente de servidor.</span><span class="sxs-lookup"><span data-stu-id="62f14-103">The InterAct adapter has a client and a server component.</span></span> <span data-ttu-id="62f14-104">Tenga en cuenta que puede haber una instalación de A4SWIFT (mínima) en el mismo equipo como puerta de enlace de Alliance de SWIFT (SAG) si se está ejecutando Windows Server.</span><span class="sxs-lookup"><span data-stu-id="62f14-104">Note that there may be an A4SWIFT (minimal) installation on the same computer as the SWIFT Alliance Gateway (SAG) if it is running Windows Server.</span></span> <span data-ttu-id="62f14-105">Tenga en cuenta también que el vínculo de SWIFTNet (SNL) pueden estar en un equipo diferente desde el SAG.</span><span class="sxs-lookup"><span data-stu-id="62f14-105">Also note that the SWIFTNet Link (SNL) may be on a separate computer from the SAG.</span></span> <span data-ttu-id="62f14-106">El adaptador de host (API) de la interfaz proporcionada por SWIFT de programación de aplicaciones remoto se utilizan para comunicarse de A4SWIFT con SAG, independientemente de la ubicación de los componentes.</span><span class="sxs-lookup"><span data-stu-id="62f14-106">The remote application programming interface (API) host adapter provided by SWIFT is used to communicate from A4SWIFT to the SAG, regardless of the location of the components.</span></span>  
  
 <span data-ttu-id="62f14-107">La siguiente ilustración muestra que los componentes que componen la cadena completa de adaptador y las comunicaciones relacionadas con el adaptador de InterAct residen.</span><span class="sxs-lookup"><span data-stu-id="62f14-107">The figure below shows where the components comprising the entire adapter and communications chain related to the InterAct adapter reside.</span></span>  
  
 <span data-ttu-id="62f14-108">![Componentes interAct](../../adapters-and-accelerators/fileact-interact/media/cf257c5a-3668-4aff-bce9-7acc6eb672bd.gif "cf257c5a-3668-4aff-bce9-7acc6eb672bd")</span><span class="sxs-lookup"><span data-stu-id="62f14-108">![InterAct components](../../adapters-and-accelerators/fileact-interact/media/cf257c5a-3668-4aff-bce9-7acc6eb672bd.gif "cf257c5a-3668-4aff-bce9-7acc6eb672bd")</span></span>  
  
 <span data-ttu-id="62f14-109">En la siguiente ilustración, la aplicación cliente usa A4SWIFT y el adaptador de InterAct.</span><span class="sxs-lookup"><span data-stu-id="62f14-109">In the following figure, the client application uses A4SWIFT and the InterAct adapter.</span></span> <span data-ttu-id="62f14-110">BizTalk Server es el middleware, que se comunica con el adaptador de host remoto de API a través de TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="62f14-110">BizTalk Server is the middleware, which communicates to the remote API host adapter over TCPIP.</span></span>  
  
 <span data-ttu-id="62f14-111">![Aplicación cliente interAct](../../adapters-and-accelerators/fileact-interact/media/7aeada39-6264-498b-92e8-303eb0cf369b.gif "7aeada39-6264-498b-92e8-303eb0cf369b")</span><span class="sxs-lookup"><span data-stu-id="62f14-111">![InterAct client application](../../adapters-and-accelerators/fileact-interact/media/7aeada39-6264-498b-92e8-303eb0cf369b.gif "7aeada39-6264-498b-92e8-303eb0cf369b")</span></span>  
  
 <span data-ttu-id="62f14-112">En la ilustración siguiente, la aplicación de servidor utiliza A4SWIFT y el adaptador de InterAct.</span><span class="sxs-lookup"><span data-stu-id="62f14-112">In the following figure, the server application uses A4SWIFT and the InterAct adapter.</span></span> <span data-ttu-id="62f14-113">BizTalk Server es el middleware, que se comunica con el adaptador de host remoto de API a través de TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="62f14-113">BizTalk Server is the middleware, which communicates to the remote API host adapter over TCPIP.</span></span>  
  
 <span data-ttu-id="62f14-114">![Aplicación del servidor interAct](../../adapters-and-accelerators/fileact-interact/media/51cbae6a-41e9-4a50-9574-5e86bc04ddba.gif "51cbae6a-41e9-4a50-9574-5e86bc04ddba")</span><span class="sxs-lookup"><span data-stu-id="62f14-114">![InterAct server application](../../adapters-and-accelerators/fileact-interact/media/51cbae6a-41e9-4a50-9574-5e86bc04ddba.gif "51cbae6a-41e9-4a50-9574-5e86bc04ddba")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62f14-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="62f14-115">See Also</span></span>  
 <span data-ttu-id="62f14-116">[Interactuar de arquitectura de adaptador](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="62f14-116">[InterAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="62f14-117">[Interactuar mensajes del adaptador para el intercambio de negocios](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span><span class="sxs-lookup"><span data-stu-id="62f14-117">[InterAct Adapter Messages for Business Exchange](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span></span>  
 <span data-ttu-id="62f14-118">[Aplicación de cliente de adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span><span class="sxs-lookup"><span data-stu-id="62f14-118">[InterAct Adapter Client Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span></span>  
 <span data-ttu-id="62f14-119">[Aplicación de servidor del adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span><span class="sxs-lookup"><span data-stu-id="62f14-119">[InterAct Adapter Server Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span></span>  
 <span data-ttu-id="62f14-120">[Interactuar el adaptador de almacenamiento y reenvío](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="62f14-120">[InterAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="62f14-121">[Arquitectura de seguridad del adaptador de interactuar](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="62f14-121">[InterAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="62f14-122">[Interactuar entrega confiable de adaptador-to-End](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span><span class="sxs-lookup"><span data-stu-id="62f14-122">[InterAct Adapter End-to-End Reliable Delivery](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span></span>  
 <span data-ttu-id="62f14-123">[Estado del adaptador de interactuar de supervisión](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span><span class="sxs-lookup"><span data-stu-id="62f14-123">[InterAct Adapter Status Monitoring](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span></span>  
 [<span data-ttu-id="62f14-124">Interactuar sin repudio de adaptador</span><span class="sxs-lookup"><span data-stu-id="62f14-124">InterAct Adapter Non-Repudiation</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)