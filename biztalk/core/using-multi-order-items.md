---
title: Uso de elementos de múltiples pedidos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JD Edwards OneWorld adapters, multiple calls
- JD Edwards OneWorld adapters, multi-order numbers
- multiple edit line calls [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], multi-order numbers
- multi-order numbers [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], multiple calls
ms.assetid: 207ea92c-03f7-4117-8414-eb174e659d26
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 389e73ede2d1062c9907bd8640f38ce74ad6f316
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287260"
---
# <a name="using-multi-order-items"></a><span data-ttu-id="f2066-102">Uso de elementos de múltiples pedidos</span><span class="sxs-lookup"><span data-stu-id="f2066-102">Using Multi-Order Items</span></span>
<span data-ttu-id="f2066-103">Debido a la estructura de la API de JD Edwards OneWorld, si desea usar números de varios pedidos con BizTalk Server, debe realizar varias llamadas a la línea de edición en su orquestación para agregar estos elementos de línea en una orquestación.</span><span class="sxs-lookup"><span data-stu-id="f2066-103">Due to the structure of the JD Edwards OneWorld API, if you want to use multi-order numbers with BizTalk Server, you must make multiple edit line calls in your orchestration to add those line items in an orchestration.</span></span> <span data-ttu-id="f2066-104">Por ejemplo, un elemento de varios pedidos podría contener un encabezado con un único número de pedido, y detalles que incluyan varios pedidos de artículos (como Juguete 1EA, Guantes 2EA).</span><span class="sxs-lookup"><span data-stu-id="f2066-104">For example, a multi-order item might contain a header with a single order number, and detail that includes several items orders (like Toy 1EA, Gloves 2EA).</span></span>  
  
 <span data-ttu-id="f2066-105">Para usar varias llamadas de línea de edición, es responsabilidad del programador de BizTalk Server su estructuración.</span><span class="sxs-lookup"><span data-stu-id="f2066-105">To use multiple edit line calls, it is the responsibility of the BizTalk Server developer to structure them.</span></span> <span data-ttu-id="f2066-106">El programador debe crear un bucle interno en la orquestación para realizar dichas llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2066-106">The developer should create an internal loop in the orchestration to make those calls.</span></span>  
  
 <span data-ttu-id="f2066-107">El sistema JD Edwards OneWorld admite varias llamadas de línea de edición, pero no así la API.</span><span class="sxs-lookup"><span data-stu-id="f2066-107">The JD Edwards OneWorld system supports multiple edit line calls, but the API does not.</span></span> <span data-ttu-id="f2066-108">Si observa la estructura del método Editar línea, se trata de una estructura plana y no de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="f2066-108">If you look at the structure of the Edit Line method, it is a flat structure and not a sequence.</span></span> <span data-ttu-id="f2066-109">Por lo tanto, debe llamar a la función cada vez que desee insertar un artículo de línea.</span><span class="sxs-lookup"><span data-stu-id="f2066-109">Therefore, you must call the function every time you want to insert a line item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2066-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2066-110">See Also</span></span>  
 [<span data-ttu-id="f2066-111">Planeamiento y arquitectura</span><span class="sxs-lookup"><span data-stu-id="f2066-111">Planning and Architecture</span></span>](../core/planning-and-architecture17.md)