---
title: 'Paso 2: Agregar la configuración de SWIFTNet al archivo de parámetros para el FileAct Store y reenvío | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 088ab41f-8325-4330-b6f2-0164aa1911b1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a287c6063ff60b08a53ec4f05d45da9225f1c30
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998245"
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="2d21c-102">Paso 2: Agregar la configuración de SWIFTNet al archivo de parámetros para el FileAct Store y el reenvío de Interact</span><span class="sxs-lookup"><span data-stu-id="2d21c-102">Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="2d21c-103">Los socios de mensaje de servidor que creó en SAG deben especificarse en el archivo de parámetros de SWIFTNet para habilitar destinatarios inicializar con estos valores.</span><span class="sxs-lookup"><span data-stu-id="2d21c-103">The Server message partners created in SAG must be specified in the SWIFTNet paramfile to enable Receivers to initialize with these values.</span></span>  
  
<span data-ttu-id="2d21c-104">Completa [paso 1: configurar el adaptador de SWIFT para el escenario de hacia delante y FileAct Store](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md) antes de comenzar este paso.</span><span class="sxs-lookup"><span data-stu-id="2d21c-104">Complete [Step 1: Configure the SWIFT Adapter for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md) before you begin this step.</span></span>
  
## <a name="add-swiftnet-configuration-to-the-paramfile"></a><span data-ttu-id="2d21c-105">Agregar la configuración de SWIFTNet al archivo de parámetros</span><span class="sxs-lookup"><span data-stu-id="2d21c-105">Add SWIFTNet configuration to the paramfile</span></span>  
  
1. <span data-ttu-id="2d21c-106">Abra el archivo de parámetros en un editor de texto como Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="2d21c-106">Open the paramfile in a text editor, such as Notepad.</span></span>  
  
2. <span data-ttu-id="2d21c-107">Se suele encontrarse en el archivo de parámetros: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span><span class="sxs-lookup"><span data-stu-id="2d21c-107">The paramfile is typically located at: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span></span>  
  
3. <span data-ttu-id="2d21c-108">En el archivo de parámetros, realice el cambio resaltado para especificar el nombre del mensaje del servidor asociado:</span><span class="sxs-lookup"><span data-stu-id="2d21c-108">In the paramfile, make the highlighted change to specify the Server Message partner name:</span></span>  
    
    <span data-ttu-id="2d21c-109">username:snlowner</span><span class="sxs-lookup"><span data-stu-id="2d21c-109">username:snlowner</span></span>  
  
    <span data-ttu-id="2d21c-110">subsystem_name:FileactStub</span><span class="sxs-lookup"><span data-stu-id="2d21c-110">subsystem_name:FileactStub</span></span>  
  
    <span data-ttu-id="2d21c-111">\#subsystem_group:fileactsnf</span><span class="sxs-lookup"><span data-stu-id="2d21c-111">\#subsystem_group:fileactsnf</span></span>  
  
    <span data-ttu-id="2d21c-112">\#subsystem_dependency:support, Swarm</span><span class="sxs-lookup"><span data-stu-id="2d21c-112">\#subsystem_dependency:Support,Swarm</span></span>  
  
    <span data-ttu-id="2d21c-113">subsystem_nature: crítico</span><span class="sxs-lookup"><span data-stu-id="2d21c-113">subsystem_nature:critical</span></span>  
  
    <span data-ttu-id="2d21c-114">subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="2d21c-114">subsystem_start:</span></span>  
  
    <span data-ttu-id="2d21c-115">**spawn "snlreceiver - SagMessagePartner \<Server MessagePartnerName para fileact SnF\> - AdapterMode fileact"**</span><span class="sxs-lookup"><span data-stu-id="2d21c-115">**spawn "snlreceiver -SagMessagePartner \<Server MessagePartnerName for fileact SnF\> -AdapterMode fileact"**</span></span>  
  
    <span data-ttu-id="2d21c-116">\* FINAL</span><span class="sxs-lookup"><span data-stu-id="2d21c-116">\*END</span></span>  
  
    <span data-ttu-id="2d21c-117">subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="2d21c-117">subsystem_stop:</span></span>  
  
    <span data-ttu-id="2d21c-118">\* KILL9:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="2d21c-118">\*KILL9:snlreceiver</span></span>  
  
    <span data-ttu-id="2d21c-119">\* FINAL</span><span class="sxs-lookup"><span data-stu-id="2d21c-119">\*END</span></span>  
  
    <span data-ttu-id="2d21c-120">subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="2d21c-120">subsystem_status:</span></span>  
  
    <span data-ttu-id="2d21c-121">\* NB:1:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="2d21c-121">\*NB:1:snlreceiver</span></span>  
  
    <span data-ttu-id="2d21c-122">\* FINAL</span><span class="sxs-lookup"><span data-stu-id="2d21c-122">\*END</span></span>  
  
    <span data-ttu-id="2d21c-123">start_event:SNL001:Subsystem FileactStubSnF está activo</span><span class="sxs-lookup"><span data-stu-id="2d21c-123">start_event:SNL001:subsystem FileactStubSnF is up</span></span>  
  
    <span data-ttu-id="2d21c-124">stop_event:SNL002:Subsystem FileactStubSnF está inactivo</span><span class="sxs-lookup"><span data-stu-id="2d21c-124">stop_event:SNL002:subsystem FileactStubSnF is down</span></span>  
  
    <span data-ttu-id="2d21c-125">\#subsystem_name:User</span><span class="sxs-lookup"><span data-stu-id="2d21c-125">\#subsystem_name:User</span></span>  
  
    <span data-ttu-id="2d21c-126">\##subsystem_group:user</span><span class="sxs-lookup"><span data-stu-id="2d21c-126">\##subsystem_group:user</span></span>  
  
    <span data-ttu-id="2d21c-127">\##subsystem_dependency:</span><span class="sxs-lookup"><span data-stu-id="2d21c-127">\##subsystem_dependency:</span></span>  
  
    <span data-ttu-id="2d21c-128">\#subsystem_nature: crítico</span><span class="sxs-lookup"><span data-stu-id="2d21c-128">\#subsystem_nature:critical</span></span>  
  
    <span data-ttu-id="2d21c-129">\#subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="2d21c-129">\#subsystem_start:</span></span>  
  
    <span data-ttu-id="2d21c-130">\#\* FINAL</span><span class="sxs-lookup"><span data-stu-id="2d21c-130">\#\*END</span></span>  
  
    <span data-ttu-id="2d21c-131">\#subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="2d21c-131">\#subsystem_stop:</span></span>  
  
    <span data-ttu-id="2d21c-132">\#\* FINAL</span><span class="sxs-lookup"><span data-stu-id="2d21c-132">\#\*END</span></span>  
  
    <span data-ttu-id="2d21c-133">\#subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="2d21c-133">\#subsystem_status:</span></span>  
  
    <span data-ttu-id="2d21c-134">\#\* FINAL</span><span class="sxs-lookup"><span data-stu-id="2d21c-134">\#\*END</span></span>  
  
    # <a name="starteventsnl001subsystem-user-is-up"></a><span data-ttu-id="2d21c-135">start_event:SNL001:Subsystem usuario está activo</span><span class="sxs-lookup"><span data-stu-id="2d21c-135">start_event:SNL001:subsystem User is up</span></span>  
  
    # <a name="stopeventsnl002subsystem-user-is-down"></a><span data-ttu-id="2d21c-136">stop_event:SNL002:Subsystem usuario está inactivo</span><span class="sxs-lookup"><span data-stu-id="2d21c-136">stop_event:SNL002:subsystem User is down</span></span>  
    
  
## <a name="complete-steps"></a><span data-ttu-id="2d21c-137">Complete los pasos</span><span class="sxs-lookup"><span data-stu-id="2d21c-137">Complete steps</span></span>
 <span data-ttu-id="2d21c-138">[FileAct Store y reenvío de Interact](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="2d21c-138">[FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="2d21c-139">[Paso 1: Configurar el adaptador de SWIFT para el FileAct Store y el reenvío de Interact](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="2d21c-139">[Step 1: Configure the SWIFT Adapter for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="2d21c-140">[Paso 3: Crear puertos de envío y recepción para el FileAct Store y el reenvío de Interact](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="2d21c-140">[Step 3: Create Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="2d21c-141">Paso 4: Probar el escenario integral de almacenamiento y reenvío de FileAct</span><span class="sxs-lookup"><span data-stu-id="2d21c-141">Step 4: Test FileAct Store and Forward End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)