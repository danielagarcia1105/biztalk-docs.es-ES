---
title: "Paso 1: Implementar la orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8988fced-b2d5-4ee7-a851-20fc7c3dd087
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47565daf53f66fc5fc898e7c023ca09a34c78113
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-deploy-the-orchestration"></a><span data-ttu-id="b8053-102">Paso 1: Implementar la orquestación</span><span class="sxs-lookup"><span data-stu-id="b8053-102">Step 1: Deploy the Orchestration</span></span>
<span data-ttu-id="b8053-103">![Paso 1 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span><span class="sxs-lookup"><span data-stu-id="b8053-103">![Step 1 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span></span>  
  
 <span data-ttu-id="b8053-104">**Tiempo en completarse:** 5 minutos</span><span class="sxs-lookup"><span data-stu-id="b8053-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="b8053-105">**Objetivo:** en este paso, implemente la solución de orquestación.</span><span class="sxs-lookup"><span data-stu-id="b8053-105">**Objective:** In this step, deploy the orchestration solution.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b8053-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b8053-106">Prerequisites</span></span>  
 <span data-ttu-id="b8053-107">Debe haber completado los pasos descritos en [lección 4: realizar una operación de inserción en la tabla de orden de compra](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md).</span><span class="sxs-lookup"><span data-stu-id="b8053-107">You must have completed the steps in [Lesson 4: Perform an Insert Operation on the Purchase Order Table](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md).</span></span>  
  
### <a name="to-deploy-the-solution"></a><span data-ttu-id="b8053-108">Procedimiento para implementar la solución</span><span class="sxs-lookup"><span data-stu-id="b8053-108">To deploy the solution</span></span>  
  
1.  <span data-ttu-id="b8053-109">En el Explorador de soluciones, haga clic en el nombre de la solución y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b8053-109">In Solution Explorer, right-click the solution name, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b8053-110">En el cuadro de diálogo páginas de propiedades, en el control de árbol, expanda **propiedades de configuración**y, a continuación, haga clic en **configuración**.</span><span class="sxs-lookup"><span data-stu-id="b8053-110">In the properties pages dialog box, in the tree control, expand **Configuration Properties**, and then click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="b8053-111">En el **configuración** página, en la **implementar** columna, active la casilla de verificación en el proyecto de BizTalk y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b8053-111">On the **Configuration** page, in the **Deploy** column, select the check box against the BizTalk project, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="b8053-112">En el Explorador de soluciones, haga clic en el nombre de la solución y, a continuación, haga clic en **implementar solución**.</span><span class="sxs-lookup"><span data-stu-id="b8053-112">In Solution Explorer, right-click the solution name, and then click **Deploy Solution**.</span></span>  
  
     <span data-ttu-id="b8053-113">El panel de salida en la parte inferior de la pantalla se lea: **implementar: 1 correctos, 0 incorrectos, 0 omitidos**.</span><span class="sxs-lookup"><span data-stu-id="b8053-113">The Output pane at the bottom of the screen should read: **Deploy: 1 succeeded, 0 failed, 0 skipped**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="b8053-114">Síntesis</span><span class="sxs-lookup"><span data-stu-id="b8053-114">What did I just do?</span></span>  
 <span data-ttu-id="b8053-115">En este paso, ha implementado la orquestación de BizTalk para [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="b8053-115">In this step, you deployed the BizTalk orchestration to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b8053-116">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b8053-116">Next Steps</span></span>  
 <span data-ttu-id="b8053-117">Crear los puertos físicos en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, como se describe en [paso 2: configurar los puertos](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md).</span><span class="sxs-lookup"><span data-stu-id="b8053-117">You create the physical ports in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, as described in [Step 2: Configure the Ports](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8053-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8053-118">See Also</span></span>  
 <span data-ttu-id="b8053-119">[Paso 2: Configurar los puertos](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md) </span><span class="sxs-lookup"><span data-stu-id="b8053-119">[Step 2: Configure the Ports](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md) </span></span>  
 [<span data-ttu-id="b8053-120">Lección 5: Implementar la solución</span><span class="sxs-lookup"><span data-stu-id="b8053-120">Lesson 5: Deploy the Solution</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)