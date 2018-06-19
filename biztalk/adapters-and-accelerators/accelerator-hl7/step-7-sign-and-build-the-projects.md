---
title: 'Paso 7: Firmar y compilar los proyectos | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, projects
- projects, building
- projects, signing
ms.assetid: b66e4dc1-4ec6-4ec0-a69a-419b116b19c1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f62a37da291bdc148369a28149cdfe29ed7fe446
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
ms.locfileid: "25961770"
---
# <a name="step-7-sign-and-build-the-projects"></a><span data-ttu-id="55f93-102">Paso 7: Firmar y compilar los proyectos</span><span class="sxs-lookup"><span data-stu-id="55f93-102">Step 7: Sign and Build the Projects</span></span>
<span data-ttu-id="55f93-103">En este paso, se asigna un nombre seguro y generar el proyecto para generar un ensamblado que contiene los recursos (el esquema) que creó en [paso 6: validar los esquemas](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="55f93-103">In this step, you assign a strong name and build the project to generate an assembly that contains the resources (the schema) that you created in [Step 6: Validate the Schemas](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md).</span></span> <span data-ttu-id="55f93-104">Esto también garantiza que no hay ningún error de compilación en el trabajo que ha completado hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="55f93-104">This also ensures that there are no compile errors in the work you have completed so far.</span></span>  
  
### <a name="to-sign-the-btahl7-project"></a><span data-ttu-id="55f93-105">Para firmar el proyecto de BTAHL7</span><span class="sxs-lookup"><span data-stu-id="55f93-105">To sign the BTAHL7 Project</span></span>  
  
1.  <span data-ttu-id="55f93-106">En el Explorador de soluciones, haga clic en **BTAHL7 proyecto**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="55f93-106">In Solution Explorer, right-click **BTAHL7 Project**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="55f93-107">En el cuadro de diálogo páginas de propiedades del proyecto de BTAHL7, haga clic en **ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="55f93-107">In the BTAHL7 Project Property Pages dialog box, click **Assembly**.</span></span>  
  
3.  <span data-ttu-id="55f93-108">En el panel derecho, desplácese hacia abajo hasta la **nombre seguro** sección, haga clic en el campo a la derecha del **archivo de clave de ensamblado**y, a continuación, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="55f93-108">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (…) button.</span></span>  
  
4.  <span data-ttu-id="55f93-109">En el cuadro de diálogo de archivo de clave de ensamblado, vaya a  **\< *unidad*\>: \Tutorial\BTAHL7V22Common\key.snk** (como se crearon en [paso 3: asignar un nombre seguro para el Ensamblado](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md)) y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="55f93-109">In the Assembly Key File dialog box, browse to **\<*drive*\>:\Tutorial\BTAHL7V22Common\key.snk** (as created in [Step 3: Assign a Strong Name to the Assembly](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md)), and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="55f93-110">Haga clic en **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="55f93-110">Click **OK** to save changes.</span></span>  
  
### <a name="to-build-the-btahl7-project"></a><span data-ttu-id="55f93-111">Para compilar el proyecto de BTAHL7</span><span class="sxs-lookup"><span data-stu-id="55f93-111">To build the BTAHL7 Project</span></span>  
  
-   <span data-ttu-id="55f93-112">En el Explorador de soluciones, haga clic en **BTAHL7 proyecto**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="55f93-112">In Solution Explorer, right-click **BTAHL7 Project**, and then click **Deploy**.</span></span> [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]<span data-ttu-id="55f93-113">compila el ensamblado en un archivo DLL y lo guarda en la \< *unidad*\>: \Tutorial\BTAHL7V22Common\Bin\Development carpeta.</span><span class="sxs-lookup"><span data-stu-id="55f93-113"> compiles the assembly into a DLL file and saves it in the \<*drive*\>:\Tutorial\BTAHL7V22Common\Bin\Development folder.</span></span>  
  
 <span data-ttu-id="55f93-114">Continúe con [paso 8: crear un mapa con el asignador de BizTalk](../../adapters-and-accelerators/accelerator-hl7/step-8-create-a-map-with-biztalk-mapper.md).</span><span class="sxs-lookup"><span data-stu-id="55f93-114">Proceed to [Step 8: Create a Map with BizTalk Mapper](../../adapters-and-accelerators/accelerator-hl7/step-8-create-a-map-with-biztalk-mapper.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55f93-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="55f93-115">See Also</span></span>  
 [<span data-ttu-id="55f93-116">Tutorial de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="55f93-116">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)