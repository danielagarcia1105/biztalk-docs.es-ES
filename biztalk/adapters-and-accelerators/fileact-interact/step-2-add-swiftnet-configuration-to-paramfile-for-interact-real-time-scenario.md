---
title: 'Paso 2: Agregar configuración SWIFTNet a la Paramfile para el escenario en tiempo real de interactuar | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a900a6e-3e08-430a-8766-4a7192adba5e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e33203279e045b28d2098ca78c55403c7070b64
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964610"
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-interact-real-time-scenario"></a><span data-ttu-id="d7ce4-102">Paso 2: Agregar configuración SWIFTNet a la Paramfile para el escenario en tiempo real de interactuar</span><span class="sxs-lookup"><span data-stu-id="d7ce4-102">Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="d7ce4-103">Los asociados de mensaje de servidor creados en SAG deben especificarse en el paramfile SWIFTNet para permitir que los receptores inicializar con estos valores.</span><span class="sxs-lookup"><span data-stu-id="d7ce4-103">The Server message partners created in SAG must be specified in the SWIFTNet paramfile to enable Receivers to initialize with these values.</span></span> <span data-ttu-id="d7ce4-104">Antes de comenzar el procedimiento, debe completar las instrucciones de [paso 1: configurar el adaptador de SWIFT para el escenario de en tiempo real interactuar](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="d7ce4-104">Before you begin the procedure, you must complete the instructions in [Step 1: Configure the SWIFT Adapter for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md).</span></span>  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a><span data-ttu-id="d7ce4-105">Para agregar configuración de SWIFTNet a la paramfile</span><span class="sxs-lookup"><span data-stu-id="d7ce4-105">To add SWIFTNet configuration to the paramfile</span></span>  
  
1.  <span data-ttu-id="d7ce4-106">Abra el paramfile en un editor de texto, como el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="d7ce4-106">Open the paramfile in a text editor, such as Notepad.</span></span>  
  
     <span data-ttu-id="d7ce4-107">Se suele encontrarse en el paramfile: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span><span class="sxs-lookup"><span data-stu-id="d7ce4-107">The paramfile is typically located at: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span></span>  
  
2.  <span data-ttu-id="d7ce4-108">En el paramfile, realice el cambio resaltado para especificar el nombre del asociado de mensaje de servidor:</span><span class="sxs-lookup"><span data-stu-id="d7ce4-108">In the paramfile, make the highlighted change to specify the Server Message partner name:</span></span>  
  
     <span data-ttu-id="d7ce4-109">username:snlowner</span><span class="sxs-lookup"><span data-stu-id="d7ce4-109">username:snlowner</span></span>  
  
     <span data-ttu-id="d7ce4-110">subsystem_name:InteractStub</span><span class="sxs-lookup"><span data-stu-id="d7ce4-110">subsystem_name:InteractStub</span></span>  
  
     <span data-ttu-id="d7ce4-111">\#subsystem_group:InteractRT</span><span class="sxs-lookup"><span data-stu-id="d7ce4-111">\#subsystem_group:InteractRT</span></span>  
  
     <span data-ttu-id="d7ce4-112">\#subsystem_dependency:support, conjunto</span><span class="sxs-lookup"><span data-stu-id="d7ce4-112">\#subsystem_dependency:Support,Swarm</span></span>  
  
     <span data-ttu-id="d7ce4-113">subsystem_nature: crítico</span><span class="sxs-lookup"><span data-stu-id="d7ce4-113">subsystem_nature:critical</span></span>  
  
     <span data-ttu-id="d7ce4-114">subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="d7ce4-114">subsystem_start:</span></span>  
  
     <span data-ttu-id="d7ce4-115">**spawn "snlreceiver - SagMessagePartner \<MessagePartnerName de servidor para interactuar RT \> - AdapterMode Interact"**</span><span class="sxs-lookup"><span data-stu-id="d7ce4-115">**spawn "snlreceiver -SagMessagePartner \<Server MessagePartnerName for Interact RT \> -AdapterMode Interact"**</span></span>  
  
     <span data-ttu-id="d7ce4-116">\* FINAL</span><span class="sxs-lookup"><span data-stu-id="d7ce4-116">\*END</span></span>  
  
     <span data-ttu-id="d7ce4-117">subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="d7ce4-117">subsystem_stop:</span></span>  
  
     <span data-ttu-id="d7ce4-118">\* KILL9:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="d7ce4-118">\*KILL9:snlreceiver</span></span>  
  
     <span data-ttu-id="d7ce4-119">\* FINAL</span><span class="sxs-lookup"><span data-stu-id="d7ce4-119">\*END</span></span>  
  
     <span data-ttu-id="d7ce4-120">subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="d7ce4-120">subsystem_status:</span></span>  
  
     <span data-ttu-id="d7ce4-121">\* NB:1:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="d7ce4-121">\*NB:1:snlreceiver</span></span>  
  
     <span data-ttu-id="d7ce4-122">\* FINAL</span><span class="sxs-lookup"><span data-stu-id="d7ce4-122">\*END</span></span>  
  
     <span data-ttu-id="d7ce4-123">start_event:SNL001:Subsystem InteractStub está activo</span><span class="sxs-lookup"><span data-stu-id="d7ce4-123">start_event:SNL001:subsystem InteractStub is up</span></span>  
  
     <span data-ttu-id="d7ce4-124">stop_event:SNL002:Subsystem InteractStub está inactivo</span><span class="sxs-lookup"><span data-stu-id="d7ce4-124">stop_event:SNL002:subsystem InteractStub is down</span></span>  
  
     <span data-ttu-id="d7ce4-125">\#subsystem_name:User</span><span class="sxs-lookup"><span data-stu-id="d7ce4-125">\#subsystem_name:User</span></span>  
  
     <span data-ttu-id="d7ce4-126">\##subsystem_group:user</span><span class="sxs-lookup"><span data-stu-id="d7ce4-126">\##subsystem_group:user</span></span>  
  
     <span data-ttu-id="d7ce4-127">\##subsystem_dependency:</span><span class="sxs-lookup"><span data-stu-id="d7ce4-127">\##subsystem_dependency:</span></span>  
  
     <span data-ttu-id="d7ce4-128">\#subsystem_nature: crítico</span><span class="sxs-lookup"><span data-stu-id="d7ce4-128">\#subsystem_nature:critical</span></span>  
  
     <span data-ttu-id="d7ce4-129">\#subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="d7ce4-129">\#subsystem_start:</span></span>  
  
     <span data-ttu-id="d7ce4-130">\#\* FINAL</span><span class="sxs-lookup"><span data-stu-id="d7ce4-130">\#\*END</span></span>  
  
     <span data-ttu-id="d7ce4-131">\#subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="d7ce4-131">\#subsystem_stop:</span></span>  
  
     <span data-ttu-id="d7ce4-132">\#\* FINAL</span><span class="sxs-lookup"><span data-stu-id="d7ce4-132">\#\*END</span></span>  
  
     <span data-ttu-id="d7ce4-133">\#subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="d7ce4-133">\#subsystem_status:</span></span>  
  
     #<a name="end"></a><span data-ttu-id="d7ce4-134">\* FINAL</span><span class="sxs-lookup"><span data-stu-id="d7ce4-134">\*END</span></span>  
  
     #<a name="starteventsnl001subsystem-user-is-up"></a><span data-ttu-id="d7ce4-135">start_event:SNL001:Subsystem usuario está activo</span><span class="sxs-lookup"><span data-stu-id="d7ce4-135">start_event:SNL001:subsystem User is up</span></span>  
  
     #<a name="stopeventsnl002subsystem-user-is-down"></a><span data-ttu-id="d7ce4-136">stop_event:SNL002:Subsystem usuario está inactivo</span><span class="sxs-lookup"><span data-stu-id="d7ce4-136">stop_event:SNL002:subsystem User is down</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7ce4-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7ce4-137">See Also</span></span>  
 <span data-ttu-id="d7ce4-138">[Interactuar en tiempo real escenario](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d7ce4-138">[InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="d7ce4-139">[Paso 1: Configurar el adaptador de SWIFT para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d7ce4-139">[Step 1: Configure the SWIFT Adapter for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="d7ce4-140">[Paso 3: Crear el envío y puertos de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d7ce4-140">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="d7ce4-141">Paso 4: Probar el escenario integral de InterAct en tiempo real</span><span class="sxs-lookup"><span data-stu-id="d7ce4-141">Step 4: Test the InterAct Real-Time End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)