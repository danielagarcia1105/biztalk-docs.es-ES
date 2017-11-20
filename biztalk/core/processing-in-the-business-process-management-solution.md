---
title: "El procesamiento en la solución de administración de procesos empresariales | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, processing
- processing, process management solutions
ms.assetid: 0b26447e-d8f1-4084-aa34-6e7f8ffccea5
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 145dd8e616048f1caaa1a59ec41d099e93e47880
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="processing-in-the-business-process-management-solution"></a><span data-ttu-id="7070b-102">Procesamiento en la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="7070b-102">Processing in the Business Process Management Solution</span></span>
<span data-ttu-id="7070b-103">Esta sección describe el funcionamiento de la solución de administración de procesos empresariales: cómo procesa los pedidos, se puede recuperar cómo hace uso de interrupciones y cómo controla las excepciones para que las acciones.</span><span class="sxs-lookup"><span data-stu-id="7070b-103">This section describes how the Business Process Management Solution works: how it processes orders, how it makes use of interrupts, and how it handles exceptions so that actions can be retried.</span></span>  
  
 <span data-ttu-id="7070b-104">Procesamiento de pedidos se basa en dos orquestaciones principales, **OrderBroker** y **OrderManager**.</span><span class="sxs-lookup"><span data-stu-id="7070b-104">Order processing relies on two main orchestrations, **OrderBroker** and **OrderManager**.</span></span> <span data-ttu-id="7070b-105">El **OrderBroker** orquestación está escrita de modo que puede haber varias orquestaciones de administrador de pedidos, uno para cada tipo de orden.</span><span class="sxs-lookup"><span data-stu-id="7070b-105">The **OrderBroker** orchestration is written so that there can be multiple order manager orchestrations, one for each kind of order.</span></span> <span data-ttu-id="7070b-106">La solución incluye sólo un **OrderManager**.</span><span class="sxs-lookup"><span data-stu-id="7070b-106">The solution includes only one **OrderManager**.</span></span> <span data-ttu-id="7070b-107">También es relativamente genérico para poder adaptarse a otros tipos de pedidos.</span><span class="sxs-lookup"><span data-stu-id="7070b-107">It, too, is relatively generic so that it can be adapted to other types of orders.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7070b-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7070b-108">In This Section</span></span>  
  
-   [<span data-ttu-id="7070b-109">Procesamiento en la orquestación OrderBroker</span><span class="sxs-lookup"><span data-stu-id="7070b-109">Processing in the OrderBroker Orchestration</span></span>](../core/processing-in-the-orderbroker-orchestration.md)  
  
-   [<span data-ttu-id="7070b-110">Lógica del Administrador de procesos</span><span class="sxs-lookup"><span data-stu-id="7070b-110">Process Manager Logic</span></span>](../core/process-manager-logic.md)  
  
-   [<span data-ttu-id="7070b-111">En las fases de procesamiento de orden de procesamiento</span><span class="sxs-lookup"><span data-stu-id="7070b-111">Processing in the Order Processing Stages</span></span>](../core/processing-in-the-order-processing-stages.md)  
  
-   [<span data-ttu-id="7070b-112">Control de interrupciones en la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="7070b-112">Interrupt Handling in the Business Process Management Solution</span></span>](../core/interrupt-handling-in-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="7070b-113">Control de excepciones en la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="7070b-113">Exception Handling in the Business Process Management Solution</span></span>](../core/exception-handling-in-the-business-process-management-solution.md)