---
title: 'Paso 1: Crear e implementar esquemas de encabezado y confirmación | Microsoft Docs'
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
ms.openlocfilehash: 50aa394f033d935c3838e056c715ee74e296b063
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989397"
---
# <a name="step-1-create-and-deploy-header-and-acknowledgment-schemas"></a><span data-ttu-id="03054-102">Paso 1: Crear e implementar esquemas de encabezado y confirmación</span><span class="sxs-lookup"><span data-stu-id="03054-102">Step 1: Create and Deploy Header and Acknowledgment Schemas</span></span>
<span data-ttu-id="03054-103">Utilice el esquema de encabezado para validar el encabezado (segmento MSH) de la instancia de mensaje.</span><span class="sxs-lookup"><span data-stu-id="03054-103">You use the header schema to validate the header (MSH segment) of the message instance.</span></span> <span data-ttu-id="03054-104">Utilice el esquema de confirmación para generar la confirmación para la instancia de mensaje.</span><span class="sxs-lookup"><span data-stu-id="03054-104">You use the acknowledgment schema to generate the acknowledgment for the message instance.</span></span> <span data-ttu-id="03054-105">Este proceso es común en todas las versiones de esquemas de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2.X.</span><span class="sxs-lookup"><span data-stu-id="03054-105">This process is common across all schemas versions of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2.X.</span></span>  
  
### <a name="to-create-the-header-and-acknowledgment-schemas"></a><span data-ttu-id="03054-106">Para crear los esquemas de encabezado y confirmación</span><span class="sxs-lookup"><span data-stu-id="03054-106">To create the header and acknowledgment schemas</span></span>  
  
1. <span data-ttu-id="03054-107">Inicie **Microsoft Visual Studio 2012**.</span><span class="sxs-lookup"><span data-stu-id="03054-107">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2. <span data-ttu-id="03054-108">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="03054-108">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="03054-109">En el cuadro de diálogo nuevo proyecto, en el **tipos de proyecto** sección, expanda **proyectos de BizTalk**y, a continuación, seleccione **BTAHL7Projects**.</span><span class="sxs-lookup"><span data-stu-id="03054-109">In the New Project dialog box, in the **Project Types** section, expand **BizTalk Projects**, and then select **BTAHL7Projects**.</span></span>  
  
4. <span data-ttu-id="03054-110">En la sección plantillas, seleccione **proyecto BTAHL7V2XCommon**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="03054-110">In the Templates section, select **BTAHL7V2XCommon Project**, and then click **OK**.</span></span>  
  
    <span data-ttu-id="03054-111">En el Explorador de soluciones, tenga en cuenta que los tres esquemas (ACK_24_GLO_DEF.xsd ACK_25_GLO_DEF.xsd y MSH_25_GLO_DEF.xsd) se incluyen en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="03054-111">In Solution Explorer, notice that the three schemas (ACK_24_GLO_DEF.xsd ACK_25_GLO_DEF.xsd, and MSH_25_GLO_DEF.xsd) are included in the project.</span></span>  
  
## <a name="step-1a-assign-a-strong-key-to-the-assembly-and-deploy"></a><span data-ttu-id="03054-112">Paso 1A: asignar una clave segura para el ensamblado e implementar</span><span class="sxs-lookup"><span data-stu-id="03054-112">Step 1A: Assign a Strong Key to the Assembly and Deploy</span></span>  
 <span data-ttu-id="03054-113">Utilice el procedimiento siguiente para asignar una clave segura para el ensamblado y, a continuación, implemente el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="03054-113">Use the following procedure to assign a strong key to the assembly and then deploy the assembly.</span></span>  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a><span data-ttu-id="03054-114">Para asignar una clave segura e implementar el ensamblado</span><span class="sxs-lookup"><span data-stu-id="03054-114">To assign a strong key and deploy the assembly</span></span>  
  
1. <span data-ttu-id="03054-115">Inicie un **símbolo del sistema de Visual Studio 2012**.</span><span class="sxs-lookup"><span data-stu-id="03054-115">Start **Visual Studio 2012 Command Prompt**.</span></span>  
  
2. <span data-ttu-id="03054-116">En el [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] símbolo del sistema, vaya a la \< *unidad*\>: \Program archivos\\Microsoft BizTalk \<versión\> Acelerador para HL7 \SDK\End-to-End Carpeta tutorial.</span><span class="sxs-lookup"><span data-stu-id="03054-116">At the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt, browse to the \<*drive*\>:\Program Files\\Microsoft BizTalk \<version\> Accelerator for HL7 \SDK\End-to-End Tutorial folder.</span></span>  
  
3. <span data-ttu-id="03054-117">En el símbolo del sistema, escriba **sn – k key.snk**, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="03054-117">At the command prompt, type **sn –k key.snk**, and then press ENTER.</span></span> <span data-ttu-id="03054-118">Asegúrese de que aparece el siguiente mensaje de éxito en la ventana de salida y, a continuación, cierre la ventana de comandos.</span><span class="sxs-lookup"><span data-stu-id="03054-118">Ensure the following success message appears in the output window, and then close the command window.</span></span>  
  
    <span data-ttu-id="03054-119">**"Par de claves escrito en key.snk."**</span><span class="sxs-lookup"><span data-stu-id="03054-119">**"Key pair written to key.snk."**</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="03054-120">Si no aparece el mensaje correcto, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de su ensamblado.</span><span class="sxs-lookup"><span data-stu-id="03054-120">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your assembly.</span></span>  
  
4. <span data-ttu-id="03054-121">En el Explorador de soluciones, haga clic en **BTAHL7V2XCommon Project1**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="03054-121">In Solution Explorer, right-click **BTAHL7V2XCommon Project1**, and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="03054-122">En la página de páginas de propiedades de Project1 BTAHL7V2XCommon **ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="03054-122">On the BTAHL7V2XCommon Project1 Property Pages page, click **Assembly**.</span></span>  
  
6. <span data-ttu-id="03054-123">En el panel derecho, desplácese hacia abajo hasta la **nombre seguro** sección, haga clic en el campo a la derecha del **archivo clave de ensamblado**y, a continuación, haga clic en el botón de puntos suspensivos (**...** ) botón.</span><span class="sxs-lookup"><span data-stu-id="03054-123">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (**…**) button.</span></span>  
  
7. <span data-ttu-id="03054-124">En el cuadro de diálogo de archivo de clave de ensamblado, vaya a \< *unidad*\>: \Program archivos\\Microsoft BizTalk \<versión\> acelerador HL7\SDK\End a otro tutorial, Seleccione **key.snk**y, a continuación, haga clic en **abierto**.</span><span class="sxs-lookup"><span data-stu-id="03054-124">In the Assembly Key File dialog box, browse to \<*drive*\>:\Program Files\\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial, select **key.snk**, and then click **Open**.</span></span>  
  
8. <span data-ttu-id="03054-125">En la página de propiedades de proyecto BTAHL7V2XCommon **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="03054-125">On the BTAHL7V2XCommon Project Property page, click **OK** to save your changes.</span></span>  
  
9. <span data-ttu-id="03054-126">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en **el Explorador de soluciones**, haga clic en **proyecto BTAHL7V2XCommon**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="03054-126">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in **Solution Explorer**, right-click **BTAHL7V2XCommon Project**, and then click **Deploy**.</span></span> <span data-ttu-id="03054-127">Asegúrese de que aparece un mensaje de éxito en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="03054-127">Ensure a success message appears in the output window.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="03054-128">Si no aparece el mensaje de la implementación correcta, utilice [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de implementación.</span><span class="sxs-lookup"><span data-stu-id="03054-128">If the correct deploy message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your deployment.</span></span>  
  
   <span data-ttu-id="03054-129">Continúe con [paso 2: crear los esquemas comunes para V2.3.1](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-3-1.md).</span><span class="sxs-lookup"><span data-stu-id="03054-129">Proceed to [Step 2: Create Common Schemas for V2.3.1](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-3-1.md).</span></span>