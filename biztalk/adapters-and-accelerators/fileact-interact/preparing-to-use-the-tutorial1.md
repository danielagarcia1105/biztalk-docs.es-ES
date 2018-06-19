---
title: Preparando para utilizar el SimulationTutorial1 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4a792b2-8351-4ae8-9d7c-75420c00af03
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efedfeb184b8b0105b8622b6b3f068faffd6a906
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225212"
---
# <a name="preparing-to-use-the-tutorial"></a><span data-ttu-id="9451c-102">Preparando para utilizar el Tutorial</span><span class="sxs-lookup"><span data-stu-id="9451c-102">Preparing to Use the Tutorial</span></span>
<span data-ttu-id="9451c-103">Debe hacer lo siguiente antes de usar el tutorial de extremo a extremo de adaptador de A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="9451c-103">You must do the following before using the A4SWIFT adapter end-to-end tutorial.</span></span>  
  
1.  <span data-ttu-id="9451c-104">Para este tutorial, necesitará los siguientes artefactos SWIFT:</span><span class="sxs-lookup"><span data-stu-id="9451c-104">You will need the following SWIFT artifacts for this tutorial:</span></span>  
  
    -   <span data-ttu-id="9451c-105">Puerta de enlace SWIFT Alliance (SAG) 6.1</span><span class="sxs-lookup"><span data-stu-id="9451c-105">SWIFT Alliance Gateway (SAG) 6.1</span></span>  
  
    -   <span data-ttu-id="9451c-106">Acceso remoto (RA) 6.1</span><span class="sxs-lookup"><span data-stu-id="9451c-106">Remote Access (RA) 6.1</span></span>  
  
    -   <span data-ttu-id="9451c-107">SWIFT WebStation 6.0</span><span class="sxs-lookup"><span data-stu-id="9451c-107">SWIFT WebStation 6.0</span></span>  
  
    -   <span data-ttu-id="9451c-108">Vínculo de SWIFTNet (SNL) 6.1</span><span class="sxs-lookup"><span data-stu-id="9451c-108">SWIFTNet Link (SNL) 6.1</span></span>  
  
2.  <span data-ttu-id="9451c-109">Debe configurar SAG: crear el MessagePartners, dos puntos finales y reglas de enrutamiento en SAG y pruebe la conectividad SAG en el equipo donde instale los adaptadores.</span><span class="sxs-lookup"><span data-stu-id="9451c-109">You must configure SAG: create the MessagePartners, End Points, and Routing Rules in SAG, and test SAG connectivity on the computer where you install the adapters.</span></span> <span data-ttu-id="9451c-110">Para obtener información, consulte la documentación de SAG.</span><span class="sxs-lookup"><span data-stu-id="9451c-110">For information, see the SAG documentation.</span></span>  
  
3.  <span data-ttu-id="9451c-111">Siga las instrucciones indicadas en el tema "Cómo para crear un nuevo Host" en la Ayuda de Microsoft BizTalk Server ([http://go.microsoft.com/fwlink/? LinkId = 100422](http://go.microsoft.com/fwlink/?LinkId=100422)) para crear un Host in-process para el adaptador de InterAct, denominado *interacthost*y otro Host en curso para el adaptador de FileAct, denominado *fileacthost*.</span><span class="sxs-lookup"><span data-stu-id="9451c-111">Follow the instructions listed in the topic “How to Create a New Host” in Microsoft BizTalk Server Help ([http://go.microsoft.com/fwlink/?LinkId=100422](http://go.microsoft.com/fwlink/?LinkId=100422)) to create one in-process Host for the InterAct adapter, named *interacthost*, and one in-process Host for the FileAct adapter, named *fileacthost*.</span></span> <span data-ttu-id="9451c-112">Utilizará estos hosts durante la creación de controladores para los adaptadores.</span><span class="sxs-lookup"><span data-stu-id="9451c-112">You will use these hosts while creating handlers for the adapters.</span></span>  
  
4.  <span data-ttu-id="9451c-113">Cree las siguientes carpetas para el tutorial:</span><span class="sxs-lookup"><span data-stu-id="9451c-113">Create the following folders for the tutorial:</span></span>  
  
    -   <span data-ttu-id="9451c-114">c:\SWIFTAdapterTutorial\Fileact\ClientLocation</span><span class="sxs-lookup"><span data-stu-id="9451c-114">c:\SWIFTAdapterTutorial\Fileact\ClientLocation</span></span>  
  
    -   <span data-ttu-id="9451c-115">c:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime</span><span class="sxs-lookup"><span data-stu-id="9451c-115">c:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime</span></span>  
  
    -   <span data-ttu-id="9451c-116">c:\SWIFTAdapterTutorial\Fileact\ResponseClient</span><span class="sxs-lookup"><span data-stu-id="9451c-116">c:\SWIFTAdapterTutorial\Fileact\ResponseClient</span></span>  
  
    -   <span data-ttu-id="9451c-117">c:\SWIFTAdapterTutorial\Fileact\ResponseServer</span><span class="sxs-lookup"><span data-stu-id="9451c-117">c:\SWIFTAdapterTutorial\Fileact\ResponseServer</span></span>  
  
    -   <span data-ttu-id="9451c-118">c:\SWIFTAdapterTutorial\Fileact\ServerLocation</span><span class="sxs-lookup"><span data-stu-id="9451c-118">c:\SWIFTAdapterTutorial\Fileact\ServerLocation</span></span>  
  
    -   <span data-ttu-id="9451c-119">c:\SWIFTAdapterTutorial\Fileact\StatusEvents</span><span class="sxs-lookup"><span data-stu-id="9451c-119">c:\SWIFTAdapterTutorial\Fileact\StatusEvents</span></span>  
  
    -   <span data-ttu-id="9451c-120">c:\SWIFTAdapterTutorial\Fileact\PullRequest</span><span class="sxs-lookup"><span data-stu-id="9451c-120">c:\SWIFTAdapterTutorial\Fileact\PullRequest</span></span>  
  
    -   <span data-ttu-id="9451c-121">c:\SWIFTAdapterTutorial\Fileact\PullResponse</span><span class="sxs-lookup"><span data-stu-id="9451c-121">c:\SWIFTAdapterTutorial\Fileact\PullResponse</span></span>  
  
    -   <span data-ttu-id="9451c-122">c:\SWIFTAdapterTutorial\Interact\HandleRequest</span><span class="sxs-lookup"><span data-stu-id="9451c-122">c:\SWIFTAdapterTutorial\Interact\HandleRequest</span></span>  
  
    -   <span data-ttu-id="9451c-123">c:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime</span><span class="sxs-lookup"><span data-stu-id="9451c-123">c:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime</span></span>  
  
    -   <span data-ttu-id="9451c-124">c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF</span><span class="sxs-lookup"><span data-stu-id="9451c-124">c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF</span></span>  
  
    -   <span data-ttu-id="9451c-125">c:\SWIFTAdapterTutorial\Interact\Response</span><span class="sxs-lookup"><span data-stu-id="9451c-125">c:\SWIFTAdapterTutorial\Interact\Response</span></span>  
  
    -   <span data-ttu-id="9451c-126">c:\SWIFTAdapterTutorial\Interact\PullRequest</span><span class="sxs-lookup"><span data-stu-id="9451c-126">c:\SWIFTAdapterTutorial\Interact\PullRequest</span></span>  
  
    -   <span data-ttu-id="9451c-127">c:\SWIFTAdapterTutorial\Interact\Pullresponse</span><span class="sxs-lookup"><span data-stu-id="9451c-127">c:\SWIFTAdapterTutorial\Interact\Pullresponse</span></span>  
  
5.  <span data-ttu-id="9451c-128">Debe tener una conexión a ITB SWIFT o entorno activo para probar el adaptador.</span><span class="sxs-lookup"><span data-stu-id="9451c-128">You must have a connection to SWIFT ITB or live environment to test the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9451c-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="9451c-129">See Also</span></span>  
 <span data-ttu-id="9451c-130">[BizTalk FileAct e interactuar Tutorial de adaptadores-to-End](../../adapters-and-accelerators/fileact-interact/biztalk-fileact-and-interact-adapters-end-to-end-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="9451c-130">[BizTalk FileAct and InterAct Adapters End-to-End Tutorial](../../adapters-and-accelerators/fileact-interact/biztalk-fileact-and-interact-adapters-end-to-end-tutorial.md) </span></span>  
 <span data-ttu-id="9451c-131">[Interactuar en tiempo real escenario](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="9451c-131">[InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="9451c-132">[Interactuar almacén y escenario de reenvío (inserción)](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="9451c-132">[InterAct Store and Forward (Push) Scenario](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span></span>  
 <span data-ttu-id="9451c-133">[Escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="9451c-133">[FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="9451c-134">Escenario de reenvío y almacenamiento de FileAct</span><span class="sxs-lookup"><span data-stu-id="9451c-134">FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md)