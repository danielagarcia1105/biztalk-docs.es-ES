---
title: 'Paso 1: Crear e implementar esquemas de confirmación y de encabezado común | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, headers
ms.assetid: e0f11f58-9a8c-4567-a537-3d182fa7dce2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 988c2922d09412aa248c08c36e727709d45e5a66
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989269"
---
# <a name="step-1-create-and-deploy-common-header-and-acknowledgment-schemas"></a><span data-ttu-id="d6dd6-102">Paso 1: Crear e implementar esquemas de confirmación y de encabezado comunes</span><span class="sxs-lookup"><span data-stu-id="d6dd6-102">Step 1: Create and Deploy Common Header and Acknowledgment Schemas</span></span>
<span data-ttu-id="d6dd6-103">Utilice el esquema de encabezado para validar el encabezado (segmento MSH) de la instancia de mensaje.</span><span class="sxs-lookup"><span data-stu-id="d6dd6-103">You use the header schema to validate the header (MSH segment) of the message instance.</span></span> <span data-ttu-id="d6dd6-104">Utilice el esquema de confirmación para generar la confirmación para la instancia de mensaje.</span><span class="sxs-lookup"><span data-stu-id="d6dd6-104">You use the acknowledgment schema to generate the acknowledgment for the message instance.</span></span> <span data-ttu-id="d6dd6-105">Este proceso es común en todas las versiones de esquema HL7.</span><span class="sxs-lookup"><span data-stu-id="d6dd6-105">This process is common across all HL7 schema versions.</span></span>  
  
### <a name="to-create-the-header-and-acknowledgment-schemas"></a><span data-ttu-id="d6dd6-106">Para crear los esquemas de encabezado y confirmación</span><span class="sxs-lookup"><span data-stu-id="d6dd6-106">To create the header and acknowledgment schemas</span></span>  
  
1. <span data-ttu-id="d6dd6-107">Inicie **Microsoft Visual Studio 2012**.</span><span class="sxs-lookup"><span data-stu-id="d6dd6-107">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2. <span data-ttu-id="d6dd6-108">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="d6dd6-108">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="d6dd6-109">En el cuadro de diálogo nuevo proyecto, en el **tipos de proyecto** lista, expanda **proyectos de BizTalk**y, a continuación, seleccione **BTAHL7Projects**.</span><span class="sxs-lookup"><span data-stu-id="d6dd6-109">In the New Project dialog box, in the **Project Types** list, expand **BizTalk Projects**, and then select **BTAHL7Projects**.</span></span>  
  
4. <span data-ttu-id="d6dd6-110">En el **plantillas** lista, seleccione **proyecto BTAHL7V2XCommon**.</span><span class="sxs-lookup"><span data-stu-id="d6dd6-110">In the **Templates** list, select **BTAHL7V2XCommon Project**.</span></span>  
  
5. <span data-ttu-id="d6dd6-111">En el **nombre** , escriba **Interrogative_2XSchemas**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d6dd6-111">In the **Name** field, type **Interrogative_2XSchemas**, and then click **OK**.</span></span>  
  
    <span data-ttu-id="d6dd6-112">En el Explorador de soluciones, tenga en cuenta que los tres esquemas (ACK_24_GLO_DEF.xsd, ACK_25_GLO_DEF.xsd y MSH_25_GLO_DEF.xsd) se incluyen en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d6dd6-112">In Solution Explorer, notice that three schemas (ACK_24_GLO_DEF.xsd, ACK_25_GLO_DEF.xsd, and MSH_25_GLO_DEF.xsd) are included in the project.</span></span>  
  
    <span data-ttu-id="d6dd6-113">Deje abierto Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d6dd6-113">Leave Visual Studio open.</span></span>  
  
## <a name="step-1a-assign-a-strong-key-to-the-assembly-and-deploy"></a><span data-ttu-id="d6dd6-114">Paso 1A: asignar una clave segura para el ensamblado e implementar</span><span class="sxs-lookup"><span data-stu-id="d6dd6-114">Step 1A: Assign a Strong Key to the Assembly and Deploy</span></span>  
 <span data-ttu-id="d6dd6-115">Utilice el procedimiento siguiente para asignar una clave segura para el ensamblado y, a continuación, implemente el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d6dd6-115">Use the following procedure to assign a strong key to the assembly and then deploy the assembly.</span></span>  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a><span data-ttu-id="d6dd6-116">Para asignar una clave segura e implementar el ensamblado</span><span class="sxs-lookup"><span data-stu-id="d6dd6-116">To assign a strong key and deploy the assembly</span></span>  
  
1. <span data-ttu-id="d6dd6-117">Inicie un **símbolo del sistema de Visual Studio 2012**.</span><span class="sxs-lookup"><span data-stu-id="d6dd6-117">Start **Visual Studio 2012 Command Prompt**.</span></span>  
  
2. <span data-ttu-id="d6dd6-118">En el [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] símbolo, cambie el directorio a la \< *unidad*\>: \Program Files\Microsoft BizTalk \<versión\> Acelerador para HL7\SDK\Interrogative Carpeta tutorial.</span><span class="sxs-lookup"><span data-stu-id="d6dd6-118">At the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt, change your directory to the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial folder.</span></span>  
  
3. <span data-ttu-id="d6dd6-119">En el símbolo del sistema, escriba **sn – k key.snk**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="d6dd6-119">At the command prompt, type **sn –k key.snk**, and then press **Enter**.</span></span> <span data-ttu-id="d6dd6-120">Asegúrese de que aparece un mensaje de éxito en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="d6dd6-120">Ensure that a success message appears in the output window.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d6dd6-121">Si no aparece el mensaje correcto, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de su ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d6dd6-121">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your assembly.</span></span>  
  
4. <span data-ttu-id="d6dd6-122">En el Explorador de soluciones, haga clic en **Interrogative_2XSchemas** del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d6dd6-122">In Solution Explorer, right-click **Interrogative_2XSchemas** project, and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="d6dd6-123">En el cuadro de diálogo páginas de propiedades Interrogative_2XSchemas, haga clic en **ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="d6dd6-123">In the Interrogative_2XSchemas Property Pages dialog box, click **Assembly**.</span></span>  
  
6. <span data-ttu-id="d6dd6-124">En el panel derecho, desplácese hacia abajo hasta la **nombre seguro** sección, haga clic en el campo a la derecha del **archivo clave de ensamblado**y, a continuación, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="d6dd6-124">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (…) button.</span></span>  
  
7. <span data-ttu-id="d6dd6-125">En el cuadro de diálogo de archivo de clave de ensamblado, vaya a \< *unidad*\>: \Program Files\Microsoft BizTalk \<versión\> acelerador HL7\SDK\Interrogative tutorial, haga clic en **key.snk**y, a continuación, haga clic en **abierto**.</span><span class="sxs-lookup"><span data-stu-id="d6dd6-125">In the Assembly Key File dialog box, browse to \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial, click **key.snk**, and then click **Open**.</span></span>  
  
8. <span data-ttu-id="d6dd6-126">En el cuadro de diálogo páginas de propiedades Interrogative_2XSchemas, haga clic en **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="d6dd6-126">In the Interrogative_2XSchemas Property Pages dialog box, click **OK** to save your changes.</span></span>  
  
9. <span data-ttu-id="d6dd6-127">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el Explorador de soluciones, haga clic en **Interrogative_2XSchemas** del proyecto y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="d6dd6-127">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in Solution Explorer, right-click **Interrogative_2XSchemas** project, and then click **Deploy**.</span></span> <span data-ttu-id="d6dd6-128">Asegúrese de que aparece un mensaje de éxito en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="d6dd6-128">Ensure a success message appears in the output window.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d6dd6-129">Si no aparece el mensaje de la implementación correcta, utilice [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de implementación.</span><span class="sxs-lookup"><span data-stu-id="d6dd6-129">If the correct deploy message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your deployment.</span></span>  
  
   <span data-ttu-id="d6dd6-130">Continúe con [paso 2: crear los esquemas comunes para V2.4](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-4.md).</span><span class="sxs-lookup"><span data-stu-id="d6dd6-130">Proceed to [Step 2: Create Common Schemas for V2.4](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-4.md).</span></span>