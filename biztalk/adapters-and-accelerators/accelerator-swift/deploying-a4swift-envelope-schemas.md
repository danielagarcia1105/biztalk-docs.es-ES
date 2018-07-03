---
title: Implementar esquemas de sobres de A4SWIFT | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, envelope schemas
- A4SWIFT, deploying envelope schemas
- envelope schemas
- schemas, envelope schemas
ms.assetid: 6440608c-d30d-4d82-827a-8a4b2738db85
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae07b6b957f608e89c3ae65802d6627440201a65
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004149"
---
# <a name="deploying-a4swift-envelope-schemas"></a><span data-ttu-id="ab6c7-102">Implementar esquemas de sobres de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="ab6c7-102">Deploying A4SWIFT Envelope Schemas</span></span>
<span data-ttu-id="ab6c7-103">Debe incluir los esquemas de sobres en los proyectos de esquema siempre que configuró la reparación de mensajes y nuevo envío.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-103">You must include envelope schemas in schema projects whenever you set up Message Repair and New Submission.</span></span> <span data-ttu-id="ab6c7-104">Un esquema de sobre, como EnvelopeMT103.xsd, es necesario para escribir en el sitio MRSR.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-104">An envelope schema, such as EnvelopeMT103.xsd, is required to write to MRSR site.</span></span>  
  
 <span data-ttu-id="ab6c7-105">**Resumen**</span><span class="sxs-lookup"><span data-stu-id="ab6c7-105">**Summary**</span></span>  
  
 <span data-ttu-id="ab6c7-106">Agregue los esquemas de sobres a su proyecto, como sigue:</span><span class="sxs-lookup"><span data-stu-id="ab6c7-106">Add envelope schemas to your project, as follows:</span></span>  
  
- <span data-ttu-id="ab6c7-107">En Visual Studio, en el proyecto que contiene los esquemas de mensaje, agregue un esquema de sobre para cada esquema de mensaje.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-107">In Visual Studio, to the project that contains your message schemas, add an envelope schema for each message schema.</span></span>  
  
- <span data-ttu-id="ab6c7-108">Agregar una referencia a RuntimeSchemas.dll a cualquier proyecto que contiene uno o varios esquemas de sobres.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-108">Add a reference to RuntimeSchemas.dll to any project that contains one or more envelope schemas.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="ab6c7-109">Para agregar una referencia a RuntimeSchemas.dll requiere un [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] sólo cuando haya agregado un esquema de sobre de reparación de mensajes y nuevo envío al proyecto del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-109">Adding a reference to RuntimeSchemas.dll is required for an [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] project only when you have added an envelope schema for Message Repair and New Submission to the project.</span></span>  
  
- <span data-ttu-id="ab6c7-110">Agregue el esquema de sobres de mensaje sin analizar (EnvelopeUnparsedMessage.xsd) al proyecto.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-110">Add the Unparsed Message envelope schema (EnvelopeUnparsedMessage.xsd) to the project.</span></span>  
  
### <a name="to-add-a-swift-envelope-schema"></a><span data-ttu-id="ab6c7-111">Para agregar un esquema de sobres SWIFT</span><span class="sxs-lookup"><span data-stu-id="ab6c7-111">To add a SWIFT envelope schema</span></span>  
  
1.  <span data-ttu-id="ab6c7-112">En el Explorador de soluciones de Visual Studio, abra el proyecto de esquemas.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-112">In Solution Explorer of Visual Studio, open your schemas project.</span></span>  
  
2.  <span data-ttu-id="ab6c7-113">Haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-113">Right-click **References**, and then click **Add Reference**.</span></span>  
  
3.  <span data-ttu-id="ab6c7-114">En el cuadro de diálogo Agregar referencia, haga clic en el **examinar** etiqueta.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-114">In the Add Reference dialog box, click the **Browse** tag.</span></span>  
  
4.  <span data-ttu-id="ab6c7-115">En el cuadro de diálogo Seleccionar componente, abra el **buscar en** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-115">In the Select Component dialog box, open the **Look in** drop-down list.</span></span> <span data-ttu-id="ab6c7-116">Mover a ***\<unidad\>*:\Program de programa\Microsoft BizTalk Accelerator para SWIFT \<versión\> Pack\Assemblies mensaje**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-116">Move to ***\<drive\>*:\Program Files\Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\Assemblies**.</span></span> <span data-ttu-id="ab6c7-117">Seleccione **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll** en la lista de ensamblados y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-117">Select **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll** from the list of assemblies, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="ab6c7-118">En el **Agregar referencia** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-118">In the **Add Reference** dialog box, click **OK**.</span></span>  
  
6.  <span data-ttu-id="ab6c7-119">Haga clic en el proyecto, elija **agregar**y, a continuación, haga clic en **Agregar elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-119">Right-click your project, point to **Add**, and then click **Add Existing Item**.</span></span>  
  
7.  <span data-ttu-id="ab6c7-120">En el Agregar elemento existente cuadro de diálogo, en el **buscar en** cuadro desplegable, desplácese a  **\<unidad\>: Acelerador de Microsoft BizTalk para SWIFT \Program Files\ \<versión\>Mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Categoryn\MTxxx**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-120">In the Add Existing Item dialog box, in the **Look in** drop-down box, move to **\<drive\>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Categoryn\MTxxx**.</span></span> <span data-ttu-id="ab6c7-121">Seleccione el esquema de sobres, por ejemplo, **EnvelopeMT103.xsd**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-121">Select the envelope schema, for example, **EnvelopeMT103.xsd**, and then click **Add**.</span></span>  
  
     <span data-ttu-id="ab6c7-122">En el Agregar elemento existente cuadro de diálogo, en el **buscar en** cuadro desplegable, desplácese a.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-122">In the Add Existing Item dialog box, in the **Look in** drop-down box, move to.</span></span> <span data-ttu-id="ab6c7-123">Seleccione el esquema de sobres, por ejemplo, EnvelopeMT103.xsd y, a continuación, haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-123">Select the envelope schema, for example, EnvelopeMT103.xsd, and then click Add.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ab6c7-124">A4SWIFT agrega el esquema de sobre para el proyecto, como se muestra en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-124">A4SWIFT adds the envelope schema for your project, as shown in Solution Explorer.</span></span>  
  
8.  <span data-ttu-id="ab6c7-125">En el Explorador de soluciones, haga clic en el proyecto, seleccione **agregar**y, a continuación, haga clic en **Agregar elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-125">In Solution Explorer, right-click your project, point to **Add**, and then click **Add Existing Item**.</span></span>  
  
9. <span data-ttu-id="ab6c7-126">Si utiliza la característica de reparación de mensajes y nuevo envío, en el cuadro de diálogo Agregar elemento existente, en el **buscar en** cuadro desplegable, desplácese a  **\< *unidad*\>: \ Acelerador de Microsoft BizTalk para SWIFT \<versión\> mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Unparsed mensaje**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-126">If using the Message Repair and New Submission feature, in the Add Existing Item dialog box, in the **Look in** drop-down box, move to **\<*drive*\>:\Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Unparsed Message**.</span></span> <span data-ttu-id="ab6c7-127">Seleccione **EnvelopeUnparsedMessage.xsd**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-127">Select **EnvelopeUnparsedMessage.xsd**, and then click **Add**.</span></span>  
  
10. <span data-ttu-id="ab6c7-128">En el Explorador de soluciones, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **Versión de compilación**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-128">In Solution Explorer, right-click the project name, and then click **Build**.</span></span>  
  
11. <span data-ttu-id="ab6c7-129">En el Explorador de soluciones, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-129">In Solution Explorer, right-click the project name, and then click **Deploy**.</span></span>