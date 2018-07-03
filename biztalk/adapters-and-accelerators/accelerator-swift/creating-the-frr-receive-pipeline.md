---
title: Creación la recepción de FRR canalización | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive pipelines, creating
- FRR, creating receive pipelines
- creating, receive pipelines
ms.assetid: 5884176b-8522-4dd3-8f93-8695858b59ac
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbf4e735019c5399e1b7f1648f3adbcffe18fed2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970805"
---
# <a name="creating-the-frr-receive-pipeline"></a><span data-ttu-id="58484-102">Crear el FRR la canalización de recepción</span><span class="sxs-lookup"><span data-stu-id="58484-102">Creating the FRR Receive Pipeline</span></span>
<span data-ttu-id="58484-103">Para llevar a cabo la conciliación de respuestas de FIN, debe crear una canalización de recepción que contiene el descodificador de FRR SWIFT y componentes de canalización de resolución de CorrelationSet FRR SWIFT, además del desensamblador de SWIFT.</span><span class="sxs-lookup"><span data-stu-id="58484-103">To perform FIN Response Reconciliation, you must create a receive pipeline that contains the SWIFT FRR Decoder and SWIFT FRR CorrelationSet Resolver pipeline components, in addition to the SWIFT disassembler.</span></span>  

 <span data-ttu-id="58484-104">**Resumen**</span><span class="sxs-lookup"><span data-stu-id="58484-104">**Summary**</span></span>  

 <span data-ttu-id="58484-105">Crear una canalización de recepción con las propiedades y las fases siguientes:</span><span class="sxs-lookup"><span data-stu-id="58484-105">Create a receive pipeline with the following stages/properties:</span></span>  

|<span data-ttu-id="58484-106">Fase o propiedad</span><span class="sxs-lookup"><span data-stu-id="58484-106">Stage/Property</span></span>|<span data-ttu-id="58484-107">Componente/configuración</span><span class="sxs-lookup"><span data-stu-id="58484-107">Component/Setting</span></span>|  
|---------------------|------------------------|  
|<span data-ttu-id="58484-108">Fase de desensamblado</span><span class="sxs-lookup"><span data-stu-id="58484-108">Disassemble stage</span></span>|<span data-ttu-id="58484-109">Desensamblador de SWIFT</span><span class="sxs-lookup"><span data-stu-id="58484-109">SWIFT Disassembler</span></span>|  
|<span data-ttu-id="58484-110">Propiedad de validación del BRE (Desensamblador de SWIFT)</span><span class="sxs-lookup"><span data-stu-id="58484-110">BRE Validation property (SWIFT Disassembler)</span></span>|<span data-ttu-id="58484-111">True</span><span class="sxs-lookup"><span data-stu-id="58484-111">True</span></span>|  
|<span data-ttu-id="58484-112">Propiedad de validación de XML (Desensamblador de SWIFT)</span><span class="sxs-lookup"><span data-stu-id="58484-112">XML Validation property (SWIFT Disassembler)</span></span>|<span data-ttu-id="58484-113">True</span><span class="sxs-lookup"><span data-stu-id="58484-113">True</span></span>|  
|<span data-ttu-id="58484-114">Propiedad de esquema de encabezado de SWIFT (Desensamblador de SWIFT)</span><span class="sxs-lookup"><span data-stu-id="58484-114">SWIFT Header Schema property (SWIFT Disassembler)</span></span>|<span data-ttu-id="58484-115">(Ninguno)</span><span class="sxs-lookup"><span data-stu-id="58484-115">(None)</span></span>|  
|<span data-ttu-id="58484-116">Fase de descodificador</span><span class="sxs-lookup"><span data-stu-id="58484-116">Decoder stage</span></span>|<span data-ttu-id="58484-117">Descodificador de MQSeries FRR SWIFT</span><span class="sxs-lookup"><span data-stu-id="58484-117">SWIFT FRR MQSeries Decoder</span></span>|  
|<span data-ttu-id="58484-118">Fase de resolución de entidades</span><span class="sxs-lookup"><span data-stu-id="58484-118">Party Resolution stage</span></span>|<span data-ttu-id="58484-119">Resolución de conjunto de correlaciones de FRR SWIFT</span><span class="sxs-lookup"><span data-stu-id="58484-119">SWIFT FRR Correlation Set Resolver</span></span>|  

### <a name="to-create-a-custom-receive-pipeline-for-frr"></a><span data-ttu-id="58484-120">Para crear una canalización de recepción personalizada de FRR</span><span class="sxs-lookup"><span data-stu-id="58484-120">To create a custom receive pipeline for FRR</span></span>  

1. <span data-ttu-id="58484-121">En el Explorador de soluciones de Visual Studio, haga clic en el proyecto que contiene su [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] canalizaciones, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="58484-121">In Solution Explorer of Visual Studio, right-click the project containing your [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] pipelines, point to **Add**, and then click **New Item**.</span></span>  

2. <span data-ttu-id="58484-122">En el cuadro de diálogo Agregar nuevo elemento, haga clic en **archivos de canalización** en el panel de categorías y, a continuación, seleccione **canalización de recepción** en el panel Plantillas.</span><span class="sxs-lookup"><span data-stu-id="58484-122">In the Add New Item dialog box, click **Pipeline Files** in the Categories pane, and then select **Receive Pipeline** in the Templates pane.</span></span>  

3. <span data-ttu-id="58484-123">En el **nombre** , escriba un nombre para la canalización de recepción, tales como **FRRReceivePipeline.btp**.</span><span class="sxs-lookup"><span data-stu-id="58484-123">In the **Name** box, type a name for your receive pipeline, such as **FRRReceivePipeline.btp**.</span></span> <span data-ttu-id="58484-124">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="58484-124">Click **Add**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="58484-125">Antes de realizar el paso 4, debe haber agregado el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FRR canalización componentes al cuadro de herramientas, como se describe en [agregar componentes de canalización de SWIFT al cuadro de herramientas](../../adapters-and-accelerators/accelerator-swift/adding-swift-pipeline-components-to-the-toolbox.md).</span><span class="sxs-lookup"><span data-stu-id="58484-125">Before you perform step 4, you must have added the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FRR pipeline components to the toolbox, as described in [Adding SWIFT Pipeline Components to the Toolbox](../../adapters-and-accelerators/accelerator-swift/adding-swift-pipeline-components-to-the-toolbox.md).</span></span>  

4. <span data-ttu-id="58484-126">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **vista** y, a continuación, haga clic en **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="58484-126">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **View** and then click **Toolbox**.</span></span>  

5. <span data-ttu-id="58484-127">En el panel cuadro de herramientas de componentes de canalización de BizTalk, arrastre el **Desensamblador de SWIFT** a la **Coloque aquí** cuadro a continuación el **desensamblar** almacenar provisionalmente la forma en el Diseñador de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="58484-127">From the BizTalk Pipeline Components Toolbox pane, drag the **SWIFT Disassembler** to the **Drop Here** box below the **Disassemble** stage shape in Pipeline Designer.</span></span>  

6. <span data-ttu-id="58484-128">Con el **componente de desensamblador de SWIFT** seleccionado en el Diseñador de canalizaciones, en **propiedades**, compruebe que la **BRE validación** y **devalidacióndeXML** propiedades se establecen en **True**y el **esquema de encabezado de SWIFT** propiedad está establecida en **(ninguno)**.</span><span class="sxs-lookup"><span data-stu-id="58484-128">With the **SWIFT Disassembler Component** selected in Pipeline Designer, in **Properties**, verify that the **BRE Validation** and **XML Validation** properties are set to **True**, and the **SWIFT Header Schema** property is set to **(None)**.</span></span>  

7. <span data-ttu-id="58484-129">En el cuadro de herramientas de componentes de canalización de BizTalk, arrastre **SWIFT FRR MQSeries descodificador** a la **Coloque aquí** cuadro a continuación el **descodificador** almacenar provisionalmente la forma en el Diseñador de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="58484-129">In the BizTalk Pipeline Components Toolbox, drag **SWIFT FRR MQSeries Decoder** to the **Drop Here** box below the **Decoder** stage shape in Pipeline Designer.</span></span>  

8. <span data-ttu-id="58484-130">En el panel cuadro de herramientas de componentes de canalización de BizTalk, arrastre **SWIFT FRR correlación establecer resolución** a la **Coloque aquí** cuadro a continuación el **ResolveParty** almacenar provisionalmente la forma en la canalización Diseñador.</span><span class="sxs-lookup"><span data-stu-id="58484-130">From the BizTalk Pipeline Components Toolbox pane, drag **SWIFT FRR Correlation Set Resolver** to the **Drop Here** box below the **ResolveParty** stage shape in Pipeline Designer.</span></span>  

9. <span data-ttu-id="58484-131">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **archivo**y, a continuación, haga clic en **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="58484-131">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **File**, and then click **Save All**.</span></span>
