---
title: 'Paso 1: Agregar esquemas de encabezado y confirmación | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 808132bf-02e7-4ff4-b914-9fae5d27e5fd
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae0712e2ee4498b8f6f2eb8cb9527aa8ee8e4582
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011319"
---
# <a name="step-1-add-header-and-acknowledgment-schemas"></a><span data-ttu-id="b6244-102">Paso 1: Agregar esquemas de encabezado y confirmación</span><span class="sxs-lookup"><span data-stu-id="b6244-102">Step 1: Add Header and Acknowledgment Schemas</span></span>
<span data-ttu-id="b6244-103">En este paso, creará un nuevo proyecto basado en la plantilla de proyecto BTAHL72XCommon.</span><span class="sxs-lookup"><span data-stu-id="b6244-103">In this step, you create a new project based on the BTAHL72XCommon Project template.</span></span> <span data-ttu-id="b6244-104">Esta plantilla contiene los tres esquemas comunes para los encabezados del mensaje (MSH_25_GLO_DEF.xsd) y confirmaciones (ACK_24_GLO_DEF.xsd) y (ACK_25_GLO_DEF.xsd).</span><span class="sxs-lookup"><span data-stu-id="b6244-104">This template contains the three common schemas for message headers (MSH_25_GLO_DEF.xsd) and acknowledgments (ACK_24_GLO_DEF.xsd) and (ACK_25_GLO_DEF.xsd).</span></span> <span data-ttu-id="b6244-105">Debe incluir por lo que estos esquemas en un proyecto que el Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) compila y valida los encabezados de mensaje y las confirmaciones correctamente.</span><span class="sxs-lookup"><span data-stu-id="b6244-105">You must include these schemas in a project so that BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) builds and/or validates the message headers and acknowledgments correctly.</span></span> <span data-ttu-id="b6244-106">Este proceso es común en todas las versiones de esquema de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2.X.</span><span class="sxs-lookup"><span data-stu-id="b6244-106">This process is common across all schema versions of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2.X.</span></span>  
  
 <span data-ttu-id="b6244-107">También crea una clave segura, asignarlo al ensamblado y, a continuación, implemente el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b6244-107">You also create a strong key, assign it to the assembly, and then deploy the assembly.</span></span> <span data-ttu-id="b6244-108">La clave segura proporciona seguridad e identidad para el ensamblado y es necesaria para la implementación.</span><span class="sxs-lookup"><span data-stu-id="b6244-108">The strong key provides security and identity to the assembly, and is necessary for deployment.</span></span> <span data-ttu-id="b6244-109">Al implementar el ensamblado, se almacena en la base de datos de configuración (también conocido como la base de datos de administración de BizTalk) y la caché global de ensamblados (GAC).</span><span class="sxs-lookup"><span data-stu-id="b6244-109">When you deploy the assembly, it is stored in the Configuration database (also known as the BizTalk Management database) and the global assembly cache (GAC).</span></span>  
  
### <a name="to-create-the-project-and-add-header-and-acknowledgment-schemas"></a><span data-ttu-id="b6244-110">Para crear el proyecto y agregar esquemas de encabezado y confirmación</span><span class="sxs-lookup"><span data-stu-id="b6244-110">To create the project and add header and acknowledgment schemas</span></span>  
  
1. <span data-ttu-id="b6244-111">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="b6244-111">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2. <span data-ttu-id="b6244-112">En el cuadro de diálogo nuevo proyecto, en el **tipos de proyecto** lista, expanda **proyectos de BizTalk**y, a continuación, haga clic en **BTAHL7Projects**.</span><span class="sxs-lookup"><span data-stu-id="b6244-112">In the New Project dialog box, in the **Project Types** list, expand **BizTalk Projects**, and then click **BTAHL7Projects**.</span></span>  
  
3. <span data-ttu-id="b6244-113">En el **plantillas** lista, haga clic en **proyecto BTAHL7V2XCommon**.</span><span class="sxs-lookup"><span data-stu-id="b6244-113">In the **Templates** list, click **BTAHL7V2XCommon Project**.</span></span>  
  
4. <span data-ttu-id="b6244-114">En el **nombre** , escriba **BTAHL7V2XCommon** como el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6244-114">In the **Name** box, type **BTAHL7V2XCommon** as the project name.</span></span>  
  
5. <span data-ttu-id="b6244-115">En el **ubicación** cuadro, vaya a **\<** <em>unidad</em>**:\>\Batching Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="b6244-115">In the **Location** box, browse to **\<**<em>drive</em>**:\>\Batching Tutorial**.</span></span>  
  
6. <span data-ttu-id="b6244-116">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b6244-116">Click **OK**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b6244-117">En el Explorador de soluciones, los tres esquemas (MSH_25_GLO_DEF.xsd, ACK_24_GLO_DEF.xsd y ACK_25_GLO_DEF.xsd) se incluyen en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6244-117">In Solution Explorer, three schemas (MSH_25_GLO_DEF.xsd, ACK_24_GLO_DEF.xsd, and ACK_25_GLO_DEF.xsd) are included in the project.</span></span>  
  
### <a name="to-assign-a-strong-key-to-the-assembly-and-deploy"></a><span data-ttu-id="b6244-118">Para asignar una clave segura para el ensamblado e implementar</span><span class="sxs-lookup"><span data-stu-id="b6244-118">To assign a strong key to the assembly and deploy</span></span>  
  
1. <span data-ttu-id="b6244-119">Abra **símbolo del sistema de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="b6244-119">Open **Visual Studio Command Prompt**.</span></span>  
  
2. <span data-ttu-id="b6244-120">En el [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] símbolo del sistema, vaya a la **\<** <em>unidad</em>**\>: \Batching Tutorial** carpeta.</span><span class="sxs-lookup"><span data-stu-id="b6244-120">On the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt, browse to the **\<**<em>drive</em>**\>:\Batching Tutorial** folder.</span></span>  
  
3. <span data-ttu-id="b6244-121">En el símbolo del sistema, escriba **sn – k key.snk**, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="b6244-121">At the command prompt, type **sn –k key.snk**, and then press ENTER.</span></span> <span data-ttu-id="b6244-122">Asegúrese de que aparece un mensaje de éxito en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="b6244-122">Ensure that a success message appears in the output window.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="b6244-123">Si no aparece el mensaje correcto, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de su ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b6244-123">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your assembly.</span></span>  
  
4. <span data-ttu-id="b6244-124">En el Explorador de soluciones, haga clic en **proyecto BTAHL7V2Xcommon**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b6244-124">In Solution Explorer, right-click **BTAHL7V2Xcommon Project**, and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="b6244-125">En el **página de propiedades de proyecto BTAHL7V2XCommon** cuadro de diálogo, haga clic en **firma**.</span><span class="sxs-lookup"><span data-stu-id="b6244-125">In the **BTAHL7V2XCommon Project Property Page** dialog box, click **Signing**.</span></span>  
  
6. <span data-ttu-id="b6244-126">Comprobar **firmar el ensamblado** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="b6244-126">Check **Sign the assembly** check box.</span></span>  
  
7. <span data-ttu-id="b6244-127">En **elegir un nombre seguro** desplegable archivo de clave de lista, seleccione  **\<Examinar... \>**.</span><span class="sxs-lookup"><span data-stu-id="b6244-127">In **Choose a Strong name** key file drop down list select **\<Browse…\>**.</span></span>  
  
8. <span data-ttu-id="b6244-128">Vaya a \< *unidad*\>: Tutorial, seleccione \Batching **key.snk**y, a continuación, haga clic en **abierto**.</span><span class="sxs-lookup"><span data-stu-id="b6244-128">Browse to \<*drive*\>:\Batching Tutorial, select **key.snk**, and then click **Open**.</span></span>  
  
9. <span data-ttu-id="b6244-129">En la ventana páginas de propiedades de proyecto BTAHL7V2XCommon, haga clic en **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="b6244-129">In the BTAHL7V2XCommon Project Property Pages window, click **OK** to save your changes.</span></span>  
  
10. <span data-ttu-id="b6244-130">En el Explorador de soluciones, haga clic en **proyecto BTAHL7V2Xcommon**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="b6244-130">In Solution Explorer, right-click **BTAHL7V2Xcommon Project**, and then click **Deploy**.</span></span> <span data-ttu-id="b6244-131">Asegúrese de que aparece un mensaje de éxito en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="b6244-131">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b6244-132">Si no aparece el mensaje de la implementación correcta, utilice [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de implementación.</span><span class="sxs-lookup"><span data-stu-id="b6244-132">If the correct deploy message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your deployment.</span></span>  
  
    <span data-ttu-id="b6244-133">Continúe con [paso 2: adición de esquemas comunes para v2.3.1](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md).</span><span class="sxs-lookup"><span data-stu-id="b6244-133">Proceed to [Step 2: Add Common Schemas for v2.3.1](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md).</span></span>