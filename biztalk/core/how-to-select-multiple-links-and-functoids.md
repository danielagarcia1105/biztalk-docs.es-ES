---
title: "Cómo seleccionar varios vínculos y Functoids | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f9ae50cb-c212-48f3-9dfb-74df282645c5
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8885fe33d0c3a2dc081fbca66a398003c3e21913
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-select-multiple-links-and-functoids"></a><span data-ttu-id="04a19-102">Selección de varios vínculos y functoids</span><span class="sxs-lookup"><span data-stu-id="04a19-102">How to Select Multiple Links and Functoids</span></span>
<span data-ttu-id="04a19-103">Si desea realizar una operación similar en un grupo de functoids y/o vínculos en un mapa, puede seleccionar ese grupo de functoids y/o vínculos todos a la vez.</span><span class="sxs-lookup"><span data-stu-id="04a19-103">When you want to perform a similar operation on a group of functoids and/or links in a map, you can select that group of functoids and/or links all at the same time.</span></span> <span data-ttu-id="04a19-104">Este tema proporciona información acerca de cómo realizar esta operación.</span><span class="sxs-lookup"><span data-stu-id="04a19-104">This topic provides information about how to perform this operation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="04a19-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="04a19-105">Prerequisites</span></span>  
 <span data-ttu-id="04a19-106">Estas instrucciones requieren que se está ejecutando el asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="04a19-106">These instructions require that BizTalk Mapper is running.</span></span>  
  
## <a name="why-do-you-need-to-bulk-select-linksfunctoids"></a><span data-ttu-id="04a19-107">¿Por qué necesita realizar selecciones masivas de vínculos y functoids?</span><span class="sxs-lookup"><span data-stu-id="04a19-107">Why do you need to bulk-select links/functoids?</span></span>  
 <span data-ttu-id="04a19-108">Puede seleccionar de forma masiva vínculos y/o functoids para llevar a cabo cualquiera de las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="04a19-108">You can bulk-select links and/or functoids to do any of the following:</span></span>  
  
-   <span data-ttu-id="04a19-109">Copiar/cortar y pegar la selección en la misma página de cuadrícula o en otra en la misma asignación.</span><span class="sxs-lookup"><span data-stu-id="04a19-109">Copy/cut and paste the selection in the same grid page or another grid page in the same map.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="04a19-110">Para obtener información acerca de cómo copiar, cortar y pegar vínculos y functoids, consulte [cómo copiar, cortar y pegar vínculos y Functoids](../core/how-to-copy-cut-and-paste-links-and-functoids.md).</span><span class="sxs-lookup"><span data-stu-id="04a19-110">For information on how to copy, cut, and paste links and functoids, see [How to Copy, Cut, and Paste Links and Functoids](../core/how-to-copy-cut-and-paste-links-and-functoids.md).</span></span>  
  
-   <span data-ttu-id="04a19-111">Mover la selección entre las páginas de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="04a19-111">Move the selection between grid pages</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="04a19-112">Para obtener información acerca de cómo mover una relación de una página de cuadrícula a otro, consulte [cómo mover una relación entre páginas de cuadrícula](../core/how-to-move-a-relationship-between-grid-pages.md).</span><span class="sxs-lookup"><span data-stu-id="04a19-112">For information on how to move a relationship from one grid page to another, see [How to Move a Relationship Between Grid Pages](../core/how-to-move-a-relationship-between-grid-pages.md).</span></span>  
  
-   <span data-ttu-id="04a19-113">Editar las propiedades comunes de functoids y vínculos de la selección.</span><span class="sxs-lookup"><span data-stu-id="04a19-113">Edit the common properties of functoids and links in the selection</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="04a19-114">Para obtener información sobre cómo establecer comentarios y etiquetas de functoids y vínculos, consulte [cómo etiquetar un vínculo](../core/how-to-label-a-link.md) o [cómo etiquetar y comentar un Functoid](../core/how-to-label-and-comment-a-functoid.md).</span><span class="sxs-lookup"><span data-stu-id="04a19-114">For information on how to set comments and labels for functoids and links, see [How to Label a Link](../core/how-to-label-a-link.md) or [How to Label and Comment a Functoid](../core/how-to-label-and-comment-a-functoid.md).</span></span>  
  
-   <span data-ttu-id="04a19-115">Eliminación de varios vínculos o functoids en un paso</span><span class="sxs-lookup"><span data-stu-id="04a19-115">Deleting multiple link(s) and/or functoid(s) in one step</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="04a19-116">Para obtener información sobre cómo eliminar functoids, consulte [cómo eliminar Functoids](../core/how-to-delete-functoids.md).</span><span class="sxs-lookup"><span data-stu-id="04a19-116">For information on how to delete functoids, see [How to Delete Functoids](../core/how-to-delete-functoids.md).</span></span>  
  
## <a name="to-select-multiple-links-and-functoids"></a><span data-ttu-id="04a19-117">Procedimiento para seleccionar varios vínculos y functoids</span><span class="sxs-lookup"><span data-stu-id="04a19-117">To select multiple links and functoids</span></span>  
 <span data-ttu-id="04a19-118">Puede seleccionar de forma masiva functoids y/o vínculos de cualquiera de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="04a19-118">You can bulk-select functoids and/or links in any of the following ways:</span></span>  
  
-   <span data-ttu-id="04a19-119">Haga clic en el vínculo o el functoid.</span><span class="sxs-lookup"><span data-stu-id="04a19-119">Click the link or the functoid.</span></span> <span data-ttu-id="04a19-120">Mantenga presionada la tecla CTRL y, a continuación, haga clic en los otros vínculos y/o functoids que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="04a19-120">Hold down the CTRL key, and then click the other links and/or functoids you want to select.</span></span>  
  
     <span data-ttu-id="04a19-121">En la figura siguiente se muestran los vínculos y functoids seleccionados resaltados.</span><span class="sxs-lookup"><span data-stu-id="04a19-121">The following figure shows the selected functoids and links highlighted.</span></span>  
  
     <span data-ttu-id="04a19-122">![Selección de functoids y vínculos de forma masiva](../core/media/bulkselect-functois-links.gif "BulkSelect_Functois & vínculos")</span><span class="sxs-lookup"><span data-stu-id="04a19-122">![Bulk selecting functoids and links](../core/media/bulkselect-functois-links.gif "BulkSelect_Functois&Links")</span></span>  
  
-   <span data-ttu-id="04a19-123">Arrastre el mouse en la superficie de asignación.</span><span class="sxs-lookup"><span data-stu-id="04a19-123">Drag the mouse on the map surface.</span></span> <span data-ttu-id="04a19-124">Se resaltan los functoids en el rectángulo de selección.</span><span class="sxs-lookup"><span data-stu-id="04a19-124">The functoids under the selection rectangle are highlighted.</span></span>  
  
     <span data-ttu-id="04a19-125">![Selección de functoids mediante rectángulo](../core/media/bulkselect-selectionrectangle.gif "BulkSelect_SelectionRectangle")</span><span class="sxs-lookup"><span data-stu-id="04a19-125">![Rectangle selection of functoids](../core/media/bulkselect-selectionrectangle.gif "BulkSelect_SelectionRectangle")</span></span>  
  
-   <span data-ttu-id="04a19-126">Puede usar una combinación de arrastrar y hacer clic con CTRL presionado.</span><span class="sxs-lookup"><span data-stu-id="04a19-126">You can use a combination of dragging and CTRL-click.</span></span> <span data-ttu-id="04a19-127">Arrastre el mouse en la superficie de asignación y seleccione los functoids y/o vínculos de ese rango.</span><span class="sxs-lookup"><span data-stu-id="04a19-127">Drag the mouse on the map surface and select the functoids and/or links in that range.</span></span> <span data-ttu-id="04a19-128">Mantenga presionada la tecla CTRL y, a continuación, haga clic en los vínculos y/o functoids que desea seleccionar fuera del rango de selección.</span><span class="sxs-lookup"><span data-stu-id="04a19-128">Hold down the CTRL key, and then click the functoids and/or links outside the selection range.</span></span>  
  
## <a name="to-select-all-links-and-functoids-on-the-grid-page"></a><span data-ttu-id="04a19-129">Para seleccionar todos los vínculos y functoids en la página de cuadrícula</span><span class="sxs-lookup"><span data-stu-id="04a19-129">To select all links and functoids on the grid page</span></span>  
 <span data-ttu-id="04a19-130">Puede seleccionar todos los functoids y vínculos en la página de cuadrícula del Asignador de alguna de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="04a19-130">You can select all the functoids and links on the Mapper grid page in any of the following ways:</span></span>  
  
-   <span data-ttu-id="04a19-131">Haga doble clic en cualquier lugar en la página de cuadrícula y haga clic en **seleccionar todo**.</span><span class="sxs-lookup"><span data-stu-id="04a19-131">Right-click anywhere on the grid page and click **Select All**.</span></span>  
  
-   <span data-ttu-id="04a19-132">Haga clic en cualquier parte de la página de cuadrícula y, a continuación, haga clic y presione CTRL+A del teclado.</span><span class="sxs-lookup"><span data-stu-id="04a19-132">Click anywhere on the grid page and click press CTRL+A from the keyboard.</span></span>  
  
-   <span data-ttu-id="04a19-133">Haga clic en cualquier parte de la página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="04a19-133">Click anywhere on the grid page.</span></span> <span data-ttu-id="04a19-134">En el menú de Visual Studio, haga clic en **editar**y, a continuación, haga clic en **seleccionar todo**.</span><span class="sxs-lookup"><span data-stu-id="04a19-134">From the Visual Studio menu, click **Edit**, and then click **Select All**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04a19-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="04a19-135">See Also</span></span>  
 [<span data-ttu-id="04a19-136">Utilizar vínculos para especificar el registro y las asignaciones de campos</span><span class="sxs-lookup"><span data-stu-id="04a19-136">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)