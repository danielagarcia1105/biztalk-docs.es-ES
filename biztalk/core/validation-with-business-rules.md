---
title: Validación con reglas de negocios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, process management solutions
- process management solution tutorial, validating
- business rules, validating
- process management solution tutorial, business rules
ms.assetid: a67f3781-629a-4157-9a27-3b73d7a5a3a8
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8926cf8bd95c2b90c7d16151b47f8893120b812e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287780"
---
# <a name="validation-with-business-rules"></a><span data-ttu-id="9f65b-102">Validación con reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="9f65b-102">Validation with Business Rules</span></span>
<span data-ttu-id="9f65b-103">Una forma habitual de realizar la validación consiste en crear un conjunto de reglas de negocios con el marco de trabajo reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="9f65b-103">A common way to do validation is to construct a set of business rules using the Business Rules Framework.</span></span> <span data-ttu-id="9f65b-104">y, a continuación, usar la forma Reglas de llamada en la orquestación en la que desea hacer la validación.</span><span class="sxs-lookup"><span data-stu-id="9f65b-104">Then you use the Call Rules shape in the orchestration where you want to perform validation.</span></span>  
  
 <span data-ttu-id="9f65b-105">En la aplicación de administración de procesos empresariales, el **validación** orquestación utiliza reglas de negocio para probar la validez del pedido.</span><span class="sxs-lookup"><span data-stu-id="9f65b-105">In the business process management application, the **Validation** orchestration uses business rules to test the validity of the order.</span></span>  
  
 <span data-ttu-id="9f65b-106">Usar el marco de trabajo de reglas de negocios le permite cambiar las reglas sin volver a compilar e implementar el **validación** orquestación.</span><span class="sxs-lookup"><span data-stu-id="9f65b-106">Using the Business Rules Framework enables you to change the rules without recompiling and redeploying the **Validation** orchestration.</span></span> <span data-ttu-id="9f65b-107">Esto se puede traducir en un menor tiempo de procesamiento de los conjuntos sencillos de reglas al codificar la lógica de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="9f65b-107">The trade-off is that for simple sets of rules, you may be able to save processing time by coding the logic in the orchestration.</span></span>  
  
 <span data-ttu-id="9f65b-108">Para obtener más información acerca de cómo utilizar el marco de trabajo de reglas de negocios, vea [crear y usar las reglas de negocios](../core/creating-and-using-business-rules.md).</span><span class="sxs-lookup"><span data-stu-id="9f65b-108">For more information about using the Business Rules Framework, see [Creating and Using Business Rules](../core/creating-and-using-business-rules.md).</span></span> <span data-ttu-id="9f65b-109">Para obtener más información sobre la forma reglas de llamada, vea [cómo usar la forma reglas de llamar a](../core/how-to-use-the-call-rules-shape.md).</span><span class="sxs-lookup"><span data-stu-id="9f65b-109">For more information about the Call Rules shape, see [How to Use the Call Rules Shape](../core/how-to-use-the-call-rules-shape.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f65b-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f65b-110">See Also</span></span>  
 <span data-ttu-id="9f65b-111">[Aspectos destacados de la implementación de la solución de administración de procesos empresariales](../core/implementation-highlights-of-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="9f65b-111">[Implementation Highlights of the Business Process Management Solution](../core/implementation-highlights-of-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="9f65b-112">Lógica del Administrador de procesos</span><span class="sxs-lookup"><span data-stu-id="9f65b-112">Process Manager Logic</span></span>](../core/process-manager-logic.md)