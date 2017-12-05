---
title: "Cómo usar el cuadro de diálogo de tipo de artefacto seleccione | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Select Artifact Type dialog box
- artifacts, Select Artifact Type dialog box
- Orchestration Designer, items
ms.assetid: f0f767f1-4130-4ff0-a898-a089343ee71f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88167cbeb5c8c6bb0a62030e64f4ed3d91a9d1aa
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-use-the-select-artifact-type-dialog-box"></a><span data-ttu-id="4a959-102">Cómo usar el cuadro de diálogo de tipo de artefacto Select</span><span class="sxs-lookup"><span data-stu-id="4a959-102">How to Use the Select Artifact Type Dialog Box</span></span>
<span data-ttu-id="4a959-103">Un *elemento* se usa para configurar los elementos de una orquestación en el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="4a959-103">An *item* is used to configure elements of an orchestration in Orchestration Designer.</span></span> <span data-ttu-id="4a959-104">Los esquemas, las asignaciones, las canalizaciones, los tipos de puerto y los tipos de mensajes de varias partes son por ejemplo elementos.</span><span class="sxs-lookup"><span data-stu-id="4a959-104">Examples of items are schemas, maps, pipelines, port types, and multi-part message types.</span></span> <span data-ttu-id="4a959-105">Al desarrollar una orquestación y las partes que la componen (por ejemplo, formas Puerto, formas Transformación y mensajes), puede que deba hacer referencia a elementos que no residen en la orquestación actual, pero que se encuentran en el proyecto actual o en otro proyecto compilado en un ensamblado de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="4a959-105">When you develop an orchestration and its constituent parts such as port shapes, transform shapes, and messages, you may need to refer to items that do not reside in the current orchestration, but are in the current project or another project that has been compiled into a BizTalk Server assembly.</span></span> <span data-ttu-id="4a959-106">Usa el **Seleccionar tipo de artefacto** cuadro de diálogo para buscar y, a continuación, especificar elementos al configurar un elemento dentro de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="4a959-106">You use the **Select Artifact Type** dialog box to locate and then specify items when configuring an element within an orchestration.</span></span>  
  
 <span data-ttu-id="4a959-107">El **Seleccionar tipo de artefacto** cuadro de diálogo está disponible desde varias ubicaciones en el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="4a959-107">The **Select Artifact Type** dialog box is available from many locations in Orchestration Designer.</span></span> <span data-ttu-id="4a959-108">Puede seleccionar \<seleccionar del ensamblado mencionado\> en una lista desplegable que muestra las opciones de configuración; al hacer clic en este texto se abre el **Seleccionar tipo de artefacto** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="4a959-108">You can select \<Select from referenced assembly\> in a drop-down list that displays configuration options; clicking this text opens the **Select Artifact Type** dialog box.</span></span>  
  
 <span data-ttu-id="4a959-109">Para poder seleccionar un elemento, primero debe seleccionar el elemento que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="4a959-109">Before you can select an item, you must first select the element you want to configure.</span></span>  
  
 <span data-ttu-id="4a959-110">Puede usar el **Seleccionar tipo de artefacto** cuadro de diálogo para los siguientes fines específicos:</span><span class="sxs-lookup"><span data-stu-id="4a959-110">You can use the **Select Artifact Type** dialog box for the following specific purposes:</span></span>  
  
|<span data-ttu-id="4a959-111">Acción</span><span class="sxs-lookup"><span data-stu-id="4a959-111">Action</span></span>|<span data-ttu-id="4a959-112">Finalidad</span><span class="sxs-lookup"><span data-stu-id="4a959-112">Purpose</span></span>|  
|------------|-------------|  
|<span data-ttu-id="4a959-113">Seleccionar una canalización</span><span class="sxs-lookup"><span data-stu-id="4a959-113">Select a pipeline</span></span>|<span data-ttu-id="4a959-114">Seleccionar una canalización para la propiedad de canalización al configurar un puerto para enlace directo (anticipado).</span><span class="sxs-lookup"><span data-stu-id="4a959-114">Select a pipeline for the pipeline property when configuring a port for direct (early) binding.</span></span>|  
|<span data-ttu-id="4a959-115">Seleccionar una asignación</span><span class="sxs-lookup"><span data-stu-id="4a959-115">Select a map</span></span>|<span data-ttu-id="4a959-116">Seleccione una asignación para utilizarla con una **transformar** forma.</span><span class="sxs-lookup"><span data-stu-id="4a959-116">Select a map to use with a **Transform** shape.</span></span>|  
|<span data-ttu-id="4a959-117">Seleccionar un esquema</span><span class="sxs-lookup"><span data-stu-id="4a959-117">Select a schema</span></span>|<span data-ttu-id="4a959-118">Seleccionar esquemas en el proyecto al crear tipos de mensajes de varias partes.</span><span class="sxs-lookup"><span data-stu-id="4a959-118">Select schemas in the project when creating multi-part message types.</span></span>|  
|<span data-ttu-id="4a959-119">Seleccionar un tipo de puerto</span><span class="sxs-lookup"><span data-stu-id="4a959-119">Select a port type</span></span>|<span data-ttu-id="4a959-120">Hacer referencia a tipos de puerto al crear un puerto.</span><span class="sxs-lookup"><span data-stu-id="4a959-120">Refer to existing port types when creating a port.</span></span>|  
|<span data-ttu-id="4a959-121">Seleccionar un tipo de mensaje de varias partes</span><span class="sxs-lookup"><span data-stu-id="4a959-121">Select a multi-part message type</span></span>|<span data-ttu-id="4a959-122">Hacer referencia a tipos de mensaje de varias partes al crear mensajes.</span><span class="sxs-lookup"><span data-stu-id="4a959-122">Refer to existing multipart types when creating messages.</span></span>|  
|<span data-ttu-id="4a959-123">Seleccionar un tipo .NET</span><span class="sxs-lookup"><span data-stu-id="4a959-123">Select a .NET type</span></span>|<span data-ttu-id="4a959-124">Hacer referencia a tipos .NET al crear variables o mensajes.</span><span class="sxs-lookup"><span data-stu-id="4a959-124">Refer to existing .NET types when creating variables or messages.</span></span>|  
  
 <span data-ttu-id="4a959-125">**Panel de referencias**</span><span class="sxs-lookup"><span data-stu-id="4a959-125">**Reference pane**</span></span>  
  
 <span data-ttu-id="4a959-126">El panel de referencias de la **Seleccionar tipo de artefacto** cuadro de diálogo muestra las referencias en el proyecto actual y en otros ensamblados disponibles.</span><span class="sxs-lookup"><span data-stu-id="4a959-126">The reference pane of the **Select Artifact Type** dialog box displays references in the current project and in other available assemblies.</span></span> <span data-ttu-id="4a959-127">Para seleccionar una referencia en este panel, haga clic sobre ella.</span><span class="sxs-lookup"><span data-stu-id="4a959-127">To select a reference in this pane, click it.</span></span> <span data-ttu-id="4a959-128">Para expandir un contenedor en este panel (como el **ensamblados** contenedor), haga clic en el signo más (+) junto a él.</span><span class="sxs-lookup"><span data-stu-id="4a959-128">To expand a container in this pane (such as the **Assemblies** container), click the plus sign (+) beside it.</span></span>  
  
 <span data-ttu-id="4a959-129">**Panel de elementos**</span><span class="sxs-lookup"><span data-stu-id="4a959-129">**Item pane**</span></span>  
  
 <span data-ttu-id="4a959-130">El panel de elementos de la **Seleccionar tipo de artefacto** cuadro de diálogo muestra los elementos incluidos en la referencia seleccionada actualmente en el panel de referencias.</span><span class="sxs-lookup"><span data-stu-id="4a959-130">The item pane of the **Select Artifact Type** dialog box displays the items contained in the reference currently selected in the reference pane.</span></span> <span data-ttu-id="4a959-131">El panel de elementos tiene dos columnas, **elemento** y **nombre completo**, que muestran información sobre los elementos de la referencia actual.</span><span class="sxs-lookup"><span data-stu-id="4a959-131">The item pane has two columns, **Item** and **Qualified Name**, which display information about the items in the current reference.</span></span>  
  
### <a name="to-use-the-select-artifact-type-dialog-box"></a><span data-ttu-id="4a959-132">Para usar el cuadro de diálogo Seleccionar tipo de artefacto</span><span class="sxs-lookup"><span data-stu-id="4a959-132">To use the Select Artifact Type dialog box</span></span>  
  
1.  <span data-ttu-id="4a959-133">Expanda el **referencias** nodo en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="4a959-133">Expand the **References** node in the left pane.</span></span> <span data-ttu-id="4a959-134">El panel muestra los proyectos y los ensamblados disponibles.</span><span class="sxs-lookup"><span data-stu-id="4a959-134">The pane displays available projects and assemblies.</span></span>  
  
2.  <span data-ttu-id="4a959-135">Expanda el **ensamblados** nodo.</span><span class="sxs-lookup"><span data-stu-id="4a959-135">Expand the **Assemblies** node.</span></span> <span data-ttu-id="4a959-136">Aparecen uno o varios ensamblados, como SYSTEM.DLL y MICROSOFT.BIZTALK.PIPELINES.DLL.</span><span class="sxs-lookup"><span data-stu-id="4a959-136">One or more assemblies are listed, such as SYSTEM.DLL and MICROSOFT.BIZTALK.PIPELINES.DLL.</span></span>  
  
3.  <span data-ttu-id="4a959-137">Haga clic en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4a959-137">Click an assembly.</span></span> <span data-ttu-id="4a959-138">Si el ensamblado contiene elementos, se mostrarán en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="4a959-138">If the assembly contains items, they are displayed in the right pane.</span></span> <span data-ttu-id="4a959-139">El nombre completo de los elementos se presenta en la columna derecha del panel de la derecha.</span><span class="sxs-lookup"><span data-stu-id="4a959-139">The qualified name of an item is displayed in the right column of the right pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4a959-140">Si el proyecto actual contiene elementos, puede hacer clic en él para ver los elementos y seleccionar uno.</span><span class="sxs-lookup"><span data-stu-id="4a959-140">If the current project contains items, you can click it to view its items and select one.</span></span>  
  
4.  <span data-ttu-id="4a959-141">Para seleccionar un elemento en el panel derecho, haga clic en él y, a continuación, haga clic en **Aceptar** para salir del **Seleccionar tipo de artefacto** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="4a959-141">To select an item in the right pane, click it and then click **OK** to exit the **Select Artifact Type** dialog box.</span></span> <span data-ttu-id="4a959-142">Con esta acción, ese elemento se asigna como el tipo del elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="4a959-142">This assigns that item as the type for the selected element.</span></span> <span data-ttu-id="4a959-143">Para cerrar la **Seleccionar tipo de artefacto** cuadro de diálogo sin seleccionar ni asignar un elemento, haga clic en **cancelar**.</span><span class="sxs-lookup"><span data-stu-id="4a959-143">To close the **Select Artifact Type** dialog box without selecting and assigning an item, click **Cancel**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a959-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a959-144">See Also</span></span>  
 <span data-ttu-id="4a959-145">[Formas de orquestación](../core/orchestration-shapes.md) </span><span class="sxs-lookup"><span data-stu-id="4a959-145">[Orchestration Shapes](../core/orchestration-shapes.md) </span></span>  
 <span data-ttu-id="4a959-146">[Cómo agregar formas a orquestaciones](../core/how-to-add-shapes-to-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="4a959-146">[How to Add Shapes to Orchestrations](../core/how-to-add-shapes-to-orchestrations.md) </span></span>  
 [<span data-ttu-id="4a959-147">Cómo agregar parámetros a orquestaciones</span><span class="sxs-lookup"><span data-stu-id="4a959-147">How to Add Parameters to Orchestrations</span></span>](../core/how-to-add-parameters-to-orchestrations.md)