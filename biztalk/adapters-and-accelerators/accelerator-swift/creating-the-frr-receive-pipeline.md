---
title: "Crear el FRR la canalización de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive pipelines, creating
- FRR, creating receive pipelines
- creating, receive pipelines
ms.assetid: 5884176b-8522-4dd3-8f93-8695858b59ac
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad31a69d579cf2bbe9f646fc87be1bea9f561a10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-the-frr-receive-pipeline"></a><span data-ttu-id="c68d8-102">Crear el FRR la canalización de recepción</span><span class="sxs-lookup"><span data-stu-id="c68d8-102">Creating the FRR Receive Pipeline</span></span>
<span data-ttu-id="c68d8-103">Para realizar la conciliación de respuesta de FIN, debe crear una canalización de recepción que contiene el descodificador de SWIFT FRR y componentes de canalización de SWIFT FRR CorrelationSet resolución, así como el Desensamblador SWIFT.</span><span class="sxs-lookup"><span data-stu-id="c68d8-103">To perform FIN Response Reconciliation, you must create a receive pipeline that contains the SWIFT FRR Decoder and SWIFT FRR CorrelationSet Resolver pipeline components, in addition to the SWIFT disassembler.</span></span>  
  
 <span data-ttu-id="c68d8-104">**Resumen**</span><span class="sxs-lookup"><span data-stu-id="c68d8-104">**Summary**</span></span>  
  
 <span data-ttu-id="c68d8-105">Crear una canalización de recepción con las siguientes fases/propiedades:</span><span class="sxs-lookup"><span data-stu-id="c68d8-105">Create a receive pipeline with the following stages/properties:</span></span>  
  
|<span data-ttu-id="c68d8-106">Fase o la propiedad</span><span class="sxs-lookup"><span data-stu-id="c68d8-106">Stage/Property</span></span>|<span data-ttu-id="c68d8-107">Componente/configuración</span><span class="sxs-lookup"><span data-stu-id="c68d8-107">Component/Setting</span></span>|  
|---------------------|------------------------|  
|<span data-ttu-id="c68d8-108">Fase de desensamblado</span><span class="sxs-lookup"><span data-stu-id="c68d8-108">Disassemble stage</span></span>|<span data-ttu-id="c68d8-109">Desensamblador SWIFT</span><span class="sxs-lookup"><span data-stu-id="c68d8-109">SWIFT Disassembler</span></span>|  
|<span data-ttu-id="c68d8-110">Propiedad de validación de BRE (SWIFT desensamblador)</span><span class="sxs-lookup"><span data-stu-id="c68d8-110">BRE Validation property (SWIFT Disassembler)</span></span>|<span data-ttu-id="c68d8-111">True</span><span class="sxs-lookup"><span data-stu-id="c68d8-111">True</span></span>|  
|<span data-ttu-id="c68d8-112">Propiedad de validación de XML (SWIFT desensamblador)</span><span class="sxs-lookup"><span data-stu-id="c68d8-112">XML Validation property (SWIFT Disassembler)</span></span>|<span data-ttu-id="c68d8-113">True</span><span class="sxs-lookup"><span data-stu-id="c68d8-113">True</span></span>|  
|<span data-ttu-id="c68d8-114">Propiedad de esquema de encabezado de SWIFT (SWIFT desensamblador)</span><span class="sxs-lookup"><span data-stu-id="c68d8-114">SWIFT Header Schema property (SWIFT Disassembler)</span></span>|<span data-ttu-id="c68d8-115">(Ninguno)</span><span class="sxs-lookup"><span data-stu-id="c68d8-115">(None)</span></span>|  
|<span data-ttu-id="c68d8-116">Fase de descodificador</span><span class="sxs-lookup"><span data-stu-id="c68d8-116">Decoder stage</span></span>|<span data-ttu-id="c68d8-117">Descodificador de MQSeries FRR SWIFT</span><span class="sxs-lookup"><span data-stu-id="c68d8-117">SWIFT FRR MQSeries Decoder</span></span>|  
|<span data-ttu-id="c68d8-118">Fase de resolución de entidades</span><span class="sxs-lookup"><span data-stu-id="c68d8-118">Party Resolution stage</span></span>|<span data-ttu-id="c68d8-119">Resolución de conjunto de correlaciones de SWIFT FRR</span><span class="sxs-lookup"><span data-stu-id="c68d8-119">SWIFT FRR Correlation Set Resolver</span></span>|  
  
### <a name="to-create-a-custom-receive-pipeline-for-frr"></a><span data-ttu-id="c68d8-120">Para crear una canalización de recepción personalizada para FRR</span><span class="sxs-lookup"><span data-stu-id="c68d8-120">To create a custom receive pipeline for FRR</span></span>  
  
1.  <span data-ttu-id="c68d8-121">En el Explorador de soluciones de Visual Studio, haga clic en el proyecto que contiene su [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] canalizaciones, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="c68d8-121">In Solution Explorer of Visual Studio, right-click the project containing your [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] pipelines, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="c68d8-122">En el cuadro de diálogo Agregar nuevo elemento, haga clic en **archivos de canalización** en el panel de categorías y, a continuación, seleccione **canalización de recepción** en el panel Plantillas.</span><span class="sxs-lookup"><span data-stu-id="c68d8-122">In the Add New Item dialog box, click **Pipeline Files** in the Categories pane, and then select **Receive Pipeline** in the Templates pane.</span></span>  
  
3.  <span data-ttu-id="c68d8-123">En el **nombre** , escriba un nombre para la canalización de recepción, como **FRRReceivePipeline.btp**.</span><span class="sxs-lookup"><span data-stu-id="c68d8-123">In the **Name** box, type a name for your receive pipeline, such as **FRRReceivePipeline.btp**.</span></span> <span data-ttu-id="c68d8-124">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c68d8-124">Click **Add**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c68d8-125">Antes de realizar el paso 4, debe haber agregado el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FRR canalización componentes al cuadro de herramientas, como se describe en [agregar componentes de canalización de SWIFT al cuadro de herramientas](../../adapters-and-accelerators/accelerator-swift/adding-swift-pipeline-components-to-the-toolbox.md).</span><span class="sxs-lookup"><span data-stu-id="c68d8-125">Before you perform step 4, you must have added the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FRR pipeline components to the toolbox, as described in [Adding SWIFT Pipeline Components to the Toolbox](../../adapters-and-accelerators/accelerator-swift/adding-swift-pipeline-components-to-the-toolbox.md).</span></span>  
  
4.  <span data-ttu-id="c68d8-126">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **vista** y, a continuación, haga clic en **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="c68d8-126">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **View** and then click **Toolbox**.</span></span>  
  
5.  <span data-ttu-id="c68d8-127">En el panel cuadro de herramientas de componentes de canalizaciones de BizTalk, arrastre el **SWIFT Desensamblador** a la **Coloque aquí los** cuadro siguiente la **desensamblar** fase forma en el Diseñador de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="c68d8-127">From the BizTalk Pipeline Components Toolbox pane, drag the **SWIFT Disassembler** to the **Drop Here** box below the **Disassemble** stage shape in Pipeline Designer.</span></span>  
  
6.  <span data-ttu-id="c68d8-128">Con el **componente de desensamblador de SWIFT** seleccionada en el Diseñador de canalizaciones, en **propiedades**, compruebe que la **BRE validación** y **devalidacióndeXML** propiedades se establecen en **True**y el **esquema de encabezado de SWIFT** propiedad está establecida en **(ninguno)**.</span><span class="sxs-lookup"><span data-stu-id="c68d8-128">With the **SWIFT Disassembler Component** selected in Pipeline Designer, in **Properties**, verify that the **BRE Validation** and **XML Validation** properties are set to **True**, and the **SWIFT Header Schema** property is set to **(None)**.</span></span>  
  
7.  <span data-ttu-id="c68d8-129">En el cuadro de herramientas de componentes de canalización de BizTalk, arrastre **SWIFT FRR MQSeries descodificador** a la **Coloque aquí los** cuadro siguiente la **descodificador** fase forma en el Diseñador de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="c68d8-129">In the BizTalk Pipeline Components Toolbox, drag **SWIFT FRR MQSeries Decoder** to the **Drop Here** box below the **Decoder** stage shape in Pipeline Designer.</span></span>  
  
8.  <span data-ttu-id="c68d8-130">En el panel cuadro de herramientas de componentes de canalizaciones de BizTalk, arrastre **resolución de conjunto de correlación de SWIFT FRR** a la **Coloque aquí los** cuadro siguiente la **ResolveParty** fase forma de canalización Diseñador.</span><span class="sxs-lookup"><span data-stu-id="c68d8-130">From the BizTalk Pipeline Components Toolbox pane, drag **SWIFT FRR Correlation Set Resolver** to the **Drop Here** box below the **ResolveParty** stage shape in Pipeline Designer.</span></span>  
  
9. <span data-ttu-id="c68d8-131">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **archivo**y, a continuación, haga clic en **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="c68d8-131">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **File**, and then click **Save All**.</span></span>