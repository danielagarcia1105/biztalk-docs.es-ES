---
title: 'Paso 3 (para Azure): Crear una cola de Bus de servicio | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b7192c3c-4ebf-49c4-b8ce-46a6e9fb5f4a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d55b3222798edb245000cdde8de52565c39758a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-for-azure-create-a-service-bus-queue"></a><span data-ttu-id="14bde-102">Paso 3 (para Azure): Crear una cola de Bus de servicio</span><span class="sxs-lookup"><span data-stu-id="14bde-102">Step 3 (For Azure): Create a Service Bus Queue</span></span>
<span data-ttu-id="14bde-103">En este tema, creará una cola de Service Bus a la que se envía el pedido de ventas X12 después de procesarse y transformarse mediante el acuerdo EDI.</span><span class="sxs-lookup"><span data-stu-id="14bde-103">In this topic, you create a Service Bus Queue to which the X12 sales order is sent after it is processed and transformed using the EDI agreement.</span></span>  
  
### <a name="to-create-a-service-bus-queue"></a><span data-ttu-id="14bde-104">Para crear una cola de Service Bus</span><span class="sxs-lookup"><span data-stu-id="14bde-104">To create a Service Bus Queue</span></span>  
  
1.  <span data-ttu-id="14bde-105">Inicie sesión en el [Portal de administración de Windows Azure CTP](http://go.microsoft.com/fwlink/p/?LinkId=202886) con su cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="14bde-105">Log in to the [Windows Azure CTP Management Portal](http://go.microsoft.com/fwlink/p/?LinkId=202886) using your Microsoft account.</span></span>  
  
2.  <span data-ttu-id="14bde-106">En la parte inferior izquierda de la página, haga clic en **AppFabric**.</span><span class="sxs-lookup"><span data-stu-id="14bde-106">On the lower left-hand side of the page, click **AppFabric**.</span></span>  
  
3.  <span data-ttu-id="14bde-107">Amplíe los servicios en el árbol de la parte izquierda, expanda su suscripción y haga clic en el espacio de nombres que ya debe haber creado.</span><span class="sxs-lookup"><span data-stu-id="14bde-107">Expand Services in the tree on the left-hand side, expand your subscription, and click a namespace that you must have already created.</span></span> <span data-ttu-id="14bde-108">Si no dispone ya de un espacio de nombres, vea [Cómo: crear o modificar un Namespace de servicio de Windows Azure CTP](http://msdn.microsoft.com/library/windowsazure/hh697699.aspx).</span><span class="sxs-lookup"><span data-stu-id="14bde-108">If you don’t have a namespace already, see [How to: Create or Modify a Windows Azure CTP Service Namespace](http://msdn.microsoft.com/library/windowsazure/hh697699.aspx).</span></span>  
  
4.  <span data-ttu-id="14bde-109">Para crear una cola, haga clic en **nueva cola** desde el **administrar entidades** categoría desde la barra de herramientas en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="14bde-109">To create a Queue click **New Queue** from the **Manage Entities** category from the toolbar at the top of the page.</span></span>  
  
5.  <span data-ttu-id="14bde-110">En el **nueva cola** diálogo cuadro, escriba un nombre para la cola.</span><span class="sxs-lookup"><span data-stu-id="14bde-110">In the **New Queue** dialog box, enter a name for the Queue.</span></span> <span data-ttu-id="14bde-111">Para este tutorial, escriba el nombre como `queueordersedi`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="14bde-111">For this tutorial, enter the name as `queueordersedi`, and then click **OK**.</span></span> <span data-ttu-id="14bde-112">Ha especificado este nombre como parte del acuerdo EDI que creó en [(para Azure) del paso 2: crear un acuerdo de EDI](../core/step-2-for-azure-create-an-edi-agreement.md).</span><span class="sxs-lookup"><span data-stu-id="14bde-112">You specified this name as part of the EDI agreement you created in [Step 2 (For Azure): Create an EDI Agreement](../core/step-2-for-azure-create-an-edi-agreement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14bde-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="14bde-113">See Also</span></span>  
 [<span data-ttu-id="14bde-114">Tutorial 4: Crear una aplicación híbrida mediante BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="14bde-114">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)