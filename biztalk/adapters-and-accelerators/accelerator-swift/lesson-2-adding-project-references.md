---
title: "Lección 2: Agregar referencias de proyecto | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- references [projects]
- projects, adding references
ms.assetid: ddc2bf49-cddd-4edb-8043-870897879655
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ce151a83389fe5f0b3884446b5b793d1b58c618
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-2-adding-project-references"></a><span data-ttu-id="99e1b-102">Lección 2: Agregar referencias de proyecto</span><span class="sxs-lookup"><span data-stu-id="99e1b-102">Lesson 2: Adding Project References</span></span>
<span data-ttu-id="99e1b-103">Agregue referencias de proyecto para sus canalizaciones pueden acceder a los esquemas de tiempo de ejecución predeterminado ubicados en el archivo Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll.</span><span class="sxs-lookup"><span data-stu-id="99e1b-103">You add project references so your pipelines can access the default runtime schemas located in the Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll file.</span></span> <span data-ttu-id="99e1b-104">Este archivo de ensamblado contiene el esquema de encabezado con propiedades promocionadas necesarias para la resolución de tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="99e1b-104">This assembly file contains the header schema with promoted properties required for message-type resolution.</span></span>  
  
 <span data-ttu-id="99e1b-105">Hacer referencia a los esquemas de encabezado más adelante cuando se agrega el componente de desensamblador a la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="99e1b-105">You reference the header schemas later when you add the disassembly component to the receive pipeline.</span></span>  
  
### <a name="to-add-a-reference-to-the-default-swift-runtimeschemas-assembly"></a><span data-ttu-id="99e1b-106">Para agregar una referencia al ensamblado de SWIFT RuntimeSchemas predeterminado</span><span class="sxs-lookup"><span data-stu-id="99e1b-106">To add a reference to the default SWIFT RuntimeSchemas assembly</span></span>  
  
1.  <span data-ttu-id="99e1b-107">En el Explorador de soluciones, asegúrese de que el **SWIFTPipelines** se expande el proyecto.</span><span class="sxs-lookup"><span data-stu-id="99e1b-107">In Solution Explorer, ensure that the **SWIFTPipelines** project is expanded.</span></span> <span data-ttu-id="99e1b-108">Haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="99e1b-108">Right-click **References**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="99e1b-109">En el cuadro de diálogo Agregar referencia, haga clic en el **examinar** ficha.</span><span class="sxs-lookup"><span data-stu-id="99e1b-109">In the Add Reference dialog box, click the **Browse** tab.</span></span>  
  
3.  <span data-ttu-id="99e1b-110">Vaya a  **\<* unidad*>: \Program Acelerador de BizTalk para SWIFT\Assemblies **.</span><span class="sxs-lookup"><span data-stu-id="99e1b-110">Browse to **\<*drive*>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\Assemblies**.</span></span>  
  
4.  <span data-ttu-id="99e1b-111">Seleccione el **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll** archivo.</span><span class="sxs-lookup"><span data-stu-id="99e1b-111">Select the **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll** file.</span></span>  
  
5.  <span data-ttu-id="99e1b-112">Haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="99e1b-112">Click **Add**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="99e1b-113">RuntimeSchemas ensamblado (dll) que seleccionó ahora aparece en la colección de referencias en el proyecto SWIFTPipelines.</span><span class="sxs-lookup"><span data-stu-id="99e1b-113">The RuntimeSchemas assembly (dll) that you selected now appears in the references collection in the SWIFTPipelines project.</span></span>  
  
#### <a name="to-add-a-reference-to-the-swiftpipelines-schemas-assembly"></a><span data-ttu-id="99e1b-114">Para agregar una referencia al ensamblado de esquemas SWIFTPipelines</span><span class="sxs-lookup"><span data-stu-id="99e1b-114">To add a reference to the SWIFTPipelines schemas assembly</span></span>  
  
1.  <span data-ttu-id="99e1b-115">En el Explorador de soluciones, bajo la **SWIFTPipelines** proyecto de equipo y haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="99e1b-115">In Solution Explorer, under the **SWIFTPipelines** project, right-click **References**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="99e1b-116">En el cuadro de diálogo Agregar referencia, en la **proyectos** , haga clic en el **SWIFTSchemas** proyecto de equipo y haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="99e1b-116">In the Add Reference dialog box, on the **Projects** tab, click the **SWIFTSchemas** project, click **Add**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="99e1b-117">En el **archivo** menú, haga clic en **guardar todo** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="99e1b-117">On the **File** menu, click **Save All** to save your changes.</span></span>  
  
 <span data-ttu-id="99e1b-118">Continúe con [lección 3: agregar una canalización de recepción personalizada](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md).</span><span class="sxs-lookup"><span data-stu-id="99e1b-118">Proceed to [Lesson 3: Adding a Custom Receive Pipeline](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md).</span></span>