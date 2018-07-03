---
title: Mediante el Diseñador de canalizaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Pipeline Designer, how to
- pipelines, Pipeline Designer
ms.assetid: bdb2f5c7-f8a2-4bd6-a8d8-8b7a64f97bd0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f5a3e2d9d3dad37372fc01f6446f0c06272589a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019026"
---
# <a name="using-pipeline-designer"></a><span data-ttu-id="8da42-102">Utilizando el diseñador de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="8da42-102">Using Pipeline Designer</span></span>
<span data-ttu-id="8da42-103">El Diseñador de canalizaciones es un editor gráfico que se aloja en Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y que permite crear nuevas canalizaciones, ver las plantillas de canalización incluidas en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], mover los componentes de canalización en el interior de una canalización, así como configurar canalizaciones, fases y componentes de canalización.</span><span class="sxs-lookup"><span data-stu-id="8da42-103">Pipeline Designer is a graphical editor, hosted in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], which enables you to create new pipelines; view the pipeline templates included with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]; move pipeline components within a pipeline; and configure pipelines, stages, and pipeline components.</span></span>  
  
 <span data-ttu-id="8da42-104">El Diseñador de canalizaciones usa tres herramientas clave del shell de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] como parte de la experiencia de diseño:</span><span class="sxs-lookup"><span data-stu-id="8da42-104">Pipeline Designer uses three key tools of the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell as part of the design experience:</span></span>  
  
- <span data-ttu-id="8da42-105">La ventana Propiedades, donde se ven y modifican la mayoría de las características de los objetos de canalización.</span><span class="sxs-lookup"><span data-stu-id="8da42-105">The Properties window, where most of the characteristics of pipeline objects are viewed and modified.</span></span>  
  
- <span data-ttu-id="8da42-106">El cuadro de herramientas, que se utiliza como un origen para la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="8da42-106">The Toolbox, which is used as a source for the design surface.</span></span>  
  
- <span data-ttu-id="8da42-107">La superficie de diseño, donde se arrastran y colocan los componentes del cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="8da42-107">The design surface, where components from the Toolbox are dragged and dropped.</span></span>  
  
  <span data-ttu-id="8da42-108">En la siguiente ilustración se muestra el entorno del Diseñador de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="8da42-108">The following figure shows the Pipeline Designer environment.</span></span>  
  
  <span data-ttu-id="8da42-109">![El entorno de edición del Diseñador de canalizaciones](../core/media/ebiz-prog-usepipe.gif "ebiz_prog_usepipe")</span><span class="sxs-lookup"><span data-stu-id="8da42-109">![The Pipeline Designer editing environment](../core/media/ebiz-prog-usepipe.gif "ebiz_prog_usepipe")</span></span>  
  <span data-ttu-id="8da42-110">Representación del entorno del Diseñador de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="8da42-110">Depicts the Pipeline Designer environment.</span></span>  
  
  <span data-ttu-id="8da42-111">El Diseñador de canalizaciones está integrado con la plantilla del proyecto de BizTalk para mejorar la experiencia de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="8da42-111">Pipeline Designer is integrated with the BizTalk project template to enhance your development experience.</span></span> <span data-ttu-id="8da42-112">Después de usar el sistema del proyecto para crear un nuevo proyecto de BizTalk, puede usar el **Agregar nuevo elemento** comando el **archivo** menú para agregar una canalización a la solución.</span><span class="sxs-lookup"><span data-stu-id="8da42-112">After using the project system to create a new BizTalk project, you can use the **Add New Item** command on the **File** menu to add a pipeline to your solution.</span></span> <span data-ttu-id="8da42-113">Para obtener más información acerca de la plantilla de proyecto de BizTalk, consulte [con el sistema del proyecto de BizTalk](../core/using-the-biztalk-project-system.md).</span><span class="sxs-lookup"><span data-stu-id="8da42-113">For more information about the BizTalk project template, see [Using the BizTalk Project System](../core/using-the-biztalk-project-system.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8da42-114">En versiones anteriores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], el concepto de canalización se encapsulaba en canales y puertos de mensajes, que definían un orden establecido de componentes específicos que se aplicaban a un documento.</span><span class="sxs-lookup"><span data-stu-id="8da42-114">In previous versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the concept of a pipeline was encapsulated in message channels and ports, which defined a set order of specific components that were applied to a document.</span></span> <span data-ttu-id="8da42-115">En esta versión, la canalización es flexible porque es posible reorganizar los componentes de cada fase de la canalización e insertar múltiples componentes personalizados a lo largo de la canalización.</span><span class="sxs-lookup"><span data-stu-id="8da42-115">In this version, the pipeline is flexible because you are free to reorder the components in each stage of the pipeline and can easily insert multiple custom components throughout the pipeline.</span></span>  
  
 <span data-ttu-id="8da42-116">La superficie de diseño del Diseñador de canalizaciones permite dibujar una representación gráfica de una canalización.</span><span class="sxs-lookup"><span data-stu-id="8da42-116">The Pipeline Designer design surface enables you to draw a graphical representation of a pipeline.</span></span> <span data-ttu-id="8da42-117">La superficie de diseño ocupa la sección principal de la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana y le permite editar las canalizaciones pertenecientes a un proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8da42-117">The design surface occupies the main section of the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] window and enables you to edit the pipelines belonging to a BizTalk project.</span></span> <span data-ttu-id="8da42-118">Es posible desplazarse entre canalizaciones haciendo clic en las pestañas de la parte superior de la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="8da42-118">You can navigate between pipelines by clicking the tabs above the design surface.</span></span>  
  
 <span data-ttu-id="8da42-119">Las canalizaciones se componen de fases, y cada fase contiene uno o más componentes.</span><span class="sxs-lookup"><span data-stu-id="8da42-119">Each pipeline is composed of stages, with each stage containing one or more components.</span></span> <span data-ttu-id="8da42-120">Si no hay componentes en una fase, una marca de agua con texto indica que pueden insertarse formas desde el cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="8da42-120">If there are no components in a stage, a watermark with text indicates that shapes can be inserted from the Toolbox.</span></span> <span data-ttu-id="8da42-121">Cuando se inserta la primera forma en una fase, desaparece el texto inicial.</span><span class="sxs-lookup"><span data-stu-id="8da42-121">When the first shape is inserted into a stage, the initial text disappears.</span></span> <span data-ttu-id="8da42-122">La superficie de diseño muestra la canalización verticalmente, ejecutándose de arriba (inicio) abajo (final).</span><span class="sxs-lookup"><span data-stu-id="8da42-122">The design surface shows the pipeline vertically, running from top (start) to bottom (end).</span></span>  
  
 <span data-ttu-id="8da42-123">Como con otros programas comunes de Microsoft Windows, puede realizar varias tareas, como **abierto** y **guardar** desde el **archivo** menú.</span><span class="sxs-lookup"><span data-stu-id="8da42-123">As with other common Microsoft Windows programs, you can perform several tasks, such as **Open** and **Save** from the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8da42-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="8da42-124">See Also</span></span>  
 <span data-ttu-id="8da42-125">[Creación de canalizaciones con el Diseñador de canalizaciones](../core/creating-pipelines-with-pipeline-designer.md) </span><span class="sxs-lookup"><span data-stu-id="8da42-125">[Creating Pipelines with Pipeline Designer](../core/creating-pipelines-with-pipeline-designer.md) </span></span>  
 [<span data-ttu-id="8da42-126">Creación de canalizaciones mediante el Diseñador de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="8da42-126">Creating Pipelines Using Pipeline Designer</span></span>](../core/creating-pipelines-using-pipeline-designer.md)