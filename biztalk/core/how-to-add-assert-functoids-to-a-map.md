---
title: Cómo agregar Functoids a una asignación de aserción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccdd79a2-b70f-489b-8711-e00a50d8e2d8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 553daa0c6e97d09e8284d2369e801c5d2ff8beee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247764"
---
# <a name="how-to-add-assert-functoids-to-a-map"></a><span data-ttu-id="6224f-102">Cómo agregar functoids de aserción a una asignación</span><span class="sxs-lookup"><span data-stu-id="6224f-102">How to Add Assert Functoids to a Map</span></span>
<span data-ttu-id="6224f-103">El **Assert** functoid le permite probar sus suposiciones acerca de las condiciones de la asignación.</span><span class="sxs-lookup"><span data-stu-id="6224f-103">The **Assert** functoid enables you to test your assumptions about conditions in your map.</span></span> <span data-ttu-id="6224f-104">Por ejemplo, si realiza cálculos para determinar un descuento adicional sobre las compras de productos, podría imponer que el descuento adicional sea no más de 100 $ mediante un functoid lógico (**Greater Than** o  **Less than**).</span><span class="sxs-lookup"><span data-stu-id="6224f-104">For example, if you perform some calculations to determine an additional discount on product purchases, you might assert that the additional discount be no more than $100 by using a logical functoid (**Greater Than** or **Less Than**).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6224f-105">El **Assert** functoid solo se activa en las compilaciones de desarrollo o cuando la **generar información de depuración** propiedad en la configuración de compilación del proyecto está establecida en **True**.</span><span class="sxs-lookup"><span data-stu-id="6224f-105">The **Assert** functoid only fires in development builds or when the **Generate Debugging Information** property in the project build settings is set to **True**.</span></span> <span data-ttu-id="6224f-106">Cuando se compila la aplicación de BizTalk para la implementación y la **generar información de depuración** propiedad está establecida en **False** (valor predeterminado), se omiten las aserciones.</span><span class="sxs-lookup"><span data-stu-id="6224f-106">When your BizTalk application is compiled for deployment and the **Generate Debugging Information** property is set to **False** (the default), assertions are ignored.</span></span>  
  
 <span data-ttu-id="6224f-107">Para obtener información conceptual acerca de la **Assert** functoid, consulte [Functoid imponer](../core/assert-functoid.md).</span><span class="sxs-lookup"><span data-stu-id="6224f-107">For conceptual information about the **Assert** functoid, see [Assert Functoid](../core/assert-functoid.md).</span></span>  
  
## <a name="add-the-assert-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="6224f-108">Agregar el functoid imponer a una asignación y configurarlo</span><span class="sxs-lookup"><span data-stu-id="6224f-108">Add the Assert functoid to a map and configure it</span></span>  
  
1.  <span data-ttu-id="6224f-109">Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] haga clic en cuadro de herramientas activa, el **Functoids avanzados** tab para seleccionar esta categoría de functoids.</span><span class="sxs-lookup"><span data-stu-id="6224f-109">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span> <span data-ttu-id="6224f-110">Aparece la lista de functoids avanzados de la categoría seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6224f-110">The list of advanced functoids in the chosen category appears.</span></span>  
  
2.  <span data-ttu-id="6224f-111">Arrastre el **Assert** functoid (![functoid de aserción](../core/media/advanced-assert-functoid.gif "advanced_assert_functoid")) en el cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="6224f-111">Drag the **Assert** functoid (![Assert functoid](../core/media/advanced-assert-functoid.gif "advanced_assert_functoid")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6224f-112">El functoid se colocará en la página de cuadrícula mostrada.</span><span class="sxs-lookup"><span data-stu-id="6224f-112">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="6224f-113">Si desea colocar el functoid en una página de cuadrícula diferente, necesitará mostrar otra página de cuadrícula en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="6224f-113">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span> 
    >    
    >  <span data-ttu-id="6224f-114">Si crea una asignación que usa más de un functoid, es necesario tener en cuenta su ubicación relativa de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="6224f-114">If you are constructing a map that uses more than one functoid, you need to consider their relative left-to-right placement.</span></span> <span data-ttu-id="6224f-115">Los functoids se ejecutan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="6224f-115">Functoids are executed from left to right.</span></span> <span data-ttu-id="6224f-116">La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.</span><span class="sxs-lookup"><span data-stu-id="6224f-116">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3.  <span data-ttu-id="6224f-117">El functoid debe tener exactamente tres parámetros de entrada y genera un parámetro de salida.</span><span class="sxs-lookup"><span data-stu-id="6224f-117">The functoid must have exactly three input parameters and it generates one output parameter.</span></span> <span data-ttu-id="6224f-118">Para establecer el primer parámetro para el **Assert** functoid, crear un vínculo de entrada, arrastre la salida desde otro **lógicos** functoid o de un campo booleano variable en el mensaje de instancia de entrada.</span><span class="sxs-lookup"><span data-stu-id="6224f-118">To establish the first parameter for the **Assert** functoid, create an input link by dragging the output from some other **Logical** functoid or from a variable Boolean field in the input instance message.</span></span>  
  
4.  <span data-ttu-id="6224f-119">Para establecer el segundo parámetro de entrada para el **Assert** functoid, cree un vínculo de entrada mediante un nodo de campo del esquema de origen a la **Assert** functoid, o insertar una constante.</span><span class="sxs-lookup"><span data-stu-id="6224f-119">To establish the second input parameter for the **Assert** functoid, create an input link by a field node in the source schema to the **Assert** functoid, or insert a constant.</span></span>  
  
5.  <span data-ttu-id="6224f-120">Para establecer el tercer parámetro de entrada para el **Assert** functoid, cree un vínculo de entrada mediante un nodo de campo del esquema de origen a la **Assert** functoid, o insertar una constante.</span><span class="sxs-lookup"><span data-stu-id="6224f-120">To establish the third input parameter for the **Assert** functoid, create an input link by a field node in the source schema to the **Assert** functoid, or insert a constant.</span></span>  
  
6.  <span data-ttu-id="6224f-121">Para utilizar el parámetro de salida desde el **Assert** functoid, crear un vínculo de salida arrastrando el **Assert** functoid a un campo del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="6224f-121">To use the output parameter from the **Assert** functoid, create an output link by dragging the **Assert** functoid to a field in the destination schema.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6224f-122">Al igual que con otros functoids, la salida de la **Assert** functoid puede utilizarse como entrada para otro functoid.</span><span class="sxs-lookup"><span data-stu-id="6224f-122">As with other functoids, the output of the **Assert** functoid can be used as input to another functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6224f-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="6224f-123">See Also</span></span>  
-  <span data-ttu-id="6224f-124">**Referencia de Functoid de aserción**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="6224f-124">**Assert Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>   
-  [<span data-ttu-id="6224f-125">Agregar Functoids avanzados a un mapa</span><span class="sxs-lookup"><span data-stu-id="6224f-125">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)