---
title: 'Paso 2: Crear los esquemas comunes para V2.4 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, common schemas
ms.assetid: 333ae85a-a307-4ab1-97f4-4d7b986e91de
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b19d735a792fff91197eb0336501264c6e9c772
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995805"
---
# <a name="step-2-create-common-schemas-for-v24"></a><span data-ttu-id="962a8-102">Paso 2: Crear los esquemas comunes para V2.4</span><span class="sxs-lookup"><span data-stu-id="962a8-102">Step 2: Create Common Schemas for V2.4</span></span>
<span data-ttu-id="962a8-103">Los esquemas V2.4 son esquemas normalmente se hace referencia, que se utilizan para validar las instancias de mensaje de consulta y respuesta.</span><span class="sxs-lookup"><span data-stu-id="962a8-103">The V2.4 schemas are commonly referenced schemas, which you use to validate the query and response message instances.</span></span>  
  
### <a name="to-create-the-common-schemas-for-v24"></a><span data-ttu-id="962a8-104">Para crear los esquemas comunes para V2.4</span><span class="sxs-lookup"><span data-stu-id="962a8-104">To create the common schemas for V2.4</span></span>  
  
1. <span data-ttu-id="962a8-105">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="962a8-105">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2. <span data-ttu-id="962a8-106">En el cuadro de diálogo nuevo proyecto, en el **tipos de proyecto** lista, expanda **proyectos de BizTalk**y, a continuación, seleccione **BTAHL7Projects**.</span><span class="sxs-lookup"><span data-stu-id="962a8-106">In the New Project dialog box, in the **Project Types** list, expand **BizTalk Projects**, and then select **BTAHL7Projects**.</span></span>  
  
3. <span data-ttu-id="962a8-107">En el **plantillas** lista, seleccione **BTAHL7V24Common proyecto**.</span><span class="sxs-lookup"><span data-stu-id="962a8-107">In the **Templates** list, select **BTAHL7V24Common Project**.</span></span>  
  
4. <span data-ttu-id="962a8-108">En el **nombre** , escriba **Interrogative_24Schemas**.</span><span class="sxs-lookup"><span data-stu-id="962a8-108">In the **Name** field, type **Interrogative_24Schemas**.</span></span>  
  
5. <span data-ttu-id="962a8-109">En el campo de la solución, seleccione **agregar a solución**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="962a8-109">In the Solution field, select **Add to Solution**, and then click **OK**.</span></span>  
  
    <span data-ttu-id="962a8-110">En el Explorador de soluciones, tenga en cuenta que los tres esquemas (datatypes_24.xsd, segments_24.xsd y tablevalues_24.xsd) se incluyen en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="962a8-110">In Solution Explorer, notice that three schemas (datatypes_24.xsd, segments_24.xsd, and tablevalues_24.xsd) are included in the project.</span></span>  
  
6. <span data-ttu-id="962a8-111">En el Explorador de soluciones, haga clic en **Interrogative_24Schemas** del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="962a8-111">In Solution Explorer, right-click **Interrogative_24Schemas** project,and then click **Properties**.</span></span>  
  
7. <span data-ttu-id="962a8-112">En el cuadro de diálogo páginas de propiedades Interrogative_24Schemas, haga clic en **ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="962a8-112">In the Interrogative_24Schemas Property Pages dialog box, click **Assembly**.</span></span>  
  
8. <span data-ttu-id="962a8-113">En el panel derecho, desplácese hacia abajo hasta la **nombre seguro** sección, haga clic en el campo a la derecha del **archivo clave de ensamblado**y, a continuación, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="962a8-113">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (…) button.</span></span>  
  
9. <span data-ttu-id="962a8-114">En el **archivo clave de ensamblado** cuadro de diálogo, vaya a \< *unidad*\>: \Program Files\Microsoft BizTalk \<versión\> Acelerador para HL7\SDK\ Interrogación clic Tutorial, **key.snk**y, a continuación, haga clic en **abierto**.</span><span class="sxs-lookup"><span data-stu-id="962a8-114">In the **Assembly Key File** dialog box, browse to \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial, click **key.snk**, and then click **Open**.</span></span>  
  
10. <span data-ttu-id="962a8-115">En el cuadro de diálogo páginas de propiedades Interrogative_24Schemas, haga clic en **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="962a8-115">In the Interrogative_24Schemas Property Pages dialog box, click **OK** to save your changes.</span></span>  
  
11. <span data-ttu-id="962a8-116">En el Explorador de soluciones, haga clic en **Interrogative_24Schemas** del proyecto y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="962a8-116">In Solution Explorer, right-click **Interrogative_24Schemas** project, and then click **Deploy**.</span></span> <span data-ttu-id="962a8-117">Haga clic en **Aceptar** al cuadro de diálogo que le pide que guarde los cambios en la solución.</span><span class="sxs-lookup"><span data-stu-id="962a8-117">Click **OK** to the dialog box asking you to save changes to the solution.</span></span> <span data-ttu-id="962a8-118">Asegúrese de que aparece un mensaje de éxito en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="962a8-118">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="962a8-119">Si no aparece el mensaje correcto, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de los esquemas.</span><span class="sxs-lookup"><span data-stu-id="962a8-119">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your schemas.</span></span>  
  
    <span data-ttu-id="962a8-120">Continúe con [paso 3: crear e implementar un proyecto de desencadenador de eventos (mensaje)](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project-hl7-main.md).</span><span class="sxs-lookup"><span data-stu-id="962a8-120">Proceed to [Step 3: Create and Deploy a Trigger Event (Message) Project](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project-hl7-main.md).</span></span>