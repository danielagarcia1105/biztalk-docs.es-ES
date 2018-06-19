---
title: Y | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80bd8f1f-edae-476d-b488-78e6c5ee70bf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 676940dfa5cbc23d0c8127923d292e382a4e3cad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230020"
---
# <a name="and"></a><span data-ttu-id="43cbf-102">And</span><span class="sxs-lookup"><span data-stu-id="43cbf-102">And</span></span>
<span data-ttu-id="43cbf-103">Quita los dos elementos principales de la pila, realiza un booleano **AND** de los dos elementos y, a continuación, inserta el resultado en la pila.</span><span class="sxs-lookup"><span data-stu-id="43cbf-103">Removes the top two items from the stack, performs a Boolean **AND** of the two items, and then pushes the result onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43cbf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43cbf-104">Syntax</span></span>  
  
```  
  
<ic:Operation Name="And" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="43cbf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="43cbf-105">Parameters</span></span>  
 <span data-ttu-id="43cbf-106">Dos elementos principales en la pila.</span><span class="sxs-lookup"><span data-stu-id="43cbf-106">Top two items on the stack.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="43cbf-107">Valor insertado</span><span class="sxs-lookup"><span data-stu-id="43cbf-107">Pushed Value</span></span>  
 <span data-ttu-id="43cbf-108">Cadena resultado booleano **AND** operación.</span><span class="sxs-lookup"><span data-stu-id="43cbf-108">String result of the Boolean **AND** operation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43cbf-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="43cbf-109">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="43cbf-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="43cbf-110">Example</span></span>  
 <span data-ttu-id="43cbf-111">El **y** operación es útil cuando necesita evaluar varias instrucciones.</span><span class="sxs-lookup"><span data-stu-id="43cbf-111">The **And** operation is useful when you need to evaluate multiple statements.</span></span> <span data-ttu-id="43cbf-112">La expresión de filtro de ejemplo siguiente comprueba si el nombre de actividad es "CheckPO" y se cierra el evento de actividad mediante el uso de la **y** operación.</span><span class="sxs-lookup"><span data-stu-id="43cbf-112">The following example filter expression checks whether the activity name is "CheckPO" and the activity event is closed by using the **And** operation.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>CheckPO</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityEvent"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <ic:Operation Name="And"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 <span data-ttu-id="43cbf-113">En este ejemplo **y** es la operación final en la expresión porque se basa en los resultados de las comparaciones (y saca de la pila para realizar la comparación).</span><span class="sxs-lookup"><span data-stu-id="43cbf-113">In this example **And** is the final operation in the expression because it relies on the results of the comparisons (and pops them from the stack to perform the comparison).</span></span> <span data-ttu-id="43cbf-114">Puede ampliar esta idea para realizar **y** operaciones en más de dos elementos.</span><span class="sxs-lookup"><span data-stu-id="43cbf-114">You can extend this idea to perform **And** operations on more than two items.</span></span> <span data-ttu-id="43cbf-115">Por ejemplo, para evaluar si se cumplen las condiciones A, B y C, se usaría una expresión como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="43cbf-115">For example, to evaluate whether Condition A and Condition B and Condition C are true, you would use an expression like the following:</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>CheckPO</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityEvent"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityType"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyType</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <ic:Operation Name="And"/>  
    <ic:Operation Name="And"/>  
  </ic:Expression>  
</ic:Filter>   
```  
  
## <a name="see-also"></a><span data-ttu-id="43cbf-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="43cbf-116">See Also</span></span>  
 [<span data-ttu-id="43cbf-117">Operaciones de interceptor</span><span class="sxs-lookup"><span data-stu-id="43cbf-117">Interceptor Operations</span></span>](../core/interceptor-operations.md)