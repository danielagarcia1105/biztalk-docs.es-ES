---
title: Visualización de recuadros informativos e información sobre herramientas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5621bd0a-7028-43fc-b6e8-74a528129285
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 833fedbcb731971bb305c759b6f87a5a575f58e8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995941"
---
# <a name="how-to-view-infotip-and-tooltip"></a><span data-ttu-id="8e2cc-102">Visualización de recuadros informativos e información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="8e2cc-102">How to View Infotip and Tooltip</span></span>
<span data-ttu-id="8e2cc-103">Al mover el cursor sobre un elemento de una asignación sin hacer clic en él, aparece una sugerencia con información de utilidad sobre dicho elemento.</span><span class="sxs-lookup"><span data-stu-id="8e2cc-103">When you move the cursor over a map item without clicking it, a screen tip appears with useful information about that item.</span></span>  
  
 <span data-ttu-id="8e2cc-104">El Asignador de BizTalk usa dos tipos de sugerencias: recuadro informativo e información sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="8e2cc-104">The BizTalk Mapper uses two types of screen tips – infotip and tooltip.</span></span>  
  
- <span data-ttu-id="8e2cc-105">**Recuadros informativos** se muestran para functoids o vínculos.</span><span class="sxs-lookup"><span data-stu-id="8e2cc-105">**Infotips** are displayed for functoids or links.</span></span> <span data-ttu-id="8e2cc-106">Al configurar etiquetas o comentarios para functoids o links, los verá como recuadro informativo en la página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="8e2cc-106">When you configure labels or comments for functoids or links, you see them as infotip on the grid page.</span></span> <span data-ttu-id="8e2cc-107">Además, cuando el valor de texto para las propiedades supera la visualización de la **cuadrícula de propiedades**, se muestra el recuadro informativo.</span><span class="sxs-lookup"><span data-stu-id="8e2cc-107">Also, when the text value for properties exceeds the display of the **Properties Grid**, the infotip is displayed.</span></span>  
  
- <span data-ttu-id="8e2cc-108">**Información sobre herramientas** se muestran para los nodos de esquema que están parcial o completamente ocultos desde la alineación actual en la vista de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="8e2cc-108">**Tooltips** are displayed for those schema nodes that are hidden partially/completely from the current alignment in the grid view.</span></span>  
  
  <span data-ttu-id="8e2cc-109">Para etiquetas de vínculos, solo se conservan los primeros 256 caracteres y la información para herramientas muestra la etiqueta completa.</span><span class="sxs-lookup"><span data-stu-id="8e2cc-109">For link labels, only the first 256 characters are retained, and the tooltip displays the complete label.</span></span> <span data-ttu-id="8e2cc-110">Para functoids, la etiqueta puede contener un máximo de 256 caracteres y los comentarios tienen un límite de 1024 caracteres.</span><span class="sxs-lookup"><span data-stu-id="8e2cc-110">For functoids, the label can contain a maximum of 256 characters and comments have a limit of 1024 characters.</span></span> <span data-ttu-id="8e2cc-111">El texto del comentario se trunca en consecuencia para mostrar solo los 256 primeros caracteres del comentario.</span><span class="sxs-lookup"><span data-stu-id="8e2cc-111">Text of comment gets truncated accordingly to display only first 256 characters of comment.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8e2cc-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8e2cc-112">Prerequisites</span></span>  
 <span data-ttu-id="8e2cc-113">Para ver la información sobre herramientas, asegúrese de que se está ejecutando el Asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8e2cc-113">To view the tooltips, ensure BizTalk Mapper is running.</span></span>  
  
## <a name="to-view-the-infotip"></a><span data-ttu-id="8e2cc-114">Procedimiento para ver el recuadro informativo</span><span class="sxs-lookup"><span data-stu-id="8e2cc-114">To view the infotip</span></span>  
 <span data-ttu-id="8e2cc-115">Al mover el ratón sobre un functoid, la información sobre herramientas muestra información acerca del nombre del functoid, su etiqueta, el comentario y los parámetros de entrada (si existen).</span><span class="sxs-lookup"><span data-stu-id="8e2cc-115">When you move the mouse on a functoid, the infotip displays information about the functoid name, the functoid label, the functoid comment, and the input parameters (if existing).</span></span> <span data-ttu-id="8e2cc-116">Para un **Scripting** functoid, el recuadro informativo muestra las primeras líneas de código.</span><span class="sxs-lookup"><span data-stu-id="8e2cc-116">For a **Scripting** functoid, the infotip displays the first few lines of code.</span></span>  
  
 <span data-ttu-id="8e2cc-117">El recuadro informativo a un vínculo muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="8e2cc-117">The infotip to a link displays the following information:</span></span>  
  
- <span data-ttu-id="8e2cc-118">Etiqueta del vínculo, si está definida</span><span class="sxs-lookup"><span data-stu-id="8e2cc-118">Link label, if set.</span></span>  
  
- <span data-ttu-id="8e2cc-119">**Desde: conexión de origen**.</span><span class="sxs-lookup"><span data-stu-id="8e2cc-119">**From: source connection**.</span></span> <span data-ttu-id="8e2cc-120">Si la conexión de origen es un elemento de esquema, muestra el nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="8e2cc-120">If the source connection is a schema element, it shows the element name.</span></span> <span data-ttu-id="8e2cc-121">Si la conexión de origen es un functoid, muestra el nombre del functoid.</span><span class="sxs-lookup"><span data-stu-id="8e2cc-121">If the source connection is a functoid, it shows the functoid name.</span></span>  
  
- <span data-ttu-id="8e2cc-122">**Para: conexión de destino**.</span><span class="sxs-lookup"><span data-stu-id="8e2cc-122">**To: destination connection**.</span></span> <span data-ttu-id="8e2cc-123">Si la conexión de destino es un elemento de esquema, muestra el nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="8e2cc-123">If the destination connection is a schema element, it shows the element name.</span></span> <span data-ttu-id="8e2cc-124">Si la conexión de destino es un functoid, muestra el nombre del functoid.</span><span class="sxs-lookup"><span data-stu-id="8e2cc-124">If the destination connection is a functoid, it shows the functoid name.</span></span>  
  
  <span data-ttu-id="8e2cc-125">Si los campos de la **cuadrícula de propiedades** tienen texto que supera la visualización, mueva el mouse en el campo.</span><span class="sxs-lookup"><span data-stu-id="8e2cc-125">If the fields in the **Properties Grid** have text that exceeds the display, move the mouse on the field.</span></span> <span data-ttu-id="8e2cc-126">El recuadro informativo mostrará el texto completo.</span><span class="sxs-lookup"><span data-stu-id="8e2cc-126">The infotip will show the full text.</span></span>  
  
  <span data-ttu-id="8e2cc-127">En la siguiente ilustración se muestra recuadros informativos a un functoid, vínculo y el **cuadrícula de propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8e2cc-127">The following figure illustrates infotips to a functoid, link, and the **Properties Grid**.</span></span>  
  
  <span data-ttu-id="8e2cc-128">![Recuadros informativos para functoid, vínculo y etiqueta](../core/media/viewing-infotips.gif "Viewing_infotips")</span><span class="sxs-lookup"><span data-stu-id="8e2cc-128">![Infotips for functoid, link, and label](../core/media/viewing-infotips.gif "Viewing_infotips")</span></span>  
  
## <a name="to-view-the-tooltip"></a><span data-ttu-id="8e2cc-129">Procedimiento para ver la información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="8e2cc-129">To view the tooltip</span></span>  
 <span data-ttu-id="8e2cc-130">Si los esquemas de origen o destino son grandes, la asignación puede expandirse verticalmente; de este modo, los nodos de esquema pueden ser parcialmente visibles.</span><span class="sxs-lookup"><span data-stu-id="8e2cc-130">When your source and/or destination schemas are big, your map can span vertically; hence the schema nodes may be partially visible.</span></span> <span data-ttu-id="8e2cc-131">En tal caso, puede ver informaciones sobre herramientas cuando mueve el ratón en dichos nodos de origen.</span><span class="sxs-lookup"><span data-stu-id="8e2cc-131">In such a scenario, you can see tooltips when you move the mouse on those source nodes.</span></span>  
  
 <span data-ttu-id="8e2cc-132">En la siguiente figura se muestra una información sobre herramientas a un nodo de esquema de destino parcialmente oculto.</span><span class="sxs-lookup"><span data-stu-id="8e2cc-132">The following figure shows a tooltip to a partially hidden target schema node.</span></span>  
  
 <span data-ttu-id="8e2cc-133">![Información sobre herramientas para un nodo de esquema](../core/media/viewing-tooltips.gif "Viewing_tooltips")</span><span class="sxs-lookup"><span data-stu-id="8e2cc-133">![Tooltip to a schema node](../core/media/viewing-tooltips.gif "Viewing_tooltips")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e2cc-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e2cc-134">See Also</span></span>  
 [<span data-ttu-id="8e2cc-135">Uso del Asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="8e2cc-135">Using BizTalk Mapper</span></span>](../core/using-biztalk-mapper.md)