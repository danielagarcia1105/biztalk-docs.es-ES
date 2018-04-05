---
title: Ámbito de las variables en orquestaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, variables
ms.assetid: 5856cdca-0ebd-4e16-8739-7bd50753b9f9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82803cd7f2b0beb8349e978fdd7b9e453dca31ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="variable-scope-in-orchestrations"></a><span data-ttu-id="e0e12-102">Ámbito de las variables en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="e0e12-102">Variable Scope in Orchestrations</span></span>
<span data-ttu-id="e0e12-103">Es necesario que comprenda algunas cuestiones importantes acerca de la visibilidad y el estado de las variables y los parámetros de las orquestaciones en varios lugares de una orquestación, incluidos los controladores de excepción y los bloques de compensación.</span><span class="sxs-lookup"><span data-stu-id="e0e12-103">There are a few important points to understand about the visibility and state of variables and orchestration parameters in various places within your orchestration, including exception handlers and compensation blocks.</span></span>  
  
-   <span data-ttu-id="e0e12-104">Los parámetros de una orquestación se pueden ver en el cuerpo de la orquestación y en el bloque de compensación correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e0e12-104">Orchestration parameters are visible throughout the body of the orchestration as well as in its compensation block.</span></span>  
  
-   <span data-ttu-id="e0e12-105">Las variables de nivel de ámbito se pueden ver en el cuerpo del ámbito, así como en todos los controlares de excepción y bloques de compensación correspondientes.</span><span class="sxs-lookup"><span data-stu-id="e0e12-105">Scope-level variables are visible in the body of the scope as well as in all of its exception handlers and compensation block.</span></span> <span data-ttu-id="e0e12-106">Dentro de los controladores de excepción, las variables se consideran no inicializadas, ya que no se puede determinar si la excepción que provocó un controlador concreto tuvo lugar antes o después de cualquier inicialización en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="e0e12-106">Inside exception handlers, the variables are considered un-initialized since it is indeterminate whether the exception that led to a given handler took place before or after any initialization in the body.</span></span> <span data-ttu-id="e0e12-107">Por este motivo, si declara una variable en un ámbito y la inicializa en el cuerpo, no podrá leerla en un controlador de excepción u obtendrá un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="e0e12-107">For this reason, if you declare a variable in a scope and initialize it in the body, you cannot read from it in an exception handler, or you will get a compiler error.</span></span> <span data-ttu-id="e0e12-108">Existe una solución a este error en el caso de las transacciones de larga ejecución.</span><span class="sxs-lookup"><span data-stu-id="e0e12-108">A workaround for that exists in the case of long running transactions.</span></span> <span data-ttu-id="e0e12-109">El siguiente ejemplo muestra cómo se puede usar el operador succeeded() para garantizar un comportamiento adecuado en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="e0e12-109">The following example shows how the succeeded() operator can be used to ensure proper runtime behavior:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0e12-110">El código siguiente es un pseudocódigo que describe un proceso lógico; este código no se puede usar en una forma Expresión de orquestación.</span><span class="sxs-lookup"><span data-stu-id="e0e12-110">The code below is pseudo code that describes a logical process; this code cannot be used within an Orchestration Expression shape.</span></span>  
  
    ```  
    scope longrunning transaction L  
    {  
       System.Int32 i;  
       System.Int32 v;  
       body  
       {  
          i = 3;  
          scope longrunning transaction T  
          {  
             body  
             {  
                i = 5;  
             }  
          }  
       }  
       exceptions  
       {  
          catch  
          {  
             if(succeeded(T))  
             {  
                v = i;  // OK to read from it here — no compiler errors!  
             }  
          }  
       }  
    }  
    ```  
  
-   <span data-ttu-id="e0e12-111">Dentro de un bloque de compensación, todas las variables asumen los valores que tenían en el momento de confirmarse el cuerpo del ámbito.</span><span class="sxs-lookup"><span data-stu-id="e0e12-111">Inside a compensation block, all variables assume the values they had when the body of the scope committed.</span></span> <span data-ttu-id="e0e12-112">Tenga en cuenta que el bloque de compensación de un ámbito nunca se ejecuta justo después de que finalice el cuerpo; siempre hay código que interviene.</span><span class="sxs-lookup"><span data-stu-id="e0e12-112">Note that the compensation block of a scope never runs immediately after its body completes; there is always intervening code.</span></span> <span data-ttu-id="e0e12-113">Si parte de ese código que interviene actualiza algunas variables de ámbito externo y, a continuación, se ejecuta el bloque de compensación, dichas actualizaciones no se verán dentro del bloque de compensación.</span><span class="sxs-lookup"><span data-stu-id="e0e12-113">If any of that intervening code updates some outer-scope variables, and then the compensation block runs, those updates will not be seen inside the compensation block.</span></span> <span data-ttu-id="e0e12-114">En lugar de ello, el valor de las variables se revertirá al existente en el momento de confirmarse el ámbito que es propietario de esa compensación.</span><span class="sxs-lookup"><span data-stu-id="e0e12-114">Instead the variables will temporarily revert to the values they had at the time the scope which owns that compensation had committed.</span></span>  
  
-   <span data-ttu-id="e0e12-115">Cuando una transacción está anidada dentro de un bucle, la transacción se compensa tantas veces como se ejecuta el bucle.</span><span class="sxs-lookup"><span data-stu-id="e0e12-115">When a transaction is nested inside a loop, the transaction will be compensated as many times as the loop executes.</span></span> <span data-ttu-id="e0e12-116">Dentro del bloque de compensación, para cada iteración, las variables de ámbito externo asumirán los valores que tenían en el momento de confirmarse la iteración de la transacción.</span><span class="sxs-lookup"><span data-stu-id="e0e12-116">Inside the compensation block for each iteration, outer-scope variables assume the values they had at the time of the iteration of the transaction committed.</span></span>  
  
-   <span data-ttu-id="e0e12-117">Cualquier actualización realizada en las variables de ámbito externo o en los parámetros de la orquestación dentro de los bloques de compensación de los ámbitos internos no se verá después de que el bloque de compensación finalice.</span><span class="sxs-lookup"><span data-stu-id="e0e12-117">Any updates made to outer-scope variables or orchestration parameters inside compensation blocks of inner scopes will not be visible after the compensation block completes.</span></span> <span data-ttu-id="e0e12-118">En otras palabras, el bloque de compensación no se puede usar para modificar directamente los valores de las variables de ámbito externo.</span><span class="sxs-lookup"><span data-stu-id="e0e12-118">In other words, the compensation block cannot be used to directly modify the values of outer-scope variables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0e12-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0e12-119">See Also</span></span>  
 [<span data-ttu-id="e0e12-120">Tipos de datos de XLANG-s</span><span class="sxs-lookup"><span data-stu-id="e0e12-120">XLANG-s Data Types</span></span>](../core/xlang-s-data-types.md)