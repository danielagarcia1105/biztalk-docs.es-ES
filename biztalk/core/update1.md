---
title: Update 1 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Update function [Business Rules Engine]
- Update function [Business Rules Engine], TypedXMLDocument
- Update function [Business Rules Engine], TypedData table
- Update function [Business Rules Engine], .NET objects
- .NET objects
- Update function [Business Rules Engine], DataConnection
ms.assetid: 939e45dc-6433-42f3-a336-8f3c247417ac
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccb9c8e8b75bc67954c30bf2b4a6e6ff39b3ee01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008829"
---
# <a name="update"></a><span data-ttu-id="806fe-102">Update</span><span class="sxs-lookup"><span data-stu-id="806fe-102">Update</span></span>
<span data-ttu-id="806fe-103">Cuando **actualización** se invoca la función de un objeto, el objeto se vuelve a imponer en el motor para volverse a evaluar, basándose en los nuevos datos y el estado.</span><span class="sxs-lookup"><span data-stu-id="806fe-103">When **Update** function is invoked an object, the object is reasserted into the engine to be re-evaluated, based on the new data and state.</span></span> <span data-ttu-id="806fe-104">El objeto puede ser de tipo **TypedXmlDocument** o clase .NET o **DataConnection** o **TypedDataTable**.</span><span class="sxs-lookup"><span data-stu-id="806fe-104">The object can be of type **TypedXmlDocument** or .NET class or **DataConnection** or **TypedDataTable**.</span></span>  
  
 <span data-ttu-id="806fe-105">También puede usar **actualización** función para mejorar el rendimiento del motor y evitar escenarios de bucle sin fin, como se describe en este tema.</span><span class="sxs-lookup"><span data-stu-id="806fe-105">You can also use **Update** function to improve engine performance and prevent endless loop scenarios as described in this topic.</span></span>  
  
 <span data-ttu-id="806fe-106">Normalmente, se utiliza **Assert** para colocar un nuevo objeto en la memoria de trabajo del motor de reglas y usar **actualizar** para actualizar un objeto ya existente en la memoria de trabajo.</span><span class="sxs-lookup"><span data-stu-id="806fe-106">Typically, you use **Assert** to place a new object in the working memory of the rule engine, and use **Update** to update an already existing object in the working memory.</span></span> <span data-ttu-id="806fe-107">Cuando se impone un objeto nuevo, se evalúan las condiciones de todas las reglas.</span><span class="sxs-lookup"><span data-stu-id="806fe-107">When you assert a new object, conditions in all the rules are evaluated.</span></span> <span data-ttu-id="806fe-108">Cuando se actualiza un objeto existente, solo se vuelven a evaluar las condiciones que usan el hecho actualizado, y las acciones se agregan a la agenda si estas condiciones se evalúan como true.</span><span class="sxs-lookup"><span data-stu-id="806fe-108">When you update an existing object, only conditions that use the updated fact are reevaluated, and actions are added to the agenda if these conditions are evaluated to true.</span></span>  
  
## <a name="using-update-function-on-net-facts"></a><span data-ttu-id="806fe-109">Uso de la función Actualizar en hechos .NET</span><span class="sxs-lookup"><span data-stu-id="806fe-109">Using Update function on .NET facts</span></span>  
 <span data-ttu-id="806fe-110">Supongamos las dos reglas siguientes como ejemplo.</span><span class="sxs-lookup"><span data-stu-id="806fe-110">Take the two rules that follow as an example.</span></span> <span data-ttu-id="806fe-111">Supongamos que los objetos **ItemA** y **ItemB** ya existen en la memoria de trabajo.</span><span class="sxs-lookup"><span data-stu-id="806fe-111">Suppose that objects **ItemA** and **ItemB** already exist in working memory.</span></span> <span data-ttu-id="806fe-112">La regla 1 evalúa el **Id** propiedad en **ItemA**, Establece el **Id** propiedad en **ItemB**y, a continuación, vuelve a imponer **ItemB** después del cambio.</span><span class="sxs-lookup"><span data-stu-id="806fe-112">Rule 1 evaluates the **Id** property on **ItemA**, sets the **Id** property on **ItemB**, and then reasserts **ItemB** after the change.</span></span> <span data-ttu-id="806fe-113">Cuando **ItemB** se vuelve a imponer, se trata como un nuevo objeto y el motor vuelve a evaluar todas las reglas que usan el objeto **ItemB** en los predicados o acciones.</span><span class="sxs-lookup"><span data-stu-id="806fe-113">When **ItemB** is reasserted, it is treated as a new object and the engine re-evaluates all rules that use object **ItemB** in the predicates or actions.</span></span> <span data-ttu-id="806fe-114">Esto garantiza que la regla 2 se vuelve a evaluar con el nuevo valor de **ItemB.Id**, como se establece en la regla 1.</span><span class="sxs-lookup"><span data-stu-id="806fe-114">This ensures that Rule 2 is re-evaluated against the new value of **ItemB.Id**, as set in Rule 1.</span></span> <span data-ttu-id="806fe-115">Regla 2 puede haber un error la primera vez se evaluó, pero se evalúa como **true** la segunda vez que se evalúa.</span><span class="sxs-lookup"><span data-stu-id="806fe-115">Rule 2 may have failed the first time it was evaluated, but evaluates to **true** the second time it is evaluated.</span></span>  
  
### <a name="rule-1"></a><span data-ttu-id="806fe-116">Regla 1</span><span class="sxs-lookup"><span data-stu-id="806fe-116">Rule 1</span></span>  
  
```  
IF ItemA.Id == 1  
THEN ItemB.Id = 2  
Assert(ItemB)  
```  
  
### <a name="rule-2"></a><span data-ttu-id="806fe-117">Regla 2</span><span class="sxs-lookup"><span data-stu-id="806fe-117">Rule 2</span></span>  
  
```  
IF ItemB.Id == 2  
THEN ItemB.Value = 100  
```  
  
 <span data-ttu-id="806fe-118">Esta capacidad de volver a imponer objetos en la memoria de trabajo permite al usuario tener un control explícito sobre el comportamiento en los escenarios de encadenamiento directo.</span><span class="sxs-lookup"><span data-stu-id="806fe-118">This ability to reassert objects into working memory allows the user explicit control over the behavior in forward-chaining scenarios.</span></span> <span data-ttu-id="806fe-119">Sin embargo, un efecto secundario de esta reimposición en este ejemplo es que la Regla 1 también se vuelve a evaluar.</span><span class="sxs-lookup"><span data-stu-id="806fe-119">A side effect of the reassertion in this example, however, is that Rule 1 is also re-evaluated.</span></span> <span data-ttu-id="806fe-120">Dado que **ItemA.Id** no se ha cambiado, la regla 1 vuelve a evaluar en **true** y **itemb** acción activa de nuevo.</span><span class="sxs-lookup"><span data-stu-id="806fe-120">Because **ItemA.Id** was not changed, Rule 1 again evaluates to **true** and the **Assert(ItemB)** action fires again.</span></span> <span data-ttu-id="806fe-121">En consecuencia, la regla crea una situación de bucle infinito.</span><span class="sxs-lookup"><span data-stu-id="806fe-121">As a result, the rule creates an endless loop situation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="806fe-122">El número de bucle máximo predeterminado de reevaluación de reglas es 2 ^ 32.</span><span class="sxs-lookup"><span data-stu-id="806fe-122">The default maximum loop count of re-evaluation of rules is 2^32.</span></span> <span data-ttu-id="806fe-123">Para ciertas reglas, la ejecución de directiva podría tardar mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="806fe-123">For certain rules, the policy execution could last for a long time.</span></span> <span data-ttu-id="806fe-124">Puede reducir el recuento ajustando el **profundidad máxima de bucle de ejecución** propiedad de la versión de directiva.</span><span class="sxs-lookup"><span data-stu-id="806fe-124">You can reduce the count by adjusting the **Maximum Execution Loop Depth** property of the policy version.</span></span>  
  
 <span data-ttu-id="806fe-125">Deberá volver a imponer objetos sin crear bucles infinitos y el **actualización** función ofrece esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="806fe-125">You need to be able to reassert objects without creating endless loops, and the **Update** function provides this capability.</span></span> <span data-ttu-id="806fe-126">Al igual que un reassert, el **actualización** función realiza **Retract** y **Assert** de las instancias de objeto asociado, que se han cambiado de acciones de regla, pero hay dos diferencias clave:</span><span class="sxs-lookup"><span data-stu-id="806fe-126">Like a reassert, the **Update** function performs **Retract** and **Assert** of the associated object instances, which have been changed from rule actions, but there are two key differences:</span></span>  
  
- <span data-ttu-id="806fe-127">Las acciones de la agenda para las reglas en las que el tipo de instancia solo se utiliza en las acciones (no en los predicados) permanecerán en la agenda.</span><span class="sxs-lookup"><span data-stu-id="806fe-127">Actions on the agenda for rules where the instance type is only used in the actions (not the predicates) will remain on the agenda.</span></span>  
  
- <span data-ttu-id="806fe-128">Las reglas que solo utilizan el tipo de instancia en las acciones no se volverán a evaluar.</span><span class="sxs-lookup"><span data-stu-id="806fe-128">Rules that only use the instance type in the actions will not be re-evaluated.</span></span>  
  
  <span data-ttu-id="806fe-129">Por lo tanto, las reglas que utilizan los tipos de instancia solo en los predicados, o tanto en los predicados como en la  acciones, se volverán a evaluar y sus acciones se agregarán a la agenda según corresponda.</span><span class="sxs-lookup"><span data-stu-id="806fe-129">Therefore, rules that use the instance types in either the predicates only or both the predicates and actions will be re-evaluated and their actions added to the agenda as appropriate.</span></span>  
  
  <span data-ttu-id="806fe-130">Cambiar el ejemplo anterior se usan los **actualización** función garantiza que solo la regla 2 se vuelve a evaluar porque **ItemB** se utiliza en la condición de la regla 2.</span><span class="sxs-lookup"><span data-stu-id="806fe-130">Changing the preceding example to use the **Update** function ensures that only Rule 2 is re-evaluated because **ItemB** is used in the condition of Rule 2.</span></span> <span data-ttu-id="806fe-131">Regla 1 no se reevalúa porque **ItemB** solo se usa en las acciones de la regla 1, lo que elimina el escenario de bucle.</span><span class="sxs-lookup"><span data-stu-id="806fe-131">Rule 1 is not reevaluated because **ItemB** is only used in the actions of Rule 1, eliminating the looping scenario.</span></span>  
  
### <a name="rule-1"></a><span data-ttu-id="806fe-132">Regla 1</span><span class="sxs-lookup"><span data-stu-id="806fe-132">Rule 1</span></span>  
  
```  
IF ItemA.Id == 1  
THEN ItemB.Id = 2  
Update(ItemB)  
```  
  
### <a name="rule-2"></a><span data-ttu-id="806fe-133">Regla 2</span><span class="sxs-lookup"><span data-stu-id="806fe-133">Rule 2</span></span>  
  
```  
IF ItemB.Id == 2  
THEN ItemB.Value = 100  
```  
  
 <span data-ttu-id="806fe-134">No obstante, todavía es posible crear escenarios de bucle.</span><span class="sxs-lookup"><span data-stu-id="806fe-134">However, it is still possible to create looping scenarios.</span></span> <span data-ttu-id="806fe-135">Por ejemplo, considere la siguiente regla.</span><span class="sxs-lookup"><span data-stu-id="806fe-135">For example, consider the following rule.</span></span>  
  
### <a name="rule-1"></a><span data-ttu-id="806fe-136">Regla 1</span><span class="sxs-lookup"><span data-stu-id="806fe-136">Rule 1</span></span>  
  
```  
IF ItemA.Id == 1  
THEN ItemA.Value = 20  
Update(ItemA)  
```  
  
 <span data-ttu-id="806fe-137">Dado que **ItemA** se usa en el predicado, se vuelve a evaluar cuando **actualización** se llama en **ItemA**.</span><span class="sxs-lookup"><span data-stu-id="806fe-137">Because **ItemA** is used in the predicate, it is re-evaluated when **Update** is called on **ItemA**.</span></span> <span data-ttu-id="806fe-138">Si el valor de **ItemA.Id** no se cambia en otra parte, la regla 1 sigue evaluando en **true**, haciendo que **actualización** que se llamará una vez más en A. El Diseñador de reglas debe asegurarse de que no se creen escenarios de bucle como éste.</span><span class="sxs-lookup"><span data-stu-id="806fe-138">If the value of **ItemA.Id** is not changed elsewhere, Rule 1 continues to evaluate to **true**, causing **Update** to once again be called on A. The rule designer must ensure that looping scenarios such as this are not created.</span></span>  
  
 <span data-ttu-id="806fe-139">El enfoque adecuado para esto será distinto en función de la naturaleza de las reglas.</span><span class="sxs-lookup"><span data-stu-id="806fe-139">The appropriate approach for this will differ based on the nature of the rules.</span></span> <span data-ttu-id="806fe-140">A continuación, se muestra un mecanismo sencillo para solucionar el problema del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="806fe-140">The following is a simple mechanism to solve the problem in the preceding example.</span></span>  
  
 <span data-ttu-id="806fe-141">El **actualización** función puede utilizarse en el Compositor de reglas de negocio con una referencia a la clase, como ocurre con la **Assert**, **Retract**, o **RetractByType** funciones.</span><span class="sxs-lookup"><span data-stu-id="806fe-141">The **Update** function may be used in the Business Rule Composer with a reference to the class, as with the **Assert**, **Retract**, or **RetractByType** functions.</span></span>  
  
### <a name="rule-1"></a><span data-ttu-id="806fe-142">Regla 1</span><span class="sxs-lookup"><span data-stu-id="806fe-142">Rule 1</span></span>  
  
```  
IF ItemA.Id == 1 and ItemA.Value != 20  
THEN ItemA.Value = 20  
Update(ItemA)  
```  
  
 <span data-ttu-id="806fe-143">Al agregar la comprobación en **ItemA.Value** impide que la regla 1 evalúe **true** nuevamente después de que se ejecutan las acciones de la regla 1 la primera vez.</span><span class="sxs-lookup"><span data-stu-id="806fe-143">Adding the check on **ItemA.Value** prevents Rule 1 from evaluating to **true** again after the actions of Rule 1 are executed the first time.</span></span>  
  
## <a name="using-update-function-on-xml-facts"></a><span data-ttu-id="806fe-144">Uso de la función Actualizar en hechos XML</span><span class="sxs-lookup"><span data-stu-id="806fe-144">Using Update function on XML facts</span></span>  
 <span data-ttu-id="806fe-145">Supongamos las dos reglas siguientes como ejemplo.</span><span class="sxs-lookup"><span data-stu-id="806fe-145">Take the two rules that follow as an example.</span></span> <span data-ttu-id="806fe-146">Suponga que.</span><span class="sxs-lookup"><span data-stu-id="806fe-146">Suppose that.</span></span> <span data-ttu-id="806fe-147">La Regla 1 evalúa el número total de elementos de un mensaje de pedido y la Regla 2 establece el estado en "Pendiente de aprobación" si el número total es mayor que o igual a 10.</span><span class="sxs-lookup"><span data-stu-id="806fe-147">Rule 1 evaluates the total count of the items in a purchase order message, and rule2 sets the status to "Needs approval" if the total count is greater than or equal to 10.</span></span>  
  
### <a name="rule-1"></a><span data-ttu-id="806fe-148">Regla 1</span><span class="sxs-lookup"><span data-stu-id="806fe-148">Rule 1</span></span>  
  
```  
IF 1 == 1  
THEN ProcessPO.Order:/Order/Items/TotalCount = (ProcessPO.Order:/Order/Items/TotalCount + ProcessPO:/Order/Items/Item/Count)  
```  
  
### <a name="rule-2"></a><span data-ttu-id="806fe-149">Regla 2</span><span class="sxs-lookup"><span data-stu-id="806fe-149">Rule 2</span></span>  
  
```  
IF ProcessPO.Order:/Order/Items/TotalCount >= 10  
THEN ProcessPO.Order:/Order/Status = "Needs approval"  
```  
  
 <span data-ttu-id="806fe-150">Si se pasa el siguiente mensaje de pedido (PO) como entrada para esta directiva, observará que el estado no se establece en "Pendiente de aprobación" aunque el número de elementos totales es 14.</span><span class="sxs-lookup"><span data-stu-id="806fe-150">If you pass the following purchase order (PO) message as an input to this policy, you notice that the status is not set to "Needs approval" even though the total item count is 14.</span></span> <span data-ttu-id="806fe-151">Es dado que la regla rule2 se evalúa solo al principio cuando el valor de la **TotalCount** campo es 0, y la regla no se evalúa cada vez que se actualiza el recuento total disponible.</span><span class="sxs-lookup"><span data-stu-id="806fe-151">It is because that the rule2 is evaluated only at the beginning when the value of the **TotalCount** field is 0, and the rule is not evaluated each time the total available count is updated.</span></span> <span data-ttu-id="806fe-152">Para que las condiciones vuelven a evaluar cada vez que el **TotalCount** está actualizado, debe llamar a la **actualización** función en el nodo primario (**elementos**) del nodo modificado ( **TotalCount**).</span><span class="sxs-lookup"><span data-stu-id="806fe-152">To have the conditions reevaluated each time the **TotalCount** is updated, you need to call the **Update** function on the parent node (**Items**) of the modified node (**TotalCount**).</span></span> <span data-ttu-id="806fe-153">Si cambia la Regla según se muestra abajo, y la prueba otra vez, debe ver el valor del campo Estado establecido en "Pendiente de aprobación".</span><span class="sxs-lookup"><span data-stu-id="806fe-153">If you change the Rule1 as shown below, and test it one more time, you should see the value of the Status field set to "Needs Approval".</span></span>  
  
```  
<ns0:Order xmlns:ns0="http://ProcessPO.Order">  
    <Items>  
        <Item>  
            <Id>ITM1</Id>  
            <Count>2</Count>  
        </Item>  
        <Item>  
            <Id>ITM2</Id>  
            <Count>5</Count>  
        </Item>  
        <Item>  
            <Id>ITM3</Id>  
            <Count>7</Count>  
        </Item>  
        <TotalCount>0</TotalCount>  
    </Items>  
    <Status>No approval needed</Status>  
</ns0:Order>  
```  
  
 <span data-ttu-id="806fe-154">Modificado **regla 1** es como sigue:</span><span class="sxs-lookup"><span data-stu-id="806fe-154">The modified **Rule 1** is as follows:</span></span>  
  
### <a name="rule-1"></a><span data-ttu-id="806fe-155">Regla 1</span><span class="sxs-lookup"><span data-stu-id="806fe-155">Rule 1</span></span>  
  
```  
IF 1 == 1  
THEN ProcessPO.Order:/Order/Items/TotalCount = (ProcessPO.Order:/Order/Items/TotalCount + ProcessPO:/Order/Items/Item/Count) AND  
Update(ProcessPO.Order:/Order/Items)  
```  
  
## <a name="using-update-function-on-database-facts"></a><span data-ttu-id="806fe-156">Uso de la función Actualizar en hechos de base de datos</span><span class="sxs-lookup"><span data-stu-id="806fe-156">Using Update function on database facts</span></span>  
  
### <a name="typeddatatable"></a><span data-ttu-id="806fe-157">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="806fe-157">TypedDataTable</span></span>  
 <span data-ttu-id="806fe-158">Si **actualización** se llama en un **TypedDataTable**, **actualización** es llamado por el motor en todos los asociados **TypedDataRows**.</span><span class="sxs-lookup"><span data-stu-id="806fe-158">If **Update** is called on a **TypedDataTable**, **Update** is called by the engine on all associated **TypedDataRows**.</span></span> <span data-ttu-id="806fe-159">**Actualización** también se pueden llamar en persona **TypedDataRows**.</span><span class="sxs-lookup"><span data-stu-id="806fe-159">**Update** may also be called on individual **TypedDataRows**.</span></span>  
  
### <a name="dataconnection"></a><span data-ttu-id="806fe-160">DataConnection</span><span class="sxs-lookup"><span data-stu-id="806fe-160">DataConnection</span></span>  
 <span data-ttu-id="806fe-161">Actualización de un **DataConnection** no se admite.</span><span class="sxs-lookup"><span data-stu-id="806fe-161">Update of a **DataConnection** is not supported.</span></span> <span data-ttu-id="806fe-162">Use **Assert** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="806fe-162">Use **Assert** instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="806fe-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="806fe-163">See Also</span></span>  
 [<span data-ttu-id="806fe-164">Funciones de control del motor</span><span class="sxs-lookup"><span data-stu-id="806fe-164">Engine Control Functions</span></span>](../core/engine-control-functions.md)