---
title: "Lección 5: Agregar el Desensamblador SWIFT a una canalización de recepción personalizada | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive pipelines, adding disassembler
- custom pipelines
- disassembler, custom pipelines
- disassembler, adding to pipelines
ms.assetid: 96e26d97-bfab-448f-b7b6-3bc2ec3ccebf
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04feeaf88cef2f4ab876b22eda1b1e060a1e0173
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-5-adding-the-swift-disassembler-to-a-custom-receive-pipeline"></a><span data-ttu-id="9a5cc-102">Lección 5: Agregar el Desensamblador SWIFT a una canalización de recepción personalizada</span><span class="sxs-lookup"><span data-stu-id="9a5cc-102">Lesson 5: Adding the SWIFT Disassembler to a Custom Receive Pipeline</span></span>
<span data-ttu-id="9a5cc-103">En esta lección, agregará el Desensamblador SWIFT personalizado (DASM) a la canalización.</span><span class="sxs-lookup"><span data-stu-id="9a5cc-103">In this lesson, you add the custom SWIFT disassembler (DASM) to your pipeline.</span></span> <span data-ttu-id="9a5cc-104">Un componente de canalización DASM es un componente de canalización que divide los mensajes de un lote en documentos individuales.</span><span class="sxs-lookup"><span data-stu-id="9a5cc-104">A DASM pipeline component is a pipeline component that divides messages in a batch into individual documents.</span></span>  
  
 <span data-ttu-id="9a5cc-105">Los componentes de canalización DASM proporcionados en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] son:</span><span class="sxs-lookup"><span data-stu-id="9a5cc-105">The DASM pipeline components provided in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] are:</span></span>  
  
-   <span data-ttu-id="9a5cc-106">Desensamblador de archivos sin formato</span><span class="sxs-lookup"><span data-stu-id="9a5cc-106">Flat file disassembler</span></span>  
  
-   <span data-ttu-id="9a5cc-107">Desensamblador de BizTalk Framework</span><span class="sxs-lookup"><span data-stu-id="9a5cc-107">BizTalk Framework disassembler</span></span>  
  
-   <span data-ttu-id="9a5cc-108">Desensamblador de XML</span><span class="sxs-lookup"><span data-stu-id="9a5cc-108">XML disassembler</span></span>  
  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="9a5cc-109">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] agrega un desensamblador SWIFT adicional.</span><span class="sxs-lookup"><span data-stu-id="9a5cc-109"> [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] adds an additional SWIFT disassembler.</span></span>  
  
### <a name="to-add-the-swift-custom-disassembler-to-your-pipeline"></a><span data-ttu-id="9a5cc-110">Para agregar el Desensamblador personalizado SWIFT a la canalización</span><span class="sxs-lookup"><span data-stu-id="9a5cc-110">To add the SWIFT custom disassembler to your pipeline</span></span>  
  
1.  <span data-ttu-id="9a5cc-111">En el menú Ver, haga clic en **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="9a5cc-111">From the View menu, click **Toolbox**.</span></span>  
  
2.  <span data-ttu-id="9a5cc-112">Desde el **cuadro de herramientas de componentes de canalizaciones de BizTalk**, haga clic en **SWIFT Desensamblador** y arrástrelo hasta el **Coloque aquí los** cuadro siguiente el **desensamblar**fase forma **Diseñador de canalizaciones de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="9a5cc-112">From the **BizTalk Pipeline Components Toolbox**, click **SWIFT Disassembler** and drag it to the **Drop Here** box below the **Disassemble** stage shape in **BizTalk Pipeline Designer**.</span></span> <span data-ttu-id="9a5cc-113">Deje el **SWIFT Desensamblador** forma seleccionada en la **Diseñador de canalizaciones de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="9a5cc-113">Leave the **SWIFT Disassembler** shape selected in the **BizTalk Pipeline Designer**.</span></span>  
  
3.  <span data-ttu-id="9a5cc-114">En el **propiedades** panel, seleccione **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema** para el **esquema de encabezado de SWIFT** propiedad.</span><span class="sxs-lookup"><span data-stu-id="9a5cc-114">In the **Properties** pane, select **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema** for the **SWIFT Header Schema** property.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9a5cc-115">No confunda **esquema de encabezado de SWIFT** y el esquema de encabezado de mensaje.</span><span class="sxs-lookup"><span data-stu-id="9a5cc-115">Do not confuse **SWIFT Header Schema** and Message Header Schema.</span></span> <span data-ttu-id="9a5cc-116">Debe establecer **esquema de encabezado de SWIFT** en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="9a5cc-116">You must set **SWIFT Header Schema** in step 3.</span></span>  
  
4.  <span data-ttu-id="9a5cc-117">En el **propiedades** panel, asegúrese de que el **BRE validación** propiedad está establecida en **True**.</span><span class="sxs-lookup"><span data-stu-id="9a5cc-117">In the **Properties** pane, ensure that the **BRE Validation** property is set to **True**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9a5cc-118">Obtener una explicación del motor de reglas de negocios (BRE) sigue más adelante en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="9a5cc-118">An explanation of the Business Rule Engine (BRE) follows later in this tutorial.</span></span>  
  
5.  <span data-ttu-id="9a5cc-119">En el **propiedades** panel, asegúrese de que el **validación XML** propiedad está establecida en **True**.</span><span class="sxs-lookup"><span data-stu-id="9a5cc-119">In the **Properties** pane, ensure that the **XML Validation** property is set to **True**.</span></span>  
  
6.  <span data-ttu-id="9a5cc-120">En el **propiedades** panel, asegúrese de que el **entrada anulando** propiedad está establecida en **False**.</span><span class="sxs-lookup"><span data-stu-id="9a5cc-120">In the **Properties** pane, ensure that the **Inbound Debatching** property is set to **False**.</span></span>  
  
7.  <span data-ttu-id="9a5cc-121">En el **archivo** menú, seleccione **guardar todo** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="9a5cc-121">On the **File** menu, select **Save All** to save your changes.</span></span>  
  
 <span data-ttu-id="9a5cc-122">Continúe con [lección 6: crear una personalizada canalización de envío](../../adapters-and-accelerators/accelerator-swift/lesson-6-creating-a-custom-send-pipeline.md).</span><span class="sxs-lookup"><span data-stu-id="9a5cc-122">Proceed to [Lesson 6: Creating a Custom Send Pipeline](../../adapters-and-accelerators/accelerator-swift/lesson-6-creating-a-custom-send-pipeline.md).</span></span>