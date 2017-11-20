---
title: "Cómo configurar la forma Iniciar excepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Throw Exception shape [Orchestration Designer]
- orchestrations, errors
- Orchestration Designer, errors
ms.assetid: d3190f1b-db5e-4988-bff6-f7a276760ece
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07d156572484ba4fbe71533252ce4fe956136699
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-throw-exception-shape"></a><span data-ttu-id="a229f-102">Cómo configurar la forma Iniciar excepción</span><span class="sxs-lookup"><span data-stu-id="a229f-102">How to Configure the Throw Exception Shape</span></span>
<span data-ttu-id="a229f-103">Puede iniciar excepciones explícitamente en una orquestación mediante el uso de la **Iniciar excepción** forma.</span><span class="sxs-lookup"><span data-stu-id="a229f-103">You can explicitly throw exceptions in an orchestration by using the **Throw Exception** shape.</span></span> <span data-ttu-id="a229f-104">Cuando se lleva a cabo el inicio, el motor de tiempo de ejecución buscará el controlador de excepción más próximo que pueda controlar el tipo de excepción que se inicia.</span><span class="sxs-lookup"><span data-stu-id="a229f-104">When the throw is performed, the runtime engine will search for the nearest exception handler that can handle the type of exception being thrown.</span></span>  
  
 <span data-ttu-id="a229f-105">En primer lugar, se busca un ámbito de inclusión en la orquestación actual y se consideran los controladores de excepción asociados del ámbito para buscar el controlador apropiado para el tipo de excepción que se inicia.</span><span class="sxs-lookup"><span data-stu-id="a229f-105">First, the current orchestration is searched for an enclosing scope, and the associated exception handlers of the scope are considered in order to locate the appropriate handler for the type of exception that has been thrown.</span></span>  
  
 <span data-ttu-id="a229f-106">Si no se encuentra ningún controlador de excepción apropiado, se busca un ámbito que contenga el punto de la llamada a la orquestación en uso en la orquestación que llamó a la orquestación actual.</span><span class="sxs-lookup"><span data-stu-id="a229f-106">If no appropriate exception handler is found, the orchestration that called the current orchestration is searched for a scope that encloses the point of the call to the current orchestration.</span></span> <span data-ttu-id="a229f-107">Esta búsqueda continúa hasta que se encuentra un controlador de excepción que pueda controlar la excepción actual.</span><span class="sxs-lookup"><span data-stu-id="a229f-107">This search continues until an exception handler is found that can handle the current exception.</span></span>  
  
 <span data-ttu-id="a229f-108">Una coincidencia exacta para la excepción es una clase de excepción de la misma clase o de una clase base que el tipo de excepción en tiempo de ejecución que se inicia.</span><span class="sxs-lookup"><span data-stu-id="a229f-108">An exact match for the exception is an exception class that is of the same class as, or a base class of, the run-time type of the exception being thrown.</span></span>  
  
 <span data-ttu-id="a229f-109">Cuando se encuentra un controlador de excepción coincidente, el control se transfiere a la primera instrucción del controlador de excepción.</span><span class="sxs-lookup"><span data-stu-id="a229f-109">After a matching exception handler is found, control is transferred to the first statement of the exception handler.</span></span>  
  
 <span data-ttu-id="a229f-110">Si se produce un error en la búsqueda de controladores de excepción coincidentes, la orquestación se detiene.</span><span class="sxs-lookup"><span data-stu-id="a229f-110">If the search for matching exception handlers fails, the orchestration halts.</span></span> <span data-ttu-id="a229f-111">Las transacciones pueden ayudar a minimizar el impacto de dicha ocurrencia.</span><span class="sxs-lookup"><span data-stu-id="a229f-111">Transactions can help you minimize the impact of such an occurrence.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="a229f-112">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="a229f-112">Procedure</span></span>  
  
#### <a name="to-configure-a-throw-exception-shape"></a><span data-ttu-id="a229f-113">Para configurar la forma Iniciar excepción</span><span class="sxs-lookup"><span data-stu-id="a229f-113">To configure a Throw Exception shape</span></span>  
  
-   <span data-ttu-id="a229f-114">En la ventana Propiedades, seleccione un tipo de objeto disponible para iniciar desde el **objeto de excepción** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="a229f-114">In the Properties window, select an available object type to throw from the **Exception Object** drop-down list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a229f-115">Seleccione excepción General en el **Iniciar excepción** if de forma única el **Iniciar excepción** forma es dentro de un controlador de excepciones y desea volver a producir la excepción detectada en el controlador de excepción actual.</span><span class="sxs-lookup"><span data-stu-id="a229f-115">Select General Exception in the **Throw Exception** shape only if the **Throw Exception** shape is within an exception handler and you want to rethrow the exception caught in the current exception handler.</span></span> <span data-ttu-id="a229f-116">Recibirá un error durante la compilación si utiliza excepción General para un **Iniciar excepción** forma en cualquier otro contexto.</span><span class="sxs-lookup"><span data-stu-id="a229f-116">You will receive an error during the compile if you use General Exception for a **Throw Exception** shape in any other context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a229f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="a229f-117">See Also</span></span>  
 [<span data-ttu-id="a229f-118">Excepciones</span><span class="sxs-lookup"><span data-stu-id="a229f-118">Exceptions</span></span>](../core/exceptions.md)