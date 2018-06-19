---
title: Cómo colocar el mapa seleccionado elementos en la vista | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e287b22-5738-428a-aa35-cced877e51ea
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1dff8e981b65b6b91c744ce26648a5f4e06adea
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005549"
---
# <a name="how-to-bring-selected-map-items-in-view"></a><span data-ttu-id="183ed-102">Agregación de elementos de asignación seleccionados en la vista</span><span class="sxs-lookup"><span data-stu-id="183ed-102">How to Bring Selected Map Items in View</span></span>
<span data-ttu-id="183ed-103">Con las versiones anteriores del Asignador de BizTalk, si un mapa comprendía esquemas grandes, era necesario desplazarse por el panel de esquema de origen, la página de cuadrícula y el panel de esquema de destino para llevar todos los elementos del mapa relevantes a una única vista.</span><span class="sxs-lookup"><span data-stu-id="183ed-103">With earlier versions of BizTalk Mapper, if a map comprised big schemas, you had to manually scroll the source schema pane, the grid page, and the target schema pane to bring all the relevant map items into a single view.</span></span> <span data-ttu-id="183ed-104">El asignador de BizTalk con BizTalk Server le permite llevar todos los elementos del mapa relevantes del functoid/vínculo seleccionado en una única vista desplazando automáticamente la página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="183ed-104">The BizTalk Mapper with BizTalk Server allows you to bring all the relevant map items of the selected functoid/link into a single view by automatically scrolling the grid page.</span></span> <span data-ttu-id="183ed-105">En este tema se proporciona información acerca de cómo realizar esta operación.</span><span class="sxs-lookup"><span data-stu-id="183ed-105">This topic provides information about how to perform the operation.</span></span>  
  
 <span data-ttu-id="183ed-106">En función de lo que seleccione (un nodo de esquema de origen, un elemento de la vista de relación o un nodo de esquema de destino), el Asignador de BizTalk desplaza automáticamente las vistas de esquema y la vista de relación de modo sincronizado, y muestra la vista de relación global del elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="183ed-106">Depending on your selection (a source schema node, an element in the relationship view, or a target schema node), the BizTalk Mapper auto-scrolls the schema views and relationship view in a synchronized fashion, and displays the overall relationship view of the selected item.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="183ed-107">La característica de desplazamiento automático entra en vigor una vez que el Asignador de BizTalk ha resaltado todos los elementos del mapa relevantes.</span><span class="sxs-lookup"><span data-stu-id="183ed-107">The auto-scroll feature comes into effect after the BizTalk Mapper has emphasized all the relevant map items.</span></span> <span data-ttu-id="183ed-108">En otras palabras, primero se resaltan los elementos relacionados con la selección y después el Asignador de BizTalk desplaza automáticamente para llevar a la vista los elementos relacionados.</span><span class="sxs-lookup"><span data-stu-id="183ed-108">In other words, first the elements related to the selection are highlighted, and then the BizTalk Mapper auto-scrolls to bring the related elements into view.</span></span>  
  
 <span data-ttu-id="183ed-109">El Asignador de BizTalk no mueve realmente los objetos de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="183ed-109">The BizTalk Mapper does not actually move the grid objects.</span></span> <span data-ttu-id="183ed-110">Los objetos de cuadrícula vuelven a sus respectivas ubicaciones al quitar o modificar la selección.</span><span class="sxs-lookup"><span data-stu-id="183ed-110">The grid objects return to their respective locations when you remove or modify the selection.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="183ed-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="183ed-111">Prerequisites</span></span>  
 <span data-ttu-id="183ed-112">Esta operación requiere que se está ejecutando el Asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="183ed-112">This operation requires that BizTalk Mapper is running.</span></span>  
  
### <a name="to-bring-the-selected-map-items-in-view"></a><span data-ttu-id="183ed-113">Procedimiento para llevar los elementos del mapa seleccionados a la vista</span><span class="sxs-lookup"><span data-stu-id="183ed-113">To bring the selected map items in view</span></span>  
  
1.  <span data-ttu-id="183ed-114">En la cinta de opciones de la utilidad asignador, haga clic en el icono de desplazamiento automático ![Auto &#45; icono de desplazamiento](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll") para desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="183ed-114">On the Mapper utility ribbon, click the auto-scroll icon ![Auto&#45;scroll icon](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll") to switch it OFF.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="183ed-115">El ![Auto &#45; icono de desplazamiento](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll") icono está desactivado OFF de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="183ed-115">The ![Auto&#45;scroll icon](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll") icon is switched OFF by default.</span></span>  
  
2.  <span data-ttu-id="183ed-116">Haga clic en un functoid o en un vínculo; se resaltarán los elementos del mapa relevantes de la relación.</span><span class="sxs-lookup"><span data-stu-id="183ed-116">Click a functoid or a link; the relevant map items in the relationship are emphasized.</span></span>  
  
     <span data-ttu-id="183ed-117">En la siguiente ilustración se muestra el vínculo seleccionado en color azul.</span><span class="sxs-lookup"><span data-stu-id="183ed-117">The following figure displays the selected link in blue color.</span></span> <span data-ttu-id="183ed-118">A su vez, el Asignador de BizTalk resalta en color verde los demás elementos de asignación que son relevantes para la selección.</span><span class="sxs-lookup"><span data-stu-id="183ed-118">In turn, BizTalk Mapper emphasizes the other map items relevant to the selection, in green color.</span></span> <span data-ttu-id="183ed-119">En la ilustración puede ver que todos los elementos de la relación seleccionada, a pesar de estar resaltados, no se encuentran totalmente en la vista actual.</span><span class="sxs-lookup"><span data-stu-id="183ed-119">From the figure, you can see that all the elements of the selected relationship, though emphasized, are completely not in the current view.</span></span>  
  
     <span data-ttu-id="183ed-120">![Cuando se vincula automáticamente &#45; desplazamiento está desactivado](../core/media/autoscroll-switchoff.gif "AutoScroll_SwitchOff")</span><span class="sxs-lookup"><span data-stu-id="183ed-120">![Links when auto&#45;scrolling is switched off](../core/media/autoscroll-switchoff.gif "AutoScroll_SwitchOff")</span></span>  
  
3.  <span data-ttu-id="183ed-121">Haga clic en el icono de desplazamiento automático ![Auto &#45; icono de desplazamiento](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll") para activarlo.</span><span class="sxs-lookup"><span data-stu-id="183ed-121">Click the auto-scroll icon ![Auto&#45;scroll icon](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll") to switch it ON.</span></span>  
  
     <span data-ttu-id="183ed-122">El Asignador de BizTalk se desplaza automáticamente para llevar todos los elementos relevantes de la selección a la vista actual del mapa.</span><span class="sxs-lookup"><span data-stu-id="183ed-122">The BizTalk Mapper automatically scrolls to bring all the relevant items in the selection into the current map view.</span></span>  
  
     <span data-ttu-id="183ed-123">![Ver cuando se cambia el desplazamiento automático en](../core/media/autoscroll-switchon.gif "AutoScroll_SwitchOn")</span><span class="sxs-lookup"><span data-stu-id="183ed-123">![View when autoscrolling is switched on](../core/media/autoscroll-switchon.gif "AutoScroll_SwitchOn")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="183ed-124">Como alternativa, puede presionar CTRL+M o CTRL+U del teclado.</span><span class="sxs-lookup"><span data-stu-id="183ed-124">Alternatively, you can press CTRL+M, CTRL+U from the keyboard.</span></span> <span data-ttu-id="183ed-125">Para obtener una lista de métodos abreviados de teclado del asignador, vea [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="183ed-125">For a list of Mapper keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="183ed-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="183ed-126">See Also</span></span>  
 [<span data-ttu-id="183ed-127">Uso de características mejoradas en el Asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="183ed-127">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)