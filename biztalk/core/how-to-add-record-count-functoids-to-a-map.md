---
title: Cómo agregar Functoids de número de registros a una asignación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fbfd2a0-fac5-49f1-bcbb-873c287cd278
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d5fda3565d2b7c3302b5ae3cb596bfed6781609
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980333"
---
# <a name="how-to-add-record-count-functoids-to-a-map"></a><span data-ttu-id="a0f28-102">Cómo agregar functoids de número de registros a una asignación</span><span class="sxs-lookup"><span data-stu-id="a0f28-102">How to Add Record Count Functoids to a Map</span></span>
<span data-ttu-id="a0f28-103">El **número de registros** functoid le permite generar un recuento del número de veces que se produce un registro en un mensaje de instancia.</span><span class="sxs-lookup"><span data-stu-id="a0f28-103">The **Record Count** functoid enables you to generate a count of the number of times a record occurs in an instance message.</span></span>  
  
 <span data-ttu-id="a0f28-104">Para obtener información conceptual sobre la **número de registros** functoid, consulte [Functoid de número de registros](../core/record-count-functoid.md).</span><span class="sxs-lookup"><span data-stu-id="a0f28-104">For conceptual information about the **Record Count** functoid, see [Record Count Functoid](../core/record-count-functoid.md).</span></span>  
  
### <a name="to-add-the-record-count-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="a0f28-105">Para agregar el functoid de número de registros a una asignación y configurarlo</span><span class="sxs-lookup"><span data-stu-id="a0f28-105">To add the Record Count functoid to a map and configure it</span></span>  
  
1. <span data-ttu-id="a0f28-106">Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el activa, haga clic en cuadro de herramientas del **Functoids avanzados** tab para seleccionar esa categoría de functoids.</span><span class="sxs-lookup"><span data-stu-id="a0f28-106">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
    <span data-ttu-id="a0f28-107">Aparece la lista de functoids avanzados de la categoría seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a0f28-107">The list of advanced functoids in the chosen category appears.</span></span>  
  
2. <span data-ttu-id="a0f28-108">Arrastre el **número de registros** functoid (![](../core/media/bts-tls-recordcount.gif "bts_tls_recordcount")) desde el cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="a0f28-108">Drag the **Record Count** functoid (![](../core/media/bts-tls-recordcount.gif "bts_tls_recordcount")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a0f28-109">El functoid se colocará en la página de cuadrícula mostrada.</span><span class="sxs-lookup"><span data-stu-id="a0f28-109">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="a0f28-110">Si desea colocar el functoid en una página de cuadrícula diferente, necesitará mostrar en primer lugar la otra página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="a0f28-110">If you want to put the functoid onto a different grid page, you need to display the other grid page first.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a0f28-111">Si crea una asignación que utiliza más de un functoid, es necesario tener en cuenta su ubicación relativa de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="a0f28-111">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="a0f28-112">Los functoids se ejecutan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="a0f28-112">Functoids are executed from left to right.</span></span> <span data-ttu-id="a0f28-113">La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.</span><span class="sxs-lookup"><span data-stu-id="a0f28-113">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3. <span data-ttu-id="a0f28-114">Para establecer el parámetro de entrada para el **número de registros** functoid, crear un vínculo de entrada arrastrando un registro de bucle del esquema de origen a la **número de registros** functoid, o bien arrastrando el  **Número de registros** functoid a un registro de bucle del esquema de origen.</span><span class="sxs-lookup"><span data-stu-id="a0f28-114">To establish the input parameter for the **Record Count** functoid, create an input link by dragging a looping record from the source schema to the **Record Count** functoid, or dragging the **Record Count** functoid to a looping record in the source schema.</span></span>  
  
4. <span data-ttu-id="a0f28-115">Para utilizar el parámetro de salida desde el **número de registros** functoid, crear un vínculo de salida arrastrando el **número de registros** functoid a un campo del esquema de destino o arrastrando un campo en el destino esquema para el **número de registros** functoid.</span><span class="sxs-lookup"><span data-stu-id="a0f28-115">To use the output parameter from the **Record Count** functoid, create an output link by dragging the **Record Count** functoid to a field in the destination schema, or by dragging a field in the destination schema to the **Record Count** functoid.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a0f28-116">Igual que con otros functoids, la salida de la **número de registros** functoid puede utilizarse como entrada para otro functoid.</span><span class="sxs-lookup"><span data-stu-id="a0f28-116">As with other functoids, the output of the **Record Count** functoid can be used as input to another functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0f28-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0f28-117">See Also</span></span>  
 [<span data-ttu-id="a0f28-118">Agregar functoids avanzados a una asignación</span><span class="sxs-lookup"><span data-stu-id="a0f28-118">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)