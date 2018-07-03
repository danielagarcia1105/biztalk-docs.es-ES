---
title: Cómo agregar Functoids de asignación a una asignación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc70067a-67a1-4a0e-95e5-b0cb327d2cee
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e4ba1b22b7db156717c2f40e91117562e879caa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996261"
---
# <a name="how-to-add-value-mapping-functoids-to-a-map"></a><span data-ttu-id="80425-102">Cómo agregar functoids de asignación de valores a una asignación</span><span class="sxs-lookup"><span data-stu-id="80425-102">How to Add Value Mapping Functoids to a Map</span></span>
<span data-ttu-id="80425-103">El **Value Mapping** functoid devuelve el valor de su segundo parámetro si el primer parámetro es true.</span><span class="sxs-lookup"><span data-stu-id="80425-103">The **Value Mapping** functoid returns the value of its second parameter if its first parameter is true.</span></span> <span data-ttu-id="80425-104">Una utilización común del functoid es cambiar los atributos de un campo a los atributos de un registro.</span><span class="sxs-lookup"><span data-stu-id="80425-104">A common use of the functoid is to change the attributes of a field into the attributes of a record.</span></span>  
  
 <span data-ttu-id="80425-105">Para obtener información conceptual sobre la **Value Mapping** functoid, consulte [el Functoid de asignación de valor](../core/value-mapping-functoid.md).</span><span class="sxs-lookup"><span data-stu-id="80425-105">For conceptual information about the **Value Mapping** functoid, see [Value Mapping Functoid](../core/value-mapping-functoid.md).</span></span>  
  
### <a name="to-add-the-value-mapping-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="80425-106">Para agregar el functoid de asignación de valores a una asignación y configurarlo</span><span class="sxs-lookup"><span data-stu-id="80425-106">To add the Value Mapping functoid to a map and configure it</span></span>  
  
1. <span data-ttu-id="80425-107">Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el activa, haga clic en cuadro de herramientas del **Functoids avanzados** tab para seleccionar esa categoría de functoids.</span><span class="sxs-lookup"><span data-stu-id="80425-107">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
    <span data-ttu-id="80425-108">Aparece la lista de functoids avanzados de la categoría seleccionada.</span><span class="sxs-lookup"><span data-stu-id="80425-108">The list of advanced functoids in the chosen category appears.</span></span>  
  
2. <span data-ttu-id="80425-109">Arrastre el **Value Mapping** functoid (![](../core/media/bts-tls-valmap.gif "bts_tls_valmap")) desde el cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="80425-109">Drag the **Value Mapping** functoid (![](../core/media/bts-tls-valmap.gif "bts_tls_valmap")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="80425-110">El functoid se colocará en la página de cuadrícula mostrada.</span><span class="sxs-lookup"><span data-stu-id="80425-110">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="80425-111">Si desea colocar el functoid en una página de cuadrícula diferente, deberá mostrar otra página de cuadrícula en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="80425-111">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="80425-112">Si crea una asignación que utiliza más de un functoid, es necesario tener en cuenta su ubicación relativa de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="80425-112">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="80425-113">Los functoids se ejecutan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="80425-113">Functoids are executed from left to right.</span></span> <span data-ttu-id="80425-114">La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.</span><span class="sxs-lookup"><span data-stu-id="80425-114">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3. <span data-ttu-id="80425-115">Para establecer el primer parámetro de entrada para el **Value Mapping** functoid, crear un vínculo de entrada arrastrando el **Value Mapping** functoid a un nodo registro o campo del esquema de origen, o hasta otro functoid para su izquierda, que tiene un tipo de datos booleano y que generará un valor de entrada "true" o "false".</span><span class="sxs-lookup"><span data-stu-id="80425-115">To establish the first input parameter for the **Value Mapping** functoid, create an input link by dragging the **Value Mapping** functoid to a record or field node in the source schema, or to another functoid to its left, that has a Boolean data type and that will produce an input value of "true" or "false".</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="80425-116">También puede arrastrar en la dirección opuesta, desplazando el origen del valor booleano para la **Value Mapping** functoid.</span><span class="sxs-lookup"><span data-stu-id="80425-116">You can also drag in the opposite direction, dragging the source of the Boolean value to the **Value Mapping** functoid.</span></span>  
  
4. <span data-ttu-id="80425-117">Para establecer el segundo parámetro de entrada para el **Value Mapping** functoid, crear un vínculo de entrada arrastrando el **Value Mapping** functoid a un nodo registro o campo del esquema de origen, o arrastrando un registro nodo de campo en el esquema de origen o el **Value Mapping** functoid.</span><span class="sxs-lookup"><span data-stu-id="80425-117">To establish the second input parameter for the **Value Mapping** functoid, create an input link by dragging the **Value Mapping** functoid to a record or field node in the source schema, or by dragging a record or field node in the source schema to the **Value Mapping** functoid.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="80425-118">El segundo parámetro de entrada la **Value Mapping** functoid también puede situarse desde la salida de otro functoid hacia su izquierda.</span><span class="sxs-lookup"><span data-stu-id="80425-118">The second input parameter to the **Value Mapping** functoid can also be from the output of another functoid to its left.</span></span> <span data-ttu-id="80425-119">Cree los vínculos que representan estos orígenes de entrada arrastrando uno de los functoids importantes hasta el otro functoid importante.</span><span class="sxs-lookup"><span data-stu-id="80425-119">Create the links that represent such sources of input by dragging one of the relevant functoids to the other relevant functoid.</span></span>  
  
5. <span data-ttu-id="80425-120">Para utilizar el parámetro de salida desde el **Value Mapping** functoid, crear un vínculo de salida arrastrando el **Value Mapping** functoid a un registro o campo del esquema de destino o arrastrando un campo de registro el esquema de destino para la **Value Mapping** functoid.</span><span class="sxs-lookup"><span data-stu-id="80425-120">To use the output parameter from the **Value Mapping** functoid, create an output link by dragging the **Value Mapping** functoid to a record or field in the destination schema, or by dragging a record field in the destination schema to the **Value Mapping** functoid.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="80425-121">Igual que con otros functoids, la salida de la **Value Mapping** functoid puede servir como entrada para otro functoid.</span><span class="sxs-lookup"><span data-stu-id="80425-121">As with other functoids, the output of the **Value Mapping** functoid can serve as input to another functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80425-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="80425-122">See Also</span></span>  
 [<span data-ttu-id="80425-123">Agregar functoids avanzados a una asignación</span><span class="sxs-lookup"><span data-stu-id="80425-123">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)