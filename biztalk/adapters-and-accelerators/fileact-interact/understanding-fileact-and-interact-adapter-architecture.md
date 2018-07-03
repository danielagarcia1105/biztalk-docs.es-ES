---
title: Descripción de FileAct e interactuar de arquitectura de adaptador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f97a7fe-20df-4509-bb6e-53743c3a57df
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a587b70eb3ae603d59dd5a6f21270133b5a8125
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005309"
---
# <a name="understanding-fileact-and-interact-adapter-architecture"></a><span data-ttu-id="4dc9b-102">Descripción de FileAct e interactuar de arquitectura de adaptador</span><span class="sxs-lookup"><span data-stu-id="4dc9b-102">Understanding FileAct and InterAct Adapter Architecture</span></span>
<span data-ttu-id="4dc9b-103">El adaptador de SWIFT se basa en el adaptador de BizTalk Framework.</span><span class="sxs-lookup"><span data-stu-id="4dc9b-103">The SWIFT Adapter is based on the BizTalk Adapter Framework.</span></span> <span data-ttu-id="4dc9b-104">Usa las clasificaciones de los adaptadores de BizTalk Server, los adaptadores de SWIFT, FileAct e InterAct, representan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4dc9b-104">Using the classifications of adapters within BizTalk Server, the SWIFT adapters, FileAct and InterAct, represent the following:</span></span>  
  
- <span data-ttu-id="4dc9b-105">Adaptador personalizado.</span><span class="sxs-lookup"><span data-stu-id="4dc9b-105">Custom Adapter.</span></span> <span data-ttu-id="4dc9b-106">Se trata de un adaptador personalizado creado específicamente para interactuar con la red SWIFT con un estándar propietario denominado FileAct e Interact.</span><span class="sxs-lookup"><span data-stu-id="4dc9b-106">This is a custom adapter built specifically to interact with the SWIFT network using a proprietary standard called FileAct and Interact.</span></span>  
  
- <span data-ttu-id="4dc9b-107">Adaptador de transporte.</span><span class="sxs-lookup"><span data-stu-id="4dc9b-107">Transport Adapter.</span></span> <span data-ttu-id="4dc9b-108">Este adaptador permite la aplicación de software empresarial Enviar y recibir mensajes con la red SWIFT.</span><span class="sxs-lookup"><span data-stu-id="4dc9b-108">This adapter allows business software application to send and receive messages with the SWIFT network.</span></span>  
  
- <span data-ttu-id="4dc9b-109">Sin transacciones.</span><span class="sxs-lookup"><span data-stu-id="4dc9b-109">Non-transacted.</span></span> <span data-ttu-id="4dc9b-110">El adaptador no hace uso de cualquier objeto de transacción para interactuar con la red SWIFT.</span><span class="sxs-lookup"><span data-stu-id="4dc9b-110">The adapter does not make use of any transaction object to interact with the SWIFT network.</span></span>  
  
- <span data-ttu-id="4dc9b-111">Aislado:</span><span class="sxs-lookup"><span data-stu-id="4dc9b-111">Isolated.</span></span> <span data-ttu-id="4dc9b-112">El adaptador de recepción se ejecuta en un proceso independiente y adaptadores de envío normal que se ejecutan en proceso.</span><span class="sxs-lookup"><span data-stu-id="4dc9b-112">The receive adapter runs in a separate process and regular send adapters run in process.</span></span>  
  
  <span data-ttu-id="4dc9b-113">Para obtener información sobre el adaptador de BizTalk Framework, consulte el "¿Cuál es el entorno de adaptador?"</span><span class="sxs-lookup"><span data-stu-id="4dc9b-113">For information about the BizTalk Adapter Framework, see the "What Is the Adapter Framework?"</span></span> <span data-ttu-id="4dc9b-114">tema de Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="4dc9b-114">topic in BizTalk Server Help.</span></span>  
  
  <span data-ttu-id="4dc9b-115">En la siguiente ilustración se muestra una visión general de la arquitectura de FileAct e InterAct.</span><span class="sxs-lookup"><span data-stu-id="4dc9b-115">The following figure shows a high-level view of the FileAct and InterAct architecture.</span></span>  
  
  <span data-ttu-id="4dc9b-116">![](../../adapters-and-accelerators/fileact-interact/media/035ebb05-ce11-447c-b56b-ba8b41e07e50.gif "035ebb05-ce11-447c-b56b-ba8b41e07e50")</span><span class="sxs-lookup"><span data-stu-id="4dc9b-116">![](../../adapters-and-accelerators/fileact-interact/media/035ebb05-ce11-447c-b56b-ba8b41e07e50.gif "035ebb05-ce11-447c-b56b-ba8b41e07e50")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4dc9b-117">Microsoft [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] admite solo API SWIFTNet vínculo (SNL) en modo strict.</span><span class="sxs-lookup"><span data-stu-id="4dc9b-117">Microsoft [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] supports only strict mode SWIFTNet Link (SNL) API.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4dc9b-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4dc9b-118">In This Section</span></span>  
  
-   [<span data-ttu-id="4dc9b-119">Cliente y servidor de SWIFTNet</span><span class="sxs-lookup"><span data-stu-id="4dc9b-119">SWIFTNet Client and Server</span></span>](../../adapters-and-accelerators/fileact-interact/swiftnet-client-and-server.md)  
  
-   [<span data-ttu-id="4dc9b-120">Arquitectura del adaptador de envío de SWIFT</span><span class="sxs-lookup"><span data-stu-id="4dc9b-120">SWIFT Send Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md)  
  
-   [<span data-ttu-id="4dc9b-121">Arquitectura del adaptador de recepción de SWIFT</span><span class="sxs-lookup"><span data-stu-id="4dc9b-121">SWIFT Receive Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)  
  
-   [<span data-ttu-id="4dc9b-122">Arquitectura del adaptador de FileAct</span><span class="sxs-lookup"><span data-stu-id="4dc9b-122">FileAct Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)  
  
-   [<span data-ttu-id="4dc9b-123">Arquitectura del adaptador de InterAct</span><span class="sxs-lookup"><span data-stu-id="4dc9b-123">InterAct Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)