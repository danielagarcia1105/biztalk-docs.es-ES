---
title: Información de salida de seguimiento de prueba de directivas para reglas de negocios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, business rules
- testing, policies
- business rules, testing
- policies, testing
ms.assetid: 26ff584e-97a1-4d76-a8a9-a55b4c99231f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c223e8bddae1ff68e77cdf881ea22e6be4cdab9a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265068"
---
# <a name="policy-test-trace-output-information-for-business-rules"></a><span data-ttu-id="eee4e-102">Información del resultado del seguimiento de pruebas de directivas para reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="eee4e-102">Policy Test Trace Output Information for Business Rules</span></span>
<span data-ttu-id="eee4e-103">En esta sección se proporciona información acerca de la información de seguimiento que se muestra al probar una directiva en el Compositor de reglas de negocio.</span><span class="sxs-lookup"><span data-stu-id="eee4e-103">This section provides information on the tracking information that is displayed when testing a policy in the Business Rule Composer.</span></span> <span data-ttu-id="eee4e-104">Se ve información muy similar al visualizar los resultados de seguimiento de la ejecución de directivas mediante las consultas de seguimiento de instancias de servicio y eventos de mensaje en la página Concentrador de grupo.</span><span class="sxs-lookup"><span data-stu-id="eee4e-104">Very similar information is seen when viewing tracking results for policy execution using the message event and service instance tracking queries on the Group Hub page.</span></span>  
  
 <span data-ttu-id="eee4e-105">Existen cuatro tipos de instrucciones que se muestran en el resultado del seguimiento:</span><span class="sxs-lookup"><span data-stu-id="eee4e-105">There are four statement types that are displayed in the tracking output:</span></span>  
  
-   <span data-ttu-id="eee4e-106">Actividad de hechos</span><span class="sxs-lookup"><span data-stu-id="eee4e-106">Fact Activity</span></span>  
  
-   <span data-ttu-id="eee4e-107">Evaluación de condición</span><span class="sxs-lookup"><span data-stu-id="eee4e-107">Condition Evaluation</span></span>  
  
-   <span data-ttu-id="eee4e-108">Actualización de agenda</span><span class="sxs-lookup"><span data-stu-id="eee4e-108">Agenda Update</span></span>  
  
-   <span data-ttu-id="eee4e-109">Regla activada</span><span class="sxs-lookup"><span data-stu-id="eee4e-109">Rule Fired</span></span>  
  
 <span data-ttu-id="eee4e-110">A continuación se describe cada tipo de instrucción.</span><span class="sxs-lookup"><span data-stu-id="eee4e-110">Each statement type is described below.</span></span>  
  
## <a name="fact-activity"></a><span data-ttu-id="eee4e-111">Actividad de hechos</span><span class="sxs-lookup"><span data-stu-id="eee4e-111">Fact Activity</span></span>  
 <span data-ttu-id="eee4e-112">Esta instrucción indica los cambios en los hechos que están en la memoria de trabajo del motor.</span><span class="sxs-lookup"><span data-stu-id="eee4e-112">This statement indicates changes to the facts present in the working memory of the engine.</span></span> <span data-ttu-id="eee4e-113">A continuación se muestra un ejemplo de entrada de actividad de datos:</span><span class="sxs-lookup"><span data-stu-id="eee4e-113">The following is an example of a fact activity entry:</span></span>  
  
```  
FACT ACTIVITY 3/16/2004 9:50:28 AM  
Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7  
Ruleset Name: LoanProcessing  
Operation: Assert  
Object Type: MyTest.test  
Object Instance Identifier: 872  
```  
  
### <a name="rule-engine-instance-identifier"></a><span data-ttu-id="eee4e-114">Identificador de instancias de motor de reglas</span><span class="sxs-lookup"><span data-stu-id="eee4e-114">Rule Engine Instance Identifier</span></span>  
 <span data-ttu-id="eee4e-115">Identificador único para la **RuleEngine** instancia que proporciona el entorno de ejecución para la activación de reglas.</span><span class="sxs-lookup"><span data-stu-id="eee4e-115">Unique identifier for the **RuleEngine** instance that provides the execution environment for the rule firing.</span></span>  
  
### <a name="ruleset-name"></a><span data-ttu-id="eee4e-116">Nombre de conjunto de reglas</span><span class="sxs-lookup"><span data-stu-id="eee4e-116">Ruleset Name</span></span>  
 <span data-ttu-id="eee4e-117">Nombre del conjunto de reglas (directiva).</span><span class="sxs-lookup"><span data-stu-id="eee4e-117">The name of the rule set (policy).</span></span>  
  
### <a name="operation"></a><span data-ttu-id="eee4e-118">Operación</span><span class="sxs-lookup"><span data-stu-id="eee4e-118">Operation</span></span>  
 <span data-ttu-id="eee4e-119">Existen tres tipos de operaciones que pueden darse en una actividad de datos:</span><span class="sxs-lookup"><span data-stu-id="eee4e-119">There are three types of operation that can occur in a fact activity:</span></span>  
  
 <span data-ttu-id="eee4e-120">Assert</span><span class="sxs-lookup"><span data-stu-id="eee4e-120">Assert</span></span>  
  
 <span data-ttu-id="eee4e-121">El hecho se agrega a la memoria de trabajo.</span><span class="sxs-lookup"><span data-stu-id="eee4e-121">The fact is being added to the working memory.</span></span>  
  
 <span data-ttu-id="eee4e-122">Update</span><span class="sxs-lookup"><span data-stu-id="eee4e-122">Update</span></span>  
  
 <span data-ttu-id="eee4e-123">El hecho se actualiza mediante una regla y, a continuación, tiene que volver a imponerse en el motor para volver a evaluarse según los nuevos datos y el nuevo estado.</span><span class="sxs-lookup"><span data-stu-id="eee4e-123">The fact is being updated by a rule and then needs to be reasserted into the engine to be re-evaluated, based on the new data and state.</span></span>  
  
 <span data-ttu-id="eee4e-124">Retirar</span><span class="sxs-lookup"><span data-stu-id="eee4e-124">Retract</span></span>  
  
 <span data-ttu-id="eee4e-125">El hecho se elimina de la memoria de trabajo.</span><span class="sxs-lookup"><span data-stu-id="eee4e-125">The fact is being removed from the working memory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eee4e-126">Si se ha impuesto un hecho cuyo tipo no coincide con ninguno de los utilizados en la directiva, la operación Imponer mostrará "Imponer - Hecho no reconocido".</span><span class="sxs-lookup"><span data-stu-id="eee4e-126">If a fact is asserted whose type does not match any of the types used in the policy, the Assert operation will display "Assert – Fact Unrecognized".</span></span>  
  
### <a name="object-type"></a><span data-ttu-id="eee4e-127">Tipo de objeto</span><span class="sxs-lookup"><span data-stu-id="eee4e-127">Object Type</span></span>  
 <span data-ttu-id="eee4e-128">Tipo de hecho de una actividad particular:</span><span class="sxs-lookup"><span data-stu-id="eee4e-128">The type of fact for a particular activity:</span></span>  
  
-   <span data-ttu-id="eee4e-129">DataConnection</span><span class="sxs-lookup"><span data-stu-id="eee4e-129">DataConnection</span></span>  
  
-   <span data-ttu-id="eee4e-130">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="eee4e-130">TypedDataTable</span></span>  
  
-   <span data-ttu-id="eee4e-131">TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="eee4e-131">TypedDataRow</span></span>  
  
     <span data-ttu-id="eee4e-132">Cuando se impone TypedDataTable, todas la filas que contiene se imponen como TypedDataRows.</span><span class="sxs-lookup"><span data-stu-id="eee4e-132">When a TypedDataTable is asserted all of the contained rows are asserted as TypedDataRows.</span></span>  <span data-ttu-id="eee4e-133">Las TypedDataRows asociadas con una DataConnection no se imponen hasta que se evalúa una condición y se ejecuta la consulta resultante.</span><span class="sxs-lookup"><span data-stu-id="eee4e-133">TypedDataRows associated with a DataConnection are not asserted until a condition is evaluated and the resulting query is executed.</span></span>  
  
-   <span data-ttu-id="eee4e-134">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="eee4e-134">TypedXmlDocument</span></span>  
  
     <span data-ttu-id="eee4e-135">Las aserciones se verán en las instancias de TypedXmlDocument tanto principal como secundaria.</span><span class="sxs-lookup"><span data-stu-id="eee4e-135">Assertions will be seen for both parent and child TypedXmlDocument instances.</span></span>  
  
### <a name="object-instance-identifier"></a><span data-ttu-id="eee4e-136">Identificador de instancia de objeto</span><span class="sxs-lookup"><span data-stu-id="eee4e-136">Object Instance Identifier</span></span>  
 <span data-ttu-id="eee4e-137">Identificador único de instancia de la referencia de hecho.</span><span class="sxs-lookup"><span data-stu-id="eee4e-137">Unique instance ID of the fact reference.</span></span>  
  
## <a name="condition-evaluation"></a><span data-ttu-id="eee4e-138">Evaluación de condición</span><span class="sxs-lookup"><span data-stu-id="eee4e-138">Condition Evaluation</span></span>  
 <span data-ttu-id="eee4e-139">Esta actividad indica el resultado de la evaluación de predicados individuales.</span><span class="sxs-lookup"><span data-stu-id="eee4e-139">This activity indicates the result of evaluating individual predicates.</span></span> <span data-ttu-id="eee4e-140">A continuación se muestra un ejemplo de entrada de evaluación de condición:</span><span class="sxs-lookup"><span data-stu-id="eee4e-140">The following is an example of a condition evaluation entry:</span></span>  
  
```  
CONDITION EVALUATION TEST (MATCH) 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Test Expression: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:Root.EmploymentType/TimeInMonths >= 18  
Left Operand Value: 31  
Right Operand Value: 18  
Test Result: True  
```  
  
 <span data-ttu-id="eee4e-141">A continuación se muestran las descripciones de algunos de los términos del ejemplo anterior:</span><span class="sxs-lookup"><span data-stu-id="eee4e-141">The descriptions for some of the terms in the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="eee4e-142">**Expresión de prueba.**</span><span class="sxs-lookup"><span data-stu-id="eee4e-142">**Test Expression.**</span></span> <span data-ttu-id="eee4e-143">Expresión simple (unaria o binaria) de una regla.</span><span class="sxs-lookup"><span data-stu-id="eee4e-143">A simple (unary or binary) expression within a rule.</span></span>  
  
-   <span data-ttu-id="eee4e-144">**Valor del operando izquierdo.**</span><span class="sxs-lookup"><span data-stu-id="eee4e-144">**Left Operand Value.**</span></span> <span data-ttu-id="eee4e-145">Valor del término situado a la izquierda de una expresión.</span><span class="sxs-lookup"><span data-stu-id="eee4e-145">The value of the term on the left side of an expression.</span></span>  
  
-   <span data-ttu-id="eee4e-146">**Valor del operando derecho.**</span><span class="sxs-lookup"><span data-stu-id="eee4e-146">**Right Operand Value.**</span></span> <span data-ttu-id="eee4e-147">Valor del término situado a la derecha de una expresión.</span><span class="sxs-lookup"><span data-stu-id="eee4e-147">The value of the term on the right side of an expression.</span></span>  
  
-   <span data-ttu-id="eee4e-148">**Resultado de pruebas.**</span><span class="sxs-lookup"><span data-stu-id="eee4e-148">**Test Result.**</span></span> <span data-ttu-id="eee4e-149">Resultado de la evaluación, que puede ser True o False.</span><span class="sxs-lookup"><span data-stu-id="eee4e-149">The result of the evaluation, which is either True or False.</span></span>  
  
## <a name="agenda-update"></a><span data-ttu-id="eee4e-150">Actualización de agenda</span><span class="sxs-lookup"><span data-stu-id="eee4e-150">Agenda Update</span></span>  
 <span data-ttu-id="eee4e-151">Esta actividad indica reglas que se agregan a la agenda del motor de reglas para su posterior ejecución.</span><span class="sxs-lookup"><span data-stu-id="eee4e-151">This activity indicates rules that are added to the rule engine agenda for subsequent execution.</span></span> <span data-ttu-id="eee4e-152">A continuación se muestra un ejemplo de entrada de actualización de agenda:</span><span class="sxs-lookup"><span data-stu-id="eee4e-152">The following is an example of an agenda update entry:</span></span>  
  
```  
AGENDA UPDATE 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Operation: Add  
Rule Name: Employment Status Rule  
Conflict Resolution Criteria: 0  
```  
  
 <span data-ttu-id="eee4e-153">A continuación se muestran las descripciones de algunos de los términos del ejemplo anterior:</span><span class="sxs-lookup"><span data-stu-id="eee4e-153">The descriptions for some of the terms in the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="eee4e-154">**Operación.**</span><span class="sxs-lookup"><span data-stu-id="eee4e-154">**Operation.**</span></span> <span data-ttu-id="eee4e-155">Se pueden agregar o quitar reglas de la agenda.</span><span class="sxs-lookup"><span data-stu-id="eee4e-155">Rules can be added or removed from the agenda.</span></span>  
  
-   <span data-ttu-id="eee4e-156">**Nombre de la regla.**</span><span class="sxs-lookup"><span data-stu-id="eee4e-156">**Rule Name.**</span></span> <span data-ttu-id="eee4e-157">Nombre de la regla que se agrega a la agenda.</span><span class="sxs-lookup"><span data-stu-id="eee4e-157">The name of the rule that is being added to the agenda.</span></span>  
  
-   <span data-ttu-id="eee4e-158">**Criterios de resolución de conflictos.**</span><span class="sxs-lookup"><span data-stu-id="eee4e-158">**Conflict Resolution Criteria.**</span></span> <span data-ttu-id="eee4e-159">Prioridad de una regla, que determina el orden relativo en que se ejecutan las acciones (las acciones de mayor prioridad se ejecutan primero).</span><span class="sxs-lookup"><span data-stu-id="eee4e-159">The priority of a rule, which determines the relative order in which actions are executed (higher-priority actions are executed first).</span></span>  
  
## <a name="rule-fired"></a><span data-ttu-id="eee4e-160">Regla activada</span><span class="sxs-lookup"><span data-stu-id="eee4e-160">Rule Fired</span></span>  
 <span data-ttu-id="eee4e-161">Esta actividad indica la ejecución de acciones de una regla.</span><span class="sxs-lookup"><span data-stu-id="eee4e-161">This activity indicates the execution of a rule's actions.</span></span> <span data-ttu-id="eee4e-162">A continuación se muestra un ejemplo de entrada de regla activada:</span><span class="sxs-lookup"><span data-stu-id="eee4e-162">The following is an example of a rule fired entry:</span></span>  
  
```  
RULE FIRED 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Rule Name: Residency Status Rule  
Conflict Resolution Criteria: 10  
```