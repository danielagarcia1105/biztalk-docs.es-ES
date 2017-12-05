---
title: 'Paso 2: Crear un nuevo proyecto | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, projects
- projects, creating
- message enrichment tutorial, projects
ms.assetid: 6e994845-53b8-4de8-a64f-32d36f7b5412
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4b296b01179b3ce52aef41dc246dbed2588c3e6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="step-2-create-a-new-project"></a><span data-ttu-id="b5911-102">Paso 2: Crear un nuevo proyecto</span><span class="sxs-lookup"><span data-stu-id="b5911-102">Step 2: Create a New Project</span></span>
<span data-ttu-id="b5911-103">En este paso, se compila una nueva solución mediante la [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] entorno.</span><span class="sxs-lookup"><span data-stu-id="b5911-103">In this step, you build a new solution by using the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] environment.</span></span> <span data-ttu-id="b5911-104">En primer lugar, cree un nuevo proyecto (BTAHL7V22Common) que contiene los tres esquemas comunes (para tipos de datos, segmentos y valores de tabla) que utilizan los esquemas de HL7 V2.2, incluido el esquema que se va a utilizar para el mensaje saliente de HL7.</span><span class="sxs-lookup"><span data-stu-id="b5911-104">First, you create a new project (BTAHL7V22Common) that contains the three common schemas (for data types, segments, and table values) that the HL7 V2.2 schemas use, including the schema that you will use for the outgoing HL7 message.</span></span> <span data-ttu-id="b5911-105">En segundo lugar, compile otro nuevo proyecto (BTAHL7V2XCommon) que contiene el esquema estándar común utilizado para los encabezados de mensajes HL7 (MSH_25_GLO_DEF).</span><span class="sxs-lookup"><span data-stu-id="b5911-105">Second, you build another new project (BTAHL7V2XCommon) that contains the common standard schema used for headers in HL7 messages (MSH_25_GLO_DEF).</span></span>  
  
### <a name="to-create-a-new-project"></a><span data-ttu-id="b5911-106">Para crear un nuevo proyecto</span><span class="sxs-lookup"><span data-stu-id="b5911-106">To create a new project</span></span>  
  
1.  <span data-ttu-id="b5911-107">Iniciar **Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="b5911-107">Start **Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="b5911-108">En el menú **Archivo** , seleccione **Nuevo**y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="b5911-108">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="b5911-109">En el cuadro de diálogo nuevo proyecto, expanda el **proyectos de BizTalk** carpeta y, a continuación, haga clic en el **BTAHL7Projects** carpeta.</span><span class="sxs-lookup"><span data-stu-id="b5911-109">In the New Project dialog box, expand the **BizTalk Projects** folder, and then click the **BTAHL7Projects** folder.</span></span>  
  
4.  <span data-ttu-id="b5911-110">En el **plantillas** panel, haga clic en **BTAHL7V22Common proyecto**.</span><span class="sxs-lookup"><span data-stu-id="b5911-110">In the **Templates** pane, click **BTAHL7V22Common Project**.</span></span>  
  
5.  <span data-ttu-id="b5911-111">En el **nombre** , escriba **BTAHL7V22Common** como el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b5911-111">In the **Name** field, type **BTAHL7V22Common** as the project name.</span></span>  
  
6.  <span data-ttu-id="b5911-112">En el **ubicación** , escriba  *\<unidad\>***: \Tutorial** como ruta de acceso y, a continuación, haga clic en **Aceptar** para abrir el nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="b5911-112">In the **Location** field, type *\<drive\>***:\Tutorial** as the path, and then click **OK** to open the new project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b5911-113">Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) agrega un nuevo proyecto en el Explorador de soluciones con los tres esquemas comunes:</span><span class="sxs-lookup"><span data-stu-id="b5911-113">BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) adds a new project to Solution Explorer with the three common schemas:</span></span>  
  
    -   <span data-ttu-id="b5911-114">datatypes_22.xsd</span><span class="sxs-lookup"><span data-stu-id="b5911-114">datatypes_22.xsd</span></span>  
  
    -   <span data-ttu-id="b5911-115">segments_22.xsd</span><span class="sxs-lookup"><span data-stu-id="b5911-115">segments_22.xsd</span></span>  
  
    -   <span data-ttu-id="b5911-116">tablevalues_22.xsd</span><span class="sxs-lookup"><span data-stu-id="b5911-116">tablevalues_22.xsd</span></span>  
  
     [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="b5911-117">crea la carpeta del proyecto y los archivos en el \< *unidad*\>: \Tutorial\BTAHL7V22Common carpeta.</span><span class="sxs-lookup"><span data-stu-id="b5911-117"> creates the project folder and files in the \<*drive*\>:\Tutorial\BTAHL7V22Common folder.</span></span>  
  
7.  <span data-ttu-id="b5911-118">En el menú **Archivo** , seleccione **Nuevo**y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="b5911-118">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
8.  <span data-ttu-id="b5911-119">En el cuadro de diálogo nuevo proyecto, expanda el **proyectos de BizTalk** carpeta y, a continuación, haga clic en el **BTAHL7Projects** carpeta.</span><span class="sxs-lookup"><span data-stu-id="b5911-119">In the New Project dialog box, expand the **BizTalk Projects** folder, and then click the **BTAHL7Projects** folder.</span></span>  
  
9. <span data-ttu-id="b5911-120">En el **plantillas** panel, haga clic en **proyecto BTAHL7V2XCommon**.</span><span class="sxs-lookup"><span data-stu-id="b5911-120">In the **Templates** pane, click **BTAHL7V2XCommon Project**.</span></span>  
  
10. <span data-ttu-id="b5911-121">En el **nombre** , escriba **BTAHL7V2XCommon** como el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b5911-121">In the **Name** field, type **BTAHL7V2XCommon** as the project name.</span></span>  
  
11. <span data-ttu-id="b5911-122">En el **ubicación** , escriba  *\<unidad\>***: \Tutorial** como la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="b5911-122">In the **Location** field, type *\<drive\>***:\Tutorial** as the path.</span></span>  
  
12. <span data-ttu-id="b5911-123">En el **solución** campo, seleccione **agregar a solución**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b5911-123">In the **Solution** field, select **Add to Solution**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="b5911-124">Agrega un nuevo proyecto en el Explorador de soluciones con los siguientes esquemas:</span><span class="sxs-lookup"><span data-stu-id="b5911-124"> adds a new project to Solution Explorer with the following schemas:</span></span>  
  
    -   <span data-ttu-id="b5911-125">ACK_24_GLO_DEF.xsd</span><span class="sxs-lookup"><span data-stu-id="b5911-125">ACK_24_GLO_DEF.xsd</span></span>  
  
    -   <span data-ttu-id="b5911-126">ACK_25_GLO_DEF.xsd</span><span class="sxs-lookup"><span data-stu-id="b5911-126">ACK_25_GLO_DEF.xsd</span></span>  
  
    -   <span data-ttu-id="b5911-127">MSH_25_GLO_DEF.xsd</span><span class="sxs-lookup"><span data-stu-id="b5911-127">MSH_25_GLO_DEF.xsd</span></span>  
  
     [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="b5911-128">crea la carpeta del proyecto y los archivos en el  **\<unidad\>: \Tutorial\BTAHL7V22Common\BTAHL72XCommon** carpeta.</span><span class="sxs-lookup"><span data-stu-id="b5911-128"> creates the project folder and files in the **\<drive\>:\Tutorial\BTAHL7V22Common\BTAHL72XCommon** folder.</span></span>  
  
 <span data-ttu-id="b5911-129">Continúe con [paso 3: asignar un nombre seguro al ensamblado](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="b5911-129">Proceed to [Step 3: Assign a Strong Name to the Assembly](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5911-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5911-130">See Also</span></span>  
 [<span data-ttu-id="b5911-131">Tutorial de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="b5911-131">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)