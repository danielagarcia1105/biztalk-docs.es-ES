---
title: "Paso 2: Agregar configuración SWIFTNet a la Paramfile para el escenario de reenvío y almacenamiento de FileAct | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 088ab41f-8325-4330-b6f2-0164aa1911b1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 394e570ad9bd1c0e7532923dac9c2cc702f2f567
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="e81ed-102">Paso 2: Agregar configuración SWIFTNet a la Paramfile para el escenario de reenvío y almacenamiento de FileAct</span><span class="sxs-lookup"><span data-stu-id="e81ed-102">Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="e81ed-103">Los asociados de mensaje de servidor creados en SAG deben especificarse en el paramfile SWIFTNet para permitir que los receptores inicializar con estos valores.</span><span class="sxs-lookup"><span data-stu-id="e81ed-103">The Server message partners created in SAG must be specified in the SWIFTNet paramfile to enable Receivers to initialize with these values.</span></span>  
  
<span data-ttu-id="e81ed-104">Completa [paso 1: configurar el adaptador de SWIFT para el escenario al día y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md) antes de comenzar este paso.</span><span class="sxs-lookup"><span data-stu-id="e81ed-104">Complete [Step 1: Configure the SWIFT Adapter for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md) before you begin this step.</span></span>
  
## <a name="add-swiftnet-configuration-to-the-paramfile"></a><span data-ttu-id="e81ed-105">Agregar configuración SWIFTNet el paramfile</span><span class="sxs-lookup"><span data-stu-id="e81ed-105">Add SWIFTNet configuration to the paramfile</span></span>  
  
1.  <span data-ttu-id="e81ed-106">Abra el paramfile en un editor de texto, como el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="e81ed-106">Open the paramfile in a text editor, such as Notepad.</span></span>  
  
2.  <span data-ttu-id="e81ed-107">Se suele encontrarse en el paramfile: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span><span class="sxs-lookup"><span data-stu-id="e81ed-107">The paramfile is typically located at: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span></span>  
  
3.  <span data-ttu-id="e81ed-108">En el paramfile, realice el cambio resaltado para especificar el nombre del asociado de mensaje de servidor:</span><span class="sxs-lookup"><span data-stu-id="e81ed-108">In the paramfile, make the highlighted change to specify the Server Message partner name:</span></span>  
    
     <span data-ttu-id="e81ed-109">username:snlowner</span><span class="sxs-lookup"><span data-stu-id="e81ed-109">username:snlowner</span></span>  
  
     <span data-ttu-id="e81ed-110">subsystem_name:FileactStub</span><span class="sxs-lookup"><span data-stu-id="e81ed-110">subsystem_name:FileactStub</span></span>  
  
     <span data-ttu-id="e81ed-111">\#subsystem_group:fileactsnf</span><span class="sxs-lookup"><span data-stu-id="e81ed-111">\#subsystem_group:fileactsnf</span></span>  
  
     <span data-ttu-id="e81ed-112">\#subsystem_dependency:support, conjunto</span><span class="sxs-lookup"><span data-stu-id="e81ed-112">\#subsystem_dependency:Support,Swarm</span></span>  
  
     <span data-ttu-id="e81ed-113">subsystem_nature: crítico</span><span class="sxs-lookup"><span data-stu-id="e81ed-113">subsystem_nature:critical</span></span>  
  
     <span data-ttu-id="e81ed-114">subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="e81ed-114">subsystem_start:</span></span>  
  
     <span data-ttu-id="e81ed-115">**spawn "snlreceiver - SagMessagePartner \<MessagePartnerName de servidor para fileact SnF\> - AdapterMode fileact"**</span><span class="sxs-lookup"><span data-stu-id="e81ed-115">**spawn "snlreceiver -SagMessagePartner \<Server MessagePartnerName for fileact SnF\> -AdapterMode fileact"**</span></span>  
  
     <span data-ttu-id="e81ed-116">* FINAL</span><span class="sxs-lookup"><span data-stu-id="e81ed-116">*END</span></span>  
  
     <span data-ttu-id="e81ed-117">subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="e81ed-117">subsystem_stop:</span></span>  
  
     <span data-ttu-id="e81ed-118">* KILL9:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="e81ed-118">*KILL9:snlreceiver</span></span>  
  
     <span data-ttu-id="e81ed-119">* FINAL</span><span class="sxs-lookup"><span data-stu-id="e81ed-119">*END</span></span>  
  
     <span data-ttu-id="e81ed-120">subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="e81ed-120">subsystem_status:</span></span>  
  
     <span data-ttu-id="e81ed-121">* NB:1:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="e81ed-121">*NB:1:snlreceiver</span></span>  
  
     <span data-ttu-id="e81ed-122">* FINAL</span><span class="sxs-lookup"><span data-stu-id="e81ed-122">*END</span></span>  
  
     <span data-ttu-id="e81ed-123">start_event:SNL001:Subsystem FileactStubSnF está activo</span><span class="sxs-lookup"><span data-stu-id="e81ed-123">start_event:SNL001:subsystem FileactStubSnF is up</span></span>  
  
     <span data-ttu-id="e81ed-124">stop_event:SNL002:Subsystem FileactStubSnF está inactivo</span><span class="sxs-lookup"><span data-stu-id="e81ed-124">stop_event:SNL002:subsystem FileactStubSnF is down</span></span>  
  
     <span data-ttu-id="e81ed-125">\#subsystem_name:User</span><span class="sxs-lookup"><span data-stu-id="e81ed-125">\#subsystem_name:User</span></span>  
  
     <span data-ttu-id="e81ed-126">\##subsystem_group:user</span><span class="sxs-lookup"><span data-stu-id="e81ed-126">\##subsystem_group:user</span></span>  
  
     <span data-ttu-id="e81ed-127">\##subsystem_dependency:</span><span class="sxs-lookup"><span data-stu-id="e81ed-127">\##subsystem_dependency:</span></span>  
  
     <span data-ttu-id="e81ed-128">\#subsystem_nature: crítico</span><span class="sxs-lookup"><span data-stu-id="e81ed-128">\#subsystem_nature:critical</span></span>  
  
     <span data-ttu-id="e81ed-129">\#subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="e81ed-129">\#subsystem_start:</span></span>  
  
     <span data-ttu-id="e81ed-130">\#* FINAL</span><span class="sxs-lookup"><span data-stu-id="e81ed-130">\#*END</span></span>  
  
     <span data-ttu-id="e81ed-131">\#subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="e81ed-131">\#subsystem_stop:</span></span>  
  
     <span data-ttu-id="e81ed-132">\#* FINAL</span><span class="sxs-lookup"><span data-stu-id="e81ed-132">\#*END</span></span>  
  
     <span data-ttu-id="e81ed-133">\#subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="e81ed-133">\#subsystem_status:</span></span>  
  
     <span data-ttu-id="e81ed-134">\#* FINAL</span><span class="sxs-lookup"><span data-stu-id="e81ed-134">\#*END</span></span>  
  
     #<a name="starteventsnl001subsystem-user-is-up"></a><span data-ttu-id="e81ed-135">start_event:SNL001:Subsystem usuario está activo</span><span class="sxs-lookup"><span data-stu-id="e81ed-135">start_event:SNL001:subsystem User is up</span></span>  
  
     #<a name="stopeventsnl002subsystem-user-is-down"></a><span data-ttu-id="e81ed-136">stop_event:SNL002:Subsystem usuario está inactivo</span><span class="sxs-lookup"><span data-stu-id="e81ed-136">stop_event:SNL002:subsystem User is down</span></span>  
    
  
## <a name="complete-steps"></a><span data-ttu-id="e81ed-137">Complete los pasos</span><span class="sxs-lookup"><span data-stu-id="e81ed-137">Complete steps</span></span>
 <span data-ttu-id="e81ed-138">[Escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="e81ed-138">[FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="e81ed-139">[Paso 1: Configurar el adaptador de SWIFT para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="e81ed-139">[Step 1: Configure the SWIFT Adapter for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="e81ed-140">[Paso 3: Crear puertos de envío y puertos de recepción para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="e81ed-140">[Step 3: Create Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="e81ed-141">Paso 4: Probar el escenario integral de almacenamiento y reenvío de FileAct</span><span class="sxs-lookup"><span data-stu-id="e81ed-141">Step 4: Test FileAct Store and Forward End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)