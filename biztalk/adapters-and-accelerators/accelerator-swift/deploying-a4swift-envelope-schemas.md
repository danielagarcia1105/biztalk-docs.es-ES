---
title: "Implementación de esquemas de sobres de A4SWIFT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, envelope schemas
- A4SWIFT, deploying envelope schemas
- envelope schemas
- schemas, envelope schemas
ms.assetid: 6440608c-d30d-4d82-827a-8a4b2738db85
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d47fb5f072be8969df61b0e384c700b7b0ddffb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-a4swift-envelope-schemas"></a><span data-ttu-id="29e58-102">Implementación de esquemas de sobres de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="29e58-102">Deploying A4SWIFT Envelope Schemas</span></span>
<span data-ttu-id="29e58-103">Debe incluir esquemas de sobres en proyectos de esquema siempre que se establezca una reparación de mensajes y nuevo envío.</span><span class="sxs-lookup"><span data-stu-id="29e58-103">You must include envelope schemas in schema projects whenever you set up Message Repair and New Submission.</span></span> <span data-ttu-id="29e58-104">Un esquema de sobre, por ejemplo, EnvelopeMT103.xsd, es necesario para escribir en el sitio de MRSR.</span><span class="sxs-lookup"><span data-stu-id="29e58-104">An envelope schema, such as EnvelopeMT103.xsd, is required to write to MRSR site.</span></span>  
  
 <span data-ttu-id="29e58-105">**Resumen**</span><span class="sxs-lookup"><span data-stu-id="29e58-105">**Summary**</span></span>  
  
 <span data-ttu-id="29e58-106">Agregar esquemas de sobres a su proyecto, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="29e58-106">Add envelope schemas to your project, as follows:</span></span>  
  
-   <span data-ttu-id="29e58-107">En Visual Studio, en el proyecto que contiene los esquemas de mensaje, agregue un esquema de sobre para cada esquema de mensaje.</span><span class="sxs-lookup"><span data-stu-id="29e58-107">In Visual Studio, to the project that contains your message schemas, add an envelope schema for each message schema.</span></span>  
  
-   <span data-ttu-id="29e58-108">Agregar una referencia a RuntimeSchemas.dll a cualquier proyecto que contiene uno o varios esquemas de sobres.</span><span class="sxs-lookup"><span data-stu-id="29e58-108">Add a reference to RuntimeSchemas.dll to any project that contains one or more envelope schemas.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="29e58-109">Agregar una referencia a RuntimeSchemas.dll es necesario para un [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] sólo cuando haya agregado un esquema de sobre de reparación de mensajes y nuevo envío al proyecto del proyecto.</span><span class="sxs-lookup"><span data-stu-id="29e58-109">Adding a reference to RuntimeSchemas.dll is required for an [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] project only when you have added an envelope schema for Message Repair and New Submission to the project.</span></span>  
  
-   <span data-ttu-id="29e58-110">Agregue el esquema de sobre mensaje sin analizar (EnvelopeUnparsedMessage.xsd) al proyecto.</span><span class="sxs-lookup"><span data-stu-id="29e58-110">Add the Unparsed Message envelope schema (EnvelopeUnparsedMessage.xsd) to the project.</span></span>  
  
### <a name="to-add-a-swift-envelope-schema"></a><span data-ttu-id="29e58-111">Para agregar un esquema de sobre SWIFT</span><span class="sxs-lookup"><span data-stu-id="29e58-111">To add a SWIFT envelope schema</span></span>  
  
1.  <span data-ttu-id="29e58-112">En el Explorador de soluciones de Visual Studio, abra el proyecto de esquemas.</span><span class="sxs-lookup"><span data-stu-id="29e58-112">In Solution Explorer of Visual Studio, open your schemas project.</span></span>  
  
2.  <span data-ttu-id="29e58-113">Haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="29e58-113">Right-click **References**, and then click **Add Reference**.</span></span>  
  
3.  <span data-ttu-id="29e58-114">En el cuadro de diálogo Agregar referencia, haga clic en el **examinar** etiqueta.</span><span class="sxs-lookup"><span data-stu-id="29e58-114">In the Add Reference dialog box, click the **Browse** tag.</span></span>  
  
4.  <span data-ttu-id="29e58-115">En el cuadro de diálogo Seleccionar componente, abra el **buscar en** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="29e58-115">In the Select Component dialog box, open the **Look in** drop-down list.</span></span> <span data-ttu-id="29e58-116">Mover a   ***\<unidad >*: \Program Acelerador de BizTalk para SWIFT \<versión > mensaje Pack\Assemblies**.</span><span class="sxs-lookup"><span data-stu-id="29e58-116">Move to ***\<drive>*:\Program Files\Microsoft BizTalk Accelerator for SWIFT \<version> Message Pack\Assemblies**.</span></span> <span data-ttu-id="29e58-117">Seleccione **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll** en la lista de ensamblados y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="29e58-117">Select **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll** from the list of assemblies, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="29e58-118">En el **Agregar referencia** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="29e58-118">In the **Add Reference** dialog box, click **OK**.</span></span>  
  
6.  <span data-ttu-id="29e58-119">Haga clic en el proyecto, seleccione **agregar**y, a continuación, haga clic en **Agregar elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="29e58-119">Right-click your project, point to **Add**, and then click **Add Existing Item**.</span></span>  
  
7.  <span data-ttu-id="29e58-120">En Agregar elemento existente cuadro de diálogo, en la **buscar en** cuadro de lista desplegable, desplácese a  **\<unidad >: \Program Files\ Acelerador de Microsoft BizTalk para SWIFT \<versión > Pack\SWIFT de mensajes de mensajes \A4SWIFT-srg\<versión > \Categoryn\MTxxx**.</span><span class="sxs-lookup"><span data-stu-id="29e58-120">In the Add Existing Item dialog box, in the **Look in** drop-down box, move to **\<drive>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version>\Categoryn\MTxxx**.</span></span> <span data-ttu-id="29e58-121">Seleccione el esquema de sobres, por ejemplo, **EnvelopeMT103.xsd**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="29e58-121">Select the envelope schema, for example, **EnvelopeMT103.xsd**, and then click **Add**.</span></span>  
  
     <span data-ttu-id="29e58-122">En Agregar elemento existente cuadro de diálogo, en la **buscar en** cuadro de lista desplegable, desplácese a.</span><span class="sxs-lookup"><span data-stu-id="29e58-122">In the Add Existing Item dialog box, in the **Look in** drop-down box, move to.</span></span> <span data-ttu-id="29e58-123">Seleccione el esquema de sobres, por ejemplo, EnvelopeMT103.xsd y, a continuación, haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="29e58-123">Select the envelope schema, for example, EnvelopeMT103.xsd, and then click Add.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="29e58-124">A4SWIFT agrega el esquema de sobre para el proyecto, como se muestra en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="29e58-124">A4SWIFT adds the envelope schema for your project, as shown in Solution Explorer.</span></span>  
  
8.  <span data-ttu-id="29e58-125">En el Explorador de soluciones, haga clic en el proyecto, seleccione **agregar**y, a continuación, haga clic en **Agregar elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="29e58-125">In Solution Explorer, right-click your project, point to **Add**, and then click **Add Existing Item**.</span></span>  
  
9. <span data-ttu-id="29e58-126">Si utiliza la característica de reparación de mensajes y nuevo envío, en el cuadro de diálogo Agregar elemento existente, en la **buscar en** cuadro de lista desplegable, desplácese a  **\<* unidad*>: \ Acelerador de Microsoft BizTalk para SWIFT \<versión > mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión > \Unparsed mensaje **.</span><span class="sxs-lookup"><span data-stu-id="29e58-126">If using the Message Repair and New Submission feature, in the Add Existing Item dialog box, in the **Look in** drop-down box, move to **\<*drive*>:\Microsoft BizTalk Accelerator for SWIFT \<version> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version>\Unparsed Message**.</span></span> <span data-ttu-id="29e58-127">Seleccione **EnvelopeUnparsedMessage.xsd**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="29e58-127">Select **EnvelopeUnparsedMessage.xsd**, and then click **Add**.</span></span>  
  
10. <span data-ttu-id="29e58-128">En el Explorador de soluciones, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **Versión de compilación**.</span><span class="sxs-lookup"><span data-stu-id="29e58-128">In Solution Explorer, right-click the project name, and then click **Build**.</span></span>  
  
11. <span data-ttu-id="29e58-129">En el Explorador de soluciones, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="29e58-129">In Solution Explorer, right-click the project name, and then click **Deploy**.</span></span>