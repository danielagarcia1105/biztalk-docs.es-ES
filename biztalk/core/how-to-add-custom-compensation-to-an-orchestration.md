---
title: "Cómo agregar la compensación personalizada a una orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, compensations
- Compensate shape [Orchestration Designer]
- Compensate shape [Orchestration Designer], orchestrations
- Compensation property
- orchestrations, transactional
- orchestrations, customizing
- customizing, orchestrations
- Compensate shape [Orchestration Designer], custom compensation
ms.assetid: d153498d-8f98-42ae-90b9-e3083d669aef
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3eadb9cba6e5a49be516a8095b01f93ca7a490f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-custom-compensation-to-an-orchestration"></a><span data-ttu-id="c0aee-102">Cómo agregar la compensación personalizada a una orquestación</span><span class="sxs-lookup"><span data-stu-id="c0aee-102">How to Add Custom Compensation to an Orchestration</span></span>
<span data-ttu-id="c0aee-103">Una transacción de orquestación configurada como de larga ejecución puede incluir código de compensación personalizada para invertir o deshacer los efectos de la transacción.</span><span class="sxs-lookup"><span data-stu-id="c0aee-103">An orchestration transaction that is configured as long running can have custom compensation code to reverse or undo the effects of the transaction.</span></span> <span data-ttu-id="c0aee-104">Si la orquestación se ha completado correctamente y se ha llamado a otra orquestación, la orquestación de llamada puede invocar su bloque de compensación mediante una **compensar** forma.</span><span class="sxs-lookup"><span data-stu-id="c0aee-104">If the orchestration has completed successfully and has been called by another orchestration, the calling orchestration can invoke its compensation block using a **Compensate** shape.</span></span>  
  
### <a name="to-specify-that-an-orchestration-will-use-custom-compensation"></a><span data-ttu-id="c0aee-105">Para especificar que una orquestación utilice la compensación personalizada</span><span class="sxs-lookup"><span data-stu-id="c0aee-105">To specify that an orchestration will use custom compensation</span></span>  
  
1.  <span data-ttu-id="c0aee-106">En la ventana Vista orquestación, seleccione **propiedades de orquestación**.</span><span class="sxs-lookup"><span data-stu-id="c0aee-106">In the Orchestration View window, select **Orchestration Properties**.</span></span>  
  
2.  <span data-ttu-id="c0aee-107">En la ventana Propiedades, seleccione **personalizado** en la lista desplegable para la **compensación** propiedad.</span><span class="sxs-lookup"><span data-stu-id="c0aee-107">In the Properties window, select **Custom** in the drop-down for the **Compensation** property.</span></span>  
  
     <span data-ttu-id="c0aee-108">El **compensación** ficha aparece junto a la **orquestación** ficha situada en la parte inferior de la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="c0aee-108">The **Compensation** tab appears next to the **Orchestration** tab at the bottom of the Design Surface.</span></span>  
  
### <a name="to-design-custom-compensation-for-an-orchestration"></a><span data-ttu-id="c0aee-109">Para diseñar una compensación personalizada para una orquestación</span><span class="sxs-lookup"><span data-stu-id="c0aee-109">To design custom compensation for an orchestration</span></span>  
  
1.  <span data-ttu-id="c0aee-110">Haga clic en el **compensación** ficha situada en la parte inferior de la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="c0aee-110">Click the **Compensation** tab at the bottom of the Design Surface.</span></span>  
  
     <span data-ttu-id="c0aee-111">El **superficie de diseño de compensación** aparece.</span><span class="sxs-lookup"><span data-stu-id="c0aee-111">The **Compensation Design Surface** appears.</span></span>  
  
2.  <span data-ttu-id="c0aee-112">Agregar formas a la **superficie de diseño de compensación** tal y como lo haría en la **superficie de diseño de orquestación**.</span><span class="sxs-lookup"><span data-stu-id="c0aee-112">Add shapes to the **Compensation Design Surface** just as you would in the **Orchestration Design Surface**.</span></span>  
  
     <span data-ttu-id="c0aee-113">Para obtener más información, consulte [agregar formas a orquestaciones](../core/how-to-add-shapes-to-orchestrations.md).</span><span class="sxs-lookup"><span data-stu-id="c0aee-113">For more information, see [Adding Shapes to Orchestrations](../core/how-to-add-shapes-to-orchestrations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0aee-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0aee-114">See Also</span></span>  
 [<span data-ttu-id="c0aee-115">Realizar orquestaciones transaccionales</span><span class="sxs-lookup"><span data-stu-id="c0aee-115">Making Orchestrations Transactional</span></span>](../core/making-orchestrations-transactional.md)