---
title: El adaptador Ops | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, Ops adapters
- Ops adapters, about Ops adapters
- Ops adapters
- process management solution tutorial, Ops adapters
- process management solution tutorial, errors
ms.assetid: 7f747a5f-14af-4e4c-bc29-f083f8f00bd0
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67463adf4e1e960ab6608e67595a679804aa223e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-ops-adapter"></a><span data-ttu-id="50031-102">El adaptador Ops</span><span class="sxs-lookup"><span data-stu-id="50031-102">The Ops Adapter</span></span>
<span data-ttu-id="50031-103">El diseño de la solución tiene como finalidad pasar, siempre que sea posible, mensajes problemáticos y errores a sistemas de operaciones que tomen una decisión respecto a si corregir el error o finalizar el pedido.</span><span class="sxs-lookup"><span data-stu-id="50031-103">The design of the solution is to pass, where possible, problematic messages and errors to operations systems that make a decision about fixing the error or terminating the order.</span></span> <span data-ttu-id="50031-104">El adaptador Ops, combinado con la característica de elaboración de informes de errores nueva, controla muchos de estos casos.</span><span class="sxs-lookup"><span data-stu-id="50031-104">The Ops adapter, combined with the new error reporting feature, handles many of these cases.</span></span>  
  
 <span data-ttu-id="50031-105">La solución utiliza el adaptador en un puerto configurado para utilizar la característica de elaboración de informes de errores nueva.</span><span class="sxs-lookup"><span data-stu-id="50031-105">The solution uses the adapter on a port configured to use the new error reporting feature.</span></span> <span data-ttu-id="50031-106">Cuando recibe un error, el adaptador llama a dos métodos, **inicializar** y **Execute**, en una clase en un ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="50031-106">When it receives an error, the adapter calls two methods, **Initialize** and **Execute**, on a class in a specified assembly.</span></span> <span data-ttu-id="50031-107">En la solución, estos métodos envían el error al grupo de operaciones correcto.</span><span class="sxs-lookup"><span data-stu-id="50031-107">In the solution, these methods send the error to the correct operations group.</span></span>  
  
 <span data-ttu-id="50031-108">La solución incluye un controlador de ejemplos, aunque puede escribir fácilmente uno propio y usar el adaptador en otras soluciones.</span><span class="sxs-lookup"><span data-stu-id="50031-108">The solution includes a sample handler, although you can easily write your own and use the adapter in other solutions.</span></span> <span data-ttu-id="50031-109">Para obtener información general sobre la nueva característica informes de errores, vea [enrutamiento de mensajes de error utilizando](../core/using-failed-message-routing.md).</span><span class="sxs-lookup"><span data-stu-id="50031-109">For general information about the new error reporting feature, see [Using Failed Message Routing](../core/using-failed-message-routing.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50031-110">El adaptador Ops se genera con el Marco de trabajo de adaptadores.</span><span class="sxs-lookup"><span data-stu-id="50031-110">The Ops adapter is built using the Adapter Framework.</span></span> <span data-ttu-id="50031-111">Para obtener información sobre la creación de adaptadores con el marco de trabajo, consulte [desarrollar adaptadores Custom](../core/developing-custom-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="50031-111">For information about building adapters with the framework, see [Developing Custom Adapters](../core/developing-custom-adapters.md).</span></span>  
  
 <span data-ttu-id="50031-112">En esta sección se explica cómo funciona el adaptador y cómo se configura. Asimismo, se suministran los detalles acerca de los ensamblados controladores de errores.</span><span class="sxs-lookup"><span data-stu-id="50031-112">This section describes how the adapter works and how to configure it, and provides details about the error handler assemblies.</span></span> <span data-ttu-id="50031-113">La sección concluye con los datos de implementación que podrían resultar útiles a los usuarios que deseen modificar el adaptador o utilizarlo en otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="50031-113">The section concludes with implementation details that would be helpful to users who wish to modify the adapter or use it in other applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="50031-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="50031-114">In This Section</span></span>  
  
-   [<span data-ttu-id="50031-115">Usar el adaptador Ops</span><span class="sxs-lookup"><span data-stu-id="50031-115">Using the Ops Adapter</span></span>](../core/using-the-ops-adapter.md)  
  
-   [<span data-ttu-id="50031-116">El controlador de errores de las operaciones de ejemplo</span><span class="sxs-lookup"><span data-stu-id="50031-116">The Sample Operations Error Handler</span></span>](../core/the-sample-operations-error-handler.md)  
  
-   [<span data-ttu-id="50031-117">Detalles de implementación del adaptador OPS</span><span class="sxs-lookup"><span data-stu-id="50031-117">Ops Adapter Implementation Details</span></span>](../core/ops-adapter-implementation-details.md)