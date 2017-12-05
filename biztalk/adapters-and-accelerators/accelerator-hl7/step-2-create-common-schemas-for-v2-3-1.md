---
title: 'Paso 2: Crear los esquemas comunes para V2.3.1 | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, common schemas
- common schemas
ms.assetid: db1a2206-559f-475a-803d-55522cce007e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5f8ed36b4a1ae8553e8df488e8fd5a606c0eabd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-create-common-schemas-for-v231"></a><span data-ttu-id="fad5d-102">Paso 2: Crear los esquemas comunes para V2.3.1</span><span class="sxs-lookup"><span data-stu-id="fad5d-102">Step 2: Create Common Schemas for V2.3.1</span></span>
<span data-ttu-id="fad5d-103">Los esquemas V2.3.1 son esquemas normalmente se hace referencia, que se utilizan para validar la instancia de mensaje.</span><span class="sxs-lookup"><span data-stu-id="fad5d-103">The V2.3.1 schemas are commonly referenced schemas, which you use to validate the message instance.</span></span>  
  
### <a name="to-create-a-common-schema-for-v231"></a><span data-ttu-id="fad5d-104">Para crear un esquema común para V2.3.1</span><span class="sxs-lookup"><span data-stu-id="fad5d-104">To create a common schema for V2.3.1</span></span>  
  
1.  <span data-ttu-id="fad5d-105">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="fad5d-105">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="fad5d-106">En el cuadro de diálogo nuevo proyecto, en la **tipos de proyecto** sección, expanda **proyectos de BizTalk**y, a continuación, seleccione **BTAHL7Projects**.</span><span class="sxs-lookup"><span data-stu-id="fad5d-106">In the New Project dialog box, in the **Project Types** section, expand **BizTalk Projects**, and then select **BTAHL7Projects**.</span></span>  
  
3.  <span data-ttu-id="fad5d-107">En la sección de plantillas, seleccione **proyecto BTAHL7V231Common**.</span><span class="sxs-lookup"><span data-stu-id="fad5d-107">In the Templates section, select **BTAHL7V231Common Project**.</span></span>  
  
4.  <span data-ttu-id="fad5d-108">En el **nombre** cuadro, escriba **proyecto BTAHL7V231Common** como el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="fad5d-108">In the **Name** box, enter **BTAHL7V231Common Project** as the project name.</span></span>  
  
5.  <span data-ttu-id="fad5d-109">En el **solución** cuadro, seleccione **agregar a solución**.</span><span class="sxs-lookup"><span data-stu-id="fad5d-109">In the **Solution** box, select **Add to Solution**.</span></span>  
  
6.  <span data-ttu-id="fad5d-110">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fad5d-110">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fad5d-111">En el Explorador de soluciones, se incluyen tres esquemas (datatypes_231.xsd, segments_231.xsd y tablevalues_231.xsd) en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="fad5d-111">In Solution Explorer, three schemas (datatypes_231.xsd, segments_231.xsd, and tablevalues_231.xsd) are included in the project.</span></span>  
  
7.  <span data-ttu-id="fad5d-112">En el Explorador de soluciones, haga clic en **proyecto BTAHL7V231Common**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fad5d-112">In Solution Explorer, right-click **BTAHL7V231Common Project**, and then click **Properties**.</span></span>  
  
8.  <span data-ttu-id="fad5d-113">En la página de propiedades BTAHL7V231Common, haga clic en **firma**.</span><span class="sxs-lookup"><span data-stu-id="fad5d-113">On the BTAHL7V231Common Property Page, click **Signing**.</span></span>  
  
9. <span data-ttu-id="fad5d-114">Seleccione el **firmar el ensamblado** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="fad5d-114">Select the **Sign the assembly** check box.</span></span>  
  
10. <span data-ttu-id="fad5d-115">En **elegir un archivo de clave de nombre seguro**, seleccione  **\<Examinar... \>** .</span><span class="sxs-lookup"><span data-stu-id="fad5d-115">In **Choose a strong name key file**, select **\<Browse…\>** .</span></span>  
  
11. <span data-ttu-id="fad5d-116">Vaya a \<unidad\>: Tutorial, seleccione \Batching **key.snk**y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="fad5d-116">Browse to \<drive\>:\Batching Tutorial, select **key.snk**, and then click **Open**.</span></span>  
  
12. <span data-ttu-id="fad5d-117">En el Explorador de soluciones, haga clic en **proyecto BTAHL7V231Common**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="fad5d-117">In Solution Explorer, right-click **BTAHL7V231Common Project**, and then click **Deploy**.</span></span> <span data-ttu-id="fad5d-118">Asegúrese de que aparece un mensaje de confirmación en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="fad5d-118">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fad5d-119">Si no aparece el mensaje correcto, utilice [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de los esquemas.</span><span class="sxs-lookup"><span data-stu-id="fad5d-119">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your schemas.</span></span>  
  
 <span data-ttu-id="fad5d-120">Continúe con [paso 3: agregar un esquema de eventos (mensaje) desencadenador](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md).</span><span class="sxs-lookup"><span data-stu-id="fad5d-120">Proceed to [Step 3: Add a Trigger Event (Message) Schema](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md).</span></span>