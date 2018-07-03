---
title: 'Lección 2: Agregar referencias de proyecto | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- references [projects]
- projects, adding references
ms.assetid: ddc2bf49-cddd-4edb-8043-870897879655
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e7ade122e725c07772dba431bd364bc8f933b82
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969701"
---
# <a name="lesson-2-adding-project-references"></a><span data-ttu-id="e04ea-102">Lección 2: Agregar referencias de proyecto</span><span class="sxs-lookup"><span data-stu-id="e04ea-102">Lesson 2: Adding Project References</span></span>
<span data-ttu-id="e04ea-103">Agregar referencias de proyecto para las canalizaciones pueden acceder a los esquemas de tiempo de ejecución predeterminado ubicados en el archivo Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll.</span><span class="sxs-lookup"><span data-stu-id="e04ea-103">You add project references so your pipelines can access the default runtime schemas located in the Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll file.</span></span> <span data-ttu-id="e04ea-104">Este archivo de ensamblado contiene el esquema de encabezado con propiedades promocionadas necesarias para la resolución de tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="e04ea-104">This assembly file contains the header schema with promoted properties required for message-type resolution.</span></span>  
  
 <span data-ttu-id="e04ea-105">Hacer referencia a los esquemas de encabezado más tarde al agregar el componente de desensamblador a la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="e04ea-105">You reference the header schemas later when you add the disassembly component to the receive pipeline.</span></span>  
  
### <a name="to-add-a-reference-to-the-default-swift-runtimeschemas-assembly"></a><span data-ttu-id="e04ea-106">Para agregar una referencia al ensamblado de SWIFT RuntimeSchemas predeterminada</span><span class="sxs-lookup"><span data-stu-id="e04ea-106">To add a reference to the default SWIFT RuntimeSchemas assembly</span></span>  
  
1.  <span data-ttu-id="e04ea-107">En el Explorador de soluciones, asegúrese de que el **SWIFTPipelines** se expande el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e04ea-107">In Solution Explorer, ensure that the **SWIFTPipelines** project is expanded.</span></span> <span data-ttu-id="e04ea-108">Haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="e04ea-108">Right-click **References**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="e04ea-109">En el cuadro de diálogo Agregar referencia, haga clic en el **examinar** ficha.</span><span class="sxs-lookup"><span data-stu-id="e04ea-109">In the Add Reference dialog box, click the **Browse** tab.</span></span>  
  
3.  <span data-ttu-id="e04ea-110">Vaya a  **\< *unidad*\>: Acelerador de BizTalk para SWIFT\Assemblies \Program Files\Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="e04ea-110">Browse to **\<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\Assemblies**.</span></span>  
  
4.  <span data-ttu-id="e04ea-111">Seleccione el **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll** archivo.</span><span class="sxs-lookup"><span data-stu-id="e04ea-111">Select the **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll** file.</span></span>  
  
5.  <span data-ttu-id="e04ea-112">Haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e04ea-112">Click **Add**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e04ea-113">El ensamblado RuntimeSchemas (dll) que ha seleccionado ahora aparece en la colección de referencias en el proyecto SWIFTPipelines.</span><span class="sxs-lookup"><span data-stu-id="e04ea-113">The RuntimeSchemas assembly (dll) that you selected now appears in the references collection in the SWIFTPipelines project.</span></span>  
  
#### <a name="to-add-a-reference-to-the-swiftpipelines-schemas-assembly"></a><span data-ttu-id="e04ea-114">Para agregar una referencia al ensamblado SWIFTPipelines esquemas</span><span class="sxs-lookup"><span data-stu-id="e04ea-114">To add a reference to the SWIFTPipelines schemas assembly</span></span>  
  
1. <span data-ttu-id="e04ea-115">En el Explorador de soluciones, bajo la **SWIFTPipelines** del proyecto, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="e04ea-115">In Solution Explorer, under the **SWIFTPipelines** project, right-click **References**, and then click **Add Reference**.</span></span>  
  
2. <span data-ttu-id="e04ea-116">En el cuadro de diálogo Agregar referencia, en el **proyectos** pestaña, haga clic en el **SWIFTSchemas** del proyecto, haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e04ea-116">In the Add Reference dialog box, on the **Projects** tab, click the **SWIFTSchemas** project, click **Add**, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="e04ea-117">En el **archivo** menú, haga clic en **guardar todo** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="e04ea-117">On the **File** menu, click **Save All** to save your changes.</span></span>  
  
   <span data-ttu-id="e04ea-118">Continúe con [lección 3: adición de una canalización de recepción personalizada](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md).</span><span class="sxs-lookup"><span data-stu-id="e04ea-118">Proceed to [Lesson 3: Adding a Custom Receive Pipeline](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md).</span></span>