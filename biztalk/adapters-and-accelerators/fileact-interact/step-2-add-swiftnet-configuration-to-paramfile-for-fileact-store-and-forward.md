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
ms.openlocfilehash: 9b3048198747dd8d283ea9f7b329db27db615436
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="4ef3c-102">Paso 2: Agregar configuración SWIFTNet a la Paramfile para el escenario de reenvío y almacenamiento de FileAct</span><span class="sxs-lookup"><span data-stu-id="4ef3c-102">Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="4ef3c-103">Los asociados de mensaje de servidor creados en SAG deben especificarse en el paramfile SWIFTNet para permitir que los receptores inicializar con estos valores.</span><span class="sxs-lookup"><span data-stu-id="4ef3c-103">The Server message partners created in SAG must be specified in the SWIFTNet paramfile to enable Receivers to initialize with these values.</span></span>  
  
<span data-ttu-id="4ef3c-104">Completa [paso 1: configurar el adaptador de SWIFT para el escenario al día y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md) antes de comenzar este paso.</span><span class="sxs-lookup"><span data-stu-id="4ef3c-104">Complete [Step 1: Configure the SWIFT Adapter for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md) before you begin this step.</span></span>
  
## <a name="add-swiftnet-configuration-to-the-paramfile"></a><span data-ttu-id="4ef3c-105">Agregar configuración SWIFTNet el paramfile</span><span class="sxs-lookup"><span data-stu-id="4ef3c-105">Add SWIFTNet configuration to the paramfile</span></span>  
  
1.  <span data-ttu-id="4ef3c-106">Abra el paramfile en un editor de texto, como el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="4ef3c-106">Open the paramfile in a text editor, such as Notepad.</span></span>  
  
2.  <span data-ttu-id="4ef3c-107">Se suele encontrarse en el paramfile: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span><span class="sxs-lookup"><span data-stu-id="4ef3c-107">The paramfile is typically located at: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span></span>  
  
3.  <span data-ttu-id="4ef3c-108">En el paramfile, realice el cambio resaltado para especificar el nombre del asociado de mensaje de servidor:</span><span class="sxs-lookup"><span data-stu-id="4ef3c-108">In the paramfile, make the highlighted change to specify the Server Message partner name:</span></span>  
    
     <span data-ttu-id="4ef3c-109">username:snlowner</span><span class="sxs-lookup"><span data-stu-id="4ef3c-109">username:snlowner</span></span>  
  
     <span data-ttu-id="4ef3c-110">subsystem_name:FileactStub</span><span class="sxs-lookup"><span data-stu-id="4ef3c-110">subsystem_name:FileactStub</span></span>  
  
     <span data-ttu-id="4ef3c-111">\#subsystem_group:fileactsnf</span><span class="sxs-lookup"><span data-stu-id="4ef3c-111">\#subsystem_group:fileactsnf</span></span>  
  
     <span data-ttu-id="4ef3c-112">\#subsystem_dependency:support, conjunto</span><span class="sxs-lookup"><span data-stu-id="4ef3c-112">\#subsystem_dependency:Support,Swarm</span></span>  
  
     <span data-ttu-id="4ef3c-113">subsystem_nature: crítico</span><span class="sxs-lookup"><span data-stu-id="4ef3c-113">subsystem_nature:critical</span></span>  
  
     <span data-ttu-id="4ef3c-114">subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="4ef3c-114">subsystem_start:</span></span>  
  
     <span data-ttu-id="4ef3c-115">**spawn "snlreceiver - SagMessagePartner \<MessagePartnerName de servidor para fileact SnF > - AdapterMode fileact"**</span><span class="sxs-lookup"><span data-stu-id="4ef3c-115">**spawn "snlreceiver -SagMessagePartner \<Server MessagePartnerName for fileact SnF> -AdapterMode fileact"**</span></span>  
  
     <span data-ttu-id="4ef3c-116">* FINAL</span><span class="sxs-lookup"><span data-stu-id="4ef3c-116">*END</span></span>  
  
     <span data-ttu-id="4ef3c-117">subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="4ef3c-117">subsystem_stop:</span></span>  
  
     <span data-ttu-id="4ef3c-118">* KILL9:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="4ef3c-118">*KILL9:snlreceiver</span></span>  
  
     <span data-ttu-id="4ef3c-119">* FINAL</span><span class="sxs-lookup"><span data-stu-id="4ef3c-119">*END</span></span>  
  
     <span data-ttu-id="4ef3c-120">subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="4ef3c-120">subsystem_status:</span></span>  
  
     <span data-ttu-id="4ef3c-121">* NB:1:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="4ef3c-121">*NB:1:snlreceiver</span></span>  
  
     <span data-ttu-id="4ef3c-122">* FINAL</span><span class="sxs-lookup"><span data-stu-id="4ef3c-122">*END</span></span>  
  
     <span data-ttu-id="4ef3c-123">start_event:SNL001:Subsystem FileactStubSnF está activo</span><span class="sxs-lookup"><span data-stu-id="4ef3c-123">start_event:SNL001:subsystem FileactStubSnF is up</span></span>  
  
     <span data-ttu-id="4ef3c-124">stop_event:SNL002:Subsystem FileactStubSnF está inactivo</span><span class="sxs-lookup"><span data-stu-id="4ef3c-124">stop_event:SNL002:subsystem FileactStubSnF is down</span></span>  
  
     <span data-ttu-id="4ef3c-125">\#subsystem_name:User</span><span class="sxs-lookup"><span data-stu-id="4ef3c-125">\#subsystem_name:User</span></span>  
  
     <span data-ttu-id="4ef3c-126">\##subsystem_group:user</span><span class="sxs-lookup"><span data-stu-id="4ef3c-126">\##subsystem_group:user</span></span>  
  
     <span data-ttu-id="4ef3c-127">\##subsystem_dependency:</span><span class="sxs-lookup"><span data-stu-id="4ef3c-127">\##subsystem_dependency:</span></span>  
  
     <span data-ttu-id="4ef3c-128">\#subsystem_nature: crítico</span><span class="sxs-lookup"><span data-stu-id="4ef3c-128">\#subsystem_nature:critical</span></span>  
  
     <span data-ttu-id="4ef3c-129">\#subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="4ef3c-129">\#subsystem_start:</span></span>  
  
     <span data-ttu-id="4ef3c-130">\#* FINAL</span><span class="sxs-lookup"><span data-stu-id="4ef3c-130">\#*END</span></span>  
  
     <span data-ttu-id="4ef3c-131">\#subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="4ef3c-131">\#subsystem_stop:</span></span>  
  
     <span data-ttu-id="4ef3c-132">\#* FINAL</span><span class="sxs-lookup"><span data-stu-id="4ef3c-132">\#*END</span></span>  
  
     <span data-ttu-id="4ef3c-133">\#subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="4ef3c-133">\#subsystem_status:</span></span>  
  
     <span data-ttu-id="4ef3c-134">\#* FINAL</span><span class="sxs-lookup"><span data-stu-id="4ef3c-134">\#*END</span></span>  
  
     #<a name="starteventsnl001subsystem-user-is-up"></a><span data-ttu-id="4ef3c-135">start_event:SNL001:Subsystem usuario está activo</span><span class="sxs-lookup"><span data-stu-id="4ef3c-135">start_event:SNL001:subsystem User is up</span></span>  
  
     #<a name="stopeventsnl002subsystem-user-is-down"></a><span data-ttu-id="4ef3c-136">stop_event:SNL002:Subsystem usuario está inactivo</span><span class="sxs-lookup"><span data-stu-id="4ef3c-136">stop_event:SNL002:subsystem User is down</span></span>  
    
  
## <a name="complete-steps"></a><span data-ttu-id="4ef3c-137">Complete los pasos</span><span class="sxs-lookup"><span data-stu-id="4ef3c-137">Complete steps</span></span>
 <span data-ttu-id="4ef3c-138">[Escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="4ef3c-138">[FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="4ef3c-139">[Paso 1: Configurar el adaptador de SWIFT para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="4ef3c-139">[Step 1: Configure the SWIFT Adapter for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="4ef3c-140">[Paso 3: Crear puertos de envío y puertos de recepción para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="4ef3c-140">[Step 3: Create Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="4ef3c-141">Paso 4: Probar el escenario de reenvío-to-End y almacenamiento de FileAct</span><span class="sxs-lookup"><span data-stu-id="4ef3c-141">Step 4: Test FileAct Store and Forward End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)