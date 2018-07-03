---
title: Cómo agregar un componente a una canalización | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, components
ms.assetid: 6b1dbeab-6acc-46d7-8ddd-79b79da3591c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b1d37c6fafcec158f63c3728c773c19089658b2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991333"
---
# <a name="how-to-add-a-component-to-a-pipeline"></a><span data-ttu-id="55f89-102">Cómo agregar un componente a una canalización</span><span class="sxs-lookup"><span data-stu-id="55f89-102">How to Add a Component to a Pipeline</span></span>
<span data-ttu-id="55f89-103">Los componentes se agregan a las canalizaciones arrastrándolos desde el cuadro de herramientas hasta la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="55f89-103">You add components to pipelines by dragging from the Toolbox to the design surface.</span></span>  
  
### <a name="to-add-a-component-to-a-pipeline"></a><span data-ttu-id="55f89-104">Para agregar un componente a una canalización</span><span class="sxs-lookup"><span data-stu-id="55f89-104">To add a component to a pipeline</span></span>  
  
- <span data-ttu-id="55f89-105">En el cuadro de herramientas, arrastre el componente de canalización hasta un **Coloque aquí!**</span><span class="sxs-lookup"><span data-stu-id="55f89-105">In the Toolbox, drag the pipeline component onto a **Drop Here!**</span></span> <span data-ttu-id="55f89-106">cuadro de la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="55f89-106">box on the design surface.</span></span>  
  
  <span data-ttu-id="55f89-107">La siguiente ilustración muestra cómo la superficie de diseño de canalización muestra las canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="55f89-107">The following illustration shows how the pipeline design surface illustrates pipelines.</span></span> <span data-ttu-id="55f89-108">Esta canalización tiene dos fases, la fase de ensamblado y la fase de codificación.</span><span class="sxs-lookup"><span data-stu-id="55f89-108">This pipeline has two stages, the Assemble stage and the Encode stage.</span></span> <span data-ttu-id="55f89-109">El componente de canalización de ensamblador XML se agregó a la fase de ensamblado, pero la fase de codificación todavía está vacía, porque aún muestra **Coloque aquí!**</span><span class="sxs-lookup"><span data-stu-id="55f89-109">The XML Assembler pipeline component was added to the Assemble stage, but the Encode stage is still empty, because it still shows **Drop Here!**</span></span> <span data-ttu-id="55f89-110">para indicar que un componente de canalización se puede agregar a la fase.</span><span class="sxs-lookup"><span data-stu-id="55f89-110">to indicate that a pipeline component can be added to the stage.</span></span>  
  
  <span data-ttu-id="55f89-111">![Fases y componentes de una canalización de BizTalk](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")</span><span class="sxs-lookup"><span data-stu-id="55f89-111">![Stages and components in a BizTalk pipeline](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")</span></span>  
  <span data-ttu-id="55f89-112">Muestra fases y componentes de una canalización de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="55f89-112">Illustrates stages and components in a BizTalk pipeline.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="55f89-113">Un componente de canalización solo puede colocarse en ubicaciones específicas de la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="55f89-113">A pipeline component can only be dropped at specific places on the design surface.</span></span> <span data-ttu-id="55f89-114">El componente de canalización solo puede colocarse en una fase con la que tenga afinidad de fases.</span><span class="sxs-lookup"><span data-stu-id="55f89-114">The pipeline component can only be dropped in a stage in which it has stage affinity.</span></span> <span data-ttu-id="55f89-115">Un círculo con una barra diagonal aparece cerca del puntero en los lugares en que no puede colocarse el componente de canalización.</span><span class="sxs-lookup"><span data-stu-id="55f89-115">A circle with a line through it appears next to the pointer where the pipeline component cannot be dropped.</span></span> <span data-ttu-id="55f89-116">En los lugares en que un componente de canalización puede colocarse, se muestra una flecha y aparece resaltada una parte de la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="55f89-116">An arrow appears, and a portion of the design surface is highlighted where a pipeline component can be placed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55f89-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="55f89-117">See Also</span></span>  
 <span data-ttu-id="55f89-118">[Cómo crear una nueva canalización](../core/how-to-create-a-new-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="55f89-118">[How to Create a New Pipeline](../core/how-to-create-a-new-pipeline.md) </span></span>  
 <span data-ttu-id="55f89-119">[Cómo abrir una canalización](../core/how-to-open-a-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="55f89-119">[How to Open a Pipeline](../core/how-to-open-a-pipeline.md) </span></span>  
 <span data-ttu-id="55f89-120">[Cómo usar el cuadro de herramientas](../core/how-to-use-the-toolbox.md) </span><span class="sxs-lookup"><span data-stu-id="55f89-120">[How to Use the Toolbox](../core/how-to-use-the-toolbox.md) </span></span>  
 <span data-ttu-id="55f89-121">[Cómo desplazarse con el teclado](../core/how-to-navigate-with-the-keyboard.md) </span><span class="sxs-lookup"><span data-stu-id="55f89-121">[How to Navigate with the Keyboard](../core/how-to-navigate-with-the-keyboard.md) </span></span>  
 [<span data-ttu-id="55f89-122">Creación de canalizaciones con el Diseñador de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="55f89-122">Creating Pipelines with Pipeline Designer</span></span>](../core/creating-pipelines-with-pipeline-designer.md)