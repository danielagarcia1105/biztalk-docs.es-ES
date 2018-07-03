---
title: Cómo agregar Functoids de (valores sin formato) de la asignación a una asignación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00a447c3-58d0-42ab-a5c4-417ee7800a6b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81486bedb71d69dde815f2849e0faf5b3b841f08
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981293"
---
# <a name="how-to-add-value-mapping-flattening-functoids-to-a-map"></a><span data-ttu-id="ca1aa-102">Cómo agregar functoids de asignación de valores (sin formato) a una asignación</span><span class="sxs-lookup"><span data-stu-id="ca1aa-102">How to Add Value Mapping (Flattening) Functoids to a Map</span></span>
<span data-ttu-id="ca1aa-103">El **asignación de valores (sin formato)** functoid permite aplanar una parte de un mensaje de instancia de entrada convirtiendo varios registros en un único registro.</span><span class="sxs-lookup"><span data-stu-id="ca1aa-103">The **Value Mapping (Flattening)** functoid enables you to flatten a portion of an input instance message by converting multiple records into a single record.</span></span> <span data-ttu-id="ca1aa-104">Ésta es una operación común para convertir catálogos de Microsoft Commerce Server.</span><span class="sxs-lookup"><span data-stu-id="ca1aa-104">This is a common operation in converting Microsoft Commerce Server catalogs.</span></span>  
  
 <span data-ttu-id="ca1aa-105">Para obtener información conceptual sobre la **asignación de valores (sin formato)** functoid, consulte [Functoid de asignación de (valores sin formato)](../core/value-mapping-flattening-functoid.md).</span><span class="sxs-lookup"><span data-stu-id="ca1aa-105">For conceptual information about the **Value Mapping (Flattening)** functoid, see [Value Mapping (Flattening) Functoid](../core/value-mapping-flattening-functoid.md).</span></span>  
  
### <a name="to-add-the-value-mapping-flattening-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="ca1aa-106">Para agregar el functoid de asignación de valores (sin formato) a una asignación y configurarla</span><span class="sxs-lookup"><span data-stu-id="ca1aa-106">To add the Value Mapping (Flattening) functoid to a map and configure it</span></span>  
  
1. <span data-ttu-id="ca1aa-107">Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el activa, haga clic en cuadro de herramientas del **Functoids avanzados** tab para seleccionar esa categoría de functoids.</span><span class="sxs-lookup"><span data-stu-id="ca1aa-107">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
    <span data-ttu-id="ca1aa-108">Aparece la lista de functoids avanzados de la categoría seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ca1aa-108">The list of advanced functoids in the chosen category appears.</span></span>  
  
2. <span data-ttu-id="ca1aa-109">Arrastre el **asignación de valores (sin formato)** functoid (![](../core/media/bts-tls-valmapflat.gif "bts_tls_valmapflat")) desde el cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="ca1aa-109">Drag the **Value Mapping (Flattening)** functoid (![](../core/media/bts-tls-valmapflat.gif "bts_tls_valmapflat")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ca1aa-110">El functoid se colocará en la página de cuadrícula mostrada.</span><span class="sxs-lookup"><span data-stu-id="ca1aa-110">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="ca1aa-111">Si desea colocar el functoid en una página de cuadrícula diferente, deberá mostrar otra página de cuadrícula en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="ca1aa-111">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ca1aa-112">Si crea una asignación que utiliza más de un functoid, es necesario tener en cuenta su ubicación relativa de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="ca1aa-112">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="ca1aa-113">Los functoids se ejecutan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="ca1aa-113">Functoids are executed from left to right.</span></span> <span data-ttu-id="ca1aa-114">La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.</span><span class="sxs-lookup"><span data-stu-id="ca1aa-114">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3. <span data-ttu-id="ca1aa-115">Para establecer el primer parámetro de entrada para el **asignación de valores (sin formato)** functoid, crear un vínculo de entrada arrastrando el **asignación de valores (sin formato)** functoid a un nodo registro o campo en el origen esquema, o a otro functoid hacia su izquierda, que tiene un tipo de datos booleano y que generará un valor de entrada de "true" o "false".</span><span class="sxs-lookup"><span data-stu-id="ca1aa-115">To establish the first input parameter for the **Value Mapping (Flattening)** functoid, create an input link by dragging the **Value Mapping (Flattening)** functoid to a record or field node in the source schema, or to another functoid to its left, that has a Boolean data type and that will produce an input value of "true" or "false."</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ca1aa-116">También puede arrastrar en la dirección opuesta, desplazando el origen del valor booleano para la **asignación de valores (sin formato)** functoid.</span><span class="sxs-lookup"><span data-stu-id="ca1aa-116">You can also drag in the opposite direction, dragging the source of the Boolean value to the **Value Mapping (Flattening)** functoid.</span></span>  
  
4. <span data-ttu-id="ca1aa-117">Para establecer el segundo parámetro de entrada para el **asignación de valores (sin formato)** functoid, crear un vínculo de entrada arrastrando el **asignación de valores (sin formato)** functoid a un nodo registro o campo en el origen esquema, o arrastrando un nodo registro o campo del esquema de origen a la **asignación de valores (sin formato)** functoid, o inserte una constante.</span><span class="sxs-lookup"><span data-stu-id="ca1aa-117">To establish the second input parameter for the **Value Mapping (Flattening)** functoid, create an input link by dragging the **Value Mapping (Flattening)** functoid to a record or field node in the source schema, or by dragging a record or field node in the source schema to the **Value Mapping (Flattening)** functoid, or insert a constant.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ca1aa-118">El segundo parámetro de entrada la **asignación de valores (sin formato)** functoid también puede situarse desde la salida de otro functoid hacia su izquierda.</span><span class="sxs-lookup"><span data-stu-id="ca1aa-118">The second input parameter to the **Value Mapping (Flattening)** functoid can also be from the output of another functoid to its left.</span></span> <span data-ttu-id="ca1aa-119">Cree los vínculos que representan estos orígenes de entrada arrastrando uno de los functoids correspondientes hasta el otro functoid correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ca1aa-119">Create the links the represent such sources of input by dragging one of the relevant functoids to the other relevant functoid.</span></span>  
  
5. <span data-ttu-id="ca1aa-120">Para utilizar el parámetro de salida desde el **asignación de valores (sin formato)** functoid, crear un vínculo de salida arrastrando el **asignación de valores (sin formato)** functoid a un registro o campo en el esquema de destino, o bien arrastrar un campo de registro en el esquema de destino para la **asignación de valores (sin formato)** functoid.</span><span class="sxs-lookup"><span data-stu-id="ca1aa-120">To use the output parameter from the **Value Mapping (Flattening)** functoid, create an output link by dragging the **Value Mapping (Flattening)** functoid to a record or field in the destination schema, or by dragging a record field in the destination schema to the **Value Mapping (Flattening)** functoid.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ca1aa-121">Igual que con otros functoids, la salida de la **asignación de valores (sin formato)** functoid puede utilizarse como entrada para otro functoid.</span><span class="sxs-lookup"><span data-stu-id="ca1aa-121">As with other functoids, the output of the **Value Mapping (Flattening)** functoid can be used as input to another functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca1aa-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca1aa-122">See Also</span></span>  
 [<span data-ttu-id="ca1aa-123">Agregar functoids avanzados a una asignación</span><span class="sxs-lookup"><span data-stu-id="ca1aa-123">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)