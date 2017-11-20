---
title: "Anular la implementación de otros proyectos del Tutorial | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5fce837f-1853-4d5d-a680-8ae2a974c750
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b00e829ad569790b257e1d5f0c16290cca68d176
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="undeploy-other-tutorial-projects"></a><span data-ttu-id="bc4a4-102">Anular la implementación de otros proyectos del Tutorial</span><span class="sxs-lookup"><span data-stu-id="bc4a4-102">Undeploy Other Tutorial Projects</span></span>
<span data-ttu-id="bc4a4-103">Cuando se implementa un acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) tutoriales, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] almacena los archivos de ensamblado del tutorial en la base de datos de configuración (también conocido como la base de datos de administración de BizTalk) y la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="bc4a4-103">When you deploy a BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) tutorials, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] stores the tutorial assembly files in the Configuration database (also known as the BizTalk Management database) and the global assembly cache.</span></span> <span data-ttu-id="bc4a4-104">Si ha ejecutado otro [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] tutorial e implementado los ensamblados que creó en este tutorial, podría experimentar errores al probar los ensamblados en las tres partes del tutorial de procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="bc4a4-104">If you have run another [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] tutorial, and deployed the assemblies that you created in that tutorial, you may encounter errors when you test your assemblies in the three parts of the Batching tutorial.</span></span> <span data-ttu-id="bc4a4-105">Esto puede ocurrir porque solo se puede implementar un esquema de mensaje al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="bc4a4-105">This may occur because you can only deploy one message schema at one time.</span></span>  
  
 <span data-ttu-id="bc4a4-106">Puede evitar estos errores al anular la implementación de los ensamblados que haya implementado en los tutoriales anteriores.</span><span class="sxs-lookup"><span data-stu-id="bc4a4-106">You can avoid these errors by undeploying assemblies that you deployed in previous tutorials.</span></span> <span data-ttu-id="bc4a4-107">Puede volver a desplegar el ensamblado más adelante si es necesario.</span><span class="sxs-lookup"><span data-stu-id="bc4a4-107">You can re-deploy the assembly later if needed.</span></span>  
  
 <span data-ttu-id="bc4a4-108">Antes de anular la implementación de un ensamblado, debe dar de baja orquestaciones del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bc4a4-108">Before undeploying an assembly, you need to unenlist orchestrations in the assembly.</span></span> <span data-ttu-id="bc4a4-109">También debe quitar cualquier referencia al ensamblado que desea anular la implementación, desde cualquier otro ensamblado que desea mantener implementado.</span><span class="sxs-lookup"><span data-stu-id="bc4a4-109">You also need to remove any reference to the assembly that you want to undeploy, from any other assembly that you want to keep deployed.</span></span> <span data-ttu-id="bc4a4-110">Una alternativa consiste en eliminar todos los archivos DLL asociado con un tutorial, antes de iniciar otro tutorial.</span><span class="sxs-lookup"><span data-stu-id="bc4a4-110">An alternative is to delete all DLLs associated with one tutorial, before starting another tutorial.</span></span>  
  
### <a name="to-undeploy-an-assembly"></a><span data-ttu-id="bc4a4-111">Para anular la implementación de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="bc4a4-111">To undeploy an assembly</span></span>  
  
1.  <span data-ttu-id="bc4a4-112">Dar de baja orquestaciones usadas en el ensamblado que desea anular la implementación haciendo clic en la orquestación en el Explorador de BizTalk de Visual Studio y, a continuación, haga clic en **dar de baja**.</span><span class="sxs-lookup"><span data-stu-id="bc4a4-112">Unenlist orchestrations used in the assembly that you want to undeploy by clicking the orchestration in BizTalk Explorer of Visual Studio, and then clicking **Unenlist**.</span></span>  
  
2.  <span data-ttu-id="bc4a4-113">En cualquier ensamblado que se desea mantener implementado, quite las referencias a los ensamblados que desea anular la implementación.</span><span class="sxs-lookup"><span data-stu-id="bc4a4-113">In any assembly that you want to keep deployed, remove references to assemblies that you want to undeploy.</span></span> <span data-ttu-id="bc4a4-114">Haga clic en la referencia en el Explorador de soluciones y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="bc4a4-114">Right click the reference in Solution Explorer, and then click **Remove**.</span></span>  
  
3.  <span data-ttu-id="bc4a4-115">Abra el Explorador de BizTalk, haga clic en el ensamblado que desea anular la implementación y, a continuación, haga clic en **anular la implementación**.</span><span class="sxs-lookup"><span data-stu-id="bc4a4-115">Open BizTalk Explorer, right-click the assembly that you want to undeploy, and then click **Undeploy**.</span></span>  
  
 <span data-ttu-id="bc4a4-116">Para obtener más información acerca de cómo anular la implementación de un ensamblado, vea "Anular la implementación un ensamblado utilizando el Explorador de BizTalk" en [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="bc4a4-116">For more information about undeploying an assembly, see "Undeploying an Assembly Using BizTalk Explorer" in [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc4a4-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc4a4-117">See Also</span></span>  
 [<span data-ttu-id="bc4a4-118">Preparando para utilizar el Tutorial de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="bc4a4-118">Preparing to Use the Batching Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)