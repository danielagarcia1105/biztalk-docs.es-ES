---
title: "Plantillas de canalización | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, templates
- Pipeline Designer, templates
- send pipelines, templates
- receive pipelines, templates
ms.assetid: b9779159-e49d-47fb-aa1c-06be5d604c67
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed6af41d3c23c889b7a7e9bd2529adc80bc7bcd2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="pipeline-templates"></a><span data-ttu-id="008d7-102">Plantillas de canalización</span><span class="sxs-lookup"><span data-stu-id="008d7-102">Pipeline Templates</span></span>
<span data-ttu-id="008d7-103">Además de las canalizaciones predeterminadas, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluye dos plantillas de canalización: una plantilla de canalización de recepción y una plantilla de canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="008d7-103">In addition to the default pipelines, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes two pipeline templates: a receive pipeline template and a send pipeline template.</span></span> <span data-ttu-id="008d7-104">Desde un proyecto de BizTalk en Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], puede agregar una plantilla de canalización al proyecto mediante el **Agregar nuevo elemento** comando el **proyecto** menú.</span><span class="sxs-lookup"><span data-stu-id="008d7-104">From a BizTalk project in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], you can add a pipeline template to your project by using the **Add New Item** command on the **Project** menu.</span></span> <span data-ttu-id="008d7-105">Cada plantilla tiene un archivo de directiva asociado, que determina las fases de la canalización e indica qué componentes de canalización están permitidos en ella.</span><span class="sxs-lookup"><span data-stu-id="008d7-105">Each template has an associated policy file, which determines the pipeline's stages and indicates which pipeline components are allowed in the pipeline.</span></span> <span data-ttu-id="008d7-106">Aunque no es posible reorganizar las fases en un archivo de directiva, puede utilizar el Diseñador de canalizaciones para reorganizar los componentes de una fase.</span><span class="sxs-lookup"><span data-stu-id="008d7-106">While you cannot reorder the stages in a policy file, you can use Pipeline Designer to reorder the components within a stage.</span></span>  
  
 <span data-ttu-id="008d7-107">Un archivo de directiva especifica:</span><span class="sxs-lookup"><span data-stu-id="008d7-107">A policy file specifies:</span></span>  
  
-   <span data-ttu-id="008d7-108">La secuencia de fases.</span><span class="sxs-lookup"><span data-stu-id="008d7-108">The sequence of stages.</span></span>  
  
-   <span data-ttu-id="008d7-109">El número de componentes permitidos por fase.</span><span class="sxs-lookup"><span data-stu-id="008d7-109">The number of components allowed per stage.</span></span>  
  
-   <span data-ttu-id="008d7-110">El modo de ejecución de cada fase.</span><span class="sxs-lookup"><span data-stu-id="008d7-110">The execution mode of each stage.</span></span>  
  
 <span data-ttu-id="008d7-111">Los archivos de directivas para las plantillas de canalización se almacenan en  *\<directorio de instalación de BizTalk Server >*\Developer Tools\Pipeline archivos de directivas.</span><span class="sxs-lookup"><span data-stu-id="008d7-111">The policy files for the pipeline templates are stored in *\<BizTalk Server installation directory>*\Developer Tools\Pipeline Policy Files.</span></span> <span data-ttu-id="008d7-112">No modifique los archivos de directiva.</span><span class="sxs-lookup"><span data-stu-id="008d7-112">Do not modify the policy files.</span></span> <span data-ttu-id="008d7-113">Para realizar cambios en una canalización, abra la plantilla de canalización con el Diseñador de canalizaciones para modificarla.</span><span class="sxs-lookup"><span data-stu-id="008d7-113">To make changes to a pipeline, open the pipeline template and use Pipeline Designer to modify it.</span></span> <span data-ttu-id="008d7-114">Para obtener más información acerca de cómo utilizar el Diseñador de canalizaciones, consulte [utilizando el Diseñador de canalizaciones](../core/using-pipeline-designer.md).</span><span class="sxs-lookup"><span data-stu-id="008d7-114">For more information about using Pipeline Designer, see [Using Pipeline Designer](../core/using-pipeline-designer.md).</span></span>  
  
 <span data-ttu-id="008d7-115">Los archivos de plantilla de canalización vacía se almacenan en  *\<directorio de instalación de BizTalk Server >*\Developer Tools\BizTalkProjectItems y denomina BTSReceivePipeline.btp y BTSTransmitPipeline.btp.</span><span class="sxs-lookup"><span data-stu-id="008d7-115">The empty pipeline template files are stored in *\<BizTalk Server installation directory>*\Developer Tools\BizTalkProjectItems, and are named BTSReceivePipeline.btp and BTSTransmitPipeline.btp.</span></span> <span data-ttu-id="008d7-116">El .btp de extensión de nombre de archivo indica que el archivo es una canalización de BizTalk Server y se puede editar en el Diseñador de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="008d7-116">The file name extension .btp indicates that the file is a BizTalk Server pipeline and can be edited in Pipeline Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="008d7-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="008d7-117">See Also</span></span>  
 <span data-ttu-id="008d7-118">[Tipos de canalizaciones](../core/types-of-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="008d7-118">[Types of Pipelines](../core/types-of-pipelines.md) </span></span>  
 <span data-ttu-id="008d7-119">[Tipos de componentes de canalización](../core/types-of-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="008d7-119">[Types of Pipeline Components](../core/types-of-pipeline-components.md) </span></span>  
 <span data-ttu-id="008d7-120">[Canalizaciones predeterminadas](../core/default-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="008d7-120">[Default Pipelines](../core/default-pipelines.md) </span></span>  
 <span data-ttu-id="008d7-121">[Componentes de canalización](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="008d7-121">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 [<span data-ttu-id="008d7-122">Acerca de las canalizaciones, fases y componentes</span><span class="sxs-lookup"><span data-stu-id="008d7-122">About Pipelines, Stages, and Components</span></span>](../core/about-pipelines-stages-and-components.md)