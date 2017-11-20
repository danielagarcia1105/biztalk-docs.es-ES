---
title: "Cómo agregar Functoids de iteración a un mapa | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1eaea929-e352-447d-b119-bd69b6b24e6c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2df7cda082a9a85e54e1dce427d73ea15d8f920
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-iteration-functoids-to-a-map"></a><span data-ttu-id="c6297-102">Cómo agregar functoids de iteración a una asignación</span><span class="sxs-lookup"><span data-stu-id="c6297-102">How to Add Iteration Functoids to a Map</span></span>
<span data-ttu-id="c6297-103">El **iteración** functoid salidas el índice del registro actual en un bucle de la estructura, empezando por 1 para el primer registro, 2 para el segundo registro y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="c6297-103">The **Iteration** functoid outputs the index of the current record in a looping structure, beginning at 1 for the first record, 2 for the second record, and so on.</span></span>  
  
 <span data-ttu-id="c6297-104">Para obtener información conceptual acerca de la **iteración** functoid, consulte [Functoid de iteración](../core/iteration-functoid.md).</span><span class="sxs-lookup"><span data-stu-id="c6297-104">For conceptual information about the **Iteration** functoid, see [Iteration Functoid](../core/iteration-functoid.md).</span></span>  
  
### <a name="to-add-the-index-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="c6297-105">Para agregar el functoid de índice a una asignación y configurarlo</span><span class="sxs-lookup"><span data-stu-id="c6297-105">To add the Index functoid to a map and configure it</span></span>  
  
1.  <span data-ttu-id="c6297-106">Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] haga clic en cuadro de herramientas activa, el **Functoids avanzados** tab para seleccionar esta categoría de functoids.</span><span class="sxs-lookup"><span data-stu-id="c6297-106">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
     <span data-ttu-id="c6297-107">Aparece la lista de functoids avanzados de la categoría seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c6297-107">The list of advanced functoids in the chosen category appears.</span></span>  
  
2.  <span data-ttu-id="c6297-108">Arrastre el **índice** functoid (![](../core/media/bts-tls-iteration.gif "bts_tls_iteration")) en el cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="c6297-108">Drag the **Index** functoid (![](../core/media/bts-tls-iteration.gif "bts_tls_iteration")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6297-109">El functoid se colocará en la página de cuadrícula mostrada.</span><span class="sxs-lookup"><span data-stu-id="c6297-109">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="c6297-110">Si desea colocar el functoid en una página de cuadrícula diferente, necesitará mostrar otra página de cuadrícula en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="c6297-110">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6297-111">Si crea una asignación que utiliza más de un functoid, es necesario tener en cuenta su ubicación relativa de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="c6297-111">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="c6297-112">Los functoids se ejecutan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="c6297-112">Functoids are executed from left to right.</span></span> <span data-ttu-id="c6297-113">La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.</span><span class="sxs-lookup"><span data-stu-id="c6297-113">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3.  <span data-ttu-id="c6297-114">Para establecer el bucle parámetro de entrada de registro para el **iteración** functoid, crear un vínculo de entrada arrastrando un registro de bucle del esquema de origen a la **iteración** functoid, o bien arrastrando el  **Iteración** functoid hasta un registro de bucle del esquema de origen.</span><span class="sxs-lookup"><span data-stu-id="c6297-114">To establish the looping record input parameter for the **Iteration** functoid, create an input link by dragging a looping record from the source schema to the **Iteration** functoid, or by dragging the **Iteration** functoid to a looping record in the source schema.</span></span>  
  
4.  <span data-ttu-id="c6297-115">Para utilizar el parámetro de salida desde el **iteración** functoid, crear un vínculo de salida arrastrando el **iteración** functoid a un campo del esquema de destino o arrastrando un campo en el esquema de destino el **iteración** functoid.</span><span class="sxs-lookup"><span data-stu-id="c6297-115">To use the output parameter from the **Iteration** functoid, create an output link by dragging the **Iteration** functoid to a field in the destination schema, or by dragging a field in the destination schema to the **Iteration** functoid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6297-116">El tipo de datos del campo correspondiente en el esquema de destino debe ser numérico o convertible a numérico para que coincida con el tipo de datos de salida de la **iteración** functoid.</span><span class="sxs-lookup"><span data-stu-id="c6297-116">The data type of the relevant field in the destination schema must be numeric or convertible to numeric so that it matches the output data type of the **Iteration** functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6297-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6297-117">See Also</span></span>  
 [<span data-ttu-id="c6297-118">Agregar Functoids avanzados a un mapa</span><span class="sxs-lookup"><span data-stu-id="c6297-118">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)