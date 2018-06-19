---
title: Cómo asignar varios ensamblados | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assemblies, tracking profiles
- tracking profiles, mapping assemblies
- assemblies, maps
ms.assetid: 136f1943-9643-4551-8b5b-150c4b4bfebe
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20a55b6e88889ccfa36adcac11fe548ab1b25bc6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254356"
---
# <a name="how-to-map-multiple-assemblies"></a><span data-ttu-id="5a732-102">Cómo asignar varios ensamblados</span><span class="sxs-lookup"><span data-stu-id="5a732-102">How to Map Multiple Assemblies</span></span>
<span data-ttu-id="5a732-103">Las aplicaciones de BizTalk se pueden componer de varios ensamblados en los que residen los elementos de datos a los que la actividad de BAM hace referencia.</span><span class="sxs-lookup"><span data-stu-id="5a732-103">BizTalk applications can consist of multiple assemblies in which the data items that a BAM activity references reside.</span></span> <span data-ttu-id="5a732-104">El procedimiento siguiente muestra cómo asignar varios ensamblados a un perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5a732-104">The following procedure shows you how to map multiple assemblies to a tracking profile.</span></span>  
  
### <a name="to-map-multiple-assemblies"></a><span data-ttu-id="5a732-105">Para asignar varios ensamblados</span><span class="sxs-lookup"><span data-stu-id="5a732-105">To map multiple assemblies</span></span>  
  
1.  <span data-ttu-id="5a732-106">Abra un perfil de seguimiento existente o cree uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="5a732-106">Open an existing tracking profile or create a new tracking profile.</span></span> <span data-ttu-id="5a732-107">Para obtener más información acerca de cómo crear un perfil de seguimiento, vea [cómo crear un perfil de seguimiento](../core/how-to-create-a-tracking-profile.md).</span><span class="sxs-lookup"><span data-stu-id="5a732-107">For more information about creating a tracking profile, see [How to Create a Tracking Profile](../core/how-to-create-a-tracking-profile.md).</span></span>  
  
2.  <span data-ttu-id="5a732-108">Haga clic en el **Seleccionar origen de eventos** (situado sobre el panel derecho, en el Editor de perfiles de seguimiento).</span><span class="sxs-lookup"><span data-stu-id="5a732-108">Click the **Select Event Source** button (located above the right pane in the Tracking Profile Editor).</span></span>  
  
3.  <span data-ttu-id="5a732-109">Seleccione el **seleccionar programación de orquestación** elemento de menú en el menú en cascada.</span><span class="sxs-lookup"><span data-stu-id="5a732-109">Select the **Select Orchestration Schedule** menu item from the cascading menu.</span></span>  
  
4.  <span data-ttu-id="5a732-110">Seleccione el ensamblado primario desde el que se va a dibujar la orquestación, haga clic en el ensamblado que contiene la orquestación en el **nombre de ensamblado** cuadro de lista y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5a732-110">Select the parent assembly from which to draw the orchestration by clicking the assembly containing the orchestration in the **Assembly Name** list box, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="5a732-111">Seleccione la orquestación que es el origen de los elementos de datos en el **nombre de la orquestación** cuadro de lista y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5a732-111">Select the orchestration that is the source for the data items in the **Orchestration Names** list box, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="5a732-112">Seleccione los elementos de datos en el panel derecho y arrástrelos a los nodos correspondientes de la actividad en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="5a732-112">Select the data items in the right pane and drag them to the appropriate nodes in the activity in the left pane.</span></span>  
  
7.  <span data-ttu-id="5a732-113">Repita los pasos de 2 a 6 para asignar ensamblados adicionales.</span><span class="sxs-lookup"><span data-stu-id="5a732-113">Repeat steps 2 through 6 to map additional assemblies.</span></span>  
  
### <a name="to-map-the-second-assembly"></a><span data-ttu-id="5a732-114">Para asignar el segundo ensamblado</span><span class="sxs-lookup"><span data-stu-id="5a732-114">To map the second assembly</span></span>  
  
1.  <span data-ttu-id="5a732-115">Haga clic en el **Seleccionar origen de eventos**.</span><span class="sxs-lookup"><span data-stu-id="5a732-115">Click the **Select Event Source**.</span></span>  
  
2.  <span data-ttu-id="5a732-116">Seleccione el **seleccionar programación de orquestación** elemento de menú en el menú en cascada.</span><span class="sxs-lookup"><span data-stu-id="5a732-116">Select the **Select Orchestration Schedule** menu item from the cascading menu.</span></span>  
  
3.  <span data-ttu-id="5a732-117">Seleccione el ensamblado primario siguiente desde el que se va a dibujar la orquestación, haga clic en el ensamblado que contiene la orquestación en el **nombre de ensamblado** cuadro de lista y, a continuación, haga clic en el **siguiente** botón.</span><span class="sxs-lookup"><span data-stu-id="5a732-117">Select the next parent assembly from which to draw the orchestration by clicking the assembly containing the orchestration in the **Assembly Name** list box, and then click the **Next** button.</span></span>  
  
4.  <span data-ttu-id="5a732-118">Seleccione la orquestación que es el origen de los elementos de datos en el **nombre de la orquestación** cuadro de lista y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5a732-118">Select the orchestration that is the source for the data items in the **Orchestration Names** list box, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="5a732-119">Seleccione los elementos de datos en el panel derecho y arrástrelos a los nodos correspondientes de la actividad en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="5a732-119">Select the data items in the right pane and drag them to the appropriate nodes in the activity in the left pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a732-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a732-120">See Also</span></span>  
 <span data-ttu-id="5a732-121">[Cómo asignar orígenes de eventos](../core/how-to-map-event-sources.md) </span><span class="sxs-lookup"><span data-stu-id="5a732-121">[How to Map Event Sources](../core/how-to-map-event-sources.md) </span></span>  
 [<span data-ttu-id="5a732-122">Creación de perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="5a732-122">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)