---
title: 'Paso 1: Agregar encabezado y esquemas de confirmación | Documentos de Microsoft'
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
ms.openlocfilehash: f79778801b1ca70d4e8356a24886c792fe447e33
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005341"
---
# <a name="step-1-add-header-and-acknowledgment-schemas"></a><span data-ttu-id="6031c-102">Paso 1: Agregar encabezado y esquemas de confirmación</span><span class="sxs-lookup"><span data-stu-id="6031c-102">Step 1: Add Header and Acknowledgment Schemas</span></span>
<span data-ttu-id="6031c-103">En este paso, creará un proyecto nuevo basado en la plantilla de proyecto de BTAHL72XCommon.</span><span class="sxs-lookup"><span data-stu-id="6031c-103">In this step, you create a new project based on the BTAHL72XCommon Project template.</span></span> <span data-ttu-id="6031c-104">Esta plantilla contiene los tres esquemas comunes para encabezados de mensaje (MSH_25_GLO_DEF.xsd) y confirmaciones (ACK_24_GLO_DEF.xsd) y (ACK_25_GLO_DEF.xsd).</span><span class="sxs-lookup"><span data-stu-id="6031c-104">This template contains the three common schemas for message headers (MSH_25_GLO_DEF.xsd) and acknowledgments (ACK_24_GLO_DEF.xsd) and (ACK_25_GLO_DEF.xsd).</span></span> <span data-ttu-id="6031c-105">Debe incluir estos esquemas en un proyecto de modo que ese Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) genera o valida correctamente los encabezados de mensaje y confirmaciones.</span><span class="sxs-lookup"><span data-stu-id="6031c-105">You must include these schemas in a project so that BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) builds and/or validates the message headers and acknowledgments correctly.</span></span> <span data-ttu-id="6031c-106">Este proceso es común en todas las versiones de esquema de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2.X.</span><span class="sxs-lookup"><span data-stu-id="6031c-106">This process is common across all schema versions of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2.X.</span></span>  
  
 <span data-ttu-id="6031c-107">Crear una clave segura, asignar al ensamblado y, a continuación, implemente el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6031c-107">You also create a strong key, assign it to the assembly, and then deploy the assembly.</span></span> <span data-ttu-id="6031c-108">La clave segura proporciona seguridad y la identidad para el ensamblado y es necesaria para la implementación.</span><span class="sxs-lookup"><span data-stu-id="6031c-108">The strong key provides security and identity to the assembly, and is necessary for deployment.</span></span> <span data-ttu-id="6031c-109">Al implementar el ensamblado, se almacena en la base de datos de configuración (también conocido como la base de datos de administración de BizTalk) y la caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="6031c-109">When you deploy the assembly, it is stored in the Configuration database (also known as the BizTalk Management database) and the global assembly cache (GAC).</span></span>  
  
### <a name="to-create-the-project-and-add-header-and-acknowledgment-schemas"></a><span data-ttu-id="6031c-110">Para crear el proyecto y agregar esquemas de encabezado y de confirmación</span><span class="sxs-lookup"><span data-stu-id="6031c-110">To create the project and add header and acknowledgment schemas</span></span>  
  
1.  <span data-ttu-id="6031c-111">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6031c-111">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="6031c-112">En el cuadro de diálogo nuevo proyecto, en la **tipos de proyecto** lista, expanda **proyectos de BizTalk**y, a continuación, haga clic en **BTAHL7Projects**.</span><span class="sxs-lookup"><span data-stu-id="6031c-112">In the New Project dialog box, in the **Project Types** list, expand **BizTalk Projects**, and then click **BTAHL7Projects**.</span></span>  
  
3.  <span data-ttu-id="6031c-113">En el **plantillas** lista, haga clic en **proyecto BTAHL7V2XCommon**.</span><span class="sxs-lookup"><span data-stu-id="6031c-113">In the **Templates** list, click **BTAHL7V2XCommon Project**.</span></span>  
  
4.  <span data-ttu-id="6031c-114">En el **nombre** , escriba **BTAHL7V2XCommon** como el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6031c-114">In the **Name** box, type **BTAHL7V2XCommon** as the project name.</span></span>  
  
5.  <span data-ttu-id="6031c-115">En el **ubicación** cuadro, vaya a  **\<**  *unidad***:\>\Batching Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="6031c-115">In the **Location** box, browse to **\<***drive***:\>\Batching Tutorial**.</span></span>  
  
6.  <span data-ttu-id="6031c-116">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6031c-116">Click **OK**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6031c-117">En el Explorador de soluciones, se incluyen tres esquemas (MSH_25_GLO_DEF.xsd, ACK_24_GLO_DEF.xsd y ACK_25_GLO_DEF.xsd) en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6031c-117">In Solution Explorer, three schemas (MSH_25_GLO_DEF.xsd, ACK_24_GLO_DEF.xsd, and ACK_25_GLO_DEF.xsd) are included in the project.</span></span>  
  
### <a name="to-assign-a-strong-key-to-the-assembly-and-deploy"></a><span data-ttu-id="6031c-118">Para asignar una clave segura para el ensamblado e implementar</span><span class="sxs-lookup"><span data-stu-id="6031c-118">To assign a strong key to the assembly and deploy</span></span>  
  
1.  <span data-ttu-id="6031c-119">Abra **símbolo del sistema de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="6031c-119">Open **Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="6031c-120">En el [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] símbolo del sistema, vaya a la  **\<**  *unidad***\>: \Batching Tutorial** carpeta.</span><span class="sxs-lookup"><span data-stu-id="6031c-120">On the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt, browse to the **\<***drive***\>:\Batching Tutorial** folder.</span></span>  
  
3.  <span data-ttu-id="6031c-121">En el símbolo del sistema, escriba **sn – k key.snk**, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="6031c-121">At the command prompt, type **sn –k key.snk**, and then press ENTER.</span></span> <span data-ttu-id="6031c-122">Asegúrese de que aparece un mensaje de confirmación en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="6031c-122">Ensure that a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6031c-123">Si no aparece el mensaje correcto, utilice [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de su ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6031c-123">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your assembly.</span></span>  
  
4.  <span data-ttu-id="6031c-124">En el Explorador de soluciones, haga clic en **proyecto BTAHL7V2Xcommon**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6031c-124">In Solution Explorer, right-click **BTAHL7V2Xcommon Project**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="6031c-125">En el **página de propiedades de proyecto BTAHL7V2XCommon** cuadro de diálogo, haga clic en **firma**.</span><span class="sxs-lookup"><span data-stu-id="6031c-125">In the **BTAHL7V2XCommon Project Property Page** dialog box, click **Signing**.</span></span>  
  
6.  <span data-ttu-id="6031c-126">Comprobar **firmar el ensamblado** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="6031c-126">Check **Sign the assembly** check box.</span></span>  
  
7.  <span data-ttu-id="6031c-127">En **elegir un nombre seguro** desplegable archivo de clave de lista, seleccione  **\<Examinar... \>**.</span><span class="sxs-lookup"><span data-stu-id="6031c-127">In **Choose a Strong name** key file drop down list select **\<Browse…\>**.</span></span>  
  
8.  <span data-ttu-id="6031c-128">Vaya a \< *unidad*\>: Tutorial, seleccione \Batching **key.snk**y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="6031c-128">Browse to \<*drive*\>:\Batching Tutorial, select **key.snk**, and then click **Open**.</span></span>  
  
9. <span data-ttu-id="6031c-129">En la ventana páginas de propiedades de proyecto BTAHL7V2XCommon, haga clic en **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="6031c-129">In the BTAHL7V2XCommon Project Property Pages window, click **OK** to save your changes.</span></span>  
  
10. <span data-ttu-id="6031c-130">En el Explorador de soluciones, haga clic en **proyecto BTAHL7V2Xcommon**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="6031c-130">In Solution Explorer, right-click **BTAHL7V2Xcommon Project**, and then click **Deploy**.</span></span> <span data-ttu-id="6031c-131">Asegúrese de que aparece un mensaje de confirmación en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="6031c-131">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6031c-132">Si no aparece el mensaje de implementación correcta, utilice [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de la implementación.</span><span class="sxs-lookup"><span data-stu-id="6031c-132">If the correct deploy message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your deployment.</span></span>  
  
 <span data-ttu-id="6031c-133">Continúe con [paso 2: agregar los esquemas comunes para v2.3.1](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md).</span><span class="sxs-lookup"><span data-stu-id="6031c-133">Proceed to [Step 2: Add Common Schemas for v2.3.1](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md).</span></span>