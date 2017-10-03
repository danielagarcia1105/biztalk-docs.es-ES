---
title: "Descripción de FileAct e interactuar de arquitectura de adaptador | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f97a7fe-20df-4509-bb6e-53743c3a57df
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c04d0ba8b1c2bbd99a71e3d76c8d7ad60c251147
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="understanding-fileact-and-interact-adapter-architecture"></a><span data-ttu-id="55756-102">Descripción de FileAct e interactuar de arquitectura de adaptador</span><span class="sxs-lookup"><span data-stu-id="55756-102">Understanding FileAct and InterAct Adapter Architecture</span></span>
<span data-ttu-id="55756-103">El adaptador de SWIFT se basa en el adaptador de BizTalk Framework.</span><span class="sxs-lookup"><span data-stu-id="55756-103">The SWIFT Adapter is based on the BizTalk Adapter Framework.</span></span> <span data-ttu-id="55756-104">Mediante las clasificaciones de los adaptadores de BizTalk Server, los adaptadores de SWIFT, FileAct e InterAct, representan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="55756-104">Using the classifications of adapters within BizTalk Server, the SWIFT adapters, FileAct and InterAct, represent the following:</span></span>  
  
-   <span data-ttu-id="55756-105">Adaptador personalizado.</span><span class="sxs-lookup"><span data-stu-id="55756-105">Custom Adapter.</span></span> <span data-ttu-id="55756-106">Se trata de un adaptador personalizado creado específicamente para interactuar con la red SWIFT con un estándar propietario denominado FileAct e Interact.</span><span class="sxs-lookup"><span data-stu-id="55756-106">This is a custom adapter built specifically to interact with the SWIFT network using a proprietary standard called FileAct and Interact.</span></span>  
  
-   <span data-ttu-id="55756-107">Adaptador de transporte.</span><span class="sxs-lookup"><span data-stu-id="55756-107">Transport Adapter.</span></span> <span data-ttu-id="55756-108">Este adaptador permite la aplicación de software empresarial Enviar y recibir mensajes con la red SWIFT.</span><span class="sxs-lookup"><span data-stu-id="55756-108">This adapter allows business software application to send and receive messages with the SWIFT network.</span></span>  
  
-   <span data-ttu-id="55756-109">Sin transacciones.</span><span class="sxs-lookup"><span data-stu-id="55756-109">Non-transacted.</span></span> <span data-ttu-id="55756-110">El adaptador no hace uso de cualquier objeto de transacción para interactuar con la red SWIFT.</span><span class="sxs-lookup"><span data-stu-id="55756-110">The adapter does not make use of any transaction object to interact with the SWIFT network.</span></span>  
  
-   <span data-ttu-id="55756-111">Aislado:</span><span class="sxs-lookup"><span data-stu-id="55756-111">Isolated.</span></span> <span data-ttu-id="55756-112">El adaptador de recepción se ejecuta en un proceso independiente y adaptadores de envío normal que se ejecutan en proceso.</span><span class="sxs-lookup"><span data-stu-id="55756-112">The receive adapter runs in a separate process and regular send adapters run in process.</span></span>  
  
 <span data-ttu-id="55756-113">Para obtener información sobre el adaptador de BizTalk Framework, consulte la "¿Cuál es el marco de trabajo?"</span><span class="sxs-lookup"><span data-stu-id="55756-113">For information about the BizTalk Adapter Framework, see the "What Is the Adapter Framework?"</span></span> <span data-ttu-id="55756-114">tema de Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="55756-114">topic in BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="55756-115">En la siguiente ilustración muestra una vista de alto nivel de la arquitectura de FileAct e InterAct.</span><span class="sxs-lookup"><span data-stu-id="55756-115">The following figure shows a high-level view of the FileAct and InterAct architecture.</span></span>  
  
 ![](../../adapters-and-accelerators/fileact-interact/media/035ebb05-ce11-447c-b56b-ba8b41e07e50.gif "035ebb05-ce11-447c-b56b-ba8b41e07e50")  
  
> [!NOTE]
>  <span data-ttu-id="55756-116">Microsoft [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] admite solo las API de vínculo SWIFTNet (SNL) de modo strict.</span><span class="sxs-lookup"><span data-stu-id="55756-116">Microsoft [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] supports only strict mode SWIFTNet Link (SNL) API.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="55756-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="55756-117">In This Section</span></span>  
  
-   [<span data-ttu-id="55756-118">SWIFTNet cliente y servidor</span><span class="sxs-lookup"><span data-stu-id="55756-118">SWIFTNet Client and Server</span></span>](../../adapters-and-accelerators/fileact-interact/swiftnet-client-and-server.md)  
  
-   [<span data-ttu-id="55756-119">Arquitectura del adaptador de envío SWIFT</span><span class="sxs-lookup"><span data-stu-id="55756-119">SWIFT Send Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md)  
  
-   [<span data-ttu-id="55756-120">Arquitectura del adaptador de recepción de SWIFT</span><span class="sxs-lookup"><span data-stu-id="55756-120">SWIFT Receive Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)  
  
-   [<span data-ttu-id="55756-121">Arquitectura del adaptador de FileAct</span><span class="sxs-lookup"><span data-stu-id="55756-121">FileAct Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)  
  
-   [<span data-ttu-id="55756-122">Interactuar de arquitectura de adaptador</span><span class="sxs-lookup"><span data-stu-id="55756-122">InterAct Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)