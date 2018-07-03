---
title: 'Lección 5: Agregar el Desensamblador de SWIFT a una canalización de recepción personalizada | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive pipelines, adding disassembler
- custom pipelines
- disassembler, custom pipelines
- disassembler, adding to pipelines
ms.assetid: 96e26d97-bfab-448f-b7b6-3bc2ec3ccebf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0af7635b424a74b160991b1d6cfdeb53bfb7f23f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971301"
---
# <a name="lesson-5-adding-the-swift-disassembler-to-a-custom-receive-pipeline"></a><span data-ttu-id="79570-102">Lección 5: Agregar el Desensamblador de SWIFT a una canalización de recepción personalizada</span><span class="sxs-lookup"><span data-stu-id="79570-102">Lesson 5: Adding the SWIFT Disassembler to a Custom Receive Pipeline</span></span>
<span data-ttu-id="79570-103">En esta lección, agregará el Desensamblador SWIFT personalizado (DASM) a la canalización.</span><span class="sxs-lookup"><span data-stu-id="79570-103">In this lesson, you add the custom SWIFT disassembler (DASM) to your pipeline.</span></span> <span data-ttu-id="79570-104">Un componente de canalización DASM es un componente de canalización que divide los mensajes en un lote en documentos individuales.</span><span class="sxs-lookup"><span data-stu-id="79570-104">A DASM pipeline component is a pipeline component that divides messages in a batch into individual documents.</span></span>  
  
 <span data-ttu-id="79570-105">Los componentes de canalización DASM proporcionados MicrosoftBizTalk Server son:</span><span class="sxs-lookup"><span data-stu-id="79570-105">The DASM pipeline components provided in MicrosoftBizTalk Server are:</span></span>  
  
- <span data-ttu-id="79570-106">Desensamblador de archivos</span><span class="sxs-lookup"><span data-stu-id="79570-106">Flat file disassembler</span></span>  
  
- <span data-ttu-id="79570-107">Desensamblador de BizTalk Framework</span><span class="sxs-lookup"><span data-stu-id="79570-107">BizTalk Framework disassembler</span></span>  
  
- <span data-ttu-id="79570-108">Desensamblador de XML</span><span class="sxs-lookup"><span data-stu-id="79570-108">XML disassembler</span></span>  
  
  <span data-ttu-id="79570-109">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] agrega un desensamblador de SWIFT adicional.</span><span class="sxs-lookup"><span data-stu-id="79570-109">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] adds an additional SWIFT disassembler.</span></span>  
  
### <a name="to-add-the-swift-custom-disassembler-to-your-pipeline"></a><span data-ttu-id="79570-110">Para agregar el Desensamblador de SWIFT personalizado a la canalización</span><span class="sxs-lookup"><span data-stu-id="79570-110">To add the SWIFT custom disassembler to your pipeline</span></span>  
  
1. <span data-ttu-id="79570-111">En el menú Ver, haga clic en **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="79570-111">From the View menu, click **Toolbox**.</span></span>  
  
2. <span data-ttu-id="79570-112">Desde el **cuadro de herramientas de componentes de canalización de BizTalk**, haga clic en **Desensamblador de SWIFT** y arrástrelo hasta el **Coloque aquí** cuadro a continuación el **desensamblar**en forma de organizar **Diseñador de canalizaciones de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="79570-112">From the **BizTalk Pipeline Components Toolbox**, click **SWIFT Disassembler** and drag it to the **Drop Here** box below the **Disassemble** stage shape in **BizTalk Pipeline Designer**.</span></span> <span data-ttu-id="79570-113">Deje el **Desensamblador de SWIFT** forma seleccionada en el **Diseñador de canalizaciones de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="79570-113">Leave the **SWIFT Disassembler** shape selected in the **BizTalk Pipeline Designer**.</span></span>  
  
3. <span data-ttu-id="79570-114">En el **propiedades** panel, seleccione **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema** para el **esquema de encabezado de SWIFT** propiedad.</span><span class="sxs-lookup"><span data-stu-id="79570-114">In the **Properties** pane, select **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema** for the **SWIFT Header Schema** property.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="79570-115">No confunda **esquema de encabezado de SWIFT** y esquema de encabezado de mensaje.</span><span class="sxs-lookup"><span data-stu-id="79570-115">Do not confuse **SWIFT Header Schema** and Message Header Schema.</span></span> <span data-ttu-id="79570-116">Debe establecer **esquema de encabezado de SWIFT** en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="79570-116">You must set **SWIFT Header Schema** in step 3.</span></span>  
  
4. <span data-ttu-id="79570-117">En el **propiedades** panel, asegúrese de que el **BRE validación** propiedad está establecida en **True**.</span><span class="sxs-lookup"><span data-stu-id="79570-117">In the **Properties** pane, ensure that the **BRE Validation** property is set to **True**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="79570-118">Obtener una explicación del motor de reglas de negocios (BRE) sigue más adelante en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="79570-118">An explanation of the Business Rule Engine (BRE) follows later in this tutorial.</span></span>  
  
5. <span data-ttu-id="79570-119">En el **propiedades** panel, asegúrese de que el **validación XML** propiedad está establecida en **True**.</span><span class="sxs-lookup"><span data-stu-id="79570-119">In the **Properties** pane, ensure that the **XML Validation** property is set to **True**.</span></span>  
  
6. <span data-ttu-id="79570-120">En el **propiedades** panel, asegúrese de que el **entrada desagrupación** propiedad está establecida en **False**.</span><span class="sxs-lookup"><span data-stu-id="79570-120">In the **Properties** pane, ensure that the **Inbound Debatching** property is set to **False**.</span></span>  
  
7. <span data-ttu-id="79570-121">En el **archivo** menú, seleccione **guardar todo** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="79570-121">On the **File** menu, select **Save All** to save your changes.</span></span>  
  
   <span data-ttu-id="79570-122">Continúe con [lección 6: creación de un archivo de canalización de envío](../../adapters-and-accelerators/accelerator-swift/lesson-6-creating-a-custom-send-pipeline.md).</span><span class="sxs-lookup"><span data-stu-id="79570-122">Proceed to [Lesson 6: Creating a Custom Send Pipeline](../../adapters-and-accelerators/accelerator-swift/lesson-6-creating-a-custom-send-pipeline.md).</span></span>