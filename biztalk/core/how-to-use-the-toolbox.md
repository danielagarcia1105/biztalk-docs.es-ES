---
title: Cómo usar el cuadro de herramientas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- pipeline components, deleting from toolbox
- pipeline components, Pipeline Designer
- pipeline components, adding to toolbox
- Pipeline Designer, toolbox
- pipelines, creating
ms.assetid: 7a60c590-1a38-46fe-addf-0aa2c8b63cf9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3965a063aebcc932f07937fd19c3998412591ea1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257276"
---
# <a name="how-to-use-the-toolbox"></a><span data-ttu-id="98b5c-102">Uso del cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="98b5c-102">How to Use the Toolbox</span></span>
<span data-ttu-id="98b5c-103">Una canalización se crea arrastrando componentes (formas) desde el cuadro de herramientas hasta la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="98b5c-103">You create a pipeline by dragging components (shapes) from the Toolbox to the design surface.</span></span> <span data-ttu-id="98b5c-104">El Diseñador de canalizaciones ayuda a ensamblar canalizaciones válidas poniendo algunas restricciones en el proceso de creación.</span><span class="sxs-lookup"><span data-stu-id="98b5c-104">Pipeline Designer helps you assemble valid pipelines by placing certain restrictions on the creation process.</span></span> <span data-ttu-id="98b5c-105">Solo puede seleccionar componentes del cuadro de herramientas aplicables al tipo de canalización que está creando.</span><span class="sxs-lookup"><span data-stu-id="98b5c-105">You can only select Toolbox components that apply to the pipeline type you are creating.</span></span> <span data-ttu-id="98b5c-106">Por ejemplo, una canalización de recepción mostrará descodificadores, desensambladores y validadores como componentes válidos del cuadro de herramientas, mientras que los codificadores y ensambladores estarán deshabilitados (atenuados).</span><span class="sxs-lookup"><span data-stu-id="98b5c-106">For example, a receive pipeline will show decoders, disassemblers, and validators as valid Toolbox components, while encoders and assemblers will be disabled (dimmed).</span></span>  
  
 <span data-ttu-id="98b5c-107">Además, las fases solo pueden aceptar componentes válidos.</span><span class="sxs-lookup"><span data-stu-id="98b5c-107">In addition, stages can accept only valid components.</span></span> <span data-ttu-id="98b5c-108">Por ejemplo, no puede arrastrar un componente de codificador hasta una fase de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="98b5c-108">For example, you cannot drag an encoder component to an Assemble stage.</span></span> <span data-ttu-id="98b5c-109">Cuando arrastra un componente cerca de una ubicación válida para la acción de colocar, aparece una flecha que indica el punto en el que el componente puede insertarse.</span><span class="sxs-lookup"><span data-stu-id="98b5c-109">When you drag a component near a valid drop location, an arrow appears, indicating the point where the component can be inserted.</span></span>  
  
 <span data-ttu-id="98b5c-110">Si arrastra un componente válido a una fase que está contraída, mantenga el mouse sobre la fase durante unos segundos para expandirla y, a continuación, coloque el componente en la fase.</span><span class="sxs-lookup"><span data-stu-id="98b5c-110">If you drag a valid component onto a stage that is collapsed, pause the mouse over the stage for a few seconds to expand it, and then drop the component into the stage.</span></span>  
  
 <span data-ttu-id="98b5c-111">Agregar un componente personalizado al cuadro de herramientas en el Diseñador de canalizaciones es parecido al procedimiento estándar en Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98b5c-111">Adding a custom component to the Toolbox in Pipeline Designer is similar to the standard Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] procedure.</span></span>  
  
 <span data-ttu-id="98b5c-112">**Formas inicio y fin**</span><span class="sxs-lookup"><span data-stu-id="98b5c-112">**Start and End Shapes**</span></span>  
  
 <span data-ttu-id="98b5c-113">**Iniciar** y **final** formas aparecen como viñetas en todas las canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="98b5c-113">**Start** and **End** shapes appear as bullets on all pipelines.</span></span> <span data-ttu-id="98b5c-114">Se muestran en la superficie de diseño únicamente para organización visual.</span><span class="sxs-lookup"><span data-stu-id="98b5c-114">They are provided on the design surface for visual organization only.</span></span> <span data-ttu-id="98b5c-115">Hay solo una de cada y no pueden ser ni agregadas ni eliminadas.</span><span class="sxs-lookup"><span data-stu-id="98b5c-115">There is only one of each, and they can neither be added nor deleted.</span></span> <span data-ttu-id="98b5c-116">El **iniciar** y **final** formas no aparecen en el cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="98b5c-116">The **Start** and **End** shapes do not appear in the Toolbox.</span></span>  
  
### <a name="to-add-a-pipeline-component-to-the-toolbox"></a><span data-ttu-id="98b5c-117">Para agregar un componente de canalización al cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="98b5c-117">To add a pipeline component to the Toolbox</span></span>  
  
1.  <span data-ttu-id="98b5c-118">En el menú **Herramientas** , haga clic en **Elegir elementos del cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="98b5c-118">On the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
     <span data-ttu-id="98b5c-119">: "O":</span><span class="sxs-lookup"><span data-stu-id="98b5c-119">—Or—</span></span>  
  
     <span data-ttu-id="98b5c-120">Haga clic en el cuadro de herramientas y, a continuación, haga clic en **elegir elementos**.</span><span class="sxs-lookup"><span data-stu-id="98b5c-120">Right-click the Toolbox and then click **Choose Items**.</span></span>  
  
2.  <span data-ttu-id="98b5c-121">En el **Personalizar cuadro de herramientas** cuadro de diálogo, haga clic en el **componentes de canalización de BizTalk** ficha.</span><span class="sxs-lookup"><span data-stu-id="98b5c-121">In the **Customize Toolbox** dialog box, click the **BizTalk Pipeline Components** tab.</span></span>  
  
     <span data-ttu-id="98b5c-122">En un cuadro de diálogo se muestran los componentes de canalización compatibles.</span><span class="sxs-lookup"><span data-stu-id="98b5c-122">A dialog box displays the compatible pipeline components.</span></span> <span data-ttu-id="98b5c-123">Puede desplazarse por las categorías haciendo clic en las pestañas de la parte superior del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="98b5c-123">You can navigate through the categories by clicking the tabs at the top of the dialog box.</span></span>  
  
3.  <span data-ttu-id="98b5c-124">Seleccione el componente que desea agregar al cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="98b5c-124">Select the component you want to add to the Toolbox.</span></span>  
  
4.  <span data-ttu-id="98b5c-125">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="98b5c-125">Click **OK**.</span></span> <span data-ttu-id="98b5c-126">El componente aparecerá en el **componentes de canalización de BizTalk** ficha del cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="98b5c-126">The component will appear on the **BizTalk Pipeline Components** tab of the Toolbox.</span></span>  
  
### <a name="to-remove-a-pipeline-component-from-the-toolbox"></a><span data-ttu-id="98b5c-127">Para quitar un componente de canalización del cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="98b5c-127">To remove a pipeline component from the Toolbox</span></span>  
  
-   <span data-ttu-id="98b5c-128">Abra la **Personalizar cuadro de herramientas** cuadro de diálogo (como en el procedimiento anterior) y desactive el componente que desee quitar.</span><span class="sxs-lookup"><span data-stu-id="98b5c-128">Open the **Customize Toolbox** dialog box (as in the preceding procedure) and clear the component to be removed.</span></span>  
  
     <span data-ttu-id="98b5c-129">Un componente sigue registrado incluso después de haberlo quitado del cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="98b5c-129">A component remains registered even after it has been removed from the Toolbox.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98b5c-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="98b5c-130">See Also</span></span>  
 <span data-ttu-id="98b5c-131">[Cómo crear una nueva canalización](../core/how-to-create-a-new-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="98b5c-131">[How to Create a New Pipeline](../core/how-to-create-a-new-pipeline.md) </span></span>  
 <span data-ttu-id="98b5c-132">[Cómo abrir una canalización](../core/how-to-open-a-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="98b5c-132">[How to Open a Pipeline](../core/how-to-open-a-pipeline.md) </span></span>  
 <span data-ttu-id="98b5c-133">[Cómo desplazarse con el teclado](../core/how-to-navigate-with-the-keyboard.md) </span><span class="sxs-lookup"><span data-stu-id="98b5c-133">[How to Navigate with the Keyboard](../core/how-to-navigate-with-the-keyboard.md) </span></span>  
 [<span data-ttu-id="98b5c-134">Crear canalizaciones con el Diseñador de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="98b5c-134">Creating Pipelines with Pipeline Designer</span></span>](../core/creating-pipelines-with-pipeline-designer.md)