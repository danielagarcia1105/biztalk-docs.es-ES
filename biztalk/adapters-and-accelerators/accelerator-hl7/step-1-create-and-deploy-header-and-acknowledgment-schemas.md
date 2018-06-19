---
title: 'Paso 1: Crear e implementar encabezado y esquemas de confirmación | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, header schemas
- header schemas
ms.assetid: 3ff013a4-6c67-4bac-be97-81b2dc5b6119
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9ffa8ab8d80a8b2da172378349eb9761a728fb7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960746"
---
# <a name="step-1-create-and-deploy-header-and-acknowledgment-schemas"></a><span data-ttu-id="7f7f8-102">Paso 1: Crear e implementar encabezado y esquemas de confirmación</span><span class="sxs-lookup"><span data-stu-id="7f7f8-102">Step 1: Create and Deploy Header and Acknowledgment Schemas</span></span>
<span data-ttu-id="7f7f8-103">Utilice el esquema de encabezado para validar el encabezado (segmento MSH) de la instancia de mensaje.</span><span class="sxs-lookup"><span data-stu-id="7f7f8-103">You use the header schema to validate the header (MSH segment) of the message instance.</span></span> <span data-ttu-id="7f7f8-104">Usar el esquema de confirmación para generar la confirmación de la instancia de mensaje.</span><span class="sxs-lookup"><span data-stu-id="7f7f8-104">You use the acknowledgment schema to generate the acknowledgment for the message instance.</span></span> <span data-ttu-id="7f7f8-105">Este proceso es común en todas las versiones de esquemas de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2.X.</span><span class="sxs-lookup"><span data-stu-id="7f7f8-105">This process is common across all schemas versions of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2.X.</span></span>  
  
### <a name="to-create-the-header-and-acknowledgment-schemas"></a><span data-ttu-id="7f7f8-106">Para crear los esquemas de encabezado y confirmación</span><span class="sxs-lookup"><span data-stu-id="7f7f8-106">To create the header and acknowledgment schemas</span></span>  
  
1.  <span data-ttu-id="7f7f8-107">Inicie **Microsoft Visual Studio 2012**.</span><span class="sxs-lookup"><span data-stu-id="7f7f8-107">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="7f7f8-108">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="7f7f8-108">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="7f7f8-109">En el cuadro de diálogo nuevo proyecto, en la **tipos de proyecto** sección, expanda **proyectos de BizTalk**y, a continuación, seleccione **BTAHL7Projects**.</span><span class="sxs-lookup"><span data-stu-id="7f7f8-109">In the New Project dialog box, in the **Project Types** section, expand **BizTalk Projects**, and then select **BTAHL7Projects**.</span></span>  
  
4.  <span data-ttu-id="7f7f8-110">En la sección de plantillas, seleccione **proyecto BTAHL7V2XCommon**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7f7f8-110">In the Templates section, select **BTAHL7V2XCommon Project**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="7f7f8-111">En el Explorador de soluciones, tenga en cuenta que los tres esquemas (ACK_24_GLO_DEF.xsd ACK_25_GLO_DEF.xsd y MSH_25_GLO_DEF.xsd) se incluyen en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7f7f8-111">In Solution Explorer, notice that the three schemas (ACK_24_GLO_DEF.xsd ACK_25_GLO_DEF.xsd, and MSH_25_GLO_DEF.xsd) are included in the project.</span></span>  
  
## <a name="step-1a-assign-a-strong-key-to-the-assembly-and-deploy"></a><span data-ttu-id="7f7f8-112">Paso 1A: asignar una clave segura para el ensamblado e implementar</span><span class="sxs-lookup"><span data-stu-id="7f7f8-112">Step 1A: Assign a Strong Key to the Assembly and Deploy</span></span>  
 <span data-ttu-id="7f7f8-113">Utilice el procedimiento siguiente para asignar una clave segura para el ensamblado y, a continuación, implemente el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7f7f8-113">Use the following procedure to assign a strong key to the assembly and then deploy the assembly.</span></span>  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a><span data-ttu-id="7f7f8-114">Para asignar una clave segura e implementar el ensamblado</span><span class="sxs-lookup"><span data-stu-id="7f7f8-114">To assign a strong key and deploy the assembly</span></span>  
  
1.  <span data-ttu-id="7f7f8-115">Inicie un **símbolo del sistema de Visual Studio 2012**.</span><span class="sxs-lookup"><span data-stu-id="7f7f8-115">Start **Visual Studio 2012 Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="7f7f8-116">En el [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] símbolo del sistema, vaya a la \< *unidad*\>: \Program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión\> Acelerador para HL7 \SDK\ Carpeta de Tutorial de extremo a extremo.</span><span class="sxs-lookup"><span data-stu-id="7f7f8-116">At the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt, browse to the \<*drive*\>:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version\> Accelerator for HL7 \SDK\End-to-End Tutorial folder.</span></span>  
  
3.  <span data-ttu-id="7f7f8-117">En el símbolo del sistema, escriba **sn – k key.snk**, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="7f7f8-117">At the command prompt, type **sn –k key.snk**, and then press ENTER.</span></span> <span data-ttu-id="7f7f8-118">Asegúrese de que el siguiente mensaje de confirmación que aparece en la ventana de salida y, a continuación, cierre la ventana de comandos.</span><span class="sxs-lookup"><span data-stu-id="7f7f8-118">Ensure the following success message appears in the output window, and then close the command window.</span></span>  
  
     <span data-ttu-id="7f7f8-119">**"Par de claves escrito en key.snk."**</span><span class="sxs-lookup"><span data-stu-id="7f7f8-119">**"Key pair written to key.snk."**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7f7f8-120">Si no aparece el mensaje correcto, utilice [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de su ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7f7f8-120">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your assembly.</span></span>  
  
4.  <span data-ttu-id="7f7f8-121">En el Explorador de soluciones, haga clic en **BTAHL7V2XCommon Proyecto1**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7f7f8-121">In Solution Explorer, right-click **BTAHL7V2XCommon Project1**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="7f7f8-122">En la página de páginas de propiedades de Project1 BTAHL7V2XCommon, haga clic en **ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="7f7f8-122">On the BTAHL7V2XCommon Project1 Property Pages page, click **Assembly**.</span></span>  
  
6.  <span data-ttu-id="7f7f8-123">En el panel derecho, desplácese hacia abajo hasta la **nombre seguro** sección, haga clic en el campo a la derecha del **archivo de clave de ensamblado**y, a continuación, haga clic en el botón de puntos suspensivos (**...** ) botón.</span><span class="sxs-lookup"><span data-stu-id="7f7f8-123">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (**…**) button.</span></span>  
  
7.  <span data-ttu-id="7f7f8-124">En el cuadro de diálogo de archivo de clave de ensamblado, vaya a \< *unidad*\>: \Program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión\> acelerador HL7\SDK\End-to-end Tutorial, seleccione **key.snk**y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="7f7f8-124">In the Assembly Key File dialog box, browse to \<*drive*\>:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial, select **key.snk**, and then click **Open**.</span></span>  
  
8.  <span data-ttu-id="7f7f8-125">En la página de propiedades del proyecto BTAHL7V2XCommon, haga clic en **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="7f7f8-125">On the BTAHL7V2XCommon Project Property page, click **OK** to save your changes.</span></span>  
  
9. <span data-ttu-id="7f7f8-126">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en **el Explorador de soluciones**, haga clic en **proyecto BTAHL7V2XCommon**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="7f7f8-126">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in **Solution Explorer**, right-click **BTAHL7V2XCommon Project**, and then click **Deploy**.</span></span> <span data-ttu-id="7f7f8-127">Asegúrese de que aparece un mensaje de confirmación en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="7f7f8-127">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7f7f8-128">Si no aparece el mensaje de implementación correcta, utilice [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de la implementación.</span><span class="sxs-lookup"><span data-stu-id="7f7f8-128">If the correct deploy message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your deployment.</span></span>  
  
 <span data-ttu-id="7f7f8-129">Continúe con [paso 2: crear los esquemas comunes para V2.3.1](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-3-1.md).</span><span class="sxs-lookup"><span data-stu-id="7f7f8-129">Proceed to [Step 2: Create Common Schemas for V2.3.1](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-3-1.md).</span></span>