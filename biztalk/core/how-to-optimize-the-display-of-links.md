---
title: "Cómo optimizar la presentación de vínculos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2a9e16ff-01d3-4b7d-91c4-59d17266ee6d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 689ab4c67bfe8cabc8109c373e899d391fdd56a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-optimize-the-display-of-links"></a><span data-ttu-id="8a1d2-102">Optimización de la visualización de vínculos</span><span class="sxs-lookup"><span data-stu-id="8a1d2-102">How to Optimize the Display of Links</span></span>
<span data-ttu-id="8a1d2-103">Cuando los esquemas son grandes, los mapas pueden incluir un elevado número de enlaces entre los esquemas de origen y de destino.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-103">When the schemas are big, your maps might include a large number of links between the source and the destination schemas.</span></span> <span data-ttu-id="8a1d2-104">Con muchos enlaces que atraviesen la superficie del mapa, puede que sea difícil realizar un seguimiento de un vínculo o de otro objeto con el que tenga que trabajar.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-104">With many links across the map surface, you may find it difficult to track a link or an object you need to work on.</span></span> <span data-ttu-id="8a1d2-105">Además, puede resultar difícil realizar un seguimiento de una relación de extremo a extremo entre un esquema de origen, los vínculos, los functoids y el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-105">Also, it can be difficult for you to track an end-to-end relationship between a source schema, the links, the functoids, and the destination schema.</span></span> <span data-ttu-id="8a1d2-106">En el Asignador de BizTalk, podrá administrar mejor esquemas grandes y complejos y mostrar una visualización optimizada de los vínculos en el mapa.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-106">In the BizTalk Mapper, you can better manage complex and large schemas, and bring out an optimized display of links in the map.</span></span> <span data-ttu-id="8a1d2-107">En este tema se proporcionan detalles acerca de cómo ver los vínculos.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-107">This topic provides details about how to view links.</span></span>  
  
 <span data-ttu-id="8a1d2-108">Puede clasificar los vínculos como sigue:</span><span class="sxs-lookup"><span data-stu-id="8a1d2-108">You can categorize the links as follows:</span></span>  
  
-   <span data-ttu-id="8a1d2-109">Parcialmente en el ámbito</span><span class="sxs-lookup"><span data-stu-id="8a1d2-109">Partially in scope</span></span>  
  
-   <span data-ttu-id="8a1d2-110">Totalmente en el ámbito</span><span class="sxs-lookup"><span data-stu-id="8a1d2-110">Completely in scope</span></span>  
  
-   <span data-ttu-id="8a1d2-111">Totalmente fuera del ámbito</span><span class="sxs-lookup"><span data-stu-id="8a1d2-111">Completely out of scope</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8a1d2-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8a1d2-112">Prerequisites</span></span>  
 <span data-ttu-id="8a1d2-113">Estas instrucciones requieren que se está ejecutando el asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-113">These instructions require that BizTalk Mapper is running.</span></span>  
  
## <a name="to-view-the-links-partially-in-scope"></a><span data-ttu-id="8a1d2-114">Para ver los vínculos parcialmente en el ámbito</span><span class="sxs-lookup"><span data-stu-id="8a1d2-114">To view the links partially in scope</span></span>  
 <span data-ttu-id="8a1d2-115">Los vínculos que tengan al menos un extremo visible en la superficie de la cuadrícula se denominan “parcialmente en el ámbito”.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-115">Links that have at least one end visible on the grid surface are called “partially in scope.”</span></span>  
  
 <span data-ttu-id="8a1d2-116">La siguiente ilustración muestra un vínculo que está “parcialmente en el ámbito”.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-116">The figure below shows a link that is “partially in scope.”</span></span> <span data-ttu-id="8a1d2-117">Estos vínculos se muestran como líneas discontinuas en la página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-117">These links are shown as dashed lines on the grid page.</span></span>  
  
 <span data-ttu-id="8a1d2-118">Haga clic en el vínculo que está parcialmente visible en la superficie de la cuadrícula y la página de la cuadrícula subirá/bajará automáticamente para llevar la relación a la vista actual.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-118">Click the link that is partially visible on the grid surface, and the grid page automatically moves up/down to bring the relationship into the current view.</span></span>  
  
 <span data-ttu-id="8a1d2-119">![Vínculos del asignador parcialmente en el ámbito](../core/media/mapper-partiallyinscope.gif "Mapper_PartiallyInScope")</span><span class="sxs-lookup"><span data-stu-id="8a1d2-119">![Mapper links partially in scope](../core/media/mapper-partiallyinscope.gif "Mapper_PartiallyInScope")</span></span>  
  
## <a name="to-view-the-links-completely-in-scope"></a><span data-ttu-id="8a1d2-120">Para ver los vínculos completamente en el ámbito</span><span class="sxs-lookup"><span data-stu-id="8a1d2-120">To view the links completely in scope</span></span>  
 <span data-ttu-id="8a1d2-121">Los vínculos que tengan ambos extremos (nodo a nodo, nodo a functoid, functoid a functoid o functoid a nodo) visibles en la superficie de la cuadrícula se denominan “totalmente en el ámbito”.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-121">A link that has both ends (node to node, node to functoid, functoid-to-functoid, or functoid to node) visible on the grid surface is called “completely in scope.”</span></span>  
  
 <span data-ttu-id="8a1d2-122">La siguiente ilustración muestra un vínculo entre “DataCollection1” y “ST01” que está totalmente en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-122">The figure below shows a link between “DataCollection1” and “ST01” that is completely in scope.</span></span>  
  
 <span data-ttu-id="8a1d2-123">Haga clic en el vínculo y se seleccionará la relación del nodo de origen al nodo de destino.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-123">Click the link, and the relationship from source node to target node is selected.</span></span>  
  
 <span data-ttu-id="8a1d2-124">![Vínculos de asignador completamente en el ámbito](../core/media/mapper-completelyinscope.gif "Mapper_CompletelyInScope")</span><span class="sxs-lookup"><span data-stu-id="8a1d2-124">![Mapper links completely in scope](../core/media/mapper-completelyinscope.gif "Mapper_CompletelyInScope")</span></span>  
  
## <a name="to-view-the-links-completely-out-of-scope"></a><span data-ttu-id="8a1d2-125">Para ver los vínculos totalmente fuera del ámbito</span><span class="sxs-lookup"><span data-stu-id="8a1d2-125">To view the links completely out of scope</span></span>  
 <span data-ttu-id="8a1d2-126">Los vínculos que no tienen visible ninguno de sus extremos en la vista actual del mapa se denominan “totalmente fuera del ámbito”.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-126">A link that has neither of its end points visible in the current map view is called “completely out of scope.”</span></span>  
  
 <span data-ttu-id="8a1d2-127">La siguiente ilustración muestra un vínculo que está totalmente fuera del ámbito.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-127">The figure below shows a link that is completely out of scope.</span></span>  
  
 <span data-ttu-id="8a1d2-128">Si no desea mostrar estos vínculos en el mapa de superficie (porque ninguno de los vínculos está visible), puede desactivarlos haciendo clic en ![mostrar todos los vínculos](../core/media/mapper-showhideoutscopelinks.gif "Mapper_ShowHideOutScopeLinks") en el asignador cinta de utilidades.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-128">If you do not want to display these links on the map surface (because none of the links are visible), you may choose to turn them off by clicking ![Show all links](../core/media/mapper-showhideoutscopelinks.gif "Mapper_ShowHideOutScopeLinks") on the Mapper utility ribbon.</span></span> <span data-ttu-id="8a1d2-129">De este modo se reduce la cantidad de vínculos que están visibles en la vista de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-129">This reduces the amount of links that are visible on the grid view.</span></span>  
  
 <span data-ttu-id="8a1d2-130">![Vínculos de asignador completamente fuera del ámbito](../core/media/mapper-completelyoutscope.gif "Mapper_CompletelyOutScope")</span><span class="sxs-lookup"><span data-stu-id="8a1d2-130">![Mapper links completely out of scope](../core/media/mapper-completelyoutscope.gif "Mapper_CompletelyOutScope")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a1d2-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a1d2-131">See Also</span></span>  
 [<span data-ttu-id="8a1d2-132">Uso de características mejoradas en el asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="8a1d2-132">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)