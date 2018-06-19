---
title: Utilizar Functoids para crear asignaciones más complejas. | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d53e3a3-5ccd-4733-8c2f-3101e41fca61
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 736b6fa99844182c59db582182056faea1d3f322
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287164"
---
# <a name="using-functoids-to-create-more-complex-mappings"></a><span data-ttu-id="5345a-102">Utilizar functoids para crear asignaciones más complejas</span><span class="sxs-lookup"><span data-stu-id="5345a-102">Using Functoids to Create More Complex Mappings</span></span>

## <a name="overview"></a><span data-ttu-id="5345a-103">Información general</span><span class="sxs-lookup"><span data-stu-id="5345a-103">Overview</span></span>
<span data-ttu-id="5345a-104">Los functoids desempeñan un rol crucial en muchos escenarios de asignación.</span><span class="sxs-lookup"><span data-stu-id="5345a-104">Functoids play a crucial role in many mapping scenarios.</span></span> <span data-ttu-id="5345a-105">Sin functoids, puede copiar elementos y datos de atributos, pero no puede, en una gran medida, manipular los propios valores.</span><span class="sxs-lookup"><span data-stu-id="5345a-105">Without functoids, you can copy element and attribute data, but you cannot, to any significant extent, manipulate the values themselves.</span></span> <span data-ttu-id="5345a-106">Con los functoids es posible casi cualquier transformación.</span><span class="sxs-lookup"><span data-stu-id="5345a-106">Using functoids, almost any transformation is possible.</span></span> <span data-ttu-id="5345a-107">Por ejemplo, con un functoid puede tomar dos valores desde ubicaciones completamente diferentes, sumarlos y colocar la suma en el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="5345a-107">For example, with a functoid you can take two values from entirely different locations, add them together, and place the sum in the destination schema.</span></span>  
  
 <span data-ttu-id="5345a-108">Los functoids aparecen en el cuadro de herramientas de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] (una pestaña del cuadro de herramientas por cada categoría), al editar una asignación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5345a-108">Functoids appear in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox, one toolbox tab per category, when you are editing a BizTalk map.</span></span> <span data-ttu-id="5345a-109">Después de abrir el cuadro de herramientas y elegir una categoría de functoids haciendo clic en la pestaña correspondiente, se arrastra el functoid hasta una página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="5345a-109">After you open the Toolbox and choose a category of functoids by clicking on the corresponding tab, you drag the functoid onto a grid page.</span></span> <span data-ttu-id="5345a-110">A continuación, se crean vínculos de entrada y salida entre el functoid y bien nodos de esquema o bien otro functoid.</span><span class="sxs-lookup"><span data-stu-id="5345a-110">Then you create input and output links between the functoid and either schema nodes or another functoid.</span></span> <span data-ttu-id="5345a-111">Los vínculos de entrada se corresponden con parámetros de entrada y llegan a un functoid desde la izquierda; el vínculo de salida se corresponde con el parámetro de salida y abandona un functoid hacia la derecha.</span><span class="sxs-lookup"><span data-stu-id="5345a-111">Input links correspond to input parameters and lead to a functoid from the left; an output link corresponds to the output parameter and leaves a functoid to the right.</span></span>  
  
 <span data-ttu-id="5345a-112">Al igual que ocurre con otros elementos de asignaciones, los functoids tienen propiedades.</span><span class="sxs-lookup"><span data-stu-id="5345a-112">Like other map elements, functoids have properties.</span></span> <span data-ttu-id="5345a-113">Una de las propiedades más importantes de un functoid es su conjunto de parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="5345a-113">One of the most important properties of a functoid is its set of input parameters.</span></span> <span data-ttu-id="5345a-114">Para obtener más información, consulte [cómo agregar Functoids básicos a una asignación](../core/how-to-add-basic-functoids-to-a-map.md).</span><span class="sxs-lookup"><span data-stu-id="5345a-114">For more information, see [How to Add Basic Functoids to a Map](../core/how-to-add-basic-functoids-to-a-map.md).</span></span>  
  
 <span data-ttu-id="5345a-115">En esta sección se proporcionan instrucciones detalladas para trabajar con functoids dentro de asignaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5345a-115">This section provides step-by-step instructions for working with functoids within BizTalk maps.</span></span> <span data-ttu-id="5345a-116">Para obtener información de referencia acerca de functoids, consulte el **referencia de Functoid** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="5345a-116">For reference information about functoids, see the **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="5345a-117">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="5345a-117">Next steps</span></span> 
  
-   [<span data-ttu-id="5345a-118">Cómo abrir el cuadro de herramientas de Functoid</span><span class="sxs-lookup"><span data-stu-id="5345a-118">How to Open the Functoid Toolbox</span></span>](../core/how-to-open-the-functoid-toolbox.md)  
  
-   [<span data-ttu-id="5345a-119">Cómo agregar Functoids básicos a un mapa</span><span class="sxs-lookup"><span data-stu-id="5345a-119">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="5345a-120">Agregar Functoids avanzados a un mapa</span><span class="sxs-lookup"><span data-stu-id="5345a-120">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="5345a-121">Editar propiedades de Functoid y parámetros de entrada</span><span class="sxs-lookup"><span data-stu-id="5345a-121">Editing Functoid Properties and Input Parameters</span></span>](../core/editing-functoid-properties-and-input-parameters.md)  
  
-   [<span data-ttu-id="5345a-122">Cómo seleccionar varios Functoids</span><span class="sxs-lookup"><span data-stu-id="5345a-122">How to Select Multiple Functoids</span></span>](../core/how-to-select-multiple-functoids.md)  
  
-   [<span data-ttu-id="5345a-123">Cómo eliminar Functoids</span><span class="sxs-lookup"><span data-stu-id="5345a-123">How to Delete Functoids</span></span>](../core/how-to-delete-functoids.md)  
  
-   [<span data-ttu-id="5345a-124">Cómo copiar, cortar y pegar un Functoid</span><span class="sxs-lookup"><span data-stu-id="5345a-124">How to Copy, Cut, and Paste a Functoid</span></span>](../core/how-to-copy-cut-and-paste-a-functoid.md)