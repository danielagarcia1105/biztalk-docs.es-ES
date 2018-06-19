---
title: 'Paso 2: Agregar configuración de SWIFTNet la Paramfile para el escenario en tiempo real de FileAct | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4feec3f-4755-477e-b3d6-1dd6d075255e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adad4d98be93e17bef4ab5eeb9e49271ffc94b74
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963770"
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-fileact-real-time-scenario"></a><span data-ttu-id="bf75a-102">Paso 2: Agregar configuración de SWIFTNet la Paramfile para el escenario en tiempo real de FileAct</span><span class="sxs-lookup"><span data-stu-id="bf75a-102">Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="bf75a-103">Los asociados de mensaje de servidor creados en SAG deben especificarse en el paramfile SWIFTNet para permitir que los receptores inicializar con estos valores.</span><span class="sxs-lookup"><span data-stu-id="bf75a-103">The Server message partners created in SAG must be specified in the SWIFTNet paramfile to enable Receivers to initialize with these values.</span></span>  
  
 <span data-ttu-id="bf75a-104">Antes de comenzar este paso, debe completar [paso 1: configurar el adaptador de SWIFT para el escenario de en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-real-time-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="bf75a-104">Before you begin this step, you must complete [Step 1: Configure the SWIFT Adapter for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-real-time-scenario.md).</span></span>  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a><span data-ttu-id="bf75a-105">Para agregar configuración de SWIFTNet a la paramfile</span><span class="sxs-lookup"><span data-stu-id="bf75a-105">To add SWIFTNet configuration to the paramfile</span></span>  
  
1.  <span data-ttu-id="bf75a-106">Abra el paramfile en un editor de texto, como el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="bf75a-106">Open the paramfile in a text editor, such as Notepad.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bf75a-107">Se suele encontrarse en el paramfile: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span><span class="sxs-lookup"><span data-stu-id="bf75a-107">The paramfile is typically located at: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span></span>  
  
2.  <span data-ttu-id="bf75a-108">En el paramfile, realice el cambio resaltado para especificar el nombre del asociado de mensaje de servidor:</span><span class="sxs-lookup"><span data-stu-id="bf75a-108">In the paramfile, make the highlighted change to specify the Server Message partner name:</span></span>  
  
     <span data-ttu-id="bf75a-109">username:snlowner</span><span class="sxs-lookup"><span data-stu-id="bf75a-109">username:snlowner</span></span>  
  
     <span data-ttu-id="bf75a-110">subsystem_name:FileactStub</span><span class="sxs-lookup"><span data-stu-id="bf75a-110">subsystem_name:FileactStub</span></span>  
  
     <span data-ttu-id="bf75a-111">\#subsystem_group:fileact</span><span class="sxs-lookup"><span data-stu-id="bf75a-111">\#subsystem_group:fileact</span></span>  
  
     <span data-ttu-id="bf75a-112">\#subsystem_dependency:support, conjunto</span><span class="sxs-lookup"><span data-stu-id="bf75a-112">\#subsystem_dependency:Support,Swarm</span></span>  
  
     <span data-ttu-id="bf75a-113">subsystem_nature: crítico</span><span class="sxs-lookup"><span data-stu-id="bf75a-113">subsystem_nature:critical</span></span>  
  
     <span data-ttu-id="bf75a-114">subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="bf75a-114">subsystem_start:</span></span>  
  
     <span data-ttu-id="bf75a-115">**spawn "snlreceiver - SagMessagePartner \<MessagePartnerName de servidor para fileact RT \> fileact - AdapterMode"**</span><span class="sxs-lookup"><span data-stu-id="bf75a-115">**spawn "snlreceiver -SagMessagePartner \<Server MessagePartnerName for fileact RT \> -AdapterMode fileact"**</span></span>  
  
     <span data-ttu-id="bf75a-116">\* FINAL</span><span class="sxs-lookup"><span data-stu-id="bf75a-116">\*END</span></span>  
  
     <span data-ttu-id="bf75a-117">subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="bf75a-117">subsystem_stop:</span></span>  
  
     <span data-ttu-id="bf75a-118">\* KILL9:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="bf75a-118">\*KILL9:snlreceiver</span></span>  
  
     <span data-ttu-id="bf75a-119">\* FINAL</span><span class="sxs-lookup"><span data-stu-id="bf75a-119">\*END</span></span>  
  
     <span data-ttu-id="bf75a-120">subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="bf75a-120">subsystem_status:</span></span>  
  
     <span data-ttu-id="bf75a-121">\* NB:1:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="bf75a-121">\*NB:1:snlreceiver</span></span>  
  
     <span data-ttu-id="bf75a-122">\* FINAL</span><span class="sxs-lookup"><span data-stu-id="bf75a-122">\*END</span></span>  
  
     <span data-ttu-id="bf75a-123">start_event:SNL001:Subsystem FileactStub está activo</span><span class="sxs-lookup"><span data-stu-id="bf75a-123">start_event:SNL001:subsystem FileactStub is up</span></span>  
  
     <span data-ttu-id="bf75a-124">stop_event:SNL002:Subsystem FileactStub está inactivo</span><span class="sxs-lookup"><span data-stu-id="bf75a-124">stop_event:SNL002:subsystem FileactStub is down</span></span>  
  
     <span data-ttu-id="bf75a-125">\#subsystem_name:User</span><span class="sxs-lookup"><span data-stu-id="bf75a-125">\#subsystem_name:User</span></span>  
  
     <span data-ttu-id="bf75a-126">\##subsystem_group:user</span><span class="sxs-lookup"><span data-stu-id="bf75a-126">\##subsystem_group:user</span></span>  
  
     <span data-ttu-id="bf75a-127">\##subsystem_dependency:</span><span class="sxs-lookup"><span data-stu-id="bf75a-127">\##subsystem_dependency:</span></span>  
  
     <span data-ttu-id="bf75a-128">\#subsystem_nature: crítico</span><span class="sxs-lookup"><span data-stu-id="bf75a-128">\#subsystem_nature:critical</span></span>  
  
     <span data-ttu-id="bf75a-129">\#subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="bf75a-129">\#subsystem_start:</span></span>  
  
     <span data-ttu-id="bf75a-130">\#\* FINAL</span><span class="sxs-lookup"><span data-stu-id="bf75a-130">\#\*END</span></span>  
  
     <span data-ttu-id="bf75a-131">\#subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="bf75a-131">\#subsystem_stop:</span></span>  
  
     <span data-ttu-id="bf75a-132">\#\* FINAL</span><span class="sxs-lookup"><span data-stu-id="bf75a-132">\#\*END</span></span>  
  
     <span data-ttu-id="bf75a-133">\#subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="bf75a-133">\#subsystem_status:</span></span>  
  
     #<a name="end"></a><span data-ttu-id="bf75a-134">\* FINAL</span><span class="sxs-lookup"><span data-stu-id="bf75a-134">\*END</span></span>  
  
     #<a name="starteventsnl001subsystem-user-is-up"></a><span data-ttu-id="bf75a-135">start_event:SNL001:Subsystem usuario está activo</span><span class="sxs-lookup"><span data-stu-id="bf75a-135">start_event:SNL001:subsystem User is up</span></span>  
  
     #<a name="stopeventsnl002subsystem-user-is-down"></a><span data-ttu-id="bf75a-136">stop_event:SNL002:Subsystem usuario está inactivo</span><span class="sxs-lookup"><span data-stu-id="bf75a-136">stop_event:SNL002:subsystem User is down</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf75a-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf75a-137">See Also</span></span>  
 <span data-ttu-id="bf75a-138">[Escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="bf75a-138">[FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="bf75a-139">[Paso 1: Configurar el adaptador de SWIFT para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="bf75a-139">[Step 1: Configure the SWIFT Adapter for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="bf75a-140">[Paso 3: Crear los puertos de envío y puertos de recepción para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="bf75a-140">[Step 3: Create the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="bf75a-141">Paso 4: Probar el escenario integral de FileAct en tiempo real</span><span class="sxs-lookup"><span data-stu-id="bf75a-141">Step 4: Test FileAct Real-Time End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md)