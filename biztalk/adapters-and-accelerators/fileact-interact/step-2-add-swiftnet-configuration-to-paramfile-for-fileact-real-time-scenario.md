---
title: 'Paso 2: Agregar la configuración de SWIFTNet al archivo de parámetros para el escenario de FileAct en tiempo real | Microsoft Docs'
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
ms.openlocfilehash: f40da4b503a5b29e161b376fc25f535c338f5f42
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010565"
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-fileact-real-time-scenario"></a><span data-ttu-id="f8577-102">Paso 2: Agregar la configuración de SWIFTNet al archivo de parámetros para el escenario de FileAct en tiempo real</span><span class="sxs-lookup"><span data-stu-id="f8577-102">Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="f8577-103">Los socios de mensaje de servidor que creó en SAG deben especificarse en el archivo de parámetros de SWIFTNet para habilitar destinatarios inicializar con estos valores.</span><span class="sxs-lookup"><span data-stu-id="f8577-103">The Server message partners created in SAG must be specified in the SWIFTNet paramfile to enable Receivers to initialize with these values.</span></span>  
  
 <span data-ttu-id="f8577-104">Antes de comenzar este paso, debe completar [paso 1: configurar el adaptador de SWIFT para el escenario de FileAct en tiempo real](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-real-time-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="f8577-104">Before you begin this step, you must complete [Step 1: Configure the SWIFT Adapter for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-real-time-scenario.md).</span></span>  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a><span data-ttu-id="f8577-105">Para agregar la configuración de SWIFTNet al archivo de parámetros</span><span class="sxs-lookup"><span data-stu-id="f8577-105">To add SWIFTNet configuration to the paramfile</span></span>  
  
1. <span data-ttu-id="f8577-106">Abra el archivo de parámetros en un editor de texto como Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="f8577-106">Open the paramfile in a text editor, such as Notepad.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f8577-107">Se suele encontrarse en el archivo de parámetros: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span><span class="sxs-lookup"><span data-stu-id="f8577-107">The paramfile is typically located at: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span></span>  
  
2. <span data-ttu-id="f8577-108">En el archivo de parámetros, realice el cambio resaltado para especificar el nombre del mensaje del servidor asociado:</span><span class="sxs-lookup"><span data-stu-id="f8577-108">In the paramfile, make the highlighted change to specify the Server Message partner name:</span></span>  
  
    <span data-ttu-id="f8577-109">username:snlowner</span><span class="sxs-lookup"><span data-stu-id="f8577-109">username:snlowner</span></span>  
  
    <span data-ttu-id="f8577-110">subsystem_name:FileactStub</span><span class="sxs-lookup"><span data-stu-id="f8577-110">subsystem_name:FileactStub</span></span>  
  
    <span data-ttu-id="f8577-111">\#subsystem_group:fileact</span><span class="sxs-lookup"><span data-stu-id="f8577-111">\#subsystem_group:fileact</span></span>  
  
    <span data-ttu-id="f8577-112">\#subsystem_dependency:support, Swarm</span><span class="sxs-lookup"><span data-stu-id="f8577-112">\#subsystem_dependency:Support,Swarm</span></span>  
  
    <span data-ttu-id="f8577-113">subsystem_nature: crítico</span><span class="sxs-lookup"><span data-stu-id="f8577-113">subsystem_nature:critical</span></span>  
  
    <span data-ttu-id="f8577-114">subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="f8577-114">subsystem_start:</span></span>  
  
    <span data-ttu-id="f8577-115">**spawn "snlreceiver - SagMessagePartner \<Server MessagePartnerName para fileact RT \> fileact - AdapterMode"**</span><span class="sxs-lookup"><span data-stu-id="f8577-115">**spawn "snlreceiver -SagMessagePartner \<Server MessagePartnerName for fileact RT \> -AdapterMode fileact"**</span></span>  
  
    <span data-ttu-id="f8577-116">\* FINAL</span><span class="sxs-lookup"><span data-stu-id="f8577-116">\*END</span></span>  
  
    <span data-ttu-id="f8577-117">subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="f8577-117">subsystem_stop:</span></span>  
  
    <span data-ttu-id="f8577-118">\* KILL9:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="f8577-118">\*KILL9:snlreceiver</span></span>  
  
    <span data-ttu-id="f8577-119">\* FINAL</span><span class="sxs-lookup"><span data-stu-id="f8577-119">\*END</span></span>  
  
    <span data-ttu-id="f8577-120">subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="f8577-120">subsystem_status:</span></span>  
  
    <span data-ttu-id="f8577-121">\* NB:1:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="f8577-121">\*NB:1:snlreceiver</span></span>  
  
    <span data-ttu-id="f8577-122">\* FINAL</span><span class="sxs-lookup"><span data-stu-id="f8577-122">\*END</span></span>  
  
    <span data-ttu-id="f8577-123">start_event:SNL001:Subsystem FileactStub está activo</span><span class="sxs-lookup"><span data-stu-id="f8577-123">start_event:SNL001:subsystem FileactStub is up</span></span>  
  
    <span data-ttu-id="f8577-124">stop_event:SNL002:Subsystem FileactStub está inactivo</span><span class="sxs-lookup"><span data-stu-id="f8577-124">stop_event:SNL002:subsystem FileactStub is down</span></span>  
  
    <span data-ttu-id="f8577-125">\#subsystem_name:User</span><span class="sxs-lookup"><span data-stu-id="f8577-125">\#subsystem_name:User</span></span>  
  
    <span data-ttu-id="f8577-126">\##subsystem_group:user</span><span class="sxs-lookup"><span data-stu-id="f8577-126">\##subsystem_group:user</span></span>  
  
    <span data-ttu-id="f8577-127">\##subsystem_dependency:</span><span class="sxs-lookup"><span data-stu-id="f8577-127">\##subsystem_dependency:</span></span>  
  
    <span data-ttu-id="f8577-128">\#subsystem_nature: crítico</span><span class="sxs-lookup"><span data-stu-id="f8577-128">\#subsystem_nature:critical</span></span>  
  
    <span data-ttu-id="f8577-129">\#subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="f8577-129">\#subsystem_start:</span></span>  
  
    <span data-ttu-id="f8577-130">\#\* FINAL</span><span class="sxs-lookup"><span data-stu-id="f8577-130">\#\*END</span></span>  
  
    <span data-ttu-id="f8577-131">\#subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="f8577-131">\#subsystem_stop:</span></span>  
  
    <span data-ttu-id="f8577-132">\#\* FINAL</span><span class="sxs-lookup"><span data-stu-id="f8577-132">\#\*END</span></span>  
  
    <span data-ttu-id="f8577-133">\#subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="f8577-133">\#subsystem_status:</span></span>  
  
    # <a name="end"></a><span data-ttu-id="f8577-134">\* FINAL</span><span class="sxs-lookup"><span data-stu-id="f8577-134">\*END</span></span>  
  
    # <a name="starteventsnl001subsystem-user-is-up"></a><span data-ttu-id="f8577-135">start_event:SNL001:Subsystem usuario está activo</span><span class="sxs-lookup"><span data-stu-id="f8577-135">start_event:SNL001:subsystem User is up</span></span>  
  
    # <a name="stopeventsnl002subsystem-user-is-down"></a><span data-ttu-id="f8577-136">stop_event:SNL002:Subsystem usuario está inactivo</span><span class="sxs-lookup"><span data-stu-id="f8577-136">stop_event:SNL002:subsystem User is down</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8577-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8577-137">See Also</span></span>  
 <span data-ttu-id="f8577-138">[Escenario de Fileact en tiempo real](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="f8577-138">[FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="f8577-139">[Paso 1: Configurar el adaptador de SWIFT para el escenario de FileAct en tiempo real](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="f8577-139">[Step 1: Configure the SWIFT Adapter for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="f8577-140">[Paso 3: Crear los puertos de envío y recepción para el escenario de FileAct en tiempo real](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="f8577-140">[Step 3: Create the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="f8577-141">Paso 4: Probar el escenario integral de FileAct en tiempo real</span><span class="sxs-lookup"><span data-stu-id="f8577-141">Step 4: Test FileAct Real-Time End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md)