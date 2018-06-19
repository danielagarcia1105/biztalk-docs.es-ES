---
title: 'Paso 2: Agregar configuración de SWIFTNet la Paramfile para el almacén de interacción y el escenario de reenvío | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a18a43c-1dd9-4113-bf32-8bc7bf9338b0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05524abd4cd57b8d804ab5995072905392fd3645
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963130"
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="3b9b5-102">Paso 2: Agregar configuración de SWIFTNet la Paramfile para el almacén de interacción y el escenario de reenvío</span><span class="sxs-lookup"><span data-stu-id="3b9b5-102">Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="3b9b5-103">Los asociados de mensaje de servidor creados en SAG deben especificarse en el paramfile SWIFTNet para permitir que los receptores inicializar con estos valores.</span><span class="sxs-lookup"><span data-stu-id="3b9b5-103">The Server message partners created in SAG must be specified in the SWIFTNet paramfile to enable Receivers to initialize with these values.</span></span>  
  
 <span data-ttu-id="3b9b5-104">Antes de comenzar este paso, debe completar [paso 1: configurar el adaptador de SWIFT para el almacén de interacción y reenviar escenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="3b9b5-104">Before you begin this step, you must complete [Step 1: Configure the SWIFT Adapter for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a><span data-ttu-id="3b9b5-105">Para agregar configuración de SWIFTNet a la paramfile</span><span class="sxs-lookup"><span data-stu-id="3b9b5-105">To add SWIFTNet configuration to the paramfile</span></span>  
  
1.  <span data-ttu-id="3b9b5-106">Abra el paramfile en un editor de texto, como el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="3b9b5-106">Open the paramfile in a text editor, such as Notepad.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3b9b5-107">Se suele encontrarse en el paramfile: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile.</span><span class="sxs-lookup"><span data-stu-id="3b9b5-107">The paramfile is typically located at: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile.</span></span>  
  
2.  <span data-ttu-id="3b9b5-108">En el paramfile, realice el cambio resaltado para especificar el nombre del asociado de mensaje de servidor:</span><span class="sxs-lookup"><span data-stu-id="3b9b5-108">In the paramfile, make the highlighted change to specify the Server Message partner name:</span></span>  
  
     <span data-ttu-id="3b9b5-109">username:snlowner</span><span class="sxs-lookup"><span data-stu-id="3b9b5-109">username:snlowner</span></span>  
  
     <span data-ttu-id="3b9b5-110">subsystem_name:InteractStub</span><span class="sxs-lookup"><span data-stu-id="3b9b5-110">subsystem_name:InteractStub</span></span>  
  
     <span data-ttu-id="3b9b5-111">\#subsystem_group:Interactsnf</span><span class="sxs-lookup"><span data-stu-id="3b9b5-111">\#subsystem_group:Interactsnf</span></span>  
  
     <span data-ttu-id="3b9b5-112">\#subsystem_dependency:support, conjunto</span><span class="sxs-lookup"><span data-stu-id="3b9b5-112">\#subsystem_dependency:Support,Swarm</span></span>  
  
     <span data-ttu-id="3b9b5-113">subsystem_nature: crítico</span><span class="sxs-lookup"><span data-stu-id="3b9b5-113">subsystem_nature:critical</span></span>  
  
     <span data-ttu-id="3b9b5-114">subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="3b9b5-114">subsystem_start:</span></span>  
  
     <span data-ttu-id="3b9b5-115">**spawn "snlreceiver - SagMessagePartner \<MessagePartnerName de servidor para interactuar SnF\> - AdapterMode Interact"**</span><span class="sxs-lookup"><span data-stu-id="3b9b5-115">**spawn "snlreceiver -SagMessagePartner \<Server MessagePartnerName for Interact SnF\> -AdapterMode Interact"**</span></span>  
  
     <span data-ttu-id="3b9b5-116">\* FINAL</span><span class="sxs-lookup"><span data-stu-id="3b9b5-116">\*END</span></span>  
  
     <span data-ttu-id="3b9b5-117">subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="3b9b5-117">subsystem_stop:</span></span>  
  
     <span data-ttu-id="3b9b5-118">\* KILL9:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="3b9b5-118">\*KILL9:snlreceiver</span></span>  
  
     <span data-ttu-id="3b9b5-119">\* FINAL</span><span class="sxs-lookup"><span data-stu-id="3b9b5-119">\*END</span></span>  
  
     <span data-ttu-id="3b9b5-120">subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="3b9b5-120">subsystem_status:</span></span>  
  
     <span data-ttu-id="3b9b5-121">\* NB:1:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="3b9b5-121">\*NB:1:snlreceiver</span></span>  
  
     <span data-ttu-id="3b9b5-122">\* FINAL</span><span class="sxs-lookup"><span data-stu-id="3b9b5-122">\*END</span></span>  
  
     <span data-ttu-id="3b9b5-123">start_event:SNL001:Subsystem InteractStubSnF está activo</span><span class="sxs-lookup"><span data-stu-id="3b9b5-123">start_event:SNL001:subsystem InteractStubSnF is up</span></span>  
  
     <span data-ttu-id="3b9b5-124">stop_event:SNL002:Subsystem InteractStubSnF está inactivo</span><span class="sxs-lookup"><span data-stu-id="3b9b5-124">stop_event:SNL002:subsystem InteractStubSnF is down</span></span>  
  
     <span data-ttu-id="3b9b5-125">\#subsystem_name:User</span><span class="sxs-lookup"><span data-stu-id="3b9b5-125">\#subsystem_name:User</span></span>  
  
     <span data-ttu-id="3b9b5-126">\##subsystem_group:user</span><span class="sxs-lookup"><span data-stu-id="3b9b5-126">\##subsystem_group:user</span></span>  
  
     <span data-ttu-id="3b9b5-127">\##subsystem_dependency:</span><span class="sxs-lookup"><span data-stu-id="3b9b5-127">\##subsystem_dependency:</span></span>  
  
     <span data-ttu-id="3b9b5-128">\#subsystem_nature: crítico</span><span class="sxs-lookup"><span data-stu-id="3b9b5-128">\#subsystem_nature:critical</span></span>  
  
     <span data-ttu-id="3b9b5-129">\#subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="3b9b5-129">\#subsystem_start:</span></span>  
  
     <span data-ttu-id="3b9b5-130">\#\* FINAL</span><span class="sxs-lookup"><span data-stu-id="3b9b5-130">\#\*END</span></span>  
  
     <span data-ttu-id="3b9b5-131">\#subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="3b9b5-131">\#subsystem_stop:</span></span>  
  
     <span data-ttu-id="3b9b5-132">\#\* FINAL</span><span class="sxs-lookup"><span data-stu-id="3b9b5-132">\#\*END</span></span>  
  
     <span data-ttu-id="3b9b5-133">\#subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="3b9b5-133">\#subsystem_status:</span></span>  
  
     <span data-ttu-id="3b9b5-134">\#\* FINAL</span><span class="sxs-lookup"><span data-stu-id="3b9b5-134">\#\*END</span></span>  
  
     #<a name="starteventsnl001subsystem-user-is-up"></a><span data-ttu-id="3b9b5-135">start_event:SNL001:Subsystem usuario está activo</span><span class="sxs-lookup"><span data-stu-id="3b9b5-135">start_event:SNL001:subsystem User is up</span></span>  
  
     #<a name="stopeventsnl002subsystem-user-is-down"></a><span data-ttu-id="3b9b5-136">stop_event:SNL002:Subsystem usuario está inactivo</span><span class="sxs-lookup"><span data-stu-id="3b9b5-136">stop_event:SNL002:subsystem User is down</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b9b5-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b9b5-137">See Also</span></span>  
 <span data-ttu-id="3b9b5-138">[Interactuar almacén y escenario de reenvío (inserción)](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="3b9b5-138">[InterAct Store and Forward (Push) Scenario](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span></span>  
 <span data-ttu-id="3b9b5-139">[Paso 1: Configurar el adaptador de SWIFT para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="3b9b5-139">[Step 1: Configure the SWIFT Adapter for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="3b9b5-140">[Paso 3: Crear puertos de envío y puertos de recepción para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="3b9b5-140">[Step 3: Create Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="3b9b5-141">Paso 4: Probar el escenario integral de almacenamiento y reenvío de InterAct</span><span class="sxs-lookup"><span data-stu-id="3b9b5-141">Step 4: Test the InterAct Store and Forward End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)