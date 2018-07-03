---
title: 'Paso 2: Agregar la configuración de SWIFTNet al archivo de parámetros para el escenario en tiempo real de InterAct | Microsoft Docs'
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
ms.openlocfilehash: d36758716fb368760e9a93909f70bf4d92c5f840
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992457"
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-interact-real-time-scenario"></a><span data-ttu-id="33cf6-102">Paso 2: Agregar la configuración de SWIFTNet al archivo de parámetros para el escenario en tiempo real de InterAct</span><span class="sxs-lookup"><span data-stu-id="33cf6-102">Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="33cf6-103">Los socios de mensaje de servidor que creó en SAG deben especificarse en el archivo de parámetros de SWIFTNet para habilitar destinatarios inicializar con estos valores.</span><span class="sxs-lookup"><span data-stu-id="33cf6-103">The Server message partners created in SAG must be specified in the SWIFTNet paramfile to enable Receivers to initialize with these values.</span></span> <span data-ttu-id="33cf6-104">Antes de comenzar el procedimiento, debe completar las instrucciones de [paso 1: configurar el adaptador de SWIFT para el escenario en tiempo real interactuar](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="33cf6-104">Before you begin the procedure, you must complete the instructions in [Step 1: Configure the SWIFT Adapter for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md).</span></span>  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a><span data-ttu-id="33cf6-105">Para agregar la configuración de SWIFTNet al archivo de parámetros</span><span class="sxs-lookup"><span data-stu-id="33cf6-105">To add SWIFTNet configuration to the paramfile</span></span>  
  
1. <span data-ttu-id="33cf6-106">Abra el archivo de parámetros en un editor de texto como Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="33cf6-106">Open the paramfile in a text editor, such as Notepad.</span></span>  
  
    <span data-ttu-id="33cf6-107">Se suele encontrarse en el archivo de parámetros: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span><span class="sxs-lookup"><span data-stu-id="33cf6-107">The paramfile is typically located at: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span></span>  
  
2. <span data-ttu-id="33cf6-108">En el archivo de parámetros, realice el cambio resaltado para especificar el nombre del mensaje del servidor asociado:</span><span class="sxs-lookup"><span data-stu-id="33cf6-108">In the paramfile, make the highlighted change to specify the Server Message partner name:</span></span>  
  
    <span data-ttu-id="33cf6-109">username:snlowner</span><span class="sxs-lookup"><span data-stu-id="33cf6-109">username:snlowner</span></span>  
  
    <span data-ttu-id="33cf6-110">subsystem_name:InteractStub</span><span class="sxs-lookup"><span data-stu-id="33cf6-110">subsystem_name:InteractStub</span></span>  
  
    <span data-ttu-id="33cf6-111">\#subsystem_group:InteractRT</span><span class="sxs-lookup"><span data-stu-id="33cf6-111">\#subsystem_group:InteractRT</span></span>  
  
    <span data-ttu-id="33cf6-112">\#subsystem_dependency:support, Swarm</span><span class="sxs-lookup"><span data-stu-id="33cf6-112">\#subsystem_dependency:Support,Swarm</span></span>  
  
    <span data-ttu-id="33cf6-113">subsystem_nature: crítico</span><span class="sxs-lookup"><span data-stu-id="33cf6-113">subsystem_nature:critical</span></span>  
  
    <span data-ttu-id="33cf6-114">subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="33cf6-114">subsystem_start:</span></span>  
  
    <span data-ttu-id="33cf6-115">**spawn "snlreceiver - SagMessagePartner \<MessagePartnerName de servidor para interactuar RT \> - AdapterMode Interact"**</span><span class="sxs-lookup"><span data-stu-id="33cf6-115">**spawn "snlreceiver -SagMessagePartner \<Server MessagePartnerName for Interact RT \> -AdapterMode Interact"**</span></span>  
  
    <span data-ttu-id="33cf6-116">\* FINAL</span><span class="sxs-lookup"><span data-stu-id="33cf6-116">\*END</span></span>  
  
    <span data-ttu-id="33cf6-117">subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="33cf6-117">subsystem_stop:</span></span>  
  
    <span data-ttu-id="33cf6-118">\* KILL9:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="33cf6-118">\*KILL9:snlreceiver</span></span>  
  
    <span data-ttu-id="33cf6-119">\* FINAL</span><span class="sxs-lookup"><span data-stu-id="33cf6-119">\*END</span></span>  
  
    <span data-ttu-id="33cf6-120">subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="33cf6-120">subsystem_status:</span></span>  
  
    <span data-ttu-id="33cf6-121">\* NB:1:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="33cf6-121">\*NB:1:snlreceiver</span></span>  
  
    <span data-ttu-id="33cf6-122">\* FINAL</span><span class="sxs-lookup"><span data-stu-id="33cf6-122">\*END</span></span>  
  
    <span data-ttu-id="33cf6-123">start_event:SNL001:Subsystem InteractStub está activo</span><span class="sxs-lookup"><span data-stu-id="33cf6-123">start_event:SNL001:subsystem InteractStub is up</span></span>  
  
    <span data-ttu-id="33cf6-124">stop_event:SNL002:Subsystem InteractStub está inactivo</span><span class="sxs-lookup"><span data-stu-id="33cf6-124">stop_event:SNL002:subsystem InteractStub is down</span></span>  
  
    <span data-ttu-id="33cf6-125">\#subsystem_name:User</span><span class="sxs-lookup"><span data-stu-id="33cf6-125">\#subsystem_name:User</span></span>  
  
    <span data-ttu-id="33cf6-126">\##subsystem_group:user</span><span class="sxs-lookup"><span data-stu-id="33cf6-126">\##subsystem_group:user</span></span>  
  
    <span data-ttu-id="33cf6-127">\##subsystem_dependency:</span><span class="sxs-lookup"><span data-stu-id="33cf6-127">\##subsystem_dependency:</span></span>  
  
    <span data-ttu-id="33cf6-128">\#subsystem_nature: crítico</span><span class="sxs-lookup"><span data-stu-id="33cf6-128">\#subsystem_nature:critical</span></span>  
  
    <span data-ttu-id="33cf6-129">\#subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="33cf6-129">\#subsystem_start:</span></span>  
  
    <span data-ttu-id="33cf6-130">\#\* FINAL</span><span class="sxs-lookup"><span data-stu-id="33cf6-130">\#\*END</span></span>  
  
    <span data-ttu-id="33cf6-131">\#subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="33cf6-131">\#subsystem_stop:</span></span>  
  
    <span data-ttu-id="33cf6-132">\#\* FINAL</span><span class="sxs-lookup"><span data-stu-id="33cf6-132">\#\*END</span></span>  
  
    <span data-ttu-id="33cf6-133">\#subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="33cf6-133">\#subsystem_status:</span></span>  
  
    # <a name="end"></a><span data-ttu-id="33cf6-134">\* FINAL</span><span class="sxs-lookup"><span data-stu-id="33cf6-134">\*END</span></span>  
  
    # <a name="starteventsnl001subsystem-user-is-up"></a><span data-ttu-id="33cf6-135">start_event:SNL001:Subsystem usuario está activo</span><span class="sxs-lookup"><span data-stu-id="33cf6-135">start_event:SNL001:subsystem User is up</span></span>  
  
    # <a name="stopeventsnl002subsystem-user-is-down"></a><span data-ttu-id="33cf6-136">stop_event:SNL002:Subsystem usuario está inactivo</span><span class="sxs-lookup"><span data-stu-id="33cf6-136">stop_event:SNL002:subsystem User is down</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33cf6-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="33cf6-137">See Also</span></span>  
 <span data-ttu-id="33cf6-138">[Escenario en tiempo real de interAct](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="33cf6-138">[InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="33cf6-139">[Paso 1: Configurar el adaptador de SWIFT para el escenario en tiempo real de InterAct](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="33cf6-139">[Step 1: Configure the SWIFT Adapter for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="33cf6-140">[Paso 3: Creación de envío y recepción para el escenario en tiempo real de InterAct](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="33cf6-140">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="33cf6-141">Paso 4: Probar el escenario integral de InterAct en tiempo real</span><span class="sxs-lookup"><span data-stu-id="33cf6-141">Step 4: Test the InterAct Real-Time End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)