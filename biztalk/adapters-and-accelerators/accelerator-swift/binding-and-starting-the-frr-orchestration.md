---
title: Enlazar e iniciar la orquestación de FRR | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, binding orchestrations
- FRR, starting orchestrations
- bindings, orchestrations
- orchestrations, bindings
ms.assetid: b74a0116-e98b-4fec-b386-710ce421a1e2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b01386cedbd25148e5ea0ce2ac44fb56e9fe3d03
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987445"
---
# <a name="binding-and-starting-the-frr-orchestration"></a><span data-ttu-id="16392-102">Enlazar e iniciar la orquestación de FRR</span><span class="sxs-lookup"><span data-stu-id="16392-102">Binding and Starting the FRR Orchestration</span></span>
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="16392-103"> incluye la orquestación de FRR como un ensamblado implementado (Microsoft. Solutions.FinancialServices.SWIFT.FrrOrchestration).</span><span class="sxs-lookup"><span data-stu-id="16392-103"> includes the FRR orchestration as a deployed assembly (Microsoft .Solutions.FinancialServices.SWIFT.FrrOrchestration).</span></span> <span data-ttu-id="16392-104">Debe iniciar esta orquestación.</span><span class="sxs-lookup"><span data-stu-id="16392-104">You need to start this orchestration.</span></span>  
  
 <span data-ttu-id="16392-105">**Resumen**</span><span class="sxs-lookup"><span data-stu-id="16392-105">**Summary**</span></span>  
  
 <span data-ttu-id="16392-106">Para iniciar la orquestación de FRR, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="16392-106">To start the FRR orchestration, do the following:</span></span>  
  
-   <span data-ttu-id="16392-107">Enlazar la orquestación FrrOrchestration.FrrMain estableciendo al host BizTalkServerApplication.</span><span class="sxs-lookup"><span data-stu-id="16392-107">Bind the FrrOrchestration.FrrMain orchestration by setting the host to BizTalkServerApplication.</span></span>  
  
-   <span data-ttu-id="16392-108">Iniciar la orquestación FrrOrchestration.FrrMain.</span><span class="sxs-lookup"><span data-stu-id="16392-108">Start the FrrOrchestration.FrrMain orchestration.</span></span>  
  
### <a name="to-bind-and-start-the-frr-orchestration"></a><span data-ttu-id="16392-109">Para enlazar e iniciar la orquestación de FRR</span><span class="sxs-lookup"><span data-stu-id="16392-109">To bind and start the FRR orchestration</span></span>  
  
1.  <span data-ttu-id="16392-110">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, **grupo de BizTalk**, **aplicaciones**y, a continuación, **BizTalk Aplicación 1**.</span><span class="sxs-lookup"><span data-stu-id="16392-110">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and then **BizTalk Application 1**.</span></span> <span data-ttu-id="16392-111">Haga clic en **orquestaciones**.</span><span class="sxs-lookup"><span data-stu-id="16392-111">Click **Orchestrations**.</span></span>  
  
2.  <span data-ttu-id="16392-112">En el panel orquestaciones, haga clic en el **FrrOrchestration.FrrMain** orquestación y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="16392-112">In the Orchestrations pane, right-click the **FrrOrchestration.FrrMain** orchestration, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="16392-113">En el cuadro de diálogo Propiedades de orquestación, haga clic en **enlaces** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="16392-113">In the Orchestration Properties dialog box, click **Bindings** in the left pane.</span></span> <span data-ttu-id="16392-114">Para **Host**, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="16392-114">For **Host**, select **BizTalkServerApplication**.</span></span> <span data-ttu-id="16392-115">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="16392-115">Click **Apply**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="16392-116">En el panel orquestaciones, haga clic en el **FrrMain** orquestación y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="16392-116">In the Orchestrations pane, right-click the **FrrMain** orchestration, and then click **Start**.</span></span>