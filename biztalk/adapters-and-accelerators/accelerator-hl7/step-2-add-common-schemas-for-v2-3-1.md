---
title: 'Paso 2: Adición de esquemas comunes para v2.3.1 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: da98fe6c-4776-4cb8-8454-af3128dea4ab
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36b07419b50d02d1f810dffbd7417533e844a3ea
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994165"
---
# <a name="step-2-add-common-schemas-for-v231"></a><span data-ttu-id="ba41d-102">Paso 2: Adición de esquemas comunes para v2.3.1</span><span class="sxs-lookup"><span data-stu-id="ba41d-102">Step 2: Add Common Schemas for v2.3.1</span></span>
<span data-ttu-id="ba41d-103">En este paso, creará un nuevo proyecto basado en la plantilla de proyecto BTAHL7231Common.</span><span class="sxs-lookup"><span data-stu-id="ba41d-103">In this step, you create a new project based on the BTAHL7231Common Project template.</span></span> <span data-ttu-id="ba41d-104">Esta plantilla contiene los tres esquemas comunes (para los tipos de datos, segmentos y valores de tabla) que Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) se utiliza para validar las instancias de mensaje v2.3.1.</span><span class="sxs-lookup"><span data-stu-id="ba41d-104">This template contains the three common schemas (for data types, segments, and table values) that Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses to validate v2.3.1 message instances.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="ba41d-105"> utiliza estos esquemas comunes junto con los esquemas HL7 v2.3.1, incluido el esquema que se va a utilizar para los mensajes individuales del lote entrante (ADT ^ A03).</span><span class="sxs-lookup"><span data-stu-id="ba41d-105"> uses these common schemas in conjunction with the HL7 v2.3.1 schemas, including the schema that you will use for the individual messages in the incoming batch (ADT^A03).</span></span>  
  
 <span data-ttu-id="ba41d-106">Al final del paso, asigne una clave segura para el ensamblado e implemente.</span><span class="sxs-lookup"><span data-stu-id="ba41d-106">At the end of the step, you assign a strong key to the assembly and deploy.</span></span> <span data-ttu-id="ba41d-107">No es necesario que crear una segunda clave segura; Puede usar la clave segura que creó en [paso 1: agregar esquemas de encabezado y confirmación](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="ba41d-107">You do not have to create a second strong key; you can use the strong key that you created in [Step 1: Add Header and Acknowledgment Schemas](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md).</span></span>  
  
### <a name="to-add-v231-common-schemas-and-deploy-the-assembly"></a><span data-ttu-id="ba41d-108">Para agregar los esquemas comunes v2.3.1 e implementar el ensamblado</span><span class="sxs-lookup"><span data-stu-id="ba41d-108">To add v2.3.1 common schemas and deploy the assembly</span></span>  
  
1. <span data-ttu-id="ba41d-109">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="ba41d-109">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2. <span data-ttu-id="ba41d-110">En el cuadro de diálogo nuevo proyecto, en el **tipos de proyecto** sección, expanda **proyectos de BizTalk**y, a continuación, seleccione **BTAHL7Projects**.</span><span class="sxs-lookup"><span data-stu-id="ba41d-110">In the New Project dialog box, in the **Project Types** section, expand **BizTalk Projects**, and then select **BTAHL7Projects**.</span></span>  
  
3. <span data-ttu-id="ba41d-111">En el **plantillas** sección, seleccione **proyecto BTAHL7V231Common**.</span><span class="sxs-lookup"><span data-stu-id="ba41d-111">In the **Templates** section, select **BTAHL7V231Common Project**.</span></span>  
  
4. <span data-ttu-id="ba41d-112">En el **nombre** , escriba **proyecto BTAHL7V231Common** como el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ba41d-112">In the **Name** box, enter **BTAHL7V231Common Project** as the project name.</span></span>  
  
5. <span data-ttu-id="ba41d-113">En el **solución** cuadro, seleccione **agregar a solución**.</span><span class="sxs-lookup"><span data-stu-id="ba41d-113">In the **Solution** box, select **Add to Solution**.</span></span>  
  
6. <span data-ttu-id="ba41d-114">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ba41d-114">Click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ba41d-115">En el Explorador de soluciones, los tres esquemas (datatypes_231.xsd, segments_231.xsd y tablevalues_231.xsd) se incluyen en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ba41d-115">In Solution Explorer, three schemas (datatypes_231.xsd, segments_231.xsd, and tablevalues_231.xsd) are included in the project.</span></span>  
  
7. <span data-ttu-id="ba41d-116">En el Explorador de soluciones, haga clic en **proyecto BTAHL7V231Common**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ba41d-116">In Solution Explorer, right-click **BTAHL7V231Common Project**, and then click **Properties**.</span></span>  
  
8. <span data-ttu-id="ba41d-117">En el cuadro de diálogo páginas de propiedades BTAHL7V231Common, haga clic en **firma**.</span><span class="sxs-lookup"><span data-stu-id="ba41d-117">On the BTAHL7V231Common Property Pages dialog box, click **Signing**.</span></span>  
  
9. <span data-ttu-id="ba41d-118">Comprobar **firmar el ensamblado** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="ba41d-118">Check **Sign the assembly** check box.</span></span>  
  
10. <span data-ttu-id="ba41d-119">En Elija un archivo de clave de nombre seguro lista desplegable de la lista, seleccione.</span><span class="sxs-lookup"><span data-stu-id="ba41d-119">In Choose a strong name key file drop down list select.</span></span>  
  
11. <span data-ttu-id="ba41d-120">Vaya a **: Tutorial \Batching**, seleccione **key.snk**y, a continuación, haga clic en **abierto**.</span><span class="sxs-lookup"><span data-stu-id="ba41d-120">Browse to **:\Batching Tutorial**, select **key.snk**, and then click **Open**.</span></span>  
  
12. <span data-ttu-id="ba41d-121">Haga clic en **BTAHL7V231Common**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="ba41d-121">Right-click **BTAHL7V231Common**, and then click **Deploy**.</span></span> <span data-ttu-id="ba41d-122">Asegúrese de que aparece un mensaje de éxito en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="ba41d-122">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ba41d-123">Si no aparece el mensaje correcto, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de los esquemas.</span><span class="sxs-lookup"><span data-stu-id="ba41d-123">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your schemas.</span></span>  
  
    <span data-ttu-id="ba41d-124">Continúe con [paso 3: agregar un esquema del desencadenador de eventos (mensaje)](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md).</span><span class="sxs-lookup"><span data-stu-id="ba41d-124">Proceed to [Step 3: Add a Trigger Event (Message) Schema](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md).</span></span>