---
title: "Enlazar e iniciar la orquestación FRR | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FRR, binding orchestrations
- FRR, starting orchestrations
- bindings, orchestrations
- orchestrations, bindings
ms.assetid: b74a0116-e98b-4fec-b386-710ce421a1e2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81cf116fc03a8f2d898752a077e8347fd395a4a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="binding-and-starting-the-frr-orchestration"></a><span data-ttu-id="4ea1d-102">Enlazar e iniciar la orquestación FRR</span><span class="sxs-lookup"><span data-stu-id="4ea1d-102">Binding and Starting the FRR Orchestration</span></span>
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="4ea1d-103">incluye la orquestación FRR como un ensamblado implementado ([!INCLUDE[btsCoName](../../includes/btsconame-md.md)]. Solutions.FinancialServices.SWIFT.FrrOrchestration).</span><span class="sxs-lookup"><span data-stu-id="4ea1d-103"> includes the FRR orchestration as a deployed assembly ([!INCLUDE[btsCoName](../../includes/btsconame-md.md)].Solutions.FinancialServices.SWIFT.FrrOrchestration).</span></span> <span data-ttu-id="4ea1d-104">Debe iniciar esta orquestación.</span><span class="sxs-lookup"><span data-stu-id="4ea1d-104">You need to start this orchestration.</span></span>  
  
 <span data-ttu-id="4ea1d-105">**Resumen**</span><span class="sxs-lookup"><span data-stu-id="4ea1d-105">**Summary**</span></span>  
  
 <span data-ttu-id="4ea1d-106">Para iniciar la orquestación FRR, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4ea1d-106">To start the FRR orchestration, do the following:</span></span>  
  
-   <span data-ttu-id="4ea1d-107">Enlazar la orquestación FrrOrchestration.FrrMain estableciendo el host BizTalkServerApplication.</span><span class="sxs-lookup"><span data-stu-id="4ea1d-107">Bind the FrrOrchestration.FrrMain orchestration by setting the host to BizTalkServerApplication.</span></span>  
  
-   <span data-ttu-id="4ea1d-108">Iniciar la orquestación FrrOrchestration.FrrMain.</span><span class="sxs-lookup"><span data-stu-id="4ea1d-108">Start the FrrOrchestration.FrrMain orchestration.</span></span>  
  
### <a name="to-bind-and-start-the-frr-orchestration"></a><span data-ttu-id="4ea1d-109">Para enlazar e iniciar la orquestación FRR</span><span class="sxs-lookup"><span data-stu-id="4ea1d-109">To bind and start the FRR orchestration</span></span>  
  
1.  <span data-ttu-id="4ea1d-110">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, **grupo de BizTalk**, **aplicaciones**y, a continuación, **BizTalk Aplicación 1**.</span><span class="sxs-lookup"><span data-stu-id="4ea1d-110">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and then **BizTalk Application 1**.</span></span> <span data-ttu-id="4ea1d-111">Haga clic en **orquestaciones**.</span><span class="sxs-lookup"><span data-stu-id="4ea1d-111">Click **Orchestrations**.</span></span>  
  
2.  <span data-ttu-id="4ea1d-112">En el panel orquestaciones, haga clic en el **FrrOrchestration.FrrMain** orquestación y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4ea1d-112">In the Orchestrations pane, right-click the **FrrOrchestration.FrrMain** orchestration, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="4ea1d-113">En el cuadro de diálogo Propiedades de orquestación, haga clic en **enlaces** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="4ea1d-113">In the Orchestration Properties dialog box, click **Bindings** in the left pane.</span></span> <span data-ttu-id="4ea1d-114">Para **Host**, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="4ea1d-114">For **Host**, select **BizTalkServerApplication**.</span></span> <span data-ttu-id="4ea1d-115">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4ea1d-115">Click **Apply**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="4ea1d-116">En el panel orquestaciones, haga clic en el **FrrMain** orquestación y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="4ea1d-116">In the Orchestrations pane, right-click the **FrrMain** orchestration, and then click **Start**.</span></span>