---
title: Cómo agregar Functoids de copia masiva a una asignación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1cff63fc-8f34-4bd0-8501-a8401bde6349
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52d79dc07c884d284fe4f6985453b86bb91b0660
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022146"
---
# <a name="how-to-add-mass-copy-functoids-to-a-map"></a><span data-ttu-id="5cf15-102">Cómo agregar functoids de copia masiva a una asignación</span><span class="sxs-lookup"><span data-stu-id="5cf15-102">How to Add Mass Copy Functoids to a Map</span></span>
<span data-ttu-id="5cf15-103">El **copia masiva** functoid permite que las asignaciones usen esquemas que incluyen **cualquier** y **anyAttribute** elementos.</span><span class="sxs-lookup"><span data-stu-id="5cf15-103">The **Mass Copy** functoid enables your maps to use schemas that include **any** and **anyAttribute** elements.</span></span> <span data-ttu-id="5cf15-104">Estos elementos son, fundamentalmente, caracteres comodín proporcionados en el lenguaje de definición de esquemas XML para coincidir con estructuras o conjuntos de atributos desconocidos.</span><span class="sxs-lookup"><span data-stu-id="5cf15-104">These elements are, in essence, wildcards provided in the XML Schema definition language to match unknown structures or sets of attributes.</span></span>  
  
 <span data-ttu-id="5cf15-105">Para obtener información conceptual sobre la **copia masiva** functoid, consulte [Functoid de copia masiva](../core/mass-copy-functoid.md).</span><span class="sxs-lookup"><span data-stu-id="5cf15-105">For conceptual information about the **Mass Copy** functoid, see [Mass Copy Functoid](../core/mass-copy-functoid.md).</span></span>  
  
### <a name="to-add-the-mass-copy-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="5cf15-106">Para agregar el functoid de copia masiva a una asignación y configurarlo</span><span class="sxs-lookup"><span data-stu-id="5cf15-106">To add the Mass Copy functoid to a map and configure it</span></span>  
  
1. <span data-ttu-id="5cf15-107">Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el activa, haga clic en cuadro de herramientas del **Functoids avanzados** tab para seleccionar esa categoría de functoids.</span><span class="sxs-lookup"><span data-stu-id="5cf15-107">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
    <span data-ttu-id="5cf15-108">Aparece la lista de functoids avanzados de la categoría seleccionada.</span><span class="sxs-lookup"><span data-stu-id="5cf15-108">The list of advanced functoids in the chosen category appears.</span></span>  
  
2. <span data-ttu-id="5cf15-109">Arrastre el **copia masiva** functoid (![](../core/media/advmasscopy.gif "advmasscopy")) desde el cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="5cf15-109">Drag the **Mass Copy** functoid (![](../core/media/advmasscopy.gif "advmasscopy")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5cf15-110">El functoid se colocará en la página de cuadrícula mostrada.</span><span class="sxs-lookup"><span data-stu-id="5cf15-110">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="5cf15-111">Si desea colocar el functoid en una página de cuadrícula diferente, deberá mostrar otra página de cuadrícula en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="5cf15-111">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5cf15-112">Si crea una asignación que utiliza más de un functoid, es necesario tener en cuenta su ubicación relativa de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="5cf15-112">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="5cf15-113">Los functoids se ejecutan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="5cf15-113">Functoids are executed from left to right.</span></span> <span data-ttu-id="5cf15-114">La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.</span><span class="sxs-lookup"><span data-stu-id="5cf15-114">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3. <span data-ttu-id="5cf15-115">Para establecer el parámetro de entrada para el **copia masiva** functoid, crear un vínculo de entrada arrastrando un registro desde el esquema de origen el **copia masiva** functoid, o bien arrastrando el **copia masiva** functoid a un registro en el esquema de origen.</span><span class="sxs-lookup"><span data-stu-id="5cf15-115">To establish the input parameter for the **Mass Copy** functoid, create an input link by dragging a record from the source schema to the **Mass Copy** functoid, or dragging the **Mass Copy** functoid to a record in the source schema.</span></span>  
  
4. <span data-ttu-id="5cf15-116">Para utilizar el parámetro de salida desde el **copia masiva** functoid, crear un vínculo de salida arrastrando el **copia masiva** functoid a un registro en el esquema de destino o arrastrando un registro en el esquema de destino el **copia masiva** functoid.</span><span class="sxs-lookup"><span data-stu-id="5cf15-116">To use the output parameter from the **Mass Copy** functoid, create an output link by dragging the **Mass Copy** functoid to a record in the destination schema, or by dragging a record in the destination schema to the **Mass Copy** functoid.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5cf15-117">A diferencia de otros functoids, no se puede usar la salida de la **copia masiva** functoid como entrada para otro functoid.</span><span class="sxs-lookup"><span data-stu-id="5cf15-117">Unlike other functoids, you cannot use the output of the **Mass Copy** functoid as input to another functoid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5cf15-118">Puede insertar y configurar el **copia masiva** functoid al vincular dos registros directamente.</span><span class="sxs-lookup"><span data-stu-id="5cf15-118">You can insert and configure the **Mass Copy** functoid by linking two records directly.</span></span> <span data-ttu-id="5cf15-119">Para obtener más información, vea la sección "para vincular mediante un functoid de copia masiva" en [cómo vincular registros automáticamente](../core/how-to-link-records-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="5cf15-119">For more information, see the section “To link using a mass copy functoid” in [How to Link Records Automatically](../core/how-to-link-records-automatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cf15-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="5cf15-120">See Also</span></span>  
 [<span data-ttu-id="5cf15-121">Agregar functoids avanzados a una asignación</span><span class="sxs-lookup"><span data-stu-id="5cf15-121">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)