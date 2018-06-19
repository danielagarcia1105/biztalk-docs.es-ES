---
title: Evaluación de condiciones y ejecución de acciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Action stage [Business Rules Engine]
- examples, business rules
- Business Rules Engine, policies
- Match stage [Business Rules Engine]
- business rules, examples
- Business Rules Engine, algorithm
- Business Rules Engine, examples
- conflict resolution [Business Rules Engine]
- Business Rules Engine, stages
ms.assetid: dcaa32c2-3403-4f54-92e2-128686bfc193
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2814a97c1907b1bb29eee2a718d04d14cfe901a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233348"
---
# <a name="condition-evaluation-and-action-execution"></a><span data-ttu-id="f64f1-102">Evaluación de condiciones y ejecución de acciones</span><span class="sxs-lookup"><span data-stu-id="f64f1-102">Condition Evaluation and Action Execution</span></span>
<span data-ttu-id="f64f1-103">El marco de trabajo de reglas de negocios proporciona un motor de interferencia extremadamente eficaz que permite la vinculación de reglas a objetos .NET, documentos XML o tablas de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="f64f1-103">The Business Rules Framework provides a highly efficient inference engine capable of linking rules to .NET objects, XML documents, or database tables.</span></span>  
  
 <span data-ttu-id="f64f1-104">El motor de reglas de negocios utiliza un algoritmo dividido en tres fases para ejecutar la directiva.</span><span class="sxs-lookup"><span data-stu-id="f64f1-104">The Business Rule Engine uses a three-stage algorithm for policy execution.</span></span> <span data-ttu-id="f64f1-105">Las fases son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="f64f1-105">The stages are as follows:</span></span>  
  
-   <span data-ttu-id="f64f1-106">**Coincidencia**.</span><span class="sxs-lookup"><span data-stu-id="f64f1-106">**Match**.</span></span> <span data-ttu-id="f64f1-107">En la fase de coincidencia, se comparan los datos con los predicados que usan el tipo de datos (referencias de objetos almacenadas en la memoria de trabajo del motor de reglas) mediante los predicados definidos en las condiciones de reglas.</span><span class="sxs-lookup"><span data-stu-id="f64f1-107">In the match stage, facts are matched against the predicates that use the fact type (object references maintained in the rule engine's working memory) using the predicates defined in the rule conditions.</span></span> <span data-ttu-id="f64f1-108">Por motivos de eficacia, la coincidencia de patrones se produce en todas las reglas de la directiva, y las condiciones que son compartidas por las reglas se comparan solo una vez.</span><span class="sxs-lookup"><span data-stu-id="f64f1-108">For the sake of efficiency, pattern matching occurs over all the rules in the policy, and conditions that are shared across rules are matched only once.</span></span> <span data-ttu-id="f64f1-109">Las coincidencias parciales de las condiciones se almacenan en la memoria de trabajo con el objetivo de acelerar las operaciones de coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="f64f1-109">Partial condition matches may be stored in working memory to expedite subsequent pattern-matching operations.</span></span> <span data-ttu-id="f64f1-110">El resultado de la fase de coincidencia de patrones se compone de las actualizaciones de la agenda del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="f64f1-110">The output of the pattern-matching phase consists of updates to the rule engine agenda.</span></span>  
  
-   <span data-ttu-id="f64f1-111">**Resolución de conflictos**.</span><span class="sxs-lookup"><span data-stu-id="f64f1-111">**Conflict resolution**.</span></span> <span data-ttu-id="f64f1-112">En la fase de resolución de conflictos se analizan las reglas establecidas para la ejecución con el objeto de determinar el conjunto siguiente de acciones de reglas que se va a ejecutar en función de un esquema de resolución predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f64f1-112">In the conflict resolution stage, the rules that are candidates for execution are examined to determine the next set of rule actions to execute based on a predetermined resolution scheme.</span></span> <span data-ttu-id="f64f1-113">Todas las reglas candidatas que se obtengan durante la fase de coincidencia se agregan a la agenda del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="f64f1-113">All candidate rules found during the matching stage are added to the rule engine's agenda.</span></span>  
  
     <span data-ttu-id="f64f1-114">El esquema de resolución de conflictos predeterminado está basado en las prioridades de reglas de una directiva.</span><span class="sxs-lookup"><span data-stu-id="f64f1-114">The default conflict resolution scheme is based on rule priorities within a policy.</span></span> <span data-ttu-id="f64f1-115">La prioridad es una propiedad configurable de las reglas del Compositor de reglas de negocio.</span><span class="sxs-lookup"><span data-stu-id="f64f1-115">The priority is a configurable property of a rule in the Business Rule Composer.</span></span> <span data-ttu-id="f64f1-116">Cuanto más grande sea el número, mayor es la prioridad; de esta forma, si se activan varias reglas, las acciones de prioridad más alta se ejecutan en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="f64f1-116">The larger the number, the higher the priority; therefore if multiple rules are triggered, the higher-priority actions are executed first.</span></span>  
  
-   <span data-ttu-id="f64f1-117">**Acción**.</span><span class="sxs-lookup"><span data-stu-id="f64f1-117">**Action**.</span></span> <span data-ttu-id="f64f1-118">En la fase de acción se ejecutan las acciones de las reglas resueltas.</span><span class="sxs-lookup"><span data-stu-id="f64f1-118">In the action stage, the actions in the resolved rule are executed.</span></span> <span data-ttu-id="f64f1-119">Tenga en cuenta que las acciones de reglas pueden imponer nuevos datos en el motor de reglas, lo que hace que el ciclo continúe.</span><span class="sxs-lookup"><span data-stu-id="f64f1-119">Note that rule actions can assert new facts into the rule engine, which causes the cycle to continue.</span></span> <span data-ttu-id="f64f1-120">Esto también recibe el nombre de encadenamiento directo.</span><span class="sxs-lookup"><span data-stu-id="f64f1-120">This is also known as forward chaining.</span></span> <span data-ttu-id="f64f1-121">Es importante tener en cuenta que el algoritmo nunca se anticipa a la regla que se encuentre en ejecución en ese momento.</span><span class="sxs-lookup"><span data-stu-id="f64f1-121">It is important to note that the algorithm never preempts the currently executing rule.</span></span> <span data-ttu-id="f64f1-122">Todas las acciones de la regla que se esté activando se ejecutarán antes de que se repita la fase de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="f64f1-122">All actions for the rule that is currently firing will be executed before the match phase is repeated.</span></span> <span data-ttu-id="f64f1-123">Sin embargo, las demás reglas de la agenda no se activarán antes de que la fase de coincidencia comience de nuevo.</span><span class="sxs-lookup"><span data-stu-id="f64f1-123">However, other rules on the agenda will not be fired before the match phase begins again.</span></span> <span data-ttu-id="f64f1-124">La fase de coincidencia puede provocar que dichas reglas se eliminen de la agenda antes de que se activen.</span><span class="sxs-lookup"><span data-stu-id="f64f1-124">The match phase may cause those rules on the agenda to be removed from the agenda before they ever fire.</span></span>  
  
 <span data-ttu-id="f64f1-125">En el siguiente ejemplo se muestra el algoritmo en tres fases de la acción o resolución de conflictos o coincidencias.</span><span class="sxs-lookup"><span data-stu-id="f64f1-125">The following example shows the three-stage algorithm of match-conflict resolution-action.</span></span>  
  
 <span data-ttu-id="f64f1-126">**Regla 1: Evaluar ingreso**</span><span class="sxs-lookup"><span data-stu-id="f64f1-126">**Rule 1: Evaluate income**</span></span>  
  
-   <span data-ttu-id="f64f1-127">Representación declarativa:</span><span class="sxs-lookup"><span data-stu-id="f64f1-127">Declarative representation:</span></span>  
  
     <span data-ttu-id="f64f1-128">El índice de solvencia crediticia de un solicitante debe obtenerse únicamente cuando la proporción ingresos/préstamo es inferior a 0,2.</span><span class="sxs-lookup"><span data-stu-id="f64f1-128">An applicant's credit rating should be obtained only if the applicant's income-to-loan ratio is less than 0.2.</span></span>  
  
-   <span data-ttu-id="f64f1-129">IF, a continuación, la representación con objetos comerciales:</span><span class="sxs-lookup"><span data-stu-id="f64f1-129">IF—THEN representation using business objects:</span></span>  
  
    ```  
    IF Application.Income / Property.Price < 0.2    
    THEN Assert new CreditRating( Application)   
    ```  
  
 <span data-ttu-id="f64f1-130">**Regla 2: Evaluar solvencia**</span><span class="sxs-lookup"><span data-stu-id="f64f1-130">**Rule 2: Evaluate credit rating**</span></span>  
  
-   <span data-ttu-id="f64f1-131">Representación declarativa:</span><span class="sxs-lookup"><span data-stu-id="f64f1-131">Declarative representation:</span></span>  
  
     <span data-ttu-id="f64f1-132">Un solicitante debe considerarse aprobado solo cuando su índice de solvencia crediticia es superior a 725.</span><span class="sxs-lookup"><span data-stu-id="f64f1-132">An applicant should be approved only if the applicant's credit rating is more than 725.</span></span>  
  
-   <span data-ttu-id="f64f1-133">IF, a continuación, representación con objetos comerciales:</span><span class="sxs-lookup"><span data-stu-id="f64f1-133">IF—THEN Representation using business objects:</span></span>  
  
    ```  
    IF Application.SSN = CreditRating.SSN AND CreditRating.Value > 725    
    THEN SendApprovalLetter(Application)    
    ```  
  
 <span data-ttu-id="f64f1-134">Los datos se resumen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="f64f1-134">The facts are summarized in the following table.</span></span>  
  
|<span data-ttu-id="f64f1-135">Hecho</span><span class="sxs-lookup"><span data-stu-id="f64f1-135">Fact</span></span>|<span data-ttu-id="f64f1-136">Campos</span><span class="sxs-lookup"><span data-stu-id="f64f1-136">Fields</span></span>|  
|----------|------------|  
|<span data-ttu-id="f64f1-137">Application: documento XML que representa una solicitud de hipoteca</span><span class="sxs-lookup"><span data-stu-id="f64f1-137">Application – An XML document representing a home loan application</span></span>|<span data-ttu-id="f64f1-138">-Ingresos = 65.000 dólares</span><span class="sxs-lookup"><span data-stu-id="f64f1-138">-   Income = $65,000</span></span><br /><span data-ttu-id="f64f1-139">-SSN = XXX-XX-XXXX</span><span class="sxs-lookup"><span data-stu-id="f64f1-139">-   SSN = XXX-XX-XXXX</span></span>|  
|<span data-ttu-id="f64f1-140">Property: documento XML que representa la propiedad adquirida</span><span class="sxs-lookup"><span data-stu-id="f64f1-140">Property – An XML document representing the property being purchased</span></span>|<span data-ttu-id="f64f1-141">-Price = $225,000</span><span class="sxs-lookup"><span data-stu-id="f64f1-141">-   Price = $225,000</span></span>|  
|<span data-ttu-id="f64f1-142">CreditRating: documento XML que contiene el índice de solvencia crediticia del solicitante</span><span class="sxs-lookup"><span data-stu-id="f64f1-142">CreditRating – An XML document containing the loan applicant's credit rating</span></span>|<span data-ttu-id="f64f1-143">-Valor = 0 – 800</span><span class="sxs-lookup"><span data-stu-id="f64f1-143">-   Value = 0 – 800</span></span><br /><span data-ttu-id="f64f1-144">-SSN = XXX-XX-XXXX</span><span class="sxs-lookup"><span data-stu-id="f64f1-144">-   SSN = XXX-XX-XXXX</span></span>|  
  
 <span data-ttu-id="f64f1-145">En un principio la agenda y la memoria de trabajo del motor de reglas están vacías.</span><span class="sxs-lookup"><span data-stu-id="f64f1-145">Initially the rule engine working memory and agenda are empty.</span></span> <span data-ttu-id="f64f1-146">Una vez que la aplicación agrega los datos Application y Property, la agenda y la memoria de trabajo del motor de reglas se actualizan de la siguiente forma.</span><span class="sxs-lookup"><span data-stu-id="f64f1-146">After the application adds the Application and Property facts, the rule engine working memory and agenda are updated as follows.</span></span>  
  
|<span data-ttu-id="f64f1-147">Memoria de trabajo</span><span class="sxs-lookup"><span data-stu-id="f64f1-147">Working memory</span></span>|<span data-ttu-id="f64f1-148">Agenda</span><span class="sxs-lookup"><span data-stu-id="f64f1-148">Agenda</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="f64f1-149">: Aplicación</span><span class="sxs-lookup"><span data-stu-id="f64f1-149">-   Application</span></span><br /><span data-ttu-id="f64f1-150">: Propiedad</span><span class="sxs-lookup"><span data-stu-id="f64f1-150">-   Property</span></span>|<span data-ttu-id="f64f1-151">Regla 1</span><span class="sxs-lookup"><span data-stu-id="f64f1-151">Rule 1</span></span>|  
  
 <span data-ttu-id="f64f1-152">Regla 1 se agrega a la agenda porque su condición (Application.Income / Property.Price < 0,2) evalúan a **true** durante la fase de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="f64f1-152">Rule 1 is added to the agenda because its condition (Application.Income / Property.Price < 0.2) evaluated to **true** during the match phase.</span></span> <span data-ttu-id="f64f1-153">Dado que el dato CreditRating no aparece en la memoria de trabajo, no se ha evaluado la condición de la Regla 2.</span><span class="sxs-lookup"><span data-stu-id="f64f1-153">There is no CreditRating fact in working memory, so the condition for Rule 2 was not evaluated.</span></span> <span data-ttu-id="f64f1-154">Al ser Regla 1 la única regla existente en la agenda, la regla se ejecuta y desaparece de la agenda.</span><span class="sxs-lookup"><span data-stu-id="f64f1-154">Because the only rule in the agenda is Rule 1, the rule is executed and then disappears from the agenda.</span></span> <span data-ttu-id="f64f1-155">La acción sencilla que se ha definido en la Regla 1 da lugar a un dato nuevo (el documento CreditRating del solicitante) que se agrega a la memoria de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f64f1-155">The single action defined for Rule 1 results in a new fact (CreditRating document for the applicant) being added to working memory.</span></span> <span data-ttu-id="f64f1-156">Cuando finaliza la ejecución de la Regla 1, el control vuelve a la fase de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="f64f1-156">After the execution of Rule 1 completes, control returns to the match phase.</span></span> <span data-ttu-id="f64f1-157">Puesto que el único objeto nuevo que se va a comparar es el dato CreditRating, los resultados de la fase de coincidencia son los siguientes.</span><span class="sxs-lookup"><span data-stu-id="f64f1-157">Because the only new object to match is the CreditRating fact, the results of the match phase are as follows.</span></span>  
  
|<span data-ttu-id="f64f1-158">Memoria de trabajo</span><span class="sxs-lookup"><span data-stu-id="f64f1-158">Working memory</span></span>|<span data-ttu-id="f64f1-159">Agenda</span><span class="sxs-lookup"><span data-stu-id="f64f1-159">Agenda</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="f64f1-160">: Aplicación</span><span class="sxs-lookup"><span data-stu-id="f64f1-160">-   Application</span></span><br /><span data-ttu-id="f64f1-161">: Propiedad</span><span class="sxs-lookup"><span data-stu-id="f64f1-161">-   Property</span></span><br /><span data-ttu-id="f64f1-162">-CreditRating</span><span class="sxs-lookup"><span data-stu-id="f64f1-162">-   CreditRating</span></span>|<span data-ttu-id="f64f1-163">Regla 2</span><span class="sxs-lookup"><span data-stu-id="f64f1-163">Rule 2</span></span>|  
  
 <span data-ttu-id="f64f1-164">En este momento se ejecuta la Regla 2, que da como resultado la invocación de una función que envía una carta de aprobación al solicitante.</span><span class="sxs-lookup"><span data-stu-id="f64f1-164">At this point Rule 2 is executed, resulting in the invocation of a function that sends an approval letter to the applicant.</span></span> <span data-ttu-id="f64f1-165">Después de completarse la Regla 2, la ejecución del algoritmo de encadenamiento directo vuelve a la fase de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="f64f1-165">After Rule 2 has completed, execution of the forward-chaining algorithm returns to the match phase.</span></span> <span data-ttu-id="f64f1-166">Puesto que ya no existen datos nuevos que se puedan comparar y la agenda está vacía, el encadenamiento directo finaliza y se termina la ejecución de la directiva.</span><span class="sxs-lookup"><span data-stu-id="f64f1-166">Because there are no longer new facts to match and the agenda is empty, forward chaining terminates and policy execution is complete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f64f1-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="f64f1-167">See Also</span></span>  
 [<span data-ttu-id="f64f1-168">Motor de reglas</span><span class="sxs-lookup"><span data-stu-id="f64f1-168">Rule Engine</span></span>](../core/rule-engine.md)