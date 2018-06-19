---
title: Agenda y prioridad | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, executing
- Business Rules Engine, agendas
- Business Rules Engine, priorities
- business rules, priorities
- business rules, examples
- Business Rules Engine, examples
- examples, Business Rules Engine
- Business Rules Engine, rules
ms.assetid: ca54f750-4f2d-4734-8e6e-7af1b4967e6a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4529753251c2bf7934616b91662bde836c8339e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230212"
---
# <a name="agenda-and-priority"></a><span data-ttu-id="f30dd-102">Agenda y prioridad</span><span class="sxs-lookup"><span data-stu-id="f30dd-102">Agenda and Priority</span></span>
<span data-ttu-id="f30dd-103">Para comprender cómo el motor de reglas de negocios evalúa las reglas y ejecuta las acciones, debe comprender los conceptos de *agenda* y *prioridad*.</span><span class="sxs-lookup"><span data-stu-id="f30dd-103">To understand how the Business Rule engine evaluates rules and executes actions, you need to understand the concepts of *agenda* and *priority*.</span></span>  
  
## <a name="agenda"></a><span data-ttu-id="f30dd-104">Agenda</span><span class="sxs-lookup"><span data-stu-id="f30dd-104">Agenda</span></span>  
 <span data-ttu-id="f30dd-105">La agenda es una programación que utiliza el motor para poner en cola las reglas que van a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="f30dd-105">The agenda is a schedule used by the engine to queue rules for execution.</span></span> <span data-ttu-id="f30dd-106">Se encuentra en una instancia del motor y actúa sobre una única directiva, no sobre una serie de directivas.</span><span class="sxs-lookup"><span data-stu-id="f30dd-106">The agenda exists for an engine instance, and acts on a single policy, not on a series of policies.</span></span> <span data-ttu-id="f30dd-107">Cuando se impone un dato en la memoria de trabajo y se cumplen las condiciones de una determinada regla, la regla se coloca en la agenda y se ejecuta de acuerdo con la prioridad.</span><span class="sxs-lookup"><span data-stu-id="f30dd-107">When a fact is asserted into working memory and the conditions of a given rule are satisfied, the rule is placed on the agenda and executed according to priority.</span></span> <span data-ttu-id="f30dd-108">Las acciones de una regla se ejecutan en orden descendente y después se ejecutan las acciones de la siguiente regla que haya en la agenda.</span><span class="sxs-lookup"><span data-stu-id="f30dd-108">A rule's actions are executed in order from top to bottom, and then the actions of the next rule on the agenda are executed.</span></span>  
  
 <span data-ttu-id="f30dd-109">Las acciones que pertenecen a una regla se consideran como un bloque, de modo que se ejecutan todas las acciones antes de pasar a la regla siguiente.</span><span class="sxs-lookup"><span data-stu-id="f30dd-109">The actions belonging to a rule are treated as a block, so that all actions are executed before moving on to the next rule.</span></span> <span data-ttu-id="f30dd-110">Todas las acciones de un bloque de reglas se ejecutarán con independencia de las demás acciones del bloque.</span><span class="sxs-lookup"><span data-stu-id="f30dd-110">All actions in a rule block will execute regardless of other actions in the block.</span></span> <span data-ttu-id="f30dd-111">Para obtener más información acerca de la aserción, consulte [las funciones de Control del motor](../core/engine-control-functions.md).</span><span class="sxs-lookup"><span data-stu-id="f30dd-111">For more information about assertion, see [Engine Control Functions](../core/engine-control-functions.md).</span></span>  
  
 <span data-ttu-id="f30dd-112">El siguiente ejemplo muestra cómo funciona la agenda.</span><span class="sxs-lookup"><span data-stu-id="f30dd-112">The following example demonstrates how the agenda works.</span></span>  
  
 <span data-ttu-id="f30dd-113">**Rule1**</span><span class="sxs-lookup"><span data-stu-id="f30dd-113">**Rule1**</span></span>  
  
```  
IF  
Fact1 == 1  
THEN  
Action1  
Action2  
```  
  
 <span data-ttu-id="f30dd-114">**Rule2**</span><span class="sxs-lookup"><span data-stu-id="f30dd-114">**Rule2**</span></span>  
  
```  
IF  
Fact1 > 0  
THEN  
Action3  
Action4  
```  
  
 <span data-ttu-id="f30dd-115">Imponemos en el motor el hecho Fact1, que tiene un valor de 1.</span><span class="sxs-lookup"><span data-stu-id="f30dd-115">We assert the fact Fact1, which has a value of 1, into the engine.</span></span> <span data-ttu-id="f30dd-116">Como se cumplen las condiciones de las reglas Rule1 y Rule2, ambas reglas se mueven a la agenda para que se ejecuten las acciones correspondientes.</span><span class="sxs-lookup"><span data-stu-id="f30dd-116">Because the conditions of both Rule 1 and Rule 2 are satisfied, both rules are moved to the agenda for execution of their actions.</span></span>  
  
|<span data-ttu-id="f30dd-117">Memoria de trabajo</span><span class="sxs-lookup"><span data-stu-id="f30dd-117">Working memory</span></span>|<span data-ttu-id="f30dd-118">Agenda</span><span class="sxs-lookup"><span data-stu-id="f30dd-118">Agenda</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="f30dd-119">Fact1 (valor = 1)</span><span class="sxs-lookup"><span data-stu-id="f30dd-119">Fact1 (value=1)</span></span>|<span data-ttu-id="f30dd-120">**Rule1**</span><span class="sxs-lookup"><span data-stu-id="f30dd-120">**Rule1**</span></span><br /><br /> <span data-ttu-id="f30dd-121">-Action1</span><span class="sxs-lookup"><span data-stu-id="f30dd-121">-   Action1</span></span><br /><span data-ttu-id="f30dd-122">-Action2</span><span class="sxs-lookup"><span data-stu-id="f30dd-122">-   Action2</span></span><br /><br /> <span data-ttu-id="f30dd-123">**Rule2**</span><span class="sxs-lookup"><span data-stu-id="f30dd-123">**Rule2**</span></span><br /><br /> <span data-ttu-id="f30dd-124">-Action3</span><span class="sxs-lookup"><span data-stu-id="f30dd-124">-   Action3</span></span><br /><span data-ttu-id="f30dd-125">-Action4</span><span class="sxs-lookup"><span data-stu-id="f30dd-125">-   Action4</span></span>|  
  
## <a name="priority"></a><span data-ttu-id="f30dd-126">Prioridad</span><span class="sxs-lookup"><span data-stu-id="f30dd-126">Priority</span></span>  
 <span data-ttu-id="f30dd-127">La prioridad de ejecución se establece en cada regla individual, con una prioridad predeterminada de 0 para todas las reglas.</span><span class="sxs-lookup"><span data-stu-id="f30dd-127">Priority for execution is set on each individual rule, with a default priority of 0 for all rules.</span></span> <span data-ttu-id="f30dd-128">El valor de prioridad puede oscilar a ambos lados del 0, donde los números más grandes significan una mayor prioridad.</span><span class="sxs-lookup"><span data-stu-id="f30dd-128">The priority can range on either side of 0, with larger numbers having higher priority.</span></span> <span data-ttu-id="f30dd-129">Las acciones se ejecutan en orden desde prioridad más alta a prioridad más baja.</span><span class="sxs-lookup"><span data-stu-id="f30dd-129">Actions are executed in order from highest priority to lowest priority.</span></span>  
  
 <span data-ttu-id="f30dd-130">En el ejemplo siguiente se muestra cómo afecta la prioridad al orden de ejecución de las reglas.</span><span class="sxs-lookup"><span data-stu-id="f30dd-130">The following example shows how priority affects the order of execution for the rules.</span></span>  
  
 <span data-ttu-id="f30dd-131">**Rule1 (prioridad = 0)**</span><span class="sxs-lookup"><span data-stu-id="f30dd-131">**Rule1 (priority = 0)**</span></span>  
  
```  
IF  
Fact1 == 1  
THEN  
Discount = 10%  
```  
  
 <span data-ttu-id="f30dd-132">**Rule2 (prioridad = 10)**</span><span class="sxs-lookup"><span data-stu-id="f30dd-132">**Rule2 (priority = 10)**</span></span>  
  
```  
IF  
Fact1 > 0  
THEN  
Discount = 15%  
```  
  
 <span data-ttu-id="f30dd-133">Las condiciones de ambas reglas se cumplen, pero la regla Rule2 se ejecuta primero porque tiene una mayor prioridad.</span><span class="sxs-lookup"><span data-stu-id="f30dd-133">The conditions for both rules have been met, but Rule2 is executed first because it has higher priority.</span></span> <span data-ttu-id="f30dd-134">El descuento final es de un 10 por ciento, ya que es el resultado de la acción ejecutada para la regla Rule1, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="f30dd-134">The final discount is 10 percent, because it is the result of the action executed for Rule1, as shown in the following table.</span></span>  
  
|<span data-ttu-id="f30dd-135">Memoria de trabajo</span><span class="sxs-lookup"><span data-stu-id="f30dd-135">Working memory</span></span>|<span data-ttu-id="f30dd-136">Agenda</span><span class="sxs-lookup"><span data-stu-id="f30dd-136">Agenda</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="f30dd-137">Fact1 (valor = 1)</span><span class="sxs-lookup"><span data-stu-id="f30dd-137">Fact1 (value=1)</span></span>|<span data-ttu-id="f30dd-138">**Rule2**</span><span class="sxs-lookup"><span data-stu-id="f30dd-138">**Rule2**</span></span><br /><br /> <span data-ttu-id="f30dd-139">Descuento = 15%</span><span class="sxs-lookup"><span data-stu-id="f30dd-139">Discount = 15%</span></span><br /><br /> <span data-ttu-id="f30dd-140">**Rule1**</span><span class="sxs-lookup"><span data-stu-id="f30dd-140">**Rule1**</span></span><br /><br /> <span data-ttu-id="f30dd-141">Descuento = 10%</span><span class="sxs-lookup"><span data-stu-id="f30dd-141">Discount = 10%</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f30dd-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="f30dd-142">See Also</span></span>  
 [<span data-ttu-id="f30dd-143">Motor de reglas</span><span class="sxs-lookup"><span data-stu-id="f30dd-143">Rule Engine</span></span>](../core/rule-engine.md)