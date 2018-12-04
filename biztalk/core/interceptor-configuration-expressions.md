---
title: Expresiones de configuración de interceptor | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2695f509-fece-40b8-aa00-fa3c0c0f19c5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae6cc008e1e8b6acad53c2fcebd59160931cdc96
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2018
ms.locfileid: "52826300"
---
# <a name="interceptor-configuration-expressions"></a><span data-ttu-id="2ac09-102">Expresiones de configuración de interceptor</span><span class="sxs-lookup"><span data-stu-id="2ac09-102">Interceptor Configuration Expressions</span></span>
<span data-ttu-id="2ac09-103">El archivo de configuración de interceptor BAM usa expresiones de filtro para identificar una actividad y las expresiones de datos utiliza para construir un elemento de datos de almacenamiento, use como un Id. de correlación o token de continuación propósito similar.</span><span class="sxs-lookup"><span data-stu-id="2ac09-103">The BAM interceptor configuration file uses filter expressions to identify an activity and uses data expressions to construct a data element for storage, use as a correlation ID or continuation token, or similar purpose.</span></span> <span data-ttu-id="2ac09-104">Independientemente del propósito, las expresiones individuales se identifican en el archivo de configuración de interceptor por el elemento `expression` y contienen una o varias operaciones que usan la Notación polaca inversa, que se conoce también como notación de polaco inverso.</span><span class="sxs-lookup"><span data-stu-id="2ac09-104">Regardless of the purpose, individual expressions are identified in the interceptor configuration file by the `expression` element and contain one or more operations using Reverse Polish Notation, also known as postfix notation.</span></span>  
  
## <a name="about-reverse-polish-notation"></a><span data-ttu-id="2ac09-105">Acerca de la Notación polaca inversa</span><span class="sxs-lookup"><span data-stu-id="2ac09-105">About Reverse Polish Notation</span></span>  
 <span data-ttu-id="2ac09-106">En la Notación polaca inversa (RPN), los operandos preceden al operador, con lo que se elimina la necesidad de usar paréntesis como operadores de precedencia.</span><span class="sxs-lookup"><span data-stu-id="2ac09-106">In Reverse Polish Notation (RPN), operands precede the operator, thereby removing the need to use parentheses as precedence operators.</span></span> <span data-ttu-id="2ac09-107">Una pila se usa para contener valores y todas las operaciones, tanto valores de insertar en la pila como de retirar (quitar) de la pila, o para realizar una combinación de insertar y retirar para completar una operación.</span><span class="sxs-lookup"><span data-stu-id="2ac09-107">A stack is used to hold values and all operations either push values onto the stack, pop (remove) values from the stack, or perform a combination of pushes and pops to complete an operation.</span></span>  
  
 <span data-ttu-id="2ac09-108">Por ejemplo, si deseara evaluar la expresión</span><span class="sxs-lookup"><span data-stu-id="2ac09-108">For example, if you wanted to evaluate the expression</span></span>  
  
 `5 + (10 - 2)`  
  
 <span data-ttu-id="2ac09-109">Convertir esto a los resultados RPN equivalentes en</span><span class="sxs-lookup"><span data-stu-id="2ac09-109">Converting this to the equivalent RPN results in</span></span>  
  
 `5 10 2 - +`  
  
 <span data-ttu-id="2ac09-110">Esto se evaluaría de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="2ac09-110">This would be evaluated as follows:</span></span>  
  
|<span data-ttu-id="2ac09-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="2ac09-111">Input</span></span>|<span data-ttu-id="2ac09-112">Operación</span><span class="sxs-lookup"><span data-stu-id="2ac09-112">Operation</span></span>|<span data-ttu-id="2ac09-113">Pila</span><span class="sxs-lookup"><span data-stu-id="2ac09-113">Stack</span></span>|  
|-----------|---------------|-----------|  
|<span data-ttu-id="2ac09-114">5</span><span class="sxs-lookup"><span data-stu-id="2ac09-114">5</span></span>|<span data-ttu-id="2ac09-115">Inserción</span><span class="sxs-lookup"><span data-stu-id="2ac09-115">Push</span></span>|<span data-ttu-id="2ac09-116">5</span><span class="sxs-lookup"><span data-stu-id="2ac09-116">5</span></span>|  
|<span data-ttu-id="2ac09-117">10</span><span class="sxs-lookup"><span data-stu-id="2ac09-117">10</span></span>|<span data-ttu-id="2ac09-118">Inserción</span><span class="sxs-lookup"><span data-stu-id="2ac09-118">Push</span></span>|<span data-ttu-id="2ac09-119">5, 10</span><span class="sxs-lookup"><span data-stu-id="2ac09-119">5, 10</span></span>|  
|<span data-ttu-id="2ac09-120">2</span><span class="sxs-lookup"><span data-stu-id="2ac09-120">2</span></span>|<span data-ttu-id="2ac09-121">Inserción</span><span class="sxs-lookup"><span data-stu-id="2ac09-121">Push</span></span>|<span data-ttu-id="2ac09-122">5, 10, 2</span><span class="sxs-lookup"><span data-stu-id="2ac09-122">5, 10, 2</span></span>|  
|-|<span data-ttu-id="2ac09-123">Subtract</span><span class="sxs-lookup"><span data-stu-id="2ac09-123">Subtract</span></span>|<span data-ttu-id="2ac09-124">5, 8</span><span class="sxs-lookup"><span data-stu-id="2ac09-124">5, 8</span></span>|  
|+|<span data-ttu-id="2ac09-125">Agregar</span><span class="sxs-lookup"><span data-stu-id="2ac09-125">Add</span></span>|<span data-ttu-id="2ac09-126">13</span><span class="sxs-lookup"><span data-stu-id="2ac09-126">13</span></span>|  
  
 <span data-ttu-id="2ac09-127">Suponiendo que el sistema RPN admitiera la operación de concatenación de cadenas, podría también evaluar la expresión</span><span class="sxs-lookup"><span data-stu-id="2ac09-127">Assuming the RPN system supported the string concatenate operation, you could also evaluate the expression</span></span>  
  
 `"The quick brown " + "fox " + "jumped over the lazy " + "dog."`  
  
 <span data-ttu-id="2ac09-128">Convertir esto al rendimiento de notación de RPN equivalente:</span><span class="sxs-lookup"><span data-stu-id="2ac09-128">Converting this to the equivalent RPN notation yields:</span></span>  
  
 `"The quick brown " "fox " "jumped over the lazy " "dog" + + +`  
  
 <span data-ttu-id="2ac09-129">Esto se evaluaría de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="2ac09-129">This would be evaluated as follows:</span></span>  
  
|<span data-ttu-id="2ac09-130">Entrada</span><span class="sxs-lookup"><span data-stu-id="2ac09-130">Input</span></span>|<span data-ttu-id="2ac09-131">Operación</span><span class="sxs-lookup"><span data-stu-id="2ac09-131">Operation</span></span>|<span data-ttu-id="2ac09-132">Pila</span><span class="sxs-lookup"><span data-stu-id="2ac09-132">Stack</span></span>|  
|-----------|---------------|-----------|  
|<span data-ttu-id="2ac09-133">"A caballo"</span><span class="sxs-lookup"><span data-stu-id="2ac09-133">"The quick brown"</span></span>|<span data-ttu-id="2ac09-134">Inserción</span><span class="sxs-lookup"><span data-stu-id="2ac09-134">Push</span></span>|<span data-ttu-id="2ac09-135">"The quick brown "</span><span class="sxs-lookup"><span data-stu-id="2ac09-135">"The quick brown "</span></span>|  
|<span data-ttu-id="2ac09-136">"fox"</span><span class="sxs-lookup"><span data-stu-id="2ac09-136">"fox"</span></span>|<span data-ttu-id="2ac09-137">Inserción</span><span class="sxs-lookup"><span data-stu-id="2ac09-137">Push</span></span>|<span data-ttu-id="2ac09-138">"The quick brown ", "fox "</span><span class="sxs-lookup"><span data-stu-id="2ac09-138">"The quick brown ", "fox "</span></span>|  
|<span data-ttu-id="2ac09-139">"jumped over the lazy"</span><span class="sxs-lookup"><span data-stu-id="2ac09-139">"jumped over the lazy"</span></span>|<span data-ttu-id="2ac09-140">Inserción</span><span class="sxs-lookup"><span data-stu-id="2ac09-140">Push</span></span>|<span data-ttu-id="2ac09-141">"The quick brown ", "fox ", "jumped over the lazy "</span><span class="sxs-lookup"><span data-stu-id="2ac09-141">"The quick brown ", "fox ", "jumped over the lazy "</span></span>|  
|<span data-ttu-id="2ac09-142">"dog."</span><span class="sxs-lookup"><span data-stu-id="2ac09-142">"dog."</span></span>|<span data-ttu-id="2ac09-143">Inserción</span><span class="sxs-lookup"><span data-stu-id="2ac09-143">Push</span></span>|<span data-ttu-id="2ac09-144">"The quick brown ", "fox ", "jumped over the lazy ", "dog."</span><span class="sxs-lookup"><span data-stu-id="2ac09-144">"The quick brown ", "fox ", "jumped over the lazy ", "dog."</span></span>|  
|+|<span data-ttu-id="2ac09-145">Concatenate</span><span class="sxs-lookup"><span data-stu-id="2ac09-145">Concatenate</span></span>|<span data-ttu-id="2ac09-146">"The quick brown ", "fox ", "jumped over the lazy dog."</span><span class="sxs-lookup"><span data-stu-id="2ac09-146">"The quick brown ", "fox ", "jumped over the lazy dog."</span></span>|  
|+|<span data-ttu-id="2ac09-147">Concatenate</span><span class="sxs-lookup"><span data-stu-id="2ac09-147">Concatenate</span></span>|<span data-ttu-id="2ac09-148">"The quick brown ", "fox jumped over the lazy dog."</span><span class="sxs-lookup"><span data-stu-id="2ac09-148">"The quick brown ", "fox jumped over the lazy dog."</span></span>|  
|+|<span data-ttu-id="2ac09-149">Concatenate</span><span class="sxs-lookup"><span data-stu-id="2ac09-149">Concatenate</span></span>|<span data-ttu-id="2ac09-150">"The quick brown fox jumped over the lazy dog."</span><span class="sxs-lookup"><span data-stu-id="2ac09-150">"The quick brown fox jumped over the lazy dog."</span></span>|  
  
 <span data-ttu-id="2ac09-151">Como puede ver, se admite un número arbitrario de operaciones, incluidas la comparación, las operaciones booleanas y las operaciones personalizadas que recuperan valores apropiados para las operaciones en las que participan.</span><span class="sxs-lookup"><span data-stu-id="2ac09-151">As you can see, an arbitrary number of operations can be supported, including comparison, Boolean operations, and custom operations that retrieve values appropriate for the operations in which they participate.</span></span> <span data-ttu-id="2ac09-152">Los valores se acumulan en la pila y se insertan y quitan en función de las operaciones individuales.</span><span class="sxs-lookup"><span data-stu-id="2ac09-152">Values accumulate on the stack and are pushed and popped according to individual operations.</span></span>  
  
## <a name="reverse-polish-notation-in-the-interceptor-configuration-file"></a><span data-ttu-id="2ac09-153">Notación polaca inversa en el archivo de configuración de interceptor</span><span class="sxs-lookup"><span data-stu-id="2ac09-153">Reverse Polish Notation in the Interceptor Configuration File</span></span>  
 <span data-ttu-id="2ac09-154">Escribirá dos tipos de expresiones en el interceptor de archivo de configuración: filtrar expresiones y expresiones de datos.</span><span class="sxs-lookup"><span data-stu-id="2ac09-154">You will write two kinds of expressions in the interceptor configuration file: filter expressions and data expressions.</span></span> <span data-ttu-id="2ac09-155">Las expresiones de filtro esperan que el resultado de la expresión de RPN sea un valor booleano `true` o `false`, mientras que las expresiones de datos esperan un único valor en la pila.</span><span class="sxs-lookup"><span data-stu-id="2ac09-155">Filter expressions expect the result of the RPN expression to be a Boolean `true` or `false` while data expressions expect a single value on the stack.</span></span>  
  
### <a name="filter-expressions"></a><span data-ttu-id="2ac09-156">Expresiones de filtro</span><span class="sxs-lookup"><span data-stu-id="2ac09-156">Filter Expressions</span></span>  
 <span data-ttu-id="2ac09-157">Las expresiones de filtro se evalúan como valor booleano `true` o `false`, y se usan para identificar un evento concreto, del cual se realiza un seguimiento en la aplicación WF o WFC.</span><span class="sxs-lookup"><span data-stu-id="2ac09-157">Filter expressions evaluate to Boolean `true` or `false` and are used to identify a specific event to track in the WF or WFC application.</span></span> <span data-ttu-id="2ac09-158">En aplicaciones WF, es común filtrar en función del nombre de la actividad y del evento.</span><span class="sxs-lookup"><span data-stu-id="2ac09-158">In WF applications, it is common to filter based on activity name and event.</span></span> <span data-ttu-id="2ac09-159">Por ejemplo, es posible que desee seleccionar el **FoodAndDrinksPolicy** actividad cuando resulta **cerrado**.</span><span class="sxs-lookup"><span data-stu-id="2ac09-159">For example, you may want to select the **FoodAndDrinksPolicy** activity when it is **Closed**.</span></span> <span data-ttu-id="2ac09-160">Mediante el uso de operaciones de WF, puede expresar el filtro como:</span><span class="sxs-lookup"><span data-stu-id="2ac09-160">Using WF operations, you could express the filter as:</span></span>  
  
 `(GetActivityName = "FoodAndDrinksPolicy") && (GetActivityEvent = "Closed")`  
  
 <span data-ttu-id="2ac09-161">Convertir en rendimiento de RPN:</span><span class="sxs-lookup"><span data-stu-id="2ac09-161">Converting this to RPN yields:</span></span>  
  
 `GetActivityName "FoodAndDrinksPolicy" == GetActivityEvent "Closed" == &&`  
  
 <span data-ttu-id="2ac09-162">La conversión de esta expresión a la expresión equivalente para el archivo de configuración de interceptor da como resultado el siguiente XML:</span><span class="sxs-lookup"><span data-stu-id="2ac09-162">Converting this expression to the equivalent expression for the interceptor configuration file results in the following XML:</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>FoodAndDrinksPolicy</ic:Argument>  
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
  
 <span data-ttu-id="2ac09-163">Por último, esta expresión debe evaluarse como sigue suponiendo **GetActivityName** devuelto "DessertPolicy" y **GetActivityEvent** devuelto "Closed":</span><span class="sxs-lookup"><span data-stu-id="2ac09-163">Finally, this expression would be evaluated as follows assuming **GetActivityName** returned "DessertPolicy" and **GetActivityEvent** returned "Closed":</span></span>  
  
|<span data-ttu-id="2ac09-164">Entrada</span><span class="sxs-lookup"><span data-stu-id="2ac09-164">Input</span></span>|<span data-ttu-id="2ac09-165">Operación</span><span class="sxs-lookup"><span data-stu-id="2ac09-165">Operation</span></span>|<span data-ttu-id="2ac09-166">Pila</span><span class="sxs-lookup"><span data-stu-id="2ac09-166">Stack</span></span>|  
|-----------|---------------|-----------|  
||<span data-ttu-id="2ac09-167">GetActivityName</span><span class="sxs-lookup"><span data-stu-id="2ac09-167">GetActivityName</span></span>|<span data-ttu-id="2ac09-168">"DessertPolicy"</span><span class="sxs-lookup"><span data-stu-id="2ac09-168">"DessertPolicy"</span></span>|  
|<span data-ttu-id="2ac09-169">"FoodAndDrinksPolicy"</span><span class="sxs-lookup"><span data-stu-id="2ac09-169">"FoodAndDrinksPolicy"</span></span>|<span data-ttu-id="2ac09-170">Constante</span><span class="sxs-lookup"><span data-stu-id="2ac09-170">Constant</span></span>|<span data-ttu-id="2ac09-171">"DessertPolicy", "FoodAndDrinksPolicy"</span><span class="sxs-lookup"><span data-stu-id="2ac09-171">"DessertPolicy", "FoodAndDrinksPolicy"</span></span>|  
|<span data-ttu-id="2ac09-172">Es igual a</span><span class="sxs-lookup"><span data-stu-id="2ac09-172">Equals</span></span>|<span data-ttu-id="2ac09-173">Comparación</span><span class="sxs-lookup"><span data-stu-id="2ac09-173">Comparison</span></span>|<span data-ttu-id="2ac09-174">False</span><span class="sxs-lookup"><span data-stu-id="2ac09-174">False</span></span>|  
||<span data-ttu-id="2ac09-175">GetActivityEvent (operación)</span><span class="sxs-lookup"><span data-stu-id="2ac09-175">GetActivityEvent</span></span>|<span data-ttu-id="2ac09-176">False, Closed</span><span class="sxs-lookup"><span data-stu-id="2ac09-176">False, Closed</span></span>|  
|<span data-ttu-id="2ac09-177">"Closed"</span><span class="sxs-lookup"><span data-stu-id="2ac09-177">"Closed"</span></span>|<span data-ttu-id="2ac09-178">Constante</span><span class="sxs-lookup"><span data-stu-id="2ac09-178">Constant</span></span>|<span data-ttu-id="2ac09-179">False, "Closed", "Closed"</span><span class="sxs-lookup"><span data-stu-id="2ac09-179">False, "Closed", "Closed"</span></span>|  
|<span data-ttu-id="2ac09-180">Es igual a</span><span class="sxs-lookup"><span data-stu-id="2ac09-180">Equals</span></span>|<span data-ttu-id="2ac09-181">Comparación</span><span class="sxs-lookup"><span data-stu-id="2ac09-181">Comparison</span></span>|<span data-ttu-id="2ac09-182">False, True</span><span class="sxs-lookup"><span data-stu-id="2ac09-182">False, True</span></span>|  
|<span data-ttu-id="2ac09-183">And</span><span class="sxs-lookup"><span data-stu-id="2ac09-183">And</span></span>|<span data-ttu-id="2ac09-184">Logical And</span><span class="sxs-lookup"><span data-stu-id="2ac09-184">Logical And</span></span>|<span data-ttu-id="2ac09-185">False</span><span class="sxs-lookup"><span data-stu-id="2ac09-185">False</span></span>|  
  
 <span data-ttu-id="2ac09-186">El valor que se ha dejado en la pila es booleano `False`.</span><span class="sxs-lookup"><span data-stu-id="2ac09-186">The value left on the stack is Boolean `False`.</span></span> <span data-ttu-id="2ac09-187">Esto provocará que el evento correspondiente no se active.</span><span class="sxs-lookup"><span data-stu-id="2ac09-187">This will cause the corresponding event to not fire.</span></span> <span data-ttu-id="2ac09-188">Si el nombre de actividad fuera "FoodAndDrinksPolicy", se habría evaluado como un valor booleano `True`.</span><span class="sxs-lookup"><span data-stu-id="2ac09-188">If the activity name were "FoodAndDrinksPolicy" then it would have evaluated to Boolean `True`.</span></span>  
  
 <span data-ttu-id="2ac09-189">Puede construir una expresión similar (con una evaluación similar). Para ello, utilice operaciones de WCF `GetEndpointName` y `GetOperationName`.</span><span class="sxs-lookup"><span data-stu-id="2ac09-189">You can construct a similar expression (with a similar evaluation) by using the WCF operations `GetEndpointName` and `GetOperationName`.</span></span>  
  
### <a name="data-expressions"></a><span data-ttu-id="2ac09-190">Expresiones de datos</span><span class="sxs-lookup"><span data-stu-id="2ac09-190">Data Expressions</span></span>  
 <span data-ttu-id="2ac09-191">Las expresiones de datos se usan para definir un único valor de datos de cadena.</span><span class="sxs-lookup"><span data-stu-id="2ac09-191">Data expressions are used to define a single string data value.</span></span> <span data-ttu-id="2ac09-192">Una expresión de datos se considera cualquier expresión que no se incluye en un elemento de `Filter`.</span><span class="sxs-lookup"><span data-stu-id="2ac09-192">A data expression is any expression that is not enclosed by a `Filter` element.</span></span> <span data-ttu-id="2ac09-193">Las expresiones de datos las usan los elementos de `OnEvent` `CorrelationID`, `ContinuationToken`, `Reference` y `Update`.</span><span class="sxs-lookup"><span data-stu-id="2ac09-193">Data expressions are used by the `OnEvent` elements `CorrelationID`, `ContinuationToken`, `Reference`, and `Update`.</span></span>  
  
 <span data-ttu-id="2ac09-194">Un requisito habitual suele ser actualizar la base de datos de actividad de BAM con una marca de tiempo sin etiqueta.</span><span class="sxs-lookup"><span data-stu-id="2ac09-194">It is a common requirement to update the BAM activity database with a labeled time stamp.</span></span> <span data-ttu-id="2ac09-195">Por ejemplo, desea capturar la hora en que se inicia un evento con una cadena con formato como "iniciar: \<EventTime\>".</span><span class="sxs-lookup"><span data-stu-id="2ac09-195">For example, you might want to capture the time an event starts with a string formatted as "Start: \<EventTime\>".</span></span> <span data-ttu-id="2ac09-196">Para hacerlo, debe usar una expresión similar a la siguiente (donde + representa la concatenación):</span><span class="sxs-lookup"><span data-stu-id="2ac09-196">To do this, you need to use an expression similar to the following (where + represents concatenation):</span></span>  
  
 `"Start: " + GetContextProperty(EventTime)`  
  
 <span data-ttu-id="2ac09-197">Convertir en rendimiento de RPN:</span><span class="sxs-lookup"><span data-stu-id="2ac09-197">Converting this to RPN yields:</span></span>  
  
 `"Start: " GetContextProperty(EventTime) +`  
  
 <span data-ttu-id="2ac09-198">La conversión de esta expresión a la expresión equivalente para un elemento `Update` en el archivo de configuración de interceptor da como resultado el siguiente XML:</span><span class="sxs-lookup"><span data-stu-id="2ac09-198">Converting this expression to the equivalent expression for an `Update` element in the interceptor configuration file results in the following XML:</span></span>  
  
```  
<ic:Update DataItemName="NewOrderCreateTime" Type="NVARCHAR">  
  <ic:Expression>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Start:</ic:Argument>  
    </ic:Operation>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>EventTime</wf:Argument>  
    </wf:Operation>  
    <ic:Operation Name="Concatenate" />  
  </ic:Expression>  
</ic:Update>  
```  
  
 <span data-ttu-id="2ac09-199">La siguiente tabla muestra cómo debe interpretarse esta expresión si la hora del evento fuera "12:00 PM".</span><span class="sxs-lookup"><span data-stu-id="2ac09-199">The following table shows how this expression would be interpreted if the event time was "12:00 PM".</span></span>  
  
|<span data-ttu-id="2ac09-200">Entrada</span><span class="sxs-lookup"><span data-stu-id="2ac09-200">Input</span></span>|<span data-ttu-id="2ac09-201">Operación</span><span class="sxs-lookup"><span data-stu-id="2ac09-201">Operation</span></span>|<span data-ttu-id="2ac09-202">Pila</span><span class="sxs-lookup"><span data-stu-id="2ac09-202">Stack</span></span>|  
|-----------|---------------|-----------|  
|<span data-ttu-id="2ac09-203">"Empezar:"</span><span class="sxs-lookup"><span data-stu-id="2ac09-203">"Start: "</span></span>|<span data-ttu-id="2ac09-204">Constante</span><span class="sxs-lookup"><span data-stu-id="2ac09-204">Constant</span></span>|<span data-ttu-id="2ac09-205">"Empezar:"</span><span class="sxs-lookup"><span data-stu-id="2ac09-205">"Start: "</span></span>|  
|<span data-ttu-id="2ac09-206">GetContextProperty(EventTime)</span><span class="sxs-lookup"><span data-stu-id="2ac09-206">GetContextProperty(EventTime)</span></span>|<span data-ttu-id="2ac09-207">Inserción</span><span class="sxs-lookup"><span data-stu-id="2ac09-207">Push</span></span>|<span data-ttu-id="2ac09-208">"Empezar:", "2006-09-27T12:00:34.000Z"</span><span class="sxs-lookup"><span data-stu-id="2ac09-208">"Start: ", "2006-09-27T12:00:34.000Z"</span></span>|  
|<span data-ttu-id="2ac09-209">Concatenate</span><span class="sxs-lookup"><span data-stu-id="2ac09-209">Concatenate</span></span>|<span data-ttu-id="2ac09-210">Concatenate</span><span class="sxs-lookup"><span data-stu-id="2ac09-210">Concatenate</span></span>|<span data-ttu-id="2ac09-211">"Empezar: 2006-09-27T12:00:34.000Z"</span><span class="sxs-lookup"><span data-stu-id="2ac09-211">"Start: 2006-09-27T12:00:34.000Z"</span></span>|  
  
 <span data-ttu-id="2ac09-212">El valor usado por el comando de actualización sería "iniciar: 2006-09-27T12:00:34.000Z".</span><span class="sxs-lookup"><span data-stu-id="2ac09-212">The value used by the update command would be "Start: 2006-09-27T12:00:34.000Z".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ac09-213">No use las operaciones de comparación "And" o "Equals" en expresiones de datos.</span><span class="sxs-lookup"><span data-stu-id="2ac09-213">Do not use the comparison operations "And" or "Equals" in data expressions.</span></span> <span data-ttu-id="2ac09-214">De hacerlo, recibirá un error cuando implemente el archivo de configuración de interceptor.</span><span class="sxs-lookup"><span data-stu-id="2ac09-214">If you do, you will receive an error when deploying your interceptor configuration file.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2ac09-215">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2ac09-215">In This Section</span></span>  
 [<span data-ttu-id="2ac09-216">Operaciones del interceptor</span><span class="sxs-lookup"><span data-stu-id="2ac09-216">Interceptor Operations</span></span>](../core/interceptor-operations.md)  
  
## <a name="see-also"></a><span data-ttu-id="2ac09-217">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ac09-217">See Also</span></span>  
 [<span data-ttu-id="2ac09-218">Estructura de un archivo de configuración de interceptores</span><span class="sxs-lookup"><span data-stu-id="2ac09-218">Structure of an Interceptor Configuration File</span></span>](../core/structure-of-an-interceptor-configuration-file.md)
