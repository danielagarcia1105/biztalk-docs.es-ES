---
title: Cómo agregar Functoids de bucle a una asignación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b24051b7-3e79-4a49-8249-a057c048ddae
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 659b9b39beea4bf5efed4c6d1553fca173191cc5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988765"
---
# <a name="how-to-add-looping-functoids-to-a-map"></a><span data-ttu-id="de7a8-102">Cómo agregar functoids de bucle a una asignación</span><span class="sxs-lookup"><span data-stu-id="de7a8-102">How to Add Looping Functoids to a Map</span></span>

## <a name="overview"></a><span data-ttu-id="de7a8-103">Información general</span><span class="sxs-lookup"><span data-stu-id="de7a8-103">Overview</span></span>
<span data-ttu-id="de7a8-104">El **bucle** functoid combina múltiples registros o campos del esquema de origen en un único registro del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="de7a8-104">The **Looping** functoid combines multiple records or fields in the source schema into a single record in the destination schema.</span></span>  

 <span data-ttu-id="de7a8-105">Para obtener información conceptual sobre la **bucle** functoid, consulte [Functoid de bucle](../core/looping-functoid.md).</span><span class="sxs-lookup"><span data-stu-id="de7a8-105">For conceptual information about the **Looping** functoid, see [Looping Functoid](../core/looping-functoid.md).</span></span>  

 <span data-ttu-id="de7a8-106">Bajo ciertas condiciones, algunos functoids podrían no funcionar según lo esperado cuando se usan en un mapa con una **bucle** functoid.</span><span class="sxs-lookup"><span data-stu-id="de7a8-106">Under certain conditions, some functoids might not behave as expected when they are used in a map with a **Looping** functoid.</span></span> <span data-ttu-id="de7a8-107">Si un functoid cumple las siguientes condiciones, no producirá los resultados esperados:</span><span class="sxs-lookup"><span data-stu-id="de7a8-107">If such a functoid meets the following conditions, it does not produce the expected results:</span></span>  

-   <span data-ttu-id="de7a8-108">El functoid tiene más de un vínculo de entrada.</span><span class="sxs-lookup"><span data-stu-id="de7a8-108">The functoid has more than one input link.</span></span>  

-   <span data-ttu-id="de7a8-109">Dos o más de los vínculos de entrada de functoid están vinculados a campos secundarios de los registros de entrada para el **bucle** functoid, donde los campos secundarios no son del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="de7a8-109">Two or more of the functoid input links are linked to child fields of the input records to the **Looping** functoid, where the child fields are not siblings.</span></span>  

-   <span data-ttu-id="de7a8-110">El functoid tiene un vínculo de salida que esté vinculado a un campo secundario del registro de salida de la **bucle** functoid.</span><span class="sxs-lookup"><span data-stu-id="de7a8-110">The functoid has an output link that is linked to a child field of the output record of the **Looping** functoid.</span></span>  

## <a name="add-the-looping-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="de7a8-111">Agregar el functoid de bucle a una asignación y configurarlo</span><span class="sxs-lookup"><span data-stu-id="de7a8-111">Add the Looping functoid to a map and configure it</span></span>  

1. <span data-ttu-id="de7a8-112">Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el activa, haga clic en cuadro de herramientas del **Functoids avanzados** tab para seleccionar esa categoría de functoids.</span><span class="sxs-lookup"><span data-stu-id="de7a8-112">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  

    <span data-ttu-id="de7a8-113">Aparece la lista de functoids avanzados de la categoría seleccionada.</span><span class="sxs-lookup"><span data-stu-id="de7a8-113">The list of advanced functoids in the chosen category appears.</span></span>  

2. <span data-ttu-id="de7a8-114">Arrastre el **bucle** functoid del cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="de7a8-114">Drag the **Looping** functoid from the Toolbox to the appropriate location on a grid page.</span></span>  

    <span data-ttu-id="de7a8-115">![](../core/media/bts-tls-looping.gif "bts_tls_looping")</span><span class="sxs-lookup"><span data-stu-id="de7a8-115">![](../core/media/bts-tls-looping.gif "bts_tls_looping")</span></span>  
   <span data-ttu-id="de7a8-116">Functoid de bucle</span><span class="sxs-lookup"><span data-stu-id="de7a8-116">Looping functoid</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="de7a8-117">El functoid se colocará en la página de cuadrícula mostrada.</span><span class="sxs-lookup"><span data-stu-id="de7a8-117">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="de7a8-118">Si desea colocar el functoid en una página de cuadrícula diferente, deberá mostrar otra página de cuadrícula en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="de7a8-118">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
   > 
   >  <span data-ttu-id="de7a8-119">Si crea una asignación que utiliza más de un functoid, es necesario tener en cuenta su ubicación relativa de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="de7a8-119">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="de7a8-120">Los functoids se ejecutan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="de7a8-120">Functoids are executed from left to right.</span></span> <span data-ttu-id="de7a8-121">La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.</span><span class="sxs-lookup"><span data-stu-id="de7a8-121">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  

3. <span data-ttu-id="de7a8-122">Para establecer los parámetros de entrada para el **bucle** functoid, crear un vínculo de entrada arrastrando un registro o campo del esquema de origen a la **bucle** functoid, o bien arrastrando el **bucle**  functoid a un registro o campo del esquema de origen.</span><span class="sxs-lookup"><span data-stu-id="de7a8-122">To establish the input parameters for the **Looping** functoid, create an input link by dragging a record or field from the source schema to the **Looping** functoid, or dragging the **Looping** functoid to a record or field in the source schema.</span></span> <span data-ttu-id="de7a8-123">Repita según sea necesario para incluir todos los registros de entrada relevantes o campos a la **bucle** functoid.</span><span class="sxs-lookup"><span data-stu-id="de7a8-123">Repeat as required to include all of the relevant input records or fields to the **Looping** functoid.</span></span>  

4. <span data-ttu-id="de7a8-124">Para utilizar el parámetro de salida desde el **bucle** functoid, crear un vínculo de salida arrastrando el **bucle** functoid a un registro o campo del esquema de destino o arrastrando un registro o campo en el esquema de destino en el **bucle** functoid.</span><span class="sxs-lookup"><span data-stu-id="de7a8-124">To use the output parameter from the **Looping** functoid, create an output link by dragging the **Looping** functoid to a record or field in the destination schema, or by dragging a record or field in the destination schema to the **Looping** functoid.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="de7a8-125">A diferencia de muchos otros functoids, la salida de la **bucle** functoid solo se puede vincular a un elemento del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="de7a8-125">Unlike many other functoids, the output of the **Looping** functoid can only be linked to an element of the destination schema.</span></span>  

## <a name="see-also"></a><span data-ttu-id="de7a8-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="de7a8-126">See Also</span></span>  
- [<span data-ttu-id="de7a8-127">Agregar functoids avanzados a una asignación</span><span class="sxs-lookup"><span data-stu-id="de7a8-127">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)   
- <span data-ttu-id="de7a8-128">**Referencia de Functoid de bucle** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="de7a8-128">**Looping Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
