---
title: Cómo agregar Functoids de índice a una asignación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbfccfcc-c333-422f-b40b-13ca4152e588
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68b560b1565638c7d82d6f497319387fc5f58755
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976189"
---
# <a name="how-to-add-index-functoids-to-a-map"></a><span data-ttu-id="ce3f4-102">Cómo agregar functoids de índice a una asignación</span><span class="sxs-lookup"><span data-stu-id="ce3f4-102">How to Add Index Functoids to a Map</span></span>
<span data-ttu-id="ce3f4-103">El **índice** functoid le permite seleccionar la información de un registro específico en una serie de registros de bucle.</span><span class="sxs-lookup"><span data-stu-id="ce3f4-103">The **Index** functoid enables you to select information from a specific record in a series of looping records.</span></span> <span data-ttu-id="ce3f4-104">Cada **índice** functoid selecciona información de un solo campo.</span><span class="sxs-lookup"><span data-stu-id="ce3f4-104">Each **Index** functoid selects information from a single field.</span></span>  
  
 <span data-ttu-id="ce3f4-105">Para obtener información conceptual sobre la **índice** functoid, consulte [el Functoid de índice](../core/index-functoid.md).</span><span class="sxs-lookup"><span data-stu-id="ce3f4-105">For conceptual information about the **Index** functoid, see [Index Functoid](../core/index-functoid.md).</span></span>  
  
### <a name="to-add-the-index-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="ce3f4-106">Para agregar el functoid de índice a una asignación y configurarlo</span><span class="sxs-lookup"><span data-stu-id="ce3f4-106">To add the Index functoid to a map and configure it</span></span>  
  
1. <span data-ttu-id="ce3f4-107">Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el activa, haga clic en cuadro de herramientas del **Functoids avanzados** tab para seleccionar esa categoría de functoids.</span><span class="sxs-lookup"><span data-stu-id="ce3f4-107">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
    <span data-ttu-id="ce3f4-108">Aparece la lista de functoids avanzados de la categoría seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ce3f4-108">The list of advanced functoids in the chosen category appears.</span></span>  
  
2. <span data-ttu-id="ce3f4-109">Arrastre el **índice** functoid (![](../core/media/bts-tls-index.gif "bts_tls_index")) desde el cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="ce3f4-109">Drag the **Index** functoid (![](../core/media/bts-tls-index.gif "bts_tls_index")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ce3f4-110">El functoid se colocará en la página de cuadrícula mostrada.</span><span class="sxs-lookup"><span data-stu-id="ce3f4-110">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="ce3f4-111">Si desea colocar el functoid en una página de cuadrícula diferente, necesitará mostrar en primer lugar la otra página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="ce3f4-111">If you want to put the functoid onto a different grid page, you need to display the other grid page first.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ce3f4-112">Si se construye un mapa con más de un functoid juntas, necesitará tener en cuenta su ubicación relativa de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="ce3f4-112">If you are constructing a map using more than one functoid together, you need to consider their relative left-to-right placement.</span></span> <span data-ttu-id="ce3f4-113">Los functoids se ejecutan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="ce3f4-113">Functoids are executed from left to right.</span></span> <span data-ttu-id="ce3f4-114">La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.</span><span class="sxs-lookup"><span data-stu-id="ce3f4-114">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3. <span data-ttu-id="ce3f4-115">Para establecer el parámetro de entrada del campo para el **índice** functoid, crear un vínculo de entrada arrastrando un campo dentro de un registro de bucle del esquema de origen a la **índice** functoid, o bien arrastrando el **Índice** functoid a un campo del registro de bucle del esquema de origen.</span><span class="sxs-lookup"><span data-stu-id="ce3f4-115">To establish the field input parameter for the **Index** functoid, create an input link by dragging a field within a looping record from the source schema to the **Index** functoid, or dragging the **Index** functoid to a field within the looping record in the source schema.</span></span>  
  
4. <span data-ttu-id="ce3f4-116">Para establecer al menos un parámetro de entrada de índice para el **índice** functoid, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ce3f4-116">To establish at least one index input parameter for the **Index** functoid, perform the following steps:</span></span>  
  
   1.  <span data-ttu-id="ce3f4-117">Con el **índice** functoid seleccionado, haga clic en el botón de puntos suspensivos (**...** ) botón asociado a la **parámetros de entrada** propiedad en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="ce3f4-117">With the **Index** functoid selected, click the ellipsis (**...**) button associated with the **Input Parameters** property in the **Properties** window.</span></span>  
  
   2.  <span data-ttu-id="ce3f4-118">En el **configurar Functoid de índice** cuadro de diálogo, haga clic en el ![agregar parámetros de entrada constantes a un functoid](../core/media/add-input-parameters.gif "Add_input_parameters") botón.</span><span class="sxs-lookup"><span data-stu-id="ce3f4-118">In the **Configure Index Functoid** dialog box, click the ![Adding constant input parameters to a functoid](../core/media/add-input-parameters.gif "Add_input_parameters") button.</span></span>  
  
   3.  <span data-ttu-id="ce3f4-119">En el cuadro de edición, escriba el parámetro de entrada de índice como un valor numérico.</span><span class="sxs-lookup"><span data-stu-id="ce3f4-119">In the edit box, type the index input parameter as a numeric value.</span></span> <span data-ttu-id="ce3f4-120">Repita según sea necesario si los valores de índice adicionales son necesarios y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ce3f4-120">Repeat as necessary if additional index values are required, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="ce3f4-121">Para utilizar el parámetro de salida desde el **índice** functoid, crear un vínculo de salida arrastrando el **índice** functoid a un campo del esquema de destino o arrastrando un campo del esquema de destino para el  **Índice** functoid.</span><span class="sxs-lookup"><span data-stu-id="ce3f4-121">To use the output parameter from the **Index** functoid, create an output link by dragging the **Index** functoid to a field in the destination schema, or by dragging a field in the destination schema to the **Index** functoid.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ce3f4-122">Igual que con otros functoids, la salida de la **índice** functoid puede utilizarse como entrada para otro functoid.</span><span class="sxs-lookup"><span data-stu-id="ce3f4-122">As with other functoids, the output of the **Index** functoid can be used as input to another functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce3f4-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce3f4-123">See Also</span></span>  
 [<span data-ttu-id="ce3f4-124">Agregar functoids avanzados a una asignación</span><span class="sxs-lookup"><span data-stu-id="ce3f4-124">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)