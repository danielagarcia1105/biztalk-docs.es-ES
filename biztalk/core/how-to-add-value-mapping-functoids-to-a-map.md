---
title: "Cómo agregar Functoids de asignación a una asignación de valores | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc70067a-67a1-4a0e-95e5-b0cb327d2cee
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47e463489332c3a1d2887dab5f7bd734fdd20af5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-value-mapping-functoids-to-a-map"></a><span data-ttu-id="64b91-102">Cómo agregar functoids de asignación de valores a una asignación</span><span class="sxs-lookup"><span data-stu-id="64b91-102">How to Add Value Mapping Functoids to a Map</span></span>
<span data-ttu-id="64b91-103">El **Value Mapping** functoid devuelve el valor de su segundo parámetro si el primer parámetro es true.</span><span class="sxs-lookup"><span data-stu-id="64b91-103">The **Value Mapping** functoid returns the value of its second parameter if its first parameter is true.</span></span> <span data-ttu-id="64b91-104">Una utilización común del functoid es cambiar los atributos de un campo a los atributos de un registro.</span><span class="sxs-lookup"><span data-stu-id="64b91-104">A common use of the functoid is to change the attributes of a field into the attributes of a record.</span></span>  
  
 <span data-ttu-id="64b91-105">Para obtener información conceptual acerca de la **Value Mapping** functoid, consulte [el Functoid de asignación de valor](../core/value-mapping-functoid.md).</span><span class="sxs-lookup"><span data-stu-id="64b91-105">For conceptual information about the **Value Mapping** functoid, see [Value Mapping Functoid](../core/value-mapping-functoid.md).</span></span>  
  
### <a name="to-add-the-value-mapping-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="64b91-106">Para agregar el functoid de asignación de valores a una asignación y configurarlo</span><span class="sxs-lookup"><span data-stu-id="64b91-106">To add the Value Mapping functoid to a map and configure it</span></span>  
  
1.  <span data-ttu-id="64b91-107">Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] haga clic en cuadro de herramientas activa, el **Functoids avanzados** tab para seleccionar esta categoría de functoids.</span><span class="sxs-lookup"><span data-stu-id="64b91-107">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
     <span data-ttu-id="64b91-108">Aparece la lista de functoids avanzados de la categoría seleccionada.</span><span class="sxs-lookup"><span data-stu-id="64b91-108">The list of advanced functoids in the chosen category appears.</span></span>  
  
2.  <span data-ttu-id="64b91-109">Arrastre el **Value Mapping** functoid (![](../core/media/bts-tls-valmap.gif "bts_tls_valmap")) en el cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="64b91-109">Drag the **Value Mapping** functoid (![](../core/media/bts-tls-valmap.gif "bts_tls_valmap")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="64b91-110">El functoid se colocará en la página de cuadrícula mostrada.</span><span class="sxs-lookup"><span data-stu-id="64b91-110">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="64b91-111">Si desea colocar el functoid en una página de cuadrícula diferente, necesitará mostrar otra página de cuadrícula en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="64b91-111">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="64b91-112">Si crea una asignación que utiliza más de un functoid, es necesario tener en cuenta su ubicación relativa de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="64b91-112">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="64b91-113">Los functoids se ejecutan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="64b91-113">Functoids are executed from left to right.</span></span> <span data-ttu-id="64b91-114">La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.</span><span class="sxs-lookup"><span data-stu-id="64b91-114">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3.  <span data-ttu-id="64b91-115">Para establecer el primer parámetro de entrada para el **Value Mapping** functoid, crear un vínculo de entrada arrastrando el **Value Mapping** functoid a un nodo registro o campo del esquema de origen o a otro functoid situado a su izquierda, que tiene un tipo de datos booleano y que generará un valor de entrada "true" o "false".</span><span class="sxs-lookup"><span data-stu-id="64b91-115">To establish the first input parameter for the **Value Mapping** functoid, create an input link by dragging the **Value Mapping** functoid to a record or field node in the source schema, or to another functoid to its left, that has a Boolean data type and that will produce an input value of "true" or "false".</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="64b91-116">También puede arrastrar en la dirección opuesta, desplazando el origen del valor booleano para la **Value Mapping** functoid.</span><span class="sxs-lookup"><span data-stu-id="64b91-116">You can also drag in the opposite direction, dragging the source of the Boolean value to the **Value Mapping** functoid.</span></span>  
  
4.  <span data-ttu-id="64b91-117">Para establecer el segundo parámetro de entrada para el **Value Mapping** functoid, crear un vínculo de entrada arrastrando el **Value Mapping** functoid a un nodo registro o campo del esquema de origen, o arrastrando un registro nodo de campo en el esquema de origen o el **Value Mapping** functoid.</span><span class="sxs-lookup"><span data-stu-id="64b91-117">To establish the second input parameter for the **Value Mapping** functoid, create an input link by dragging the **Value Mapping** functoid to a record or field node in the source schema, or by dragging a record or field node in the source schema to the **Value Mapping** functoid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="64b91-118">El segundo parámetro de entrada el **Value Mapping** functoid también puede situarse desde la salida de otro functoid hacia su izquierda.</span><span class="sxs-lookup"><span data-stu-id="64b91-118">The second input parameter to the **Value Mapping** functoid can also be from the output of another functoid to its left.</span></span> <span data-ttu-id="64b91-119">Cree los vínculos que representan estos orígenes de entrada arrastrando uno de los functoids importantes hasta el otro functoid importante.</span><span class="sxs-lookup"><span data-stu-id="64b91-119">Create the links that represent such sources of input by dragging one of the relevant functoids to the other relevant functoid.</span></span>  
  
5.  <span data-ttu-id="64b91-120">Para utilizar el parámetro de salida desde el **Value Mapping** functoid, crear un vínculo de salida arrastrando el **Value Mapping** functoid hasta un registro o campo del esquema de destino o arrastrando un campo de registro el esquema de destino para la **Value Mapping** functoid.</span><span class="sxs-lookup"><span data-stu-id="64b91-120">To use the output parameter from the **Value Mapping** functoid, create an output link by dragging the **Value Mapping** functoid to a record or field in the destination schema, or by dragging a record field in the destination schema to the **Value Mapping** functoid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="64b91-121">Al igual que con otros functoids, la salida de la **Value Mapping** functoid puede servir como entrada para otro functoid.</span><span class="sxs-lookup"><span data-stu-id="64b91-121">As with other functoids, the output of the **Value Mapping** functoid can serve as input to another functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64b91-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="64b91-122">See Also</span></span>  
 [<span data-ttu-id="64b91-123">Agregar Functoids avanzados a un mapa</span><span class="sxs-lookup"><span data-stu-id="64b91-123">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)