---
title: Cómo crear una nueva canalización | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- pipelines, warnings
- Pipeline Designer, warnings
- pipelines, creating
ms.assetid: bd95325e-1a72-4705-80f6-37ac092d11a3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00f19818dd5df6cafaf51298a0463ea745736ab5
ms.sourcegitcommit: c3070a7a3f332857357f056dc632829b43869c17
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2018
ms.locfileid: "51630393"
---
# <a name="how-to-create-a-new-pipeline"></a><span data-ttu-id="02883-102">Cómo crear una nueva canalización</span><span class="sxs-lookup"><span data-stu-id="02883-102">How to Create a New Pipeline</span></span>
<span data-ttu-id="02883-103">Puede agregar una plantilla de canalización al proyecto para crear una nueva canalización.</span><span class="sxs-lookup"><span data-stu-id="02883-103">You can add a pipeline template to your project to create a new pipeline.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="02883-104">No debe agregar un proyecto que contiene una implementación de un componente de canalización personalizado a una solución que contiene un proyecto que usa ese componente de canalización.</span><span class="sxs-lookup"><span data-stu-id="02883-104">You should not add a project that contains an implementation of a custom pipeline component to a solution that contains a project that uses that pipeline component.</span></span> <span data-ttu-id="02883-105">Si lo hace, la próxima vez que vuelva a generar la solución, aparecerá un error que informará de que otro proceso está utilizando el dll de salida.</span><span class="sxs-lookup"><span data-stu-id="02883-105">If you do, the next time you rebuild the solution you will get an error saying the output dll is being used by another process.</span></span>  
  
### <a name="to-create-a-new-pipeline"></a><span data-ttu-id="02883-106">Para crear una nueva canalización</span><span class="sxs-lookup"><span data-stu-id="02883-106">To create a new pipeline</span></span>  
  
1. <span data-ttu-id="02883-107">En el Explorador de soluciones, seleccione el proyecto en el que desea crear la canalización.</span><span class="sxs-lookup"><span data-stu-id="02883-107">In Solution Explorer, select the project in which you want to create the pipeline.</span></span>  
  
2. <span data-ttu-id="02883-108">En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="02883-108">On the **Project** menu, click **Add New Item**.</span></span>  
  
3. <span data-ttu-id="02883-109">En el **Agregar nuevo elemento** cuadro de diálogo, seleccione un **canalización de recepción** o **canalización de envío** plantilla haciendo clic en él una vez.</span><span class="sxs-lookup"><span data-stu-id="02883-109">In the **Add New Item** dialog box, select a **Receive Pipeline** or **Send Pipeline** template by clicking it once.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="02883-110">Si hace doble clic en la plantilla, la canalización se crearán automáticamente con el nombre predeterminado que aparece en el **nombre** campo.</span><span class="sxs-lookup"><span data-stu-id="02883-110">If you double-click the template, the pipeline will automatically be created with the default name that appears in the **Name** field.</span></span>  
  
4. <span data-ttu-id="02883-111">En el **nombre** , escriba un nombre para la canalización.</span><span class="sxs-lookup"><span data-stu-id="02883-111">In the **Name** field, type a name for the pipeline.</span></span>  
  
5. <span data-ttu-id="02883-112">Haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="02883-112">Click **Open**.</span></span>  
  
    <span data-ttu-id="02883-113">La nueva canalización aparecerá en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="02883-113">The new pipeline appears in Solution Explorer.</span></span> <span data-ttu-id="02883-114">La superficie de diseño muestra las fases de canalización y un conjunto predeterminado de componentes.</span><span class="sxs-lookup"><span data-stu-id="02883-114">The design surface displays pipeline stages and a default set of components.</span></span>  
  
   <span data-ttu-id="02883-115">Para obtener información acerca de cómo agregar componentes de canalización a la canalización, consulte [cómo agregar un componente a una canalización](../core/how-to-add-a-component-to-a-pipeline.md).</span><span class="sxs-lookup"><span data-stu-id="02883-115">For information about adding pipeline components to the pipeline, see [How to Add a Component to a Pipeline](../core/how-to-add-a-component-to-a-pipeline.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02883-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="02883-116">See Also</span></span>  
 <span data-ttu-id="02883-117">[Cómo abrir una canalización](../core/how-to-open-a-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="02883-117">[How to Open a Pipeline](../core/how-to-open-a-pipeline.md) </span></span>  
 <span data-ttu-id="02883-118">[Cómo guardar una canalización](../core/how-to-save-a-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="02883-118">[How to Save a Pipeline](../core/how-to-save-a-pipeline.md) </span></span>  
 <span data-ttu-id="02883-119">[Cómo usar el cuadro de herramientas](../core/how-to-use-the-toolbox.md) </span><span class="sxs-lookup"><span data-stu-id="02883-119">[How to Use the Toolbox](../core/how-to-use-the-toolbox.md) </span></span>  
 <span data-ttu-id="02883-120">[Cómo desplazarse con el teclado](../core/how-to-navigate-with-the-keyboard.md) </span><span class="sxs-lookup"><span data-stu-id="02883-120">[How to Navigate with the Keyboard](../core/how-to-navigate-with-the-keyboard.md) </span></span>  
 [<span data-ttu-id="02883-121">Creación de canalizaciones con el Diseñador de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="02883-121">Creating Pipelines with Pipeline Designer</span></span>](../core/creating-pipelines-with-pipeline-designer.md)