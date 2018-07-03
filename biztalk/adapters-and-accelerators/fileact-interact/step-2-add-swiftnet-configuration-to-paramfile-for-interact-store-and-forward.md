---
title: 'Paso 2: Agregar la configuración de SWIFTNet al archivo de parámetros para la interacción Store y reenvío | Microsoft Docs'
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
ms.openlocfilehash: 9495d6a53e9048dc5dee839f1dc859c62b4e9187
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014501"
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="0fb35-102">Paso 2: Agregar la configuración de SWIFTNet al archivo de parámetros para la interacción Store y el reenvío de Interact</span><span class="sxs-lookup"><span data-stu-id="0fb35-102">Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="0fb35-103">Los socios de mensaje de servidor que creó en SAG deben especificarse en el archivo de parámetros de SWIFTNet para habilitar destinatarios inicializar con estos valores.</span><span class="sxs-lookup"><span data-stu-id="0fb35-103">The Server message partners created in SAG must be specified in the SWIFTNet paramfile to enable Receivers to initialize with these values.</span></span>  
  
 <span data-ttu-id="0fb35-104">Antes de comenzar este paso, debe completar [paso 1: configurar el adaptador de SWIFT para el escenario de hacia delante y Store InterAct](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="0fb35-104">Before you begin this step, you must complete [Step 1: Configure the SWIFT Adapter for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a><span data-ttu-id="0fb35-105">Para agregar la configuración de SWIFTNet al archivo de parámetros</span><span class="sxs-lookup"><span data-stu-id="0fb35-105">To add SWIFTNet configuration to the paramfile</span></span>  
  
1. <span data-ttu-id="0fb35-106">Abra el archivo de parámetros en un editor de texto como Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="0fb35-106">Open the paramfile in a text editor, such as Notepad.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="0fb35-107">Se suele encontrarse en el archivo de parámetros: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile.</span><span class="sxs-lookup"><span data-stu-id="0fb35-107">The paramfile is typically located at: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile.</span></span>  
  
2. <span data-ttu-id="0fb35-108">En el archivo de parámetros, realice el cambio resaltado para especificar el nombre del mensaje del servidor asociado:</span><span class="sxs-lookup"><span data-stu-id="0fb35-108">In the paramfile, make the highlighted change to specify the Server Message partner name:</span></span>  
  
    <span data-ttu-id="0fb35-109">username:snlowner</span><span class="sxs-lookup"><span data-stu-id="0fb35-109">username:snlowner</span></span>  
  
    <span data-ttu-id="0fb35-110">subsystem_name:InteractStub</span><span class="sxs-lookup"><span data-stu-id="0fb35-110">subsystem_name:InteractStub</span></span>  
  
    <span data-ttu-id="0fb35-111">\#subsystem_group:Interactsnf</span><span class="sxs-lookup"><span data-stu-id="0fb35-111">\#subsystem_group:Interactsnf</span></span>  
  
    <span data-ttu-id="0fb35-112">\#subsystem_dependency:support, Swarm</span><span class="sxs-lookup"><span data-stu-id="0fb35-112">\#subsystem_dependency:Support,Swarm</span></span>  
  
    <span data-ttu-id="0fb35-113">subsystem_nature: crítico</span><span class="sxs-lookup"><span data-stu-id="0fb35-113">subsystem_nature:critical</span></span>  
  
    <span data-ttu-id="0fb35-114">subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="0fb35-114">subsystem_start:</span></span>  
  
    <span data-ttu-id="0fb35-115">**spawn "snlreceiver - SagMessagePartner \<MessagePartnerName del servidor de Interact SnF\> - AdapterMode Interact"**</span><span class="sxs-lookup"><span data-stu-id="0fb35-115">**spawn "snlreceiver -SagMessagePartner \<Server MessagePartnerName for Interact SnF\> -AdapterMode Interact"**</span></span>  
  
    <span data-ttu-id="0fb35-116">\* FINAL</span><span class="sxs-lookup"><span data-stu-id="0fb35-116">\*END</span></span>  
  
    <span data-ttu-id="0fb35-117">subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="0fb35-117">subsystem_stop:</span></span>  
  
    <span data-ttu-id="0fb35-118">\* KILL9:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="0fb35-118">\*KILL9:snlreceiver</span></span>  
  
    <span data-ttu-id="0fb35-119">\* FINAL</span><span class="sxs-lookup"><span data-stu-id="0fb35-119">\*END</span></span>  
  
    <span data-ttu-id="0fb35-120">subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="0fb35-120">subsystem_status:</span></span>  
  
    <span data-ttu-id="0fb35-121">\* NB:1:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="0fb35-121">\*NB:1:snlreceiver</span></span>  
  
    <span data-ttu-id="0fb35-122">\* FINAL</span><span class="sxs-lookup"><span data-stu-id="0fb35-122">\*END</span></span>  
  
    <span data-ttu-id="0fb35-123">start_event:SNL001:Subsystem InteractStubSnF está activo</span><span class="sxs-lookup"><span data-stu-id="0fb35-123">start_event:SNL001:subsystem InteractStubSnF is up</span></span>  
  
    <span data-ttu-id="0fb35-124">stop_event:SNL002:Subsystem InteractStubSnF está inactivo</span><span class="sxs-lookup"><span data-stu-id="0fb35-124">stop_event:SNL002:subsystem InteractStubSnF is down</span></span>  
  
    <span data-ttu-id="0fb35-125">\#subsystem_name:User</span><span class="sxs-lookup"><span data-stu-id="0fb35-125">\#subsystem_name:User</span></span>  
  
    <span data-ttu-id="0fb35-126">\##subsystem_group:user</span><span class="sxs-lookup"><span data-stu-id="0fb35-126">\##subsystem_group:user</span></span>  
  
    <span data-ttu-id="0fb35-127">\##subsystem_dependency:</span><span class="sxs-lookup"><span data-stu-id="0fb35-127">\##subsystem_dependency:</span></span>  
  
    <span data-ttu-id="0fb35-128">\#subsystem_nature: crítico</span><span class="sxs-lookup"><span data-stu-id="0fb35-128">\#subsystem_nature:critical</span></span>  
  
    <span data-ttu-id="0fb35-129">\#subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="0fb35-129">\#subsystem_start:</span></span>  
  
    <span data-ttu-id="0fb35-130">\#\* FINAL</span><span class="sxs-lookup"><span data-stu-id="0fb35-130">\#\*END</span></span>  
  
    <span data-ttu-id="0fb35-131">\#subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="0fb35-131">\#subsystem_stop:</span></span>  
  
    <span data-ttu-id="0fb35-132">\#\* FINAL</span><span class="sxs-lookup"><span data-stu-id="0fb35-132">\#\*END</span></span>  
  
    <span data-ttu-id="0fb35-133">\#subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="0fb35-133">\#subsystem_status:</span></span>  
  
    <span data-ttu-id="0fb35-134">\#\* FINAL</span><span class="sxs-lookup"><span data-stu-id="0fb35-134">\#\*END</span></span>  
  
    # <a name="starteventsnl001subsystem-user-is-up"></a><span data-ttu-id="0fb35-135">start_event:SNL001:Subsystem usuario está activo</span><span class="sxs-lookup"><span data-stu-id="0fb35-135">start_event:SNL001:subsystem User is up</span></span>  
  
    # <a name="stopeventsnl002subsystem-user-is-down"></a><span data-ttu-id="0fb35-136">stop_event:SNL002:Subsystem usuario está inactivo</span><span class="sxs-lookup"><span data-stu-id="0fb35-136">stop_event:SNL002:subsystem User is down</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fb35-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="0fb35-137">See Also</span></span>  
 <span data-ttu-id="0fb35-138">[Store y reenvío (inserción) de Interact](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="0fb35-138">[InterAct Store and Forward (Push) Scenario](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span></span>  
 <span data-ttu-id="0fb35-139">[Paso 1: Configurar el adaptador de SWIFT para la interacción Store y el reenvío de Interact](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="0fb35-139">[Step 1: Configure the SWIFT Adapter for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="0fb35-140">[Paso 3: Crear puertos de envío y recepción para la interacción Store y el reenvío de Interact](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="0fb35-140">[Step 3: Create Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="0fb35-141">Paso 4: Probar el escenario integral de almacenamiento y reenvío de InterAct</span><span class="sxs-lookup"><span data-stu-id="0fb35-141">Step 4: Test the InterAct Store and Forward End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)