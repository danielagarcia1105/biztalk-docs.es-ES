---
title: Canalización de envío de la creación de la FRR | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, creating send pipelines
- creating, send pipelines
- send pipelines, creating
ms.assetid: c6cd2047-ea53-425f-80cc-b02a1deb5292
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d16003e489944016a7b840b870d33d8ebcf671d5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005749"
---
# <a name="creating-the-frr-send-pipeline"></a><span data-ttu-id="8bfd7-102">Creación de la canalización de envío FRR</span><span class="sxs-lookup"><span data-stu-id="8bfd7-102">Creating the FRR Send Pipeline</span></span>
<span data-ttu-id="8bfd7-103">Para llevar a cabo la conciliación de respuestas de FIN, deberá crear una canalización de envío que contiene el componente de canalización SWIFTAsmFrrMQSeriesHelper, además del ensamblador de SWIFT.</span><span class="sxs-lookup"><span data-stu-id="8bfd7-103">To perform FIN Response Reconciliation, you need to create a send pipeline that contains the SWIFTAsmFrrMQSeriesHelper pipeline component, in addition to the SWIFT assembler.</span></span>  

 <span data-ttu-id="8bfd7-104">**Resumen**</span><span class="sxs-lookup"><span data-stu-id="8bfd7-104">**Summary**</span></span>  

 <span data-ttu-id="8bfd7-105">Crear una canalización de envío con las siguientes fases:</span><span class="sxs-lookup"><span data-stu-id="8bfd7-105">Create a send pipeline with the following stages:</span></span>  

|<span data-ttu-id="8bfd7-106">Fase</span><span class="sxs-lookup"><span data-stu-id="8bfd7-106">Stage</span></span>|<span data-ttu-id="8bfd7-107">Componente</span><span class="sxs-lookup"><span data-stu-id="8bfd7-107">Component</span></span>|  
|-----------|---------------|  
|<span data-ttu-id="8bfd7-108">Fase de ensamblado</span><span class="sxs-lookup"><span data-stu-id="8bfd7-108">Assemble stage</span></span>|<span data-ttu-id="8bfd7-109">Ensamblador de SWIFT</span><span class="sxs-lookup"><span data-stu-id="8bfd7-109">SWIFT assembler</span></span>|  
|<span data-ttu-id="8bfd7-110">Fase de codificación</span><span class="sxs-lookup"><span data-stu-id="8bfd7-110">Encode stage</span></span>|<span data-ttu-id="8bfd7-111">Componente de MQSeries envío Frr SWIFT</span><span class="sxs-lookup"><span data-stu-id="8bfd7-111">SWIFT Frr MQSeries Send Component</span></span>|  

### <a name="to-create-a-custom-send-pipeline-for-frr"></a><span data-ttu-id="8bfd7-112">Para crear una canalización de envío personalizado de FRR</span><span class="sxs-lookup"><span data-stu-id="8bfd7-112">To create a custom send pipeline for FRR</span></span>  

1. <span data-ttu-id="8bfd7-113">En el Explorador de soluciones de Visual Studio, haga clic en el proyecto de canalización, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="8bfd7-113">In Solution Explorer of Visual Studio, right-click your pipeline project, point to **Add**, and then click **New Item**.</span></span>  

2. <span data-ttu-id="8bfd7-114">En el cuadro de diálogo Agregar nuevo elemento, seleccione **canalización de envío** desde el panel Plantillas.</span><span class="sxs-lookup"><span data-stu-id="8bfd7-114">In the Add New Item dialog box, select **Send Pipeline** from the Templates pane.</span></span>  

3. <span data-ttu-id="8bfd7-115">En el **nombre** , escriba un nombre para la canalización de recepción, tales como **FRRSendPipeline.btp**.</span><span class="sxs-lookup"><span data-stu-id="8bfd7-115">In the **Name** box, type a name for your receive pipeline, such as **FRRSendPipeline.btp**.</span></span> <span data-ttu-id="8bfd7-116">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="8bfd7-116">Click **Add**.</span></span>  

4. <span data-ttu-id="8bfd7-117">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **vista** y, a continuación, **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="8bfd7-117">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **View** and then **Toolbox**.</span></span>  

5. <span data-ttu-id="8bfd7-118">En el cuadro de herramientas de componentes de canalización de BizTalk, arrastre **ensamblador de SWIFT** a la **Coloque aquí** cuadro a continuación el **ensamblar** en forma de organizar **canalizaciones de BizTalk Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="8bfd7-118">From the BizTalk Pipeline Components Toolbox, drag **SWIFT Assembler** to the **Drop Here** box below the **Assemble** stage shape in **BizTalk Pipeline Designer**.</span></span>  

6. <span data-ttu-id="8bfd7-119">En el cuadro de herramientas de componentes de canalización de BizTalk, arrastre **componente de envío de SWIFT Frr MQSeries** a la **Coloque aquí** cuadro a continuación el **Encode** en forma de organizar  **Diseñador de canalizaciones de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="8bfd7-119">From the BizTalk Pipeline Components Toolbox, drag **SWIFT Frr MQSeries Send Component** to the **Drop Here** box below the **Encode** stage shape in **BizTalk Pipeline Designer**.</span></span>  

7. <span data-ttu-id="8bfd7-120">En el Explorador de BizTalk, haga clic en el proyecto de canalización, haga clic en **Undeploy**y, a continuación, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="8bfd7-120">In BizTalk Explorer, right-click your pipeline project, click **Undeploy**, and then click **Yes**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="8bfd7-121">Después de anular la implementación y, a continuación, volver a implementar el proyecto de canalización, debe restablecer los puertos de envío o ubicaciones de recepción que utilice canalizaciones en el proyecto implementado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8bfd7-121">After undeploying and then redeploying your pipeline project, you must reset any send ports or receive locations that use pipelines in the previously deployed project.</span></span>  

8. <span data-ttu-id="8bfd7-122">En el Explorador de soluciones, haga clic en el proyecto de canalización y, a continuación, haga clic en **compilar**.</span><span class="sxs-lookup"><span data-stu-id="8bfd7-122">In Solution Explorer, right-click your pipeline project, and then click **Build**.</span></span>  

9. <span data-ttu-id="8bfd7-123">Después de la compilación se ha realizado correctamente, haga clic en el proyecto de canalización y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="8bfd7-123">After the build has succeeded, right-click your pipeline project, and then click **Deploy**.</span></span>
