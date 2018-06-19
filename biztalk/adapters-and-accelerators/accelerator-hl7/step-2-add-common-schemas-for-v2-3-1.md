---
title: 'Paso 2: Agregar los esquemas comunes para v2.3.1 | Documentos de Microsoft'
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
ms.openlocfilehash: ba84c9f45c477aefe7615eca906c40014b06bd04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206516"
---
# <a name="step-2-add-common-schemas-for-v231"></a><span data-ttu-id="78322-102">Paso 2: Agregar los esquemas comunes para v2.3.1</span><span class="sxs-lookup"><span data-stu-id="78322-102">Step 2: Add Common Schemas for v2.3.1</span></span>
<span data-ttu-id="78322-103">En este paso, creará un proyecto nuevo basado en la plantilla de proyecto de BTAHL7231Common.</span><span class="sxs-lookup"><span data-stu-id="78322-103">In this step, you create a new project based on the BTAHL7231Common Project template.</span></span> <span data-ttu-id="78322-104">Esta plantilla contiene los tres esquemas comunes (para tipos de datos, segmentos y valores de tabla) que [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) se utiliza para validar las instancias de mensaje v2.3.1.</span><span class="sxs-lookup"><span data-stu-id="78322-104">This template contains the three common schemas (for data types, segments, and table values) that [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses to validate v2.3.1 message instances.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="78322-105">estos esquemas comunes se utiliza junto con los esquemas de v2.3.1 HL7, incluido el esquema que se va a utilizar para los mensajes individuales del lote entrante (ADT ^ A03).</span><span class="sxs-lookup"><span data-stu-id="78322-105"> uses these common schemas in conjunction with the HL7 v2.3.1 schemas, including the schema that you will use for the individual messages in the incoming batch (ADT^A03).</span></span>  
  
 <span data-ttu-id="78322-106">Al final del paso que asigne una clave segura para el ensamblado y se implemente.</span><span class="sxs-lookup"><span data-stu-id="78322-106">At the end of the step, you assign a strong key to the assembly and deploy.</span></span> <span data-ttu-id="78322-107">No tienes que volver a crear una segunda clave segura; Puede usar la clave segura que creó en [paso 1: agregar encabezado y esquemas de confirmación](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="78322-107">You do not have to create a second strong key; you can use the strong key that you created in [Step 1: Add Header and Acknowledgment Schemas](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md).</span></span>  
  
### <a name="to-add-v231-common-schemas-and-deploy-the-assembly"></a><span data-ttu-id="78322-108">Para agregar los esquemas comunes de v2.3.1 e implementar el ensamblado</span><span class="sxs-lookup"><span data-stu-id="78322-108">To add v2.3.1 common schemas and deploy the assembly</span></span>  
  
1.  <span data-ttu-id="78322-109">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="78322-109">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="78322-110">En el cuadro de diálogo nuevo proyecto, en la **tipos de proyecto** sección, expanda **proyectos de BizTalk**y, a continuación, seleccione **BTAHL7Projects**.</span><span class="sxs-lookup"><span data-stu-id="78322-110">In the New Project dialog box, in the **Project Types** section, expand **BizTalk Projects**, and then select **BTAHL7Projects**.</span></span>  
  
3.  <span data-ttu-id="78322-111">En el **plantillas** sección, seleccione **proyecto BTAHL7V231Common**.</span><span class="sxs-lookup"><span data-stu-id="78322-111">In the **Templates** section, select **BTAHL7V231Common Project**.</span></span>  
  
4.  <span data-ttu-id="78322-112">En el **nombre** cuadro, escriba **proyecto BTAHL7V231Common** como el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="78322-112">In the **Name** box, enter **BTAHL7V231Common Project** as the project name.</span></span>  
  
5.  <span data-ttu-id="78322-113">En el **solución** cuadro, seleccione **agregar a solución**.</span><span class="sxs-lookup"><span data-stu-id="78322-113">In the **Solution** box, select **Add to Solution**.</span></span>  
  
6.  <span data-ttu-id="78322-114">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="78322-114">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="78322-115">En el Explorador de soluciones, se incluyen tres esquemas (datatypes_231.xsd, segments_231.xsd y tablevalues_231.xsd) en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="78322-115">In Solution Explorer, three schemas (datatypes_231.xsd, segments_231.xsd, and tablevalues_231.xsd) are included in the project.</span></span>  
  
7.  <span data-ttu-id="78322-116">En el Explorador de soluciones, haga clic en **proyecto BTAHL7V231Common**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="78322-116">In Solution Explorer, right-click **BTAHL7V231Common Project**, and then click **Properties**.</span></span>  
  
8.  <span data-ttu-id="78322-117">En el cuadro de diálogo páginas de propiedades de BTAHL7V231Common, haga clic en **firma**.</span><span class="sxs-lookup"><span data-stu-id="78322-117">On the BTAHL7V231Common Property Pages dialog box, click **Signing**.</span></span>  
  
9. <span data-ttu-id="78322-118">Comprobar **firmar el ensamblado** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="78322-118">Check **Sign the assembly** check box.</span></span>  
  
10. <span data-ttu-id="78322-119">En Elija un archivo de clave de nombre seguro lista desplegable lista, seleccione.</span><span class="sxs-lookup"><span data-stu-id="78322-119">In Choose a strong name key file drop down list select.</span></span>  
  
11. <span data-ttu-id="78322-120">Vaya a **: \Batching Tutorial**, seleccione **key.snk**y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="78322-120">Browse to **:\Batching Tutorial**, select **key.snk**, and then click **Open**.</span></span>  
  
12. <span data-ttu-id="78322-121">Haga clic en **BTAHL7V231Common**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="78322-121">Right-click **BTAHL7V231Common**, and then click **Deploy**.</span></span> <span data-ttu-id="78322-122">Asegúrese de que aparece un mensaje de confirmación en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="78322-122">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="78322-123">Si no aparece el mensaje correcto, utilice [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de los esquemas.</span><span class="sxs-lookup"><span data-stu-id="78322-123">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your schemas.</span></span>  
  
 <span data-ttu-id="78322-124">Continúe con [paso 3: agregar un esquema de eventos (mensaje) desencadenador](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md).</span><span class="sxs-lookup"><span data-stu-id="78322-124">Proceed to [Step 3: Add a Trigger Event (Message) Schema](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md).</span></span>