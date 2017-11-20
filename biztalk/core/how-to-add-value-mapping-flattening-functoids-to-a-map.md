---
title: "Cómo agregar la asignación de valores (sin formato) Functoids a una asignación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00a447c3-58d0-42ab-a5c4-417ee7800a6b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e5fe3f7b55a5bd5ef532bf2727c60bad2a621c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-value-mapping-flattening-functoids-to-a-map"></a><span data-ttu-id="54c59-102">Cómo agregar functoids de asignación de valores (sin formato) a una asignación</span><span class="sxs-lookup"><span data-stu-id="54c59-102">How to Add Value Mapping (Flattening) Functoids to a Map</span></span>
<span data-ttu-id="54c59-103">El **asignación de valores (sin formato)** functoid permite aplanar una parte de un mensaje de instancia de entrada convirtiendo varios registros en un único registro.</span><span class="sxs-lookup"><span data-stu-id="54c59-103">The **Value Mapping (Flattening)** functoid enables you to flatten a portion of an input instance message by converting multiple records into a single record.</span></span> <span data-ttu-id="54c59-104">Ésta es una operación común para convertir catálogos de Microsoft Commerce Server.</span><span class="sxs-lookup"><span data-stu-id="54c59-104">This is a common operation in converting Microsoft Commerce Server catalogs.</span></span>  
  
 <span data-ttu-id="54c59-105">Para obtener información conceptual acerca de la **asignación de valores (sin formato)** functoid, consulte [Functoid de asignación de valores (sin formato)](../core/value-mapping-flattening-functoid.md).</span><span class="sxs-lookup"><span data-stu-id="54c59-105">For conceptual information about the **Value Mapping (Flattening)** functoid, see [Value Mapping (Flattening) Functoid](../core/value-mapping-flattening-functoid.md).</span></span>  
  
### <a name="to-add-the-value-mapping-flattening-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="54c59-106">Para agregar el functoid de asignación de valores (sin formato) a una asignación y configurarla</span><span class="sxs-lookup"><span data-stu-id="54c59-106">To add the Value Mapping (Flattening) functoid to a map and configure it</span></span>  
  
1.  <span data-ttu-id="54c59-107">Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] haga clic en cuadro de herramientas activa, el **Functoids avanzados** tab para seleccionar esta categoría de functoids.</span><span class="sxs-lookup"><span data-stu-id="54c59-107">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
     <span data-ttu-id="54c59-108">Aparece la lista de functoids avanzados de la categoría seleccionada.</span><span class="sxs-lookup"><span data-stu-id="54c59-108">The list of advanced functoids in the chosen category appears.</span></span>  
  
2.  <span data-ttu-id="54c59-109">Arrastre el **asignación de valores (sin formato)** functoid (![](../core/media/bts-tls-valmapflat.gif "bts_tls_valmapflat")) en el cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="54c59-109">Drag the **Value Mapping (Flattening)** functoid (![](../core/media/bts-tls-valmapflat.gif "bts_tls_valmapflat")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="54c59-110">El functoid se colocará en la página de cuadrícula mostrada.</span><span class="sxs-lookup"><span data-stu-id="54c59-110">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="54c59-111">Si desea colocar el functoid en una página de cuadrícula diferente, necesitará mostrar otra página de cuadrícula en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="54c59-111">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="54c59-112">Si crea una asignación que utiliza más de un functoid, es necesario tener en cuenta su ubicación relativa de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="54c59-112">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="54c59-113">Los functoids se ejecutan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="54c59-113">Functoids are executed from left to right.</span></span> <span data-ttu-id="54c59-114">La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.</span><span class="sxs-lookup"><span data-stu-id="54c59-114">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3.  <span data-ttu-id="54c59-115">Para establecer el primer parámetro de entrada para el **asignación de valores (sin formato)** functoid, crear un vínculo de entrada arrastrando el **asignación de valores (sin formato)** functoid a un nodo registro o campo en el origen esquema, o a otro functoid situado a su izquierda, que tiene un tipo de datos booleano y que producirá un valor de entrada "true" o "false".</span><span class="sxs-lookup"><span data-stu-id="54c59-115">To establish the first input parameter for the **Value Mapping (Flattening)** functoid, create an input link by dragging the **Value Mapping (Flattening)** functoid to a record or field node in the source schema, or to another functoid to its left, that has a Boolean data type and that will produce an input value of "true" or "false."</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="54c59-116">También puede arrastrar en la dirección opuesta, desplazando el origen del valor booleano para la **asignación de valores (sin formato)** functoid.</span><span class="sxs-lookup"><span data-stu-id="54c59-116">You can also drag in the opposite direction, dragging the source of the Boolean value to the **Value Mapping (Flattening)** functoid.</span></span>  
  
4.  <span data-ttu-id="54c59-117">Para establecer el segundo parámetro de entrada para el **asignación de valores (sin formato)** functoid, crear un vínculo de entrada arrastrando el **asignación de valores (sin formato)** functoid a un nodo registro o campo en el origen esquema, o arrastrando un nodo registro o campo del esquema de origen a la **asignación de valores (sin formato)** functoid, o insertar una constante.</span><span class="sxs-lookup"><span data-stu-id="54c59-117">To establish the second input parameter for the **Value Mapping (Flattening)** functoid, create an input link by dragging the **Value Mapping (Flattening)** functoid to a record or field node in the source schema, or by dragging a record or field node in the source schema to the **Value Mapping (Flattening)** functoid, or insert a constant.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="54c59-118">El segundo parámetro de entrada el **asignación de valores (sin formato)** functoid también puede situarse desde la salida de otro functoid hacia su izquierda.</span><span class="sxs-lookup"><span data-stu-id="54c59-118">The second input parameter to the **Value Mapping (Flattening)** functoid can also be from the output of another functoid to its left.</span></span> <span data-ttu-id="54c59-119">Cree los vínculos que representan estos orígenes de entrada arrastrando uno de los functoids correspondientes hasta el otro functoid correspondiente.</span><span class="sxs-lookup"><span data-stu-id="54c59-119">Create the links the represent such sources of input by dragging one of the relevant functoids to the other relevant functoid.</span></span>  
  
5.  <span data-ttu-id="54c59-120">Para utilizar el parámetro de salida desde el **asignación de valores (sin formato)** functoid, crear un vínculo de salida arrastrando el **asignación de valores (sin formato)** functoid hasta un registro o campo del esquema de destino, o por Arrastre un campo de registro en el esquema de destino para la **asignación de valores (sin formato)** functoid.</span><span class="sxs-lookup"><span data-stu-id="54c59-120">To use the output parameter from the **Value Mapping (Flattening)** functoid, create an output link by dragging the **Value Mapping (Flattening)** functoid to a record or field in the destination schema, or by dragging a record field in the destination schema to the **Value Mapping (Flattening)** functoid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="54c59-121">Al igual que con otros functoids, la salida de la **asignación de valores (sin formato)** functoid puede utilizarse como entrada para otro functoid.</span><span class="sxs-lookup"><span data-stu-id="54c59-121">As with other functoids, the output of the **Value Mapping (Flattening)** functoid can be used as input to another functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54c59-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="54c59-122">See Also</span></span>  
 [<span data-ttu-id="54c59-123">Agregar Functoids avanzados a un mapa</span><span class="sxs-lookup"><span data-stu-id="54c59-123">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)