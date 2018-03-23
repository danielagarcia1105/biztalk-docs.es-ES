---
title: Cómo resaltar elementos de mapa | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2732b36-ca57-4566-ba26-da27a3082f32
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6bb03969a044c6a474f5d2d1c1e5e1a5067cf81
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-emphasize-map-items"></a><span data-ttu-id="eac26-102">Enfatización de elementos de asignación</span><span class="sxs-lookup"><span data-stu-id="eac26-102">How to Emphasize Map Items</span></span>
<span data-ttu-id="eac26-103">En el Asignador de BizTalk, al seleccionar un elemento de asignación, todos los vínculos y functoids asociados se destacan.</span><span class="sxs-lookup"><span data-stu-id="eac26-103">In the BizTalk Mapper, when you select a map item, all the associated links and functoids are emphasized.</span></span> <span data-ttu-id="eac26-104">Es útil en las asignaciones con muchos vínculos, en las que es difícil identificar una relación y los elementos de esquema relacionados.</span><span class="sxs-lookup"><span data-stu-id="eac26-104">This is useful in maps with many links, where it is difficult to identify a relationship and the related schema items.</span></span>  
  
 <span data-ttu-id="eac26-105">Al seleccionar un vínculo, un functoid o un elemento de esquema, el Asignador de BizTalk destaca la relación relacionada y los elementos de esquema.</span><span class="sxs-lookup"><span data-stu-id="eac26-105">When you select a link, a functoid, or a schema element, the BizTalk Mapper emphasizes the related relationship and schema elements.</span></span> <span data-ttu-id="eac26-106">Para el elemento de asignación seleccionado, todos los vínculos entrantes y los salientes (recursivamente) se resaltan en negrita y todos los demás elementos de la asignación aparecen en gris. La siguiente instantánea muestra el elemento de asignación seleccionado en negrita y en color y los demás elementos de asignación aparecen más claros.</span><span class="sxs-lookup"><span data-stu-id="eac26-106">For the selected map item, all the incoming links and the outgoing links (recursively) are highlighted in bold, and all the other map items are greyed out. The following screenshot shows the selected map item in bold and color and the other map items appear lighter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eac26-107">En este contexto, una relación relacionada significa que todos los vínculos, los functoids o los elementos de esquema están directa o indirectamente vinculados al elemento de asignación seleccionado.</span><span class="sxs-lookup"><span data-stu-id="eac26-107">In this context, a related relationship means all the links, functoids, or schema elements directly or indirectly linked to the selected map item.</span></span>  
  
 <span data-ttu-id="eac26-108">![Enfatizar un elemento de mapa](../core/media/mapper-intelliselect.gif "Mapper_IntelliSelect")</span><span class="sxs-lookup"><span data-stu-id="eac26-108">![Emphasizing a map item](../core/media/mapper-intelliselect.gif "Mapper_IntelliSelect")</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="eac26-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="eac26-109">Prerequisites</span></span>  
 <span data-ttu-id="eac26-110">Esta operación requiere que se está ejecutando el Asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="eac26-110">This operation requires that BizTalk Mapper is running.</span></span>  
  
## <a name="to-emphasize-a-map-item"></a><span data-ttu-id="eac26-111">Procedimiento para destacar un elemento de asignación</span><span class="sxs-lookup"><span data-stu-id="eac26-111">To emphasize a map item</span></span>  
  
-   <span data-ttu-id="eac26-112">Haga clic en un elemento de asignación (un vínculo, un functoid o un elemento de esquema).</span><span class="sxs-lookup"><span data-stu-id="eac26-112">Click a map item (a link, a functoid, or a schema element).</span></span> <span data-ttu-id="eac26-113">Puede ver que todos los demás vínculos y functoids (incluidos los nodos de esquema) asociados al elemento de asignación seleccionado en la página de cuadrícula actual están resaltados.</span><span class="sxs-lookup"><span data-stu-id="eac26-113">You can see that all the other links and functoids (including the schema nodes) associated with the selected map item in the current grid page are highlighted.</span></span>  
  
     <span data-ttu-id="eac26-114">A veces, para el nodo seleccionado, pueden existir relaciones en otras páginas de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="eac26-114">Sometimes, for the selected node, there might be relationships existing in other grid pages.</span></span> <span data-ttu-id="eac26-115">En este caso, el Asignador de BizTalk destaca la instancia de la página de cuadrícula actual y también resalta la pestaña de la página donde existe la otra relación con el nodo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="eac26-115">In such a case, the BizTalk Mapper emphasizes the instance in current grid page and also highlights the page tab where the other related relationship to the selected node exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eac26-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="eac26-116">See Also</span></span>  
 [<span data-ttu-id="eac26-117">Uso de características mejoradas en el asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="eac26-117">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)