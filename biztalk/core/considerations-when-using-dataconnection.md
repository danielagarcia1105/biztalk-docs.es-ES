---
title: Consideraciones al utilizar DataConnection | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Retract function [Business Rules Engine], DataConnection
- RetractByType function [Business Rules Engine], DataConnection
- Business Rules Engine, DataConnection tips
- Assert function [Business Rules Engine], DataConnection
- Update function [Business Rules Engine], DataConnection
ms.assetid: 1b4c8aa5-053f-43d7-9f5f-050383405fed
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f99110daafa74cb16b6cc5b98e1382049bbb158
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="considerations-when-using-dataconnection"></a><span data-ttu-id="b3db0-102">Consideraciones al utilizar DataConnection</span><span class="sxs-lookup"><span data-stu-id="b3db0-102">Considerations When Using DataConnection</span></span>
<span data-ttu-id="b3db0-103">Considere lo siguiente al utilizar DataConnection con el motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="b3db0-103">Consider the following when using DataConnection with the Business Rule Engine.</span></span>  
  
## <a name="use-primary-keys"></a><span data-ttu-id="b3db0-104">Utilice claves principales</span><span class="sxs-lookup"><span data-stu-id="b3db0-104">Use primary keys</span></span>  
 <span data-ttu-id="b3db0-105">Cuando hay una clave principal, la igualdad de dos filas se determina considerando si las filas tienen la misma clave principal en vez de comparando objetos.</span><span class="sxs-lookup"><span data-stu-id="b3db0-105">When there is a primary key, the equality of two rows is determined by whether the rows have the same primary key, rather than by object comparison.</span></span> <span data-ttu-id="b3db0-106">Si se determina que las filas son iguales, solo se conserva una copia en la memoria y la otra se descarta.</span><span class="sxs-lookup"><span data-stu-id="b3db0-106">If the rows are determined to be the same, only one copy is retained in memory, and the other is released.</span></span> <span data-ttu-id="b3db0-107">Esto supone una menor utilización de la memoria.</span><span class="sxs-lookup"><span data-stu-id="b3db0-107">This results in less memory consumption.</span></span>  
  
 <span data-ttu-id="b3db0-108">Cuando un **DataConnection** se impone en el motor de reglas por primera vez, el motor siempre intenta localizar su información de clave principal de su esquema.</span><span class="sxs-lookup"><span data-stu-id="b3db0-108">When a **DataConnection** is asserted into the rule engine for the first time, the engine always tries to locate its primary key information from its schema.</span></span> <span data-ttu-id="b3db0-109">Si existe una clave principal, se recupera la información y se utiliza en todas las evaluaciones posteriores.</span><span class="sxs-lookup"><span data-stu-id="b3db0-109">If a primary key exists, primary key information is then retrieved and used in all subsequent evaluations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3db0-110">Es obligatoria una clave principal si hay que hacer cambios en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b3db0-110">A primary key is mandatory if changes need to be made to the database.</span></span>  
  
## <a name="provide-a-running-transaction-to-the-dataconnection-whenever-possible"></a><span data-ttu-id="b3db0-111">Proporcione una transacción de ejecución a la DataConnection siempre que sea posible</span><span class="sxs-lookup"><span data-stu-id="b3db0-111">Provide a running transaction to the DataConnection whenever possible</span></span>  
 <span data-ttu-id="b3db0-112">Sin una transacción, cada uno de ellos consultar y actualizar en el **DataConnection** inicia su propia transacción local y diferentes consultas podrían devolver diferentes resultados en diferentes partes de las evaluaciones de reglas.</span><span class="sxs-lookup"><span data-stu-id="b3db0-112">Without a transaction, each query and update on the **DataConnection** initiates its own local transaction, and different queries might return different results in different parts of rule evaluations.</span></span> <span data-ttu-id="b3db0-113">Los usuarios pueden experimentar un comportamiento incoherente si hay cambios en la tabla de la base de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="b3db0-113">Users may experience inconsistent behavior if there are changes in the underlying database table.</span></span>  
  
 <span data-ttu-id="b3db0-114">Aunque puede usar un **DataConnection** sin proporcionar ninguna transacción cuando la tabla no cambia con el tiempo, se recomienda utilizar una transacción incluso si la **DataConnection** solo se va a se utiliza para operaciones de lectura.</span><span class="sxs-lookup"><span data-stu-id="b3db0-114">Although you can use a **DataConnection** without providing a transaction when the table does not change over time, it is recommended that a transaction be used even when the **DataConnection** is only being used for read operations.</span></span>  
  
 <span data-ttu-id="b3db0-115">Sin embargo, siempre se debe utilizar una transacción cuando actualice datos.</span><span class="sxs-lookup"><span data-stu-id="b3db0-115">However, a transaction should always be used when updating data.</span></span>  
  
## <a name="number-of-queries-may-grow-linearly"></a><span data-ttu-id="b3db0-116">El número de consultas se puede incrementar linealmente</span><span class="sxs-lookup"><span data-stu-id="b3db0-116">Number of queries may grow linearly</span></span>  
 <span data-ttu-id="b3db0-117">Al igual que las consultas en el **DataConnection** parametrizadas por otros objetos combinados, el número de consultas ejecutadas en la **DataConnection** se corresponde directamente con el número de objetos combinados alcanzar la **DataConnection**.</span><span class="sxs-lookup"><span data-stu-id="b3db0-117">As queries against the **DataConnection** are parameterized by other joined objects, the number of queries executed against the **DataConnection** corresponds directly to the number of joining objects reaching the **DataConnection**.</span></span> <span data-ttu-id="b3db0-118">Por lo tanto, si el número de combinar objetos alcanzar la **DataConnection** objeto incrementa linealmente, el número de consultas en el **DataConnection** aumentará linealmente así.</span><span class="sxs-lookup"><span data-stu-id="b3db0-118">Therefore, if the number of joining objects reaching the **DataConnection** object grows linearly, the number of queries against the **DataConnection** will grow linearly as well.</span></span> <span data-ttu-id="b3db0-119">Actualmente, no existe ninguna optimización para reducir el número de consultas.</span><span class="sxs-lookup"><span data-stu-id="b3db0-119">Currently, there is no optimization in place to reduce the number of queries.</span></span>  
  
 <span data-ttu-id="b3db0-120">Un ejemplo es la regla:</span><span class="sxs-lookup"><span data-stu-id="b3db0-120">An example of this is the rule:</span></span>  
  
```  
IF A.x = 7 AND DC.y = A.y  
THEN  
```  
  
 <span data-ttu-id="b3db0-121">A representa un **ObjectBinding**, DC representa una **DataConnection**y x e y representan atributos de A y DC.</span><span class="sxs-lookup"><span data-stu-id="b3db0-121">A represents an **ObjectBinding**, DC represents a **DataConnection**, and x and y represent attributes of A and DC.</span></span>  
  
 <span data-ttu-id="b3db0-122">Para cada instancia de un que pasa la prueba (x = 7), se genera una consulta mediante el uso de la **DataConnection**.</span><span class="sxs-lookup"><span data-stu-id="b3db0-122">For every instance of A that passes the test (x = 7), a query is generated by using the **DataConnection**.</span></span> <span data-ttu-id="b3db0-123">Si existen muchas instancias coincidentes, se producirán el mismo número de consultas.</span><span class="sxs-lookup"><span data-stu-id="b3db0-123">If there are many matching instances, the same number of queries results.</span></span>  
  
## <a name="use-or-conditions-with-caution"></a><span data-ttu-id="b3db0-124">Utilice las condiciones OR con precaución</span><span class="sxs-lookup"><span data-stu-id="b3db0-124">Use OR conditions with caution</span></span>  
 <span data-ttu-id="b3db0-125">Si la regla utiliza solo conjuntivas (**AND**) condiciones, las pruebas y las consultas se ejecutarán tan pronto como sea posible, por lo que se reducirá instancias de objetos que se pasan a través.</span><span class="sxs-lookup"><span data-stu-id="b3db0-125">If the rule uses only conjunctive (**AND**) conditions, tests and queries will be executed as early as possible, so instances of objects passing through will be reduced.</span></span> <span data-ttu-id="b3db0-126">Como resultado, el número de consultas en la subsiguiente **DataConnection** se reducirá proporcionalmente.</span><span class="sxs-lookup"><span data-stu-id="b3db0-126">As a result, the number of queries against the subsequent **DataConnection** will be reduced proportionally.</span></span> <span data-ttu-id="b3db0-127">Si disyuntiva (**o**) condiciones y una **DataConnection** se utilizan conjuntamente en una regla, condición todas las evaluaciones se insertará en la consulta final.</span><span class="sxs-lookup"><span data-stu-id="b3db0-127">If disjunctive (**OR**) conditions and a **DataConnection** are used together in a rule, all condition evaluations will be pushed to the final query.</span></span> <span data-ttu-id="b3db0-128">Si más de un **DataConnection** se utiliza en una regla, todas las consultas excepto la última de ellas se convierte en una instrucción de consulta Select-ALL.</span><span class="sxs-lookup"><span data-stu-id="b3db0-128">If more than one **DataConnection** is used in a rule, all queries except the last one will effectively become a Select-ALL query statement.</span></span>  
  
 <span data-ttu-id="b3db0-129">En general, es mejor dividir cualquier regla con una condición OR en dos o más reglas discretas, porque la utilización de condiciones OR disminuirá rendimiento si se compara con la definición de más reglas atómicas.</span><span class="sxs-lookup"><span data-stu-id="b3db0-129">In general, it is better to split any rule with an OR condition into two or more discrete rules, because the use of OR conditions will decrease performance compared to the definition of more atomic rules.</span></span> <span data-ttu-id="b3db0-130">Esto es así independientemente de que se utilicen DataConnections o no.</span><span class="sxs-lookup"><span data-stu-id="b3db0-130">This is true whether DataConnections are used or not.</span></span>  
  
 <span data-ttu-id="b3db0-131">También puede considerar la utilización de reglas separadas que consten solo de condiciones conjuntivas en vez de una regla con **o** condiciones.</span><span class="sxs-lookup"><span data-stu-id="b3db0-131">You may also consider using separate rules that consist only of conjunctive conditions instead of one rule with **OR** conditions.</span></span> <span data-ttu-id="b3db0-132">Con **o** condiciones, el número de consultas aumenta la velocidad de multiplicación de las instancias de todos los objetos combinados.</span><span class="sxs-lookup"><span data-stu-id="b3db0-132">With **OR** conditions, the number of queries grows at the speed of multiplication of instances of all joining objects.</span></span> <span data-ttu-id="b3db0-133">Esto se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b3db0-133">This is shown in the following example.</span></span>  
  
```  
IF (A.x ==7 OR A.x == 8) AND DC.y == A.y  
THEN DC.z = 10  
```  
  
 <span data-ttu-id="b3db0-134">En este ejemplo, se representa A un **ObjectBinding**; DC representa una **DataConnection**y x, y y z representan atributos de A y DC.</span><span class="sxs-lookup"><span data-stu-id="b3db0-134">In this example, A represents an **ObjectBinding**; DC represents a **DataConnection**, and x, y, and z represent attributes of A and DC.</span></span> <span data-ttu-id="b3db0-135">Si A tiene 100 instancias y x es 1 en el primer objeto, 2 en el segundo objeto, hasta 100 en el objeto 100, 100 consultas tienen que ejecutar en el **DataConnection**.</span><span class="sxs-lookup"><span data-stu-id="b3db0-135">If A has 100 instances, and x is 1 in the first object, 2 in the second object, through 100 in the 100th object, 100 queries have to run against the **DataConnection**.</span></span>  
  
 <span data-ttu-id="b3db0-136">Es mejor volver a escribir la regla anterior dividiéndola en dos reglas.</span><span class="sxs-lookup"><span data-stu-id="b3db0-136">It is better to rewrite the preceding rule by splitting it in to two rules.</span></span>  
  
 <span data-ttu-id="b3db0-137">**Regla 1**</span><span class="sxs-lookup"><span data-stu-id="b3db0-137">**Rule 1**</span></span>  
  
```  
IF A.x =7 AND DC.y = A.y  
THEN DC.z = 10  
```  
  
 <span data-ttu-id="b3db0-138">**Regla 2**</span><span class="sxs-lookup"><span data-stu-id="b3db0-138">**Rule 2**</span></span>  
  
```  
IF A.x = 8 AND DC.y = A.y  
THEN DC.z = 10  
```  
  
## <a name="sql-does-not-support-some-predicates-and-functions"></a><span data-ttu-id="b3db0-139">SQL no admite algunos predicados y funciones</span><span class="sxs-lookup"><span data-stu-id="b3db0-139">SQL does not support some predicates and functions</span></span>  
 <span data-ttu-id="b3db0-140">SQL no admite algunos predicados y funciones que admite el motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="b3db0-140">Some predicates and functions that the rule engine supports are not supported by SQL.</span></span> <span data-ttu-id="b3db0-141">Si estos predicados y funciones no admitidos se utilizan en las condiciones de la regla, no se pueden incorporar a la consulta.</span><span class="sxs-lookup"><span data-stu-id="b3db0-141">If these unsupported predicates and functions are used in the rule conditions, it cannot be incorporated into the query.</span></span> <span data-ttu-id="b3db0-142">Los términos siguientes no se pueden optimizar como una consulta SQL:</span><span class="sxs-lookup"><span data-stu-id="b3db0-142">The following terms cannot be optimized as an SQL query:</span></span>  
  
-   <span data-ttu-id="b3db0-143">Algunas de las funciones integradas del motor no tienen equivalente en una consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="b3db0-143">Some of the engine built-in functions have no equivalent in an SQL query.</span></span> <span data-ttu-id="b3db0-144">Se trata de **Power**, **FindFirst**, y **Encontrartodos**.</span><span class="sxs-lookup"><span data-stu-id="b3db0-144">These are **Power**, **FindFirst**, and **FindAll**.</span></span> <span data-ttu-id="b3db0-145">Con un **DataConnection** columna como uno o más de sus argumentos no se puede optimizar como parte de una consulta; por ejemplo, potencia (2, controlador de dominio. Column1).</span><span class="sxs-lookup"><span data-stu-id="b3db0-145">Using a **DataConnection** column as one or more of their arguments cannot be optimized as part of a query; for example, Power( 2, dc.Column1).</span></span>  
  
-   <span data-ttu-id="b3db0-146">Predicado integrado coincidencia que utiliza un **DataConnection** columna como su argumento de expresión regular (primer argumento).</span><span class="sxs-lookup"><span data-stu-id="b3db0-146">Built-in predicate Match that uses a **DataConnection** column as its regular expression argument (the first argument).</span></span> <span data-ttu-id="b3db0-147">Por ejemplo, Coincidencia("abc\*", dc1.Column2) es válido, pero Coincidencia(dc1.Column1, dc1.Column2) no se puede traducir.</span><span class="sxs-lookup"><span data-stu-id="b3db0-147">For example, Match("abc\*", dc1.Column2) is valid, but Match(dc1.Column1, dc1.Column2) cannot be translated.</span></span>  
  
-   <span data-ttu-id="b3db0-148">Con una función de usuario que tiene un **DataConnection** columna como uno de sus parámetros.</span><span class="sxs-lookup"><span data-stu-id="b3db0-148">Using a user function that has a **DataConnection** column as one of its parameters.</span></span> <span data-ttu-id="b3db0-149">Por ejemplo, c1.M(dc.Column1) no se puede optimizar porque la función de usuario no se puede ejecutar en el servidor de base de datos, sino que debe ejecutarlo el motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="b3db0-149">For example, c1.M(dc.Column1) cannot be optimized because the user function cannot execute on the database server, but must be executed by the Business Rule Engine.</span></span>  
  
-   <span data-ttu-id="b3db0-150">Funciones de usuario que representan las operaciones set en el **DataConnection**; por ejemplo, controlador de dominio. Column1(5).</span><span class="sxs-lookup"><span data-stu-id="b3db0-150">User functions that represent set operations on the **DataConnection**; for example, dc.Column1(5).</span></span>  
  
-   <span data-ttu-id="b3db0-151">Funciones que utilizan un **ObjectReference** a la **DataConnection**; por ejemplo, objecref (DC).</span><span class="sxs-lookup"><span data-stu-id="b3db0-151">Functions that use an **ObjectReference** to the **DataConnection**; for example, ObjecRef(dc).</span></span>  
  
-   <span data-ttu-id="b3db0-152">Si no es posible traducir uno o más argumentos de una función, la llamada a la función se convierte en intraducible; por ejemplo, Agregar(c1.M(dc.Column1), 5 ).</span><span class="sxs-lookup"><span data-stu-id="b3db0-152">If one or more of a function's arguments is untranslatable, the function call becomes untranslatable; for example, Add(c1.M(dc.Column1), 5).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3db0-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3db0-153">See Also</span></span>  
 [<span data-ttu-id="b3db0-154">Acceso a datos en el motor de reglas de negocio</span><span class="sxs-lookup"><span data-stu-id="b3db0-154">Data Access in the Business Rule Engine</span></span>](../core/data-access-in-the-business-rule-engine.md)