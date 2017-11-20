---
title: "Canalización de envío de crear el FRR | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FRR, creating send pipelines
- creating, send pipelines
- send pipelines, creating
ms.assetid: c6cd2047-ea53-425f-80cc-b02a1deb5292
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87733b6b3a93d2543d26cd6d11b366b84218d207
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-the-frr-send-pipeline"></a><span data-ttu-id="fe8ce-102">Crear la canalización de envío FRR</span><span class="sxs-lookup"><span data-stu-id="fe8ce-102">Creating the FRR Send Pipeline</span></span>
<span data-ttu-id="fe8ce-103">Para realizar la conciliación de respuesta de FIN, debe crear una canalización de envío que contiene el componente de canalización SWIFTAsmFrrMQSeriesHelper, además el ensamblador SWIFT.</span><span class="sxs-lookup"><span data-stu-id="fe8ce-103">To perform FIN Response Reconciliation, you need to create a send pipeline that contains the SWIFTAsmFrrMQSeriesHelper pipeline component, in addition to the SWIFT assembler.</span></span>  
  
 <span data-ttu-id="fe8ce-104">**Resumen**</span><span class="sxs-lookup"><span data-stu-id="fe8ce-104">**Summary**</span></span>  
  
 <span data-ttu-id="fe8ce-105">Crear una canalización de envío con las siguientes fases:</span><span class="sxs-lookup"><span data-stu-id="fe8ce-105">Create a send pipeline with the following stages:</span></span>  
  
|<span data-ttu-id="fe8ce-106">Fase</span><span class="sxs-lookup"><span data-stu-id="fe8ce-106">Stage</span></span>|<span data-ttu-id="fe8ce-107">Componente</span><span class="sxs-lookup"><span data-stu-id="fe8ce-107">Component</span></span>|  
|-----------|---------------|  
|<span data-ttu-id="fe8ce-108">Fase de ensamblado</span><span class="sxs-lookup"><span data-stu-id="fe8ce-108">Assemble stage</span></span>|<span data-ttu-id="fe8ce-109">Ensamblador SWIFT</span><span class="sxs-lookup"><span data-stu-id="fe8ce-109">SWIFT assembler</span></span>|  
|<span data-ttu-id="fe8ce-110">Fase de codificación</span><span class="sxs-lookup"><span data-stu-id="fe8ce-110">Encode stage</span></span>|<span data-ttu-id="fe8ce-111">Componente de MQSeries envío Frr SWIFT</span><span class="sxs-lookup"><span data-stu-id="fe8ce-111">SWIFT Frr MQSeries Send Component</span></span>|  
  
### <a name="to-create-a-custom-send-pipeline-for-frr"></a><span data-ttu-id="fe8ce-112">Para crear una canalización de envío personalizada para FRR</span><span class="sxs-lookup"><span data-stu-id="fe8ce-112">To create a custom send pipeline for FRR</span></span>  
  
1.  <span data-ttu-id="fe8ce-113">En el Explorador de soluciones de Visual Studio, haga clic en el proyecto de canalización, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="fe8ce-113">In Solution Explorer of Visual Studio, right-click your pipeline project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="fe8ce-114">En el cuadro de diálogo Agregar nuevo elemento, seleccione **canalización de envío** desde el panel de plantillas.</span><span class="sxs-lookup"><span data-stu-id="fe8ce-114">In the Add New Item dialog box, select **Send Pipeline** from the Templates pane.</span></span>  
  
3.  <span data-ttu-id="fe8ce-115">En el **nombre** , escriba un nombre para la canalización de recepción, como **FRRSendPipeline.btp**.</span><span class="sxs-lookup"><span data-stu-id="fe8ce-115">In the **Name** box, type a name for your receive pipeline, such as **FRRSendPipeline.btp**.</span></span> <span data-ttu-id="fe8ce-116">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="fe8ce-116">Click **Add**.</span></span>  
  
4.  <span data-ttu-id="fe8ce-117">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **vista** y, a continuación, **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="fe8ce-117">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **View** and then **Toolbox**.</span></span>  
  
5.  <span data-ttu-id="fe8ce-118">En el cuadro de herramientas de componentes de canalización de BizTalk, arrastre **SWIFT ensamblador** a la **Coloque aquí los** cuadro siguiente la **ensamblar** almacenar provisionalmente la forma en **canalizaciones de BizTalk Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="fe8ce-118">From the BizTalk Pipeline Components Toolbox, drag **SWIFT Assembler** to the **Drop Here** box below the **Assemble** stage shape in **BizTalk Pipeline Designer**.</span></span>  
  
6.  <span data-ttu-id="fe8ce-119">En el cuadro de herramientas de componentes de canalización de BizTalk, arrastre **SWIFT Frr MQSeries enviar componente** a la **Coloque aquí los** cuadro siguiente la **Encode** almacenar provisionalmente la forma en  **Diseñador de canalizaciones de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="fe8ce-119">From the BizTalk Pipeline Components Toolbox, drag **SWIFT Frr MQSeries Send Component** to the **Drop Here** box below the **Encode** stage shape in **BizTalk Pipeline Designer**.</span></span>  
  
7.  <span data-ttu-id="fe8ce-120">En el Explorador de BizTalk, haga clic en el proyecto de canalización, haga clic en **anular la implementación**y, a continuación, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="fe8ce-120">In BizTalk Explorer, right-click your pipeline project, click **Undeploy**, and then click **Yes**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fe8ce-121">Después de anular la implementación y, a continuación, volver a implementar el proyecto de canalización, debe restablecer los puertos de envío o ubicaciones de recepción que utilice canalizaciones en el proyecto implementado previamente.</span><span class="sxs-lookup"><span data-stu-id="fe8ce-121">After undeploying and then redeploying your pipeline project, you must reset any send ports or receive locations that use pipelines in the previously deployed project.</span></span>  
  
8.  <span data-ttu-id="fe8ce-122">En el Explorador de soluciones, haga clic en el proyecto de canalización y, a continuación, haga clic en **generar**.</span><span class="sxs-lookup"><span data-stu-id="fe8ce-122">In Solution Explorer, right-click your pipeline project, and then click **Build**.</span></span>  
  
9. <span data-ttu-id="fe8ce-123">Después de la compilación finalice correctamente, haga clic en el proyecto de canalización y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="fe8ce-123">After the build has succeeded, right-click your pipeline project, and then click **Deploy**.</span></span>