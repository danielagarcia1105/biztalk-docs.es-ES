---
title: 'Lección 2: Confirmar la implementación mediante la herramienta de Compositor de reglas de negocios | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, verifying
- verifying, business rules
- verifying, Business Rule Composer tool
- business rules, Business Rule Composer tool
- Business Rule Composer tool
ms.assetid: 337dc469-cf9e-406b-90ae-0f580b17d7c9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3115dc425fedca9019f0e5e5171f7234e6fbdbb2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210244"
---
# <a name="lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool"></a><span data-ttu-id="525dd-102">Lección 2: Confirmar la implementación mediante la herramienta de Compositor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="525dd-102">Lesson 2: Confirming the Deployment Using the Business Rule Composer Tool</span></span>
<span data-ttu-id="525dd-103">En esta lección, confirme que la herramienta de Compositor de reglas de negocios creado los vocabularios e implementado las directivas.</span><span class="sxs-lookup"><span data-stu-id="525dd-103">In this lesson, you confirm that the Business Rule Composer tool created your vocabularies and deployed your policies.</span></span> <span data-ttu-id="525dd-104">Un vocabulario es una colección de elementos de vocabulario utilizados en la composición de regla.</span><span class="sxs-lookup"><span data-stu-id="525dd-104">A vocabulary is a collection of vocabulary elements you use in rule composition.</span></span> <span data-ttu-id="525dd-105">Las directivas son colecciones de reglas de negocios y tienen asignada una versión.</span><span class="sxs-lookup"><span data-stu-id="525dd-105">A policy is a versioned collection of business rules.</span></span>  
  
### <a name="to-confirm-the-deployment-using-the-business-rule-composer-tool"></a><span data-ttu-id="525dd-106">Para confirmar la implementación mediante la herramienta de Compositor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="525dd-106">To confirm the deployment using the Business Rule Composer tool</span></span>  
  
1.  <span data-ttu-id="525dd-107">Iniciar **Compositor de reglas de negocios** en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="525dd-107">Start **Business Rule Composer** in BizTalk Server.</span></span>  
  
2.  <span data-ttu-id="525dd-108">En el cuadro de diálogo Abrir almacén de reglas, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="525dd-108">In the Open Rule Store dialog box, click **OK**.</span></span>  
  
3.  <span data-ttu-id="525dd-109">En el panel Explorador de hechos de la herramienta de Compositor de reglas de negocios, confirme que los vocabularios que desea que aparezcan en el Explorador de hechos, como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="525dd-109">In the Facts Explorer pane of the Business Rule Composer tool, confirm that the vocabularies you want appear in the Facts Explorer, as shown in the following figure.</span></span>  
  
     ![](../../adapters-and-accelerators/accelerator-swift/media/tut2-scrn2.gif "Tut2_scrn2")  
  
4.  <span data-ttu-id="525dd-110">En el Explorador de directivas, confirme que la herramienta de Compositor de reglas de negocio implementa las siguientes directivas:</span><span class="sxs-lookup"><span data-stu-id="525dd-110">In the Policy Explorer, confirm that the Business Rule Composer tool deployed the following policies:</span></span>  
  
     <span data-ttu-id="525dd-111">MT103_Master_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-111">MT103_Master_Policy</span></span>  
  
     <span data-ttu-id="525dd-112">MT103_Validation_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-112">MT103_Validation_Policy</span></span>  
  
     <span data-ttu-id="525dd-113">SWIFT_NetworkRule149_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-113">SWIFT_NetworkRule149_Policy</span></span>  
  
     <span data-ttu-id="525dd-114">SWIFT_NetworkRule150_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-114">SWIFT_NetworkRule150_Policy</span></span>  
  
     <span data-ttu-id="525dd-115">SWIFT_NetworkRule151_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-115">SWIFT_NetworkRule151_Policy</span></span>  
  
     <span data-ttu-id="525dd-116">SWIFT_NetworkRule175_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-116">SWIFT_NetworkRule175_Policy</span></span>  
  
     <span data-ttu-id="525dd-117">SWIFT_NetworkRule2_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-117">SWIFT_NetworkRule2_Policy</span></span>  
  
     <span data-ttu-id="525dd-118">SWIFT_NetworkRule201_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-118">SWIFT_NetworkRule201_Policy</span></span>  
  
     <span data-ttu-id="525dd-119">SWIFT_NetworkRule202_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-119">SWIFT_NetworkRule202_Policy</span></span>  
  
     <span data-ttu-id="525dd-120">SWIFT_NetworkRule203_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-120">SWIFT_NetworkRule203_Policy</span></span>  
  
     <span data-ttu-id="525dd-121">SWIFT_NetworkRule204_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-121">SWIFT_NetworkRule204_Policy</span></span>  
  
     <span data-ttu-id="525dd-122">SWIFT_NetworkRule205_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-122">SWIFT_NetworkRule205_Policy</span></span>  
  
     <span data-ttu-id="525dd-123">SWIFT_NetworkRule206_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-123">SWIFT_NetworkRule206_Policy</span></span>  
  
     <span data-ttu-id="525dd-124">SWIFT_NetworkRule207_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-124">SWIFT_NetworkRule207_Policy</span></span>  
  
     <span data-ttu-id="525dd-125">SWIFT_NetworkRule209_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-125">SWIFT_NetworkRule209_Policy</span></span>  
  
     <span data-ttu-id="525dd-126">SWIFT_NetworkRule210_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-126">SWIFT_NetworkRule210_Policy</span></span>  
  
     <span data-ttu-id="525dd-127">SWIFT_NetworkRule212_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-127">SWIFT_NetworkRule212_Policy</span></span>  
  
     <span data-ttu-id="525dd-128">SWIFT_NetworkRule213_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-128">SWIFT_NetworkRule213_Policy</span></span>  
  
     <span data-ttu-id="525dd-129">SWIFT_NetworkRule215_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-129">SWIFT_NetworkRule215_Policy</span></span>  
  
     <span data-ttu-id="525dd-130">SWIFT_NetworkRule216_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-130">SWIFT_NetworkRule216_Policy</span></span>  
  
     <span data-ttu-id="525dd-131">SWIFT_NetworkRule217_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-131">SWIFT_NetworkRule217_Policy</span></span>  
  
     <span data-ttu-id="525dd-132">SWIFT_NetworkRule218_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-132">SWIFT_NetworkRule218_Policy</span></span>  
  
     <span data-ttu-id="525dd-133">SWIFT_NetworkRule244_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-133">SWIFT_NetworkRule244_Policy</span></span>  
  
     <span data-ttu-id="525dd-134">SWIFT_NetworkRule245_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-134">SWIFT_NetworkRule245_Policy</span></span>  
  
     <span data-ttu-id="525dd-135">SWIFT_NetworkRule81_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-135">SWIFT_NetworkRule81_Policy</span></span>  
  
     <span data-ttu-id="525dd-136">SWIFT_PartyIdentifier_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-136">SWIFT_PartyIdentifier_Policy</span></span>  
  
     <span data-ttu-id="525dd-137">SWIFT_Reference_Policy</span><span class="sxs-lookup"><span data-stu-id="525dd-137">SWIFT_Reference_Policy</span></span>  
  
### <a name="to-view-a-policy"></a><span data-ttu-id="525dd-138">Para ver una directiva</span><span class="sxs-lookup"><span data-stu-id="525dd-138">To view a policy</span></span>  
  
1.  <span data-ttu-id="525dd-139">En el panel Explorador de directivas del compositor de reglas de negocios, asegúrese de que el **SWIFT_NetworkRule149_Policy** se expande y, a continuación, expanda el **versión 1.0 – implementada** nodo.</span><span class="sxs-lookup"><span data-stu-id="525dd-139">In the Policy Explorer pane of the Business Rules Composer, ensure that the **SWIFT_NetworkRule149_Policy** is expanded, and then expand the **Version 1.0 – Deployed** node.</span></span>  
  
2.  <span data-ttu-id="525dd-140">Haga doble clic en el **Validate_MT103** nodo para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="525dd-140">Double-click the **Validate_MT103** node to open it.</span></span>  
  
     <span data-ttu-id="525dd-141">La directiva se abre en el panel del editor en el lado derecho de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="525dd-141">The policy opens in the editor pane on the right side of the screen.</span></span>  
  
 <span data-ttu-id="525dd-142">Continúe con [módulo 7: probar una instancia de archivo sin formato válido](../../adapters-and-accelerators/accelerator-swift/module-7-testing-a-valid-flat-file-instance.md).</span><span class="sxs-lookup"><span data-stu-id="525dd-142">Proceed to [Module 7: Testing a Valid Flat File Instance](../../adapters-and-accelerators/accelerator-swift/module-7-testing-a-valid-flat-file-instance.md).</span></span>