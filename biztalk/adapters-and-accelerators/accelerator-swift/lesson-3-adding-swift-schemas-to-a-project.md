---
title: "Lección 3: Agregar esquemas SWIFT a un proyecto | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, adding to projects
- projects
ms.assetid: e17ef4b8-f060-44cc-b988-0f9f54deab90
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12fb5741b75fb9792cbabf46bf7a0402972d7bb4
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="lesson-3-adding-swift-schemas-to-a-project"></a><span data-ttu-id="b5ffe-102">Lección 3: Agregar esquemas SWIFT a un proyecto</span><span class="sxs-lookup"><span data-stu-id="b5ffe-102">Lesson 3: Adding SWIFT Schemas to a Project</span></span>
<span data-ttu-id="b5ffe-103">Ahora que tiene una solución y un nuevo proyecto, puede agregar elementos al proyecto.</span><span class="sxs-lookup"><span data-stu-id="b5ffe-103">Now that you have a solution and a new project, you can add items to the project.</span></span> <span data-ttu-id="b5ffe-104">El primer elemento que se agrega es un esquema para un mensaje de pago de SWIFT MT103.</span><span class="sxs-lookup"><span data-stu-id="b5ffe-104">The first item you add is a schema for an MT103 SWIFT Payment message.</span></span> <span data-ttu-id="b5ffe-105">Cuando se selecciona la plantilla de esquema, se inicia el Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b5ffe-105">When you select the Schema template, BizTalk Editor starts.</span></span>  
  
### <a name="to-add-a-new-schema-to-the-project"></a><span data-ttu-id="b5ffe-106">Para agregar un nuevo esquema al proyecto</span><span class="sxs-lookup"><span data-stu-id="b5ffe-106">To add a new schema to the project</span></span>  
  
1.  <span data-ttu-id="b5ffe-107">En el Explorador de soluciones, haga clic en el **SWIFTSchemas** , seleccione **agregar**y, a continuación, haga clic en **elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="b5ffe-107">In Solution Explorer, right-click the **SWIFTSchemas** project, point to **Add**, and then click **Existing Item**.</span></span>  
  
2.  <span data-ttu-id="b5ffe-108">En el cuadro de diálogo Agregar elemento existente-SWIFTSchemas, vaya a  **\< *unidad*\>: \Program Acelerador de BizTalk para SWIFT \<versión\> MessagePack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Base esquemas**.</span><span class="sxs-lookup"><span data-stu-id="b5ffe-108">In the Add Existing Item-SWIFTSchemas dialog box, browse to **\<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT \<version\> MessagePack\SWIFT Messages\A4SWIFT-SRG\<version\>\Base Schemas**.</span></span>  
  
3.  <span data-ttu-id="b5ffe-109">Seleccione el **SWIFT Base Types.xsd** y **Types.xsd de datos común de SWIFT** esquemas y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="b5ffe-109">Select the **SWIFT Base Types.xsd** and the **SWIFT Common Data Types.xsd** schemas, and then click **Add**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b5ffe-110">El Types.xsd de la Base de SWIFT y los esquemas de SWIFT Types.xsd de datos comunes aparecen en el Explorador de soluciones bajo el proyecto SWIFTSchemas.</span><span class="sxs-lookup"><span data-stu-id="b5ffe-110">The SWIFT Base Types.xsd and the SWIFT Common Data Types.xsd schemas appear in Solution Explorer under the SWIFTSchemas project.</span></span>  
  
4.  <span data-ttu-id="b5ffe-111">En el Explorador de soluciones, haga clic en el **SWIFTSchemas** , seleccione **agregar**y, a continuación, haga clic en **elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="b5ffe-111">In Solution Explorer, right-click the **SWIFTSchemas** project, point to **Add**, and then click **Existing Item**.</span></span>  
  
5.  <span data-ttu-id="b5ffe-112">En el cuadro de diálogo Agregar elemento existente-SWIFTSchemas, vaya a la  **\< *unidad*\>: \Program Acelerador de BizTalk para SWIFT \<versión\> MessagePack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Category 1\MT103** carpeta.</span><span class="sxs-lookup"><span data-stu-id="b5ffe-112">In the Add Existing Item-SWIFTSchemas dialog box, browse to the **\<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT \<version\> MessagePack\SWIFT Messages\A4SWIFT-SRG\<version\>\Category 1\MT103** folder.</span></span>  
  
6.  <span data-ttu-id="b5ffe-113">Seleccione el **MT103.xsd** esquema y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="b5ffe-113">Select the **MT103.xsd** schema, and then click **Add**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b5ffe-114">El nuevo esquema, MT103.xsd, aparece en el Explorador de soluciones bajo el proyecto SWIFTSchemas.</span><span class="sxs-lookup"><span data-stu-id="b5ffe-114">The new schema, MT103.xsd, appears in Solution Explorer under the SWIFTSchemas project.</span></span>  
  
7.  <span data-ttu-id="b5ffe-115">En el Explorador de soluciones, haga doble clic en **MT103.xsd** para ver el esquema en el Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b5ffe-115">In Solution Explorer, double-click **MT103.xsd** to view the schema in BizTalk Editor.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b5ffe-116">El árbol de esquema (panel izquierdo) y la vista XSD (panel derecho) aparecen en el Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b5ffe-116">The schema tree (left pane) and XSD view (right pane) appear in BizTalk Editor.</span></span>  
  
8.  <span data-ttu-id="b5ffe-117">En el **archivo** menú, haga clic en **guardar todo** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="b5ffe-117">On the **File** menu, click **Save All** to save your changes.</span></span>  
  
 <span data-ttu-id="b5ffe-118">Continúe con [lección 4: crear e implementar el ensamblado](../../adapters-and-accelerators/accelerator-swift/lesson-4-building-and-deploying-the-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="b5ffe-118">Proceed to [Lesson 4: Building and Deploying the Assembly](../../adapters-and-accelerators/accelerator-swift/lesson-4-building-and-deploying-the-assembly.md).</span></span>