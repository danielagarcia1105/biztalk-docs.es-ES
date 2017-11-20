---
title: Es igual a | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac93031a-9d18-443d-9e38-71ef9edd5a30
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b82ac5c779dc6b4d3624b48cebe9df1bc3d1966
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="equals"></a><span data-ttu-id="836b6-102">Es igual a</span><span class="sxs-lookup"><span data-stu-id="836b6-102">Equals</span></span>
<span data-ttu-id="836b6-103">Quita los dos elementos principales de la pila, los compara y después inserta el resultado en la pila.</span><span class="sxs-lookup"><span data-stu-id="836b6-103">Removes the top two items from the stack, compares the two items, and then pushes the result onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="836b6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="836b6-104">Syntax</span></span>  
  
```  
  
<ic:Operation Name="Equals" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="836b6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="836b6-105">Parameters</span></span>  
 <span data-ttu-id="836b6-106">Dos elementos principales en la pila.</span><span class="sxs-lookup"><span data-stu-id="836b6-106">Top two items on the stack.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="836b6-107">Valor insertado</span><span class="sxs-lookup"><span data-stu-id="836b6-107">Pushed Value</span></span>  
 <span data-ttu-id="836b6-108">Cadena resultado de la operación de comparación.</span><span class="sxs-lookup"><span data-stu-id="836b6-108">String result of the comparison operation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="836b6-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="836b6-109">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="836b6-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="836b6-110">Example</span></span>  
 <span data-ttu-id="836b6-111">La siguiente expresión de filtro en el ejemplo se utiliza la **es igual a** operación al comparar el nombre de la actividad actual a la constante "CheckPO".</span><span class="sxs-lookup"><span data-stu-id="836b6-111">The following example filter expression uses the **Equals** operation to compare the current activity name to the constant "CheckPO".</span></span> <span data-ttu-id="836b6-112">Si ambas son iguales, la expresión se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="836b6-112">If the two are equal, the expression evaluates to `true`.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>CheckPO</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 <span data-ttu-id="836b6-113">Se puede caer en la tentación de crear la expresión tal y como se escribiría una instrucción en C# al realizar las comparaciones.</span><span class="sxs-lookup"><span data-stu-id="836b6-113">You may be tempted to build your expression exactly as you would write a statement in C# when performing comparisons.</span></span> <span data-ttu-id="836b6-114">Por ejemplo, si se quisieran comparar tres valores, la sintaxis en C# sería similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="836b6-114">For example, you might want to compare three values; in C# you would write something like:</span></span>  
  
```  
bool res = a == b == c;  
```  
  
 <span data-ttu-id="836b6-115">Sin embargo, como modelo para el filtro de expresión, no sería suficiente.</span><span class="sxs-lookup"><span data-stu-id="836b6-115">However, as a model for your expression filter this falls a little short.</span></span> <span data-ttu-id="836b6-116">En su lugar, veamos la instrucción modificada (pero equivalente):</span><span class="sxs-lookup"><span data-stu-id="836b6-116">Instead, consider the modified (but equivalent) statement:</span></span>  
  
```  
Bool res = (a == b) && (a == c);  
```  
  
 <span data-ttu-id="836b6-117">Se aproxima mucho más a la expresión de filtro que usaría para realizar la comparación.</span><span class="sxs-lookup"><span data-stu-id="836b6-117">This more closely matches the filter expression you would use to perform the comparison.</span></span> <span data-ttu-id="836b6-118">Para obtener más información y un ejemplo, vea [y](../core/and.md).</span><span class="sxs-lookup"><span data-stu-id="836b6-118">For more details and an example, see [And](../core/and.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="836b6-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="836b6-119">See Also</span></span>  
 [<span data-ttu-id="836b6-120">Operaciones de interceptor</span><span class="sxs-lookup"><span data-stu-id="836b6-120">Interceptor Operations</span></span>](../core/interceptor-operations.md)