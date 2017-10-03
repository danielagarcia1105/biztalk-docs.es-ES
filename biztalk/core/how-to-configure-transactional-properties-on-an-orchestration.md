---
title: "Cómo configurar propiedades de transacción en una orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- atomic transactions
- orchestrations, transactions
- transactions, long-running
- orchestrations, configuring
- transactions, atomic
ms.assetid: 8eec6019-4d96-4ed6-8a90-9403738d8af4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9164a9f5670a996a62450a19d802c97b89d8e242
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-transactional-properties-on-an-orchestration"></a><span data-ttu-id="e91a7-102">Cómo configurar propiedades de transacción en una orquestación</span><span class="sxs-lookup"><span data-stu-id="e91a7-102">How to Configure Transactional Properties on an Orchestration</span></span>
<span data-ttu-id="e91a7-103">Una orquestación puede tratarse como una transacción atómica, una transacción de larga ejecución o como ninguna de ellas.</span><span class="sxs-lookup"><span data-stu-id="e91a7-103">An orchestration can be treated as an atomic transaction, a long-running transaction, or neither.</span></span>  
  
### <a name="to-make-your-orchestration-an-atomic-transaction"></a><span data-ttu-id="e91a7-104">Para convertir la orquestación en una transacción atómica</span><span class="sxs-lookup"><span data-stu-id="e91a7-104">To make your orchestration an atomic transaction</span></span>  
  
1.  <span data-ttu-id="e91a7-105">En la ventana Vista orquestación, seleccione **propiedades de orquestación**.</span><span class="sxs-lookup"><span data-stu-id="e91a7-105">In the Orchestration View window, select **Orchestration Properties**.</span></span>  
  
2.  <span data-ttu-id="e91a7-106">En la ventana Propiedades, seleccione **atómica** en la lista desplegable para la **tipo de transacción** propiedad.</span><span class="sxs-lookup"><span data-stu-id="e91a7-106">In the Properties window, select **Atomic** in the drop-down for the **Transaction Type** property.</span></span>  
  
     <span data-ttu-id="e91a7-107">**Lote**, **compensación**, **nivel de aislamiento**, **vuelva a intentar**, **tiempo de espera**, y **transacciones Identificador** aparecen como propiedades en la ventana Propiedades, tal y como hace para cualquier ámbito.</span><span class="sxs-lookup"><span data-stu-id="e91a7-107">**Batch**, **Compensation**, **Isolation Level**, **Retry**, **Timeout**, and **Transaction Identifier** appear as properties in the Properties window, just as they do for any scope.</span></span> <span data-ttu-id="e91a7-108">Para obtener más información acerca de estas propiedades, vea [cómo configurar la forma ámbito](../core/how-to-configure-the-scope-shape.md).</span><span class="sxs-lookup"><span data-stu-id="e91a7-108">For more information on these properties, see [How to Configure the Scope Shape](../core/how-to-configure-the-scope-shape.md).</span></span>  
  
### <a name="to-make-your-orchestration-a-long-running-transaction"></a><span data-ttu-id="e91a7-109">Para convertir la orquestación en una transacción de larga ejecución</span><span class="sxs-lookup"><span data-stu-id="e91a7-109">To make your orchestration a long-running transaction</span></span>  
  
1.  <span data-ttu-id="e91a7-110">En la ventana Vista orquestación, seleccione **propiedades de orquestación**.</span><span class="sxs-lookup"><span data-stu-id="e91a7-110">In the Orchestration View window, select **Orchestration Properties**.</span></span>  
  
2.  <span data-ttu-id="e91a7-111">En la ventana Propiedades, seleccione **larga ejecución** en la lista desplegable para la **tipo de transacción** propiedad.</span><span class="sxs-lookup"><span data-stu-id="e91a7-111">In the Properties window, select **Long Running** in the drop-down for the **Transaction Type** property.</span></span>  
  
     <span data-ttu-id="e91a7-112">**Compensación**, **tiempo de espera**, y **identificador de transacción** aparecen como propiedades en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="e91a7-112">**Compensation**, **Timeout**, and **Transaction Identifier** appear as properties in the Properties window.</span></span> <span data-ttu-id="e91a7-113">Para obtener más información acerca de estas propiedades, tal y como se comportan con cualquier ámbito.</span><span class="sxs-lookup"><span data-stu-id="e91a7-113">For more information on these properties, just as they do for any scope.</span></span> <span data-ttu-id="e91a7-114">Para obtener más información acerca de estas propiedades, vea [cómo configurar la forma ámbito](../core/how-to-configure-the-scope-shape.md).</span><span class="sxs-lookup"><span data-stu-id="e91a7-114">For more information on these properties, see [How to Configure the Scope Shape](../core/how-to-configure-the-scope-shape.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e91a7-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e91a7-115">See Also</span></span>  
 [<span data-ttu-id="e91a7-116">Realizar orquestaciones transaccionales</span><span class="sxs-lookup"><span data-stu-id="e91a7-116">Making Orchestrations Transactional</span></span>](../core/making-orchestrations-transactional.md)