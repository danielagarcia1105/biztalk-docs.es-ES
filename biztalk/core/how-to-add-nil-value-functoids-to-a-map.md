---
title: Cómo agregar Functoids de valor nulo a un mapa | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b2e193ed-fe5c-4b12-aab8-ff2d81fd45e1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cc7d8b0035161b4a2126ace021072ffcd1d17e8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248212"
---
# <a name="how-to-add-nil-value-functoids-to-a-map"></a><span data-ttu-id="b14ee-102">Cómo agregar functoids de valor nulo a una asignación</span><span class="sxs-lookup"><span data-stu-id="b14ee-102">How to Add Nil Value Functoids to a Map</span></span>
<span data-ttu-id="b14ee-103">El **valor nulo** functoid establece el valor del nodo de destino a **Nil**.</span><span class="sxs-lookup"><span data-stu-id="b14ee-103">The **Nil Value** functoid sets the value of the destination node to **Nil**.</span></span>  
  
 <span data-ttu-id="b14ee-104">Para obtener información conceptual acerca de la **valor nulo** functoid, consulte [Functoid de valor nulo](../core/nil-value-functoid.md).</span><span class="sxs-lookup"><span data-stu-id="b14ee-104">For conceptual information about the **Nil Value** functoid, see [Nil Value Functoid](../core/nil-value-functoid.md).</span></span>  
  
## <a name="add-the-nil-value-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="b14ee-105">Agregar el functoid valor nulo a una asignación y configurarlo</span><span class="sxs-lookup"><span data-stu-id="b14ee-105">Add the Nil Value functoid to a map and configure it</span></span>  
  
1.  <span data-ttu-id="b14ee-106">Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] haga clic en cuadro de herramientas activa, el **Functoids avanzados** tab para seleccionar esta categoría de functoids.</span><span class="sxs-lookup"><span data-stu-id="b14ee-106">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span> <span data-ttu-id="b14ee-107">Aparece la lista de functoids avanzados de la categoría seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b14ee-107">The list of advanced functoids in the chosen category appears.</span></span>  
  
2.  <span data-ttu-id="b14ee-108">Arrastre el **valor nulo** functoid (![functoid valor nulo](../core/media/advanced-nil-value-functoid.gif "advanced_nil_value_functoid")) en el cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="b14ee-108">Drag the **Nil Value** functoid (![Nil Value functoid](../core/media/advanced-nil-value-functoid.gif "advanced_nil_value_functoid")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b14ee-109">El functoid se colocará en la página de cuadrícula mostrada.</span><span class="sxs-lookup"><span data-stu-id="b14ee-109">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="b14ee-110">Si desea colocar el functoid en una página de cuadrícula diferente, necesitará mostrar otra página de cuadrícula en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="b14ee-110">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
    >
    >  <span data-ttu-id="b14ee-111">Si crea una asignación que usa más de un functoid, es necesario tener en cuenta su ubicación relativa de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="b14ee-111">If you are constructing a map that uses more than one functoid, you need to consider their relative left-to-right placement.</span></span> <span data-ttu-id="b14ee-112">Los functoids se ejecutan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="b14ee-112">Functoids are executed from left to right.</span></span> <span data-ttu-id="b14ee-113">La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.</span><span class="sxs-lookup"><span data-stu-id="b14ee-113">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3.  <span data-ttu-id="b14ee-114">El **valor nulo** functoid puede tener cero para un parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="b14ee-114">The **Nil Value** functoid can have zero to one input parameters.</span></span> <span data-ttu-id="b14ee-115">Si no hay ningún parámetro de entrada para el functoid, el nodo de destino se establece en **Nil**.</span><span class="sxs-lookup"><span data-stu-id="b14ee-115">If there is no input parameter for this functoid, the target node is set to **Nil**.</span></span> <span data-ttu-id="b14ee-116">Para establecer el parámetro de entrada para el **valor nulo** functoid, crear un vínculo de entrada, arrastre la salida desde otro **lógicos** functoid o de un campo booleano variable en el mensaje de instancia de entrada.</span><span class="sxs-lookup"><span data-stu-id="b14ee-116">To establish the input parameter for the **Nil Value** functoid, create an input link by dragging the output from some other **Logical** functoid or from a variable Boolean field in the input instance message.</span></span>  
  
4.  <span data-ttu-id="b14ee-117">Para utilizar el parámetro de salida desde el **valor nulo** functoid, crear un vínculo de salida arrastrando el **valor nulo** functoid a un registro o campo del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="b14ee-117">To use the output parameter from the **Nil Value** functoid, create an output link by dragging the **Nil Value** functoid to a record or field in the destination schema.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b14ee-118">Al igual que con otros functoids, la salida de la **valor nulo** functoid puede utilizarse como entrada para otro functoid.</span><span class="sxs-lookup"><span data-stu-id="b14ee-118">As with other functoids, the output of the **Nil Value** functoid can be used as input to another functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b14ee-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="b14ee-119">See Also</span></span>  
-  <span data-ttu-id="b14ee-120">**Referencia de Functoid de valor nulo**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="b14ee-120">**Nil Value Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>   
-  [<span data-ttu-id="b14ee-121">Agregar Functoids avanzados a un mapa</span><span class="sxs-lookup"><span data-stu-id="b14ee-121">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)