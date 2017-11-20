---
title: "Cómo agregar Functoids a una asignación de bucle | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b24051b7-3e79-4a49-8249-a057c048ddae
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faa380b4a92de685ad8dc19c27a98f6578d12dc4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-looping-functoids-to-a-map"></a><span data-ttu-id="9b530-102">Cómo agregar functoids de bucle a una asignación</span><span class="sxs-lookup"><span data-stu-id="9b530-102">How to Add Looping Functoids to a Map</span></span>

## <a name="overview"></a><span data-ttu-id="9b530-103">Información general</span><span class="sxs-lookup"><span data-stu-id="9b530-103">Overview</span></span>
<span data-ttu-id="9b530-104">El **bucle** functoid combina múltiples registros o campos del esquema de origen en un único registro del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="9b530-104">The **Looping** functoid combines multiple records or fields in the source schema into a single record in the destination schema.</span></span>  
  
 <span data-ttu-id="9b530-105">Para obtener información conceptual acerca de la **bucle** functoid, consulte [Functoid de bucle de](../core/looping-functoid.md).</span><span class="sxs-lookup"><span data-stu-id="9b530-105">For conceptual information about the **Looping** functoid, see [Looping Functoid](../core/looping-functoid.md).</span></span>  
  
 <span data-ttu-id="9b530-106">Bajo ciertas condiciones, algunos functoids podrían no funcionar según lo esperado cuando se utilizan en un mapa con una **bucle** functoid.</span><span class="sxs-lookup"><span data-stu-id="9b530-106">Under certain conditions, some functoids might not behave as expected when they are used in a map with a **Looping** functoid.</span></span> <span data-ttu-id="9b530-107">Si un functoid cumple las siguientes condiciones, no producirá los resultados esperados:</span><span class="sxs-lookup"><span data-stu-id="9b530-107">If such a functoid meets the following conditions, it does not produce the expected results:</span></span>  
  
-   <span data-ttu-id="9b530-108">El functoid tiene más de un vínculo de entrada.</span><span class="sxs-lookup"><span data-stu-id="9b530-108">The functoid has more than one input link.</span></span>  
  
-   <span data-ttu-id="9b530-109">Dos o más de los vínculos de entrada de functoid están vinculados a campos secundarios de los registros de entrada a la **bucle** functoid, donde los campos secundarios no son del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="9b530-109">Two or more of the functoid input links are linked to child fields of the input records to the **Looping** functoid, where the child fields are not siblings.</span></span>  
  
-   <span data-ttu-id="9b530-110">El functoid tiene un vínculo de salida que está vinculado a un campo de elemento secundario del registro de salida de la **bucle** functoid.</span><span class="sxs-lookup"><span data-stu-id="9b530-110">The functoid has an output link that is linked to a child field of the output record of the **Looping** functoid.</span></span>  
  
## <a name="add-the-looping-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="9b530-111">Agregar el functoid de bucle a una asignación y configurarlo</span><span class="sxs-lookup"><span data-stu-id="9b530-111">Add the Looping functoid to a map and configure it</span></span>  
  
1.  <span data-ttu-id="9b530-112">Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] haga clic en cuadro de herramientas activa, el **Functoids avanzados** tab para seleccionar esta categoría de functoids.</span><span class="sxs-lookup"><span data-stu-id="9b530-112">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
     <span data-ttu-id="9b530-113">Aparece la lista de functoids avanzados de la categoría seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9b530-113">The list of advanced functoids in the chosen category appears.</span></span>  
  
2.  <span data-ttu-id="9b530-114">Arrastre el **bucle** functoid del cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="9b530-114">Drag the **Looping** functoid from the Toolbox to the appropriate location on a grid page.</span></span>  
  
     ![](../core/media/bts-tls-looping.gif "bts_tls_looping")  
<span data-ttu-id="9b530-115">Functoid de bucle</span><span class="sxs-lookup"><span data-stu-id="9b530-115">Looping functoid</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9b530-116">El functoid se colocará en la página de cuadrícula mostrada.</span><span class="sxs-lookup"><span data-stu-id="9b530-116">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="9b530-117">Si desea colocar el functoid en una página de cuadrícula diferente, necesitará mostrar otra página de cuadrícula en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="9b530-117">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
    > 
    >  <span data-ttu-id="9b530-118">Si crea una asignación que utiliza más de un functoid, es necesario tener en cuenta su ubicación relativa de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="9b530-118">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="9b530-119">Los functoids se ejecutan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="9b530-119">Functoids are executed from left to right.</span></span> <span data-ttu-id="9b530-120">La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.</span><span class="sxs-lookup"><span data-stu-id="9b530-120">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3.  <span data-ttu-id="9b530-121">Para establecer los parámetros de entrada para el **bucle** functoid, crear un vínculo de entrada arrastrando un registro o campo del esquema de origen a la **bucle** functoid, o bien arrastrando el **bucle**  functoid a un registro o campo del esquema de origen.</span><span class="sxs-lookup"><span data-stu-id="9b530-121">To establish the input parameters for the **Looping** functoid, create an input link by dragging a record or field from the source schema to the **Looping** functoid, or dragging the **Looping** functoid to a record or field in the source schema.</span></span> <span data-ttu-id="9b530-122">Repita según sea necesario para incluir todos los registros de entrada relevantes o campos a la **bucle** functoid.</span><span class="sxs-lookup"><span data-stu-id="9b530-122">Repeat as required to include all of the relevant input records or fields to the **Looping** functoid.</span></span>  
  
4.  <span data-ttu-id="9b530-123">Para utilizar el parámetro de salida desde el **bucle** functoid, crear un vínculo de salida arrastrando el **bucle** functoid a un registro o campo del esquema de destino, o arrastrando un registro o campo en el esquema de destino en la **bucle** functoid.</span><span class="sxs-lookup"><span data-stu-id="9b530-123">To use the output parameter from the **Looping** functoid, create an output link by dragging the **Looping** functoid to a record or field in the destination schema, or by dragging a record or field in the destination schema to the **Looping** functoid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9b530-124">A diferencia de muchos otros functoids, la salida de la **bucle** functoid solo puede vincularse a un elemento del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="9b530-124">Unlike many other functoids, the output of the **Looping** functoid can only be linked to an element of the destination schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b530-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b530-125">See Also</span></span>  
-  [<span data-ttu-id="9b530-126">Agregar Functoids avanzados a un mapa</span><span class="sxs-lookup"><span data-stu-id="9b530-126">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)   
-  <span data-ttu-id="9b530-127">**Referencia de Functoid de bucle**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="9b530-127">**Looping Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>