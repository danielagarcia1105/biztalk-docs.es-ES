---
title: Cómo crear nuevas asignaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43b36cd8-f28e-4349-87d5-c94b7d8761bf
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 910d79782f4332ae1d706e12a8c5dda8c399a41b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249876"
---
# <a name="how-to-create-new-maps"></a><span data-ttu-id="cd54d-102">Cómo crear asignaciones nuevas</span><span class="sxs-lookup"><span data-stu-id="cd54d-102">How to Create New Maps</span></span>

## <a name="overview"></a><span data-ttu-id="cd54d-103">Información general</span><span class="sxs-lookup"><span data-stu-id="cd54d-103">Overview</span></span>
<span data-ttu-id="cd54d-104">Para generar una nueva asignación de BizTalk hay que llevar a cabo tres pasos de nivel superior:</span><span class="sxs-lookup"><span data-stu-id="cd54d-104">To build a new BizTalk map, there are three high-level steps to perform:</span></span>  
  
1.  <span data-ttu-id="cd54d-105">Crear la nueva asignación en un proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="cd54d-105">Create the new map within a BizTalk project.</span></span>  
  
2.  <span data-ttu-id="cd54d-106">Agregue los esquemas de origen y destino para la asignación.</span><span class="sxs-lookup"><span data-stu-id="cd54d-106">Add the source and destination schemas to the map.</span></span>  
  
3.  <span data-ttu-id="cd54d-107">Generar el conjunto de vínculos y, posiblemente, functoids intermedios que especifiquen cómo se asigna el esquema de origen al esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="cd54d-107">Build the set of links and, perhaps, intermediate functoids specifying how the source schema maps to the destination schema.</span></span>  
  
 <span data-ttu-id="cd54d-108">En el contexto actual, los dos primeros pasos de los tres mencionados, se consideran "crear" la asignación.</span><span class="sxs-lookup"><span data-stu-id="cd54d-108">In the current context, the first two of these three steps is considered "creating" the map.</span></span> <span data-ttu-id="cd54d-109">El tercer paso se considera "generar" la asignación.</span><span class="sxs-lookup"><span data-stu-id="cd54d-109">The third step is considered "building" the map.</span></span> <span data-ttu-id="cd54d-110">Para obtener instrucciones paso a paso acerca de muchas de las tareas relacionadas con el proceso de compilación del mapa, vea [utilizar Functoids para crear asignaciones más complejas](../core/using-functoids-to-create-more-complex-mappings.md).</span><span class="sxs-lookup"><span data-stu-id="cd54d-110">For step-by-step instructions on many of the tasks related to the process of building the map, see [Using Functoids to Create More Complex Mappings](../core/using-functoids-to-create-more-complex-mappings.md).</span></span>  
  
## <a name="create-a-new-map"></a><span data-ttu-id="cd54d-111">Crear una nueva asignación</span><span class="sxs-lookup"><span data-stu-id="cd54d-111">Create a new map</span></span> 
  
1.  <span data-ttu-id="cd54d-112">Haga clic en un proyecto de BizTalk en el Explorador de soluciones, seleccione **agregar**y, a continuación, seleccione **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="cd54d-112">Right-click a BizTalk project in Solution Explorer, select **Add**, and then select **New Item**.</span></span>  
  
2.  <span data-ttu-id="cd54d-113">En el **Agregar nuevo elemento** cuadro de diálogo, en la **plantillas** área, seleccione **mapa**.</span><span class="sxs-lookup"><span data-stu-id="cd54d-113">In the **Add New Item** dialog box, in the **Templates** area, select **Map**.</span></span>  
  
3.  <span data-ttu-id="cd54d-114">Seleccione el texto en el **nombre** cuadro, escriba un nombre para la asignación y, a continuación, seleccione **agregar**.</span><span class="sxs-lookup"><span data-stu-id="cd54d-114">Select the text in the **Name** box, type a name for the map, and then select **Add**.</span></span>  
  
     <span data-ttu-id="cd54d-115">El Asignador de BizTalk se abre en la ventana de edición de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y muestra adyacentemente tres paneles diferenciados.</span><span class="sxs-lookup"><span data-stu-id="cd54d-115">BizTalk Mapper opens in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window, showing three distinct panes, side-by-side.</span></span> <span data-ttu-id="cd54d-116">De izquierda a derecha, estos paneles muestran el esquema de origen, la cuadrícula (que puede tener múltiples páginas) y el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="cd54d-116">From left to right, these panes show the source schema, the grid (which may have multiple pages), and the destination schema.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="cd54d-117">No se puede usar los siguientes nombres para asignaciones: "XmlContent", "SourceSchemas", "TargetSchemas" o "XsltArgumentListContent".</span><span class="sxs-lookup"><span data-stu-id="cd54d-117">You cannot use the following names for maps: "XmlContent", "SourceSchemas", "TargetSchemas", or "XsltArgumentListContent".</span></span> <span data-ttu-id="cd54d-118">No pueden utilizarse estos nombres porque una compilación en un ensamblado .NET provoca restricciones de nombre como resultado del código C# generado.</span><span class="sxs-lookup"><span data-stu-id="cd54d-118">These names cannot be used because compilation into a .NET assembly produces naming restrictions as the result of generated C# code.</span></span>  
  
4.  <span data-ttu-id="cd54d-119">En el asignador de BizTalk, en el panel izquierdo, seleccione **Abrir esquema de origen**.</span><span class="sxs-lookup"><span data-stu-id="cd54d-119">In BizTalk Mapper, in the left pane, select **Open Source Schema**.</span></span>  
  
5.  <span data-ttu-id="cd54d-120">En el **selector de tipos de BizTalk** cuadro de diálogo, expanda el **esquemas** nodo, seleccione el esquema de origen que corresponda y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cd54d-120">In the **BizTalk Type Picker** dialog box, expand the **Schemas** node, select the appropriate source schema, and then select **OK**.</span></span>  

    > [!TIP] 
    > <span data-ttu-id="cd54d-121">**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** , puede cambiar el tamaño de la ventana del selector de tipos para ver el nombre completo del esquema.</span><span class="sxs-lookup"><span data-stu-id="cd54d-121">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, you can resize the Type Picker window to see the full name of your schema.</span></span>
  
     <span data-ttu-id="cd54d-122">Si solo existe una raíz del esquema de origen, o se ha establecido un nodo de raíz para el esquema mediante la **referencia raíz** propiedad de la **esquema** nodo, el esquema de origen se abre en el panel izquierdo y, puede continuar con el paso 7.</span><span class="sxs-lookup"><span data-stu-id="cd54d-122">If only a single root exists in the source schema, or a root node has been established for the schema using the **Root Reference** property of the **Schema** node, the source schema opens in the left pane, and you can proceed to step 7.</span></span>  
  
6.  <span data-ttu-id="cd54d-123">Si el esquema de origen tiene múltiples nodos raíz, y no se ha establecido ningún nodo de raíz para el esquema de origen mediante el **esquema** del nodo **referencia raíz** propiedad, en la **nodo raíz para el origen Esquema** cuadro de diálogo, seleccione el nodo raíz apropiado y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cd54d-123">If the source schema has multiple root nodes, and no root node has been established for the source schema using the **Schema** node's **Root Reference** property, in the **Root Node for Source Schema** dialog box, select the appropriate root node, and select **OK**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="cd54d-124">Si elige un nodo raíz para un esquema en el asignador de BizTalk y después cambie la **referencia raíz** propiedad en el esquema, la próxima vez que abra el esquema en el asignador de BizTalk, el nodo raíz no se actualizará con la nueva referencia raíz configurada en el Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="cd54d-124">If you choose a root node for a schema in BizTalk Mapper and then later change the **Root Reference** property in the schema, the next time you open the schema in BizTalk Mapper, the root node will not update to the new root reference configured in BizTalk Editor.</span></span>  
  
7.  <span data-ttu-id="cd54d-125">En el asignador de BizTalk, en el panel derecho, seleccione **Abrir esquema de destino**.</span><span class="sxs-lookup"><span data-stu-id="cd54d-125">In BizTalk Mapper, in the right pane, select **Open Destination Schema**.</span></span>  
  
8.  <span data-ttu-id="cd54d-126">En el **selector de tipos de BizTalk** cuadro de diálogo, expanda el **esquema** nodo en el árbol, si fuera necesario, seleccione el esquema de destino adecuado y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cd54d-126">In the **BizTalk Type Picker** dialog box, expand the **Schema** node in the tree, if necessary, select the appropriate destination schema, and then select **OK**.</span></span>  
  
     <span data-ttu-id="cd54d-127">Si solo existe una raíz del esquema de destino, o se ha establecido un nodo de raíz para el esquema de destino mediante el **referencia raíz** propiedad de la **esquema** abre el nodo, el esquema de destino en el panel derecho, y no debe realizar el paso 9.</span><span class="sxs-lookup"><span data-stu-id="cd54d-127">If only a single root exists in the destination schema, or a root node has been established for the destination schema using the **Root Reference** property of the **Schema** node, the destination schema opens in the right pane, and you will not need to perform step 9.</span></span>  
  
9. <span data-ttu-id="cd54d-128">Si el esquema de destino tiene múltiples nodos raíz, y no se ha establecido ningún nodo de raíz para el esquema de destino mediante el **referencia raíz** propiedad de la **esquema** nodo, en la **nodo raíz para el esquema de destino** cuadro de diálogo, seleccione el nodo raíz apropiado y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cd54d-128">If the destination schema has multiple root nodes, and no root node has been established for the destination schema using the **Root Reference** property of the **Schema** node, in the **Root Node for Target Schema** dialog box, select the appropriate root node, and select **OK**.</span></span>  
  
     <span data-ttu-id="cd54d-129">El esquema de destino se abre en el panel de la derecha.</span><span class="sxs-lookup"><span data-stu-id="cd54d-129">The destination schema opens in the right pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd54d-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd54d-130">See Also</span></span>  
 [<span data-ttu-id="cd54d-131">Administrar asignaciones en proyectos</span><span class="sxs-lookup"><span data-stu-id="cd54d-131">Managing Maps Within Projects</span></span>](../core/managing-maps-within-projects.md)