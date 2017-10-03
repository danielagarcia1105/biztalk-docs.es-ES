---
title: "Agregar componentes de canalización SWIFT al cuadro de herramientas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbox, adding pipelines
- pipelines, adding to toolbox
ms.assetid: 3821c10e-ef9b-4657-b934-cff6d096f654
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aaef345994a1d849e09025d9ad1bb0f133c1b224
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="adding-swift-pipeline-components-to-the-toolbox"></a><span data-ttu-id="be71b-102">Agregar componentes de canalización SWIFT al cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="be71b-102">Adding SWIFT Pipeline Components to the Toolbox</span></span>
<span data-ttu-id="be71b-103">Debe agregar los componentes de canalización SWIFT a la [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] cuadro de herramientas, para que pueda crear canalizaciones personalizadas mediante estos componentes.</span><span class="sxs-lookup"><span data-stu-id="be71b-103">You must add the SWIFT pipeline components to the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] Toolbox, so that you can create custom pipelines using these components.</span></span> <span data-ttu-id="be71b-104">Esto es necesario para crear canalizaciones de reparación de mensajes y nuevo envío o conciliación de respuesta de FIN.</span><span class="sxs-lookup"><span data-stu-id="be71b-104">This is required to create pipelines for either Message Repair and New Submission or FIN Response Reconciliation.</span></span>  
  
 <span data-ttu-id="be71b-105">**Resumen**</span><span class="sxs-lookup"><span data-stu-id="be71b-105">**Summary**</span></span>  
  
 <span data-ttu-id="be71b-106">Agregue los siguientes componentes de canalización SWIFT para el [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] cuadro de herramientas:</span><span class="sxs-lookup"><span data-stu-id="be71b-106">Add the following SWIFT pipeline components to the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] Toolbox:</span></span>  
  
-   <span data-ttu-id="be71b-107">Ensamblador SWIFT (para la reparación de mensajes y nuevo envío o la conciliación de respuesta FIN (FRR))</span><span class="sxs-lookup"><span data-stu-id="be71b-107">SWIFT Assembler (for Message Repair and New Submission or FIN Response Reconciliation (FRR))</span></span>  
  
-   <span data-ttu-id="be71b-108">Desensamblador SWIFT (para la reparación de mensajes y nuevo envío o FRR)</span><span class="sxs-lookup"><span data-stu-id="be71b-108">SWIFT Disassembler (for Message Repair and New Submission or FRR)</span></span>  
  
-   <span data-ttu-id="be71b-109">Resolución de conjunto de correlación de SWIFT Frr (para FRR)</span><span class="sxs-lookup"><span data-stu-id="be71b-109">SWIFT Frr Correlation Set Resolver (for FRR)</span></span>  
  
-   <span data-ttu-id="be71b-110">Descodificador de MQSeries SWIFT Frr (para FRR)</span><span class="sxs-lookup"><span data-stu-id="be71b-110">SWIFT Frr MQSeries Decoder (for FRR)</span></span>  
  
-   <span data-ttu-id="be71b-111">Componente de envío SWIFT Frr MQSeries (para FRR)</span><span class="sxs-lookup"><span data-stu-id="be71b-111">SWIFT Frr MQSeries Send Component (for FRR)</span></span>  
  
### <a name="to-add-a4swift-pipeline-components-to-the-toolbox"></a><span data-ttu-id="be71b-112">Para agregar componentes de canalización de A4SWIFT al cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="be71b-112">To add A4SWIFT pipeline components to the toolbox</span></span>  
  
1.  <span data-ttu-id="be71b-113">En Visual Studio, en el **herramientas** menú, haga clic en **elegir elementos del cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="be71b-113">In Visual Studio, on the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
2.  <span data-ttu-id="be71b-114">En el **elegir elementos del cuadro de herramientas** cuadro de diálogo, en la **componentes de canalización de BizTalk** ficha, seleccione **SWIFT ensamblador** y **SWIFT Desensamblador**.</span><span class="sxs-lookup"><span data-stu-id="be71b-114">In the **Choose Toolbox Items** dialog box, on the **BizTalk Pipeline Components** tab, select **SWIFT Assembler** and **SWIFT Disassembler**.</span></span> <span data-ttu-id="be71b-115">Si va a utilizar Conciliación de respuesta de FIN, seleccione **resolución de conjunto de correlación de SWIFT Frr**, **SWIFT Frr MQSeries descodificador**, y **SWIFT Frr MQSeries enviar componente**.</span><span class="sxs-lookup"><span data-stu-id="be71b-115">If you will be using FIN Response Reconciliation, select **SWIFT Frr Correlation Set Resolver**, **SWIFT Frr MQSeries Decoder**, and **SWIFT Frr MQSeries Send Component**.</span></span>  
  
3.  <span data-ttu-id="be71b-116">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="be71b-116">Click **OK**.</span></span>