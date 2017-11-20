---
title: Acerca de las canalizaciones, fases y componentes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Microsoft.BizTalk.Component.Interop namespace
- pipelines, about pipelines
ms.assetid: a98e1c93-f264-4577-bd12-4430a5859e3c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 070c785924021f8e398a547c01afe969fa6430cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="about-pipelines-stages-and-components"></a><span data-ttu-id="58928-102">Canalizaciones, fases y componentes</span><span class="sxs-lookup"><span data-stu-id="58928-102">About Pipelines, Stages, and Components</span></span>
<span data-ttu-id="58928-103">Una canalización es una parte de infraestructura de software que contiene un conjunto de componentes .NET o COM que procesan mensajes según una secuencia predefinida.</span><span class="sxs-lookup"><span data-stu-id="58928-103">A pipeline is a piece of software infrastructure that contains a set of .NET or COM components that process messages in a predefined sequence.</span></span> <span data-ttu-id="58928-104">Una canalización divide el procesamiento en categorías de trabajo llamadas fases y determina la secuencia en la que se llevan a cabo éstas.</span><span class="sxs-lookup"><span data-stu-id="58928-104">A pipeline divides processing into categories of work called stages, and determines the sequence in which the stages are performed.</span></span> <span data-ttu-id="58928-105">Cada fase define grupos de trabajo lógicos, determina los componentes que pueden ir en esa fase y especifica cómo se ejecutan los componentes de canalización de la fase.</span><span class="sxs-lookup"><span data-stu-id="58928-105">Each stage defines logical work groups, determines which components can go in that stage, and specifies how the pipeline components in the stage are run.</span></span>  
  
 <span data-ttu-id="58928-106">Dentro de cada fase, los componentes de canalización llevan a cabo tareas específicas.</span><span class="sxs-lookup"><span data-stu-id="58928-106">Within each stage, pipeline components perform specific tasks.</span></span> <span data-ttu-id="58928-107">Por ejemplo, los componentes que están dentro de fases de una canalización de recepción pueden descodificar, desensamblar y, a continuación, convertir documentos de otros formatos en XML.</span><span class="sxs-lookup"><span data-stu-id="58928-107">For example, components within stages of a receive pipeline may decode, disassemble, and then convert documents from other formats to XML.</span></span> <span data-ttu-id="58928-108">Canalizaciones de envío realizan la acción inversa: convertir documentos de XML a otros formatos, ensamblar y cifrar, con cada componente de canalización de realización de una parte de todo el proceso.</span><span class="sxs-lookup"><span data-stu-id="58928-108">Send pipelines do essentially the opposite: convert documents from XML to other formats, assemble, and encrypt, with each pipeline component performing a portion of the entire process.</span></span> <span data-ttu-id="58928-109">Aunque una fase es un contenedor de componentes, cada una de ellas es en sí misma un componente con metadatos.</span><span class="sxs-lookup"><span data-stu-id="58928-109">Although a stage is a container of components, each stage is itself a component with metadata.</span></span> <span data-ttu-id="58928-110">Las fases no tienen código de ejecución, al contrario que los componentes de canalización, que sí lo tienen.</span><span class="sxs-lookup"><span data-stu-id="58928-110">Stages have no execution code, as opposed to pipeline components, which do have execution code.</span></span>  
  
 <span data-ttu-id="58928-111">En la siguiente ilustración se muestra cómo la superficie de diseño de canalización muestra las canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="58928-111">The following figure shows how the pipeline design surface illustrates pipelines.</span></span> <span data-ttu-id="58928-112">Esta canalización tiene dos fases, la fase de ensamblado y la fase de codificación.</span><span class="sxs-lookup"><span data-stu-id="58928-112">This pipeline has two stages, the Assemble stage and the Encode stage.</span></span> <span data-ttu-id="58928-113">El componente de canalización de ensamblador XML se agregó a la fase de ensamblado, pero la fase de codificación está todavía vacía, porque aún muestra **Coloque aquí.**</span><span class="sxs-lookup"><span data-stu-id="58928-113">The XML Assembler pipeline component was added to the Assemble stage, but the Encode stage is still empty, because it still shows **Drop Here!**</span></span> <span data-ttu-id="58928-114">para indicar que un componente de canalización puede agregarse a la fase.</span><span class="sxs-lookup"><span data-stu-id="58928-114">to indicate that a pipeline component can be added to the stage.</span></span>  
  
 <span data-ttu-id="58928-115">![Fases y componentes de una canalización de BizTalk](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")</span><span class="sxs-lookup"><span data-stu-id="58928-115">![Stages and components in a BizTalk pipeline](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")</span></span>  
<span data-ttu-id="58928-116">Muestra fases y componentes de una canalización de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="58928-116">Illustrates stages and components in a BizTalk pipeline.</span></span>  
  
 <span data-ttu-id="58928-117">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tiene un conjunto de plantillas de canalización, componentes de canalización y canalizaciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="58928-117">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] contains a set of pipeline templates, pipeline components, and default pipelines.</span></span> <span data-ttu-id="58928-118">Puede crear y configurar canalizaciones mediante la interfaz de usuario del Diseñador de canalizaciones; implementar canalizaciones mediante la API en el **Microsoft.BizTalk.Component.Interop** espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="58928-118">You can create and configure pipelines by using the Pipeline Designer user interface; you implement pipelines by using the API in the **Microsoft.BizTalk.Component.Interop** namespace.</span></span> <span data-ttu-id="58928-119">No es posible modificar las plantillas de canalización.</span><span class="sxs-lookup"><span data-stu-id="58928-119">You cannot modify the pipeline templates.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="58928-120">En esta sección</span><span class="sxs-lookup"><span data-stu-id="58928-120">In This Section</span></span>  
  
-   [<span data-ttu-id="58928-121">Tipos de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="58928-121">Types of Pipelines</span></span>](../core/types-of-pipelines.md)  
  
-   [<span data-ttu-id="58928-122">Tipos de componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="58928-122">Types of Pipeline Components</span></span>](../core/types-of-pipeline-components.md)  
  
-   [<span data-ttu-id="58928-123">Etapas de canalización</span><span class="sxs-lookup"><span data-stu-id="58928-123">Pipeline Stages</span></span>](../core/pipeline-stages.md)  
  
-   [<span data-ttu-id="58928-124">Canalizaciones predeterminadas</span><span class="sxs-lookup"><span data-stu-id="58928-124">Default Pipelines</span></span>](../core/default-pipelines.md)  
  
-   [<span data-ttu-id="58928-125">Plantillas de canalización</span><span class="sxs-lookup"><span data-stu-id="58928-125">Pipeline Templates</span></span>](../core/pipeline-templates.md)  
  
-   [<span data-ttu-id="58928-126">Componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="58928-126">Pipeline Components</span></span>](../core/pipeline-components.md)  
  
-   [<span data-ttu-id="58928-127">Resolución de esquemas en componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="58928-127">Schema Resolution in Pipeline Components</span></span>](../core/schema-resolution-in-pipeline-components.md)  
  
-   [<span data-ttu-id="58928-128">Utilización de sobres en el ensamblador de XML y los componentes de canalización de desensamblador</span><span class="sxs-lookup"><span data-stu-id="58928-128">Envelope Use in the XML Assembler and Disassembler Pipeline Components</span></span>](../core/envelope-use-in-the-xml-assembler-and-disassembler-pipeline-components.md)  
  
-   [<span data-ttu-id="58928-129">Degradación de propiedades en componentes de canalización de ensamblador</span><span class="sxs-lookup"><span data-stu-id="58928-129">Property Demotion in Assembler Pipeline Components</span></span>](../core/property-demotion-in-assembler-pipeline-components.md)  
  
-   [<span data-ttu-id="58928-130">Promoción de propiedades en componentes de canalización de desensamblador</span><span class="sxs-lookup"><span data-stu-id="58928-130">Property Promotion in Disassembler Pipeline Components</span></span>](../core/property-promotion-in-disassembler-pipeline-components.md)  
  
-   [<span data-ttu-id="58928-131">Componentes de canalización de campos distintivos en el Desensamblador</span><span class="sxs-lookup"><span data-stu-id="58928-131">Distinguished Fields in Disassembler Pipeline Components</span></span>](../core/distinguished-fields-in-disassembler-pipeline-components.md)