---
title: Ejemplos del resultado de seguimiento de pruebas de directivas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, policies
- policies, testing
- testing, examples
ms.assetid: 92e1dc7f-1a8d-41a5-84b6-46d5ad9f2ef2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e3678769dffa03bb77c3e86fef02998a354b1fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22266684"
---
# <a name="policy-test-trace-output-examples"></a><span data-ttu-id="d9df4-102">Ejemplos del resultado del seguimiento de pruebas de directivas</span><span class="sxs-lookup"><span data-stu-id="d9df4-102">Policy Test Trace Output Examples</span></span>
<span data-ttu-id="d9df4-103">Esta sección contiene ejemplos de salida de pruebas de directivas para diferentes tipos de hechos.</span><span class="sxs-lookup"><span data-stu-id="d9df4-103">This section contains examples of the policy test output for different types of facts.</span></span>  
  
## <a name="net-class"></a><span data-ttu-id="d9df4-104">Clase .Net</span><span class="sxs-lookup"><span data-stu-id="d9df4-104">.Net Class</span></span>  
 <span data-ttu-id="d9df4-105">Regla de ejemplo "TestRule1" en la directiva "LoanProcessing":</span><span class="sxs-lookup"><span data-stu-id="d9df4-105">Example rule "TestRule1" in policy "LoanProcessing":</span></span>  
  
```  
IF test.get_ID > 0  
THEN <do something>  
```  
  
 <span data-ttu-id="d9df4-106">**Resultado:**</span><span class="sxs-lookup"><span data-stu-id="d9df4-106">**Output:**</span></span>  
  
 <span data-ttu-id="d9df4-107">SEGUIMIENTO de motor de reglas para conjunto de reglas: LoanProcessing 3/16/2004 9:50:28 A.M.</span><span class="sxs-lookup"><span data-stu-id="d9df4-107">RULE ENGINE TRACE for RULESET: LoanProcessing 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="d9df4-108">ACTIVIDAD DE DATOS 3/16/2004 9:50:28 A.M.</span><span class="sxs-lookup"><span data-stu-id="d9df4-108">FACT ACTIVITY 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="d9df4-109">Identificador de la instancia de motor de reglas: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span><span class="sxs-lookup"><span data-stu-id="d9df4-109">Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span></span>  
  
 <span data-ttu-id="d9df4-110">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-110">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-111">Operación: Assert</span><span class="sxs-lookup"><span data-stu-id="d9df4-111">Operation: Assert</span></span>  
  
 <span data-ttu-id="d9df4-112">Tipo de objeto: MyTest.test</span><span class="sxs-lookup"><span data-stu-id="d9df4-112">Object Type: MyTest.test</span></span>  
  
 <span data-ttu-id="d9df4-113">Identificador de instancia de objeto: 872</span><span class="sxs-lookup"><span data-stu-id="d9df4-113">Object Instance Identifier: 872</span></span>  
  
 <span data-ttu-id="d9df4-114">PRUEBA DE EVALUACIÓN DE CONDICIÓN (COINCIDENCIA) 3/16/2004 9:50:28 A.M.</span><span class="sxs-lookup"><span data-stu-id="d9df4-114">CONDITION EVALUATION TEST (MATCH) 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="d9df4-115">Identificador de la instancia de motor de reglas: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span><span class="sxs-lookup"><span data-stu-id="d9df4-115">Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span></span>  
  
 <span data-ttu-id="d9df4-116">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-116">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-117">Expresión de prueba: MyTest.test.get_ID > 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-117">Test Expression: MyTest.test.get_ID > 0</span></span>  
  
 <span data-ttu-id="d9df4-118">Deja el valor del operando: 100</span><span class="sxs-lookup"><span data-stu-id="d9df4-118">Left Operand Value: 100</span></span>  
  
 <span data-ttu-id="d9df4-119">Valor del operando de la derecha: 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-119">Right Operand Value: 0</span></span>  
  
 <span data-ttu-id="d9df4-120">Resultado de pruebas: True</span><span class="sxs-lookup"><span data-stu-id="d9df4-120">Test Result: True</span></span>  
  
 <span data-ttu-id="d9df4-121">ACTUALIZACIÓN DE AGENDA 3/16/2004 9:50:28 A.M.</span><span class="sxs-lookup"><span data-stu-id="d9df4-121">AGENDA UPDATE 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="d9df4-122">Identificador de la instancia de motor de reglas: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span><span class="sxs-lookup"><span data-stu-id="d9df4-122">Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span></span>  
  
 <span data-ttu-id="d9df4-123">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-123">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-124">Operación: agregar</span><span class="sxs-lookup"><span data-stu-id="d9df4-124">Operation: Add</span></span>  
  
 <span data-ttu-id="d9df4-125">Nombre de regla: TestRule1</span><span class="sxs-lookup"><span data-stu-id="d9df4-125">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="d9df4-126">Criterios de resolución de conflictos: 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-126">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="d9df4-127">REGLA ACTIVADA 3/16/2004 9:50:28 A.M.</span><span class="sxs-lookup"><span data-stu-id="d9df4-127">RULE FIRED 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="d9df4-128">Identificador de la instancia de motor de reglas: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span><span class="sxs-lookup"><span data-stu-id="d9df4-128">Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span></span>  
  
 <span data-ttu-id="d9df4-129">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-129">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-130">Nombre de regla: TestRule1</span><span class="sxs-lookup"><span data-stu-id="d9df4-130">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="d9df4-131">Criterios de resolución de conflictos: 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-131">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="d9df4-132">ACTIVIDAD DE DATOS 3/16/2004 9:50:28 A.M.</span><span class="sxs-lookup"><span data-stu-id="d9df4-132">FACT ACTIVITY 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="d9df4-133">Identificador de la instancia de motor de reglas: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span><span class="sxs-lookup"><span data-stu-id="d9df4-133">Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span></span>  
  
 <span data-ttu-id="d9df4-134">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-134">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-135">Operación: retirar</span><span class="sxs-lookup"><span data-stu-id="d9df4-135">Operation: Retract</span></span>  
  
 <span data-ttu-id="d9df4-136">Tipo de objeto: MyTest.test</span><span class="sxs-lookup"><span data-stu-id="d9df4-136">Object Type: MyTest.test</span></span>  
  
 <span data-ttu-id="d9df4-137">Identificador de instancia de objeto: 872</span><span class="sxs-lookup"><span data-stu-id="d9df4-137">Object Instance Identifier: 872</span></span>  
  
## <a name="dataconnectiontypeddatarow"></a><span data-ttu-id="d9df4-138">DataConnection/TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="d9df4-138">DataConnection/TypedDataRow</span></span>  
 <span data-ttu-id="d9df4-139">Regla de ejemplo "TestRule1" en la directiva "LoanProcessing":</span><span class="sxs-lookup"><span data-stu-id="d9df4-139">Example rule "TestRule1" in policy "LoanProcessing":</span></span>  
  
```  
IF NorthWind.CustInfo.CreditCardBalance > 0  
THEN <do something>  
```  
  
 <span data-ttu-id="d9df4-140">**Resultado:**</span><span class="sxs-lookup"><span data-stu-id="d9df4-140">**Output:**</span></span>  
  
 <span data-ttu-id="d9df4-141">SEGUIMIENTO de motor de reglas para conjunto de reglas: LoanProcessing 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-141">RULE ENGINE TRACE for RULESET: LoanProcessing 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="d9df4-142">ACTIVIDAD DE DATOS 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-142">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="d9df4-143">Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="d9df4-143">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="d9df4-144">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-144">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-145">Operación: Assert</span><span class="sxs-lookup"><span data-stu-id="d9df4-145">Operation: Assert</span></span>  
  
 <span data-ttu-id="d9df4-146">Tipo de objeto: DataConnection:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="d9df4-146">Object Type: DataConnection:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="d9df4-147">Identificador de instancia de objeto: 874</span><span class="sxs-lookup"><span data-stu-id="d9df4-147">Object Instance Identifier: 874</span></span>  
  
 <span data-ttu-id="d9df4-148">PRUEBA DE EVALUACIÓN DE CONDICIÓN (COINCIDENCIA) 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-148">CONDITION EVALUATION TEST (MATCH) 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="d9df4-149">Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="d9df4-149">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="d9df4-150">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-150">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-151">Expresión de prueba: seleccione \* de [CustInfo] donde [CreditCardBalance] > 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-151">Test Expression: select \* from [CustInfo] where [CreditCardBalance] > 0</span></span>  
  
 <span data-ttu-id="d9df4-152">Valor del operando izquierdo:</span><span class="sxs-lookup"><span data-stu-id="d9df4-152">Left Operand Value:</span></span>  
  
 <span data-ttu-id="d9df4-153">Valor del operando derecho:</span><span class="sxs-lookup"><span data-stu-id="d9df4-153">Right Operand Value:</span></span>  
  
 <span data-ttu-id="d9df4-154">Resultado de pruebas: True</span><span class="sxs-lookup"><span data-stu-id="d9df4-154">Test Result: True</span></span>  
  
 <span data-ttu-id="d9df4-155">ACTIVIDAD DE DATOS 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-155">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="d9df4-156">Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="d9df4-156">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="d9df4-157">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-157">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-158">Operación: Assert</span><span class="sxs-lookup"><span data-stu-id="d9df4-158">Operation: Assert</span></span>  
  
 <span data-ttu-id="d9df4-159">Tipo de objeto: TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="d9df4-159">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="d9df4-160">Identificador de instancia de objeto: 177556</span><span class="sxs-lookup"><span data-stu-id="d9df4-160">Object Instance Identifier: 177556</span></span>  
  
 <span data-ttu-id="d9df4-161">ACTUALIZACIÓN DE AGENDA 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-161">AGENDA UPDATE 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="d9df4-162">Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="d9df4-162">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="d9df4-163">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-163">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-164">Operación: agregar</span><span class="sxs-lookup"><span data-stu-id="d9df4-164">Operation: Add</span></span>  
  
 <span data-ttu-id="d9df4-165">Nombre de regla: TestRule1</span><span class="sxs-lookup"><span data-stu-id="d9df4-165">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="d9df4-166">Criterios de resolución de conflictos: 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-166">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="d9df4-167">ACTIVIDAD DE DATOS 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-167">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="d9df4-168">Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="d9df4-168">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="d9df4-169">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-169">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-170">Operación: Assert</span><span class="sxs-lookup"><span data-stu-id="d9df4-170">Operation: Assert</span></span>  
  
 <span data-ttu-id="d9df4-171">Tipo de objeto: TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="d9df4-171">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="d9df4-172">Identificador de instancia de objeto: 177559</span><span class="sxs-lookup"><span data-stu-id="d9df4-172">Object Instance Identifier: 177559</span></span>  
  
 <span data-ttu-id="d9df4-173">ACTUALIZACIÓN DE AGENDA 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-173">AGENDA UPDATE 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="d9df4-174">Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="d9df4-174">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="d9df4-175">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-175">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-176">Operación: agregar</span><span class="sxs-lookup"><span data-stu-id="d9df4-176">Operation: Add</span></span>  
  
 <span data-ttu-id="d9df4-177">Nombre de regla: TestRule1</span><span class="sxs-lookup"><span data-stu-id="d9df4-177">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="d9df4-178">Criterios de resolución de conflictos: 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-178">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="d9df4-179">ACTIVIDAD DE DATOS 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-179">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="d9df4-180">Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="d9df4-180">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="d9df4-181">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-181">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-182">Operación: Assert</span><span class="sxs-lookup"><span data-stu-id="d9df4-182">Operation: Assert</span></span>  
  
 <span data-ttu-id="d9df4-183">Tipo de objeto: TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="d9df4-183">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="d9df4-184">Identificador de instancia de objeto: 177558</span><span class="sxs-lookup"><span data-stu-id="d9df4-184">Object Instance Identifier: 177558</span></span>  
  
 <span data-ttu-id="d9df4-185">ACTUALIZACIÓN DE AGENDA 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-185">AGENDA UPDATE 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="d9df4-186">Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="d9df4-186">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="d9df4-187">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-187">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-188">Operación: agregar</span><span class="sxs-lookup"><span data-stu-id="d9df4-188">Operation: Add</span></span>  
  
 <span data-ttu-id="d9df4-189">Nombre de regla: TestRule1</span><span class="sxs-lookup"><span data-stu-id="d9df4-189">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="d9df4-190">Criterios de resolución de conflictos: 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-190">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="d9df4-191">REGLA ACTIVADA 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-191">RULE FIRED 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="d9df4-192">Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="d9df4-192">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="d9df4-193">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-193">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-194">Nombre de regla: TestRule1</span><span class="sxs-lookup"><span data-stu-id="d9df4-194">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="d9df4-195">Criterios de resolución de conflictos: 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-195">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="d9df4-196">REGLA ACTIVADA 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-196">RULE FIRED 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="d9df4-197">Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="d9df4-197">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="d9df4-198">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-198">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-199">Nombre de regla: TestRule1</span><span class="sxs-lookup"><span data-stu-id="d9df4-199">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="d9df4-200">Criterios de resolución de conflictos: 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-200">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="d9df4-201">REGLA ACTIVADA 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-201">RULE FIRED 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="d9df4-202">Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="d9df4-202">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="d9df4-203">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-203">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-204">Nombre de regla: TestRule1</span><span class="sxs-lookup"><span data-stu-id="d9df4-204">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="d9df4-205">Criterios de resolución de conflictos: 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-205">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="d9df4-206">ACTIVIDAD DE DATOS 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-206">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="d9df4-207">Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="d9df4-207">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="d9df4-208">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-208">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-209">Operación: retirar</span><span class="sxs-lookup"><span data-stu-id="d9df4-209">Operation: Retract</span></span>  
  
 <span data-ttu-id="d9df4-210">Tipo de objeto: DataConnection:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="d9df4-210">Object Type: DataConnection:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="d9df4-211">Identificador de instancia de objeto: 874</span><span class="sxs-lookup"><span data-stu-id="d9df4-211">Object Instance Identifier: 874</span></span>  
  
 <span data-ttu-id="d9df4-212">ACTIVIDAD DE DATOS 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-212">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="d9df4-213">Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="d9df4-213">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="d9df4-214">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-214">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-215">Operación: retirar</span><span class="sxs-lookup"><span data-stu-id="d9df4-215">Operation: Retract</span></span>  
  
 <span data-ttu-id="d9df4-216">Tipo de objeto: TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="d9df4-216">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="d9df4-217">Identificador de instancia de objeto: 177559</span><span class="sxs-lookup"><span data-stu-id="d9df4-217">Object Instance Identifier: 177559</span></span>  
  
 <span data-ttu-id="d9df4-218">ACTIVIDAD DE DATOS 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-218">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="d9df4-219">Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="d9df4-219">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="d9df4-220">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-220">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-221">Operación: retirar</span><span class="sxs-lookup"><span data-stu-id="d9df4-221">Operation: Retract</span></span>  
  
 <span data-ttu-id="d9df4-222">Tipo de objeto: TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="d9df4-222">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="d9df4-223">Identificador de instancia de objeto: 177558</span><span class="sxs-lookup"><span data-stu-id="d9df4-223">Object Instance Identifier: 177558</span></span>  
  
 <span data-ttu-id="d9df4-224">ACTIVIDAD DE DATOS 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-224">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="d9df4-225">Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="d9df4-225">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="d9df4-226">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-226">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-227">Operación: retirar</span><span class="sxs-lookup"><span data-stu-id="d9df4-227">Operation: Retract</span></span>  
  
 <span data-ttu-id="d9df4-228">Tipo de objeto: TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="d9df4-228">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="d9df4-229">Identificador de instancia de objeto: 177556</span><span class="sxs-lookup"><span data-stu-id="d9df4-229">Object Instance Identifier: 177556</span></span>  
  
 <span data-ttu-id="d9df4-230">En el ejemplo anterior se indica que tres filas de la tabla CustInfo cumplen la condición de la regla.</span><span class="sxs-lookup"><span data-stu-id="d9df4-230">The example above indicates that three rows in the CustInfo table met the condition in the rule.</span></span>  <span data-ttu-id="d9df4-231">Por eso hubo que imponer únicamente tres TypedDataRows en el motor y se produjo una actualización de agenda y activación de reglas para cada instancia.</span><span class="sxs-lookup"><span data-stu-id="d9df4-231">This caused three unique TypedDataRows to be asserted into the engine and an agenda update and rule firing to occur for each instance.</span></span>  
  
## <a name="typedatatabletypeddatarow"></a><span data-ttu-id="d9df4-232">TypeDataTable/TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="d9df4-232">TypeDataTable/TypedDataRow</span></span>  
 <span data-ttu-id="d9df4-233">Regla de ejemplo "TestRule1" en la directiva "LoanProcessing":</span><span class="sxs-lookup"><span data-stu-id="d9df4-233">Example rule "TestRule1" in policy "LoanProcessing":</span></span>  
  
```  
IF NorthWind.CustInfo.CreditCardBalance > 0  
THEN <do something>  
```  
  
 <span data-ttu-id="d9df4-234">**Resultado:**</span><span class="sxs-lookup"><span data-stu-id="d9df4-234">**Output:**</span></span>  
  
 <span data-ttu-id="d9df4-235">SEGUIMIENTO de motor de reglas para conjunto de reglas: LoanProcessing 3/17/2004 11:27:35 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-235">RULE ENGINE TRACE for RULESET: LoanProcessing 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="d9df4-236">ACTIVIDAD DE DATOS 3/17/2004 11:27:35 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-236">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="d9df4-237">Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="d9df4-237">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="d9df4-238">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-238">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-239">Operación: Assert</span><span class="sxs-lookup"><span data-stu-id="d9df4-239">Operation: Assert</span></span>  
  
 <span data-ttu-id="d9df4-240">Tipo de objeto: TypedDataTable:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="d9df4-240">Object Type: TypedDataTable:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="d9df4-241">Identificador de instancia de objeto: 377</span><span class="sxs-lookup"><span data-stu-id="d9df4-241">Object Instance Identifier: 377</span></span>  
  
 <span data-ttu-id="d9df4-242">ACTIVIDAD DE DATOS 3/17/2004 11:27:35 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-242">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="d9df4-243">Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="d9df4-243">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="d9df4-244">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-244">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-245">Operación: Assert</span><span class="sxs-lookup"><span data-stu-id="d9df4-245">Operation: Assert</span></span>  
  
 <span data-ttu-id="d9df4-246">Tipo de objeto: TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="d9df4-246">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="d9df4-247">Identificador de instancia de objeto: 376</span><span class="sxs-lookup"><span data-stu-id="d9df4-247">Object Instance Identifier: 376</span></span>  
  
 <span data-ttu-id="d9df4-248">PRUEBA DE EVALUACIÓN DE CONDICIÓN (COINCIDENCIA) 3/17/2004 11:27:35 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-248">CONDITION EVALUATION TEST (MATCH) 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="d9df4-249">Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="d9df4-249">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="d9df4-250">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-250">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-251">Expresión de prueba: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-251">Test Expression: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span></span>  
  
 <span data-ttu-id="d9df4-252">Deja el valor del operando: 500</span><span class="sxs-lookup"><span data-stu-id="d9df4-252">Left Operand Value: 500</span></span>  
  
 <span data-ttu-id="d9df4-253">Valor del operando de la derecha: 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-253">Right Operand Value: 0</span></span>  
  
 <span data-ttu-id="d9df4-254">Resultado de pruebas: True</span><span class="sxs-lookup"><span data-stu-id="d9df4-254">Test Result: True</span></span>  
  
 <span data-ttu-id="d9df4-255">ACTUALIZACIÓN DE AGENDA 3/17/2004 11:27:35 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-255">AGENDA UPDATE 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="d9df4-256">Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="d9df4-256">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="d9df4-257">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-257">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-258">Operación: agregar</span><span class="sxs-lookup"><span data-stu-id="d9df4-258">Operation: Add</span></span>  
  
 <span data-ttu-id="d9df4-259">Nombre de regla: TestRule1</span><span class="sxs-lookup"><span data-stu-id="d9df4-259">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="d9df4-260">Criterios de resolución de conflictos: 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-260">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="d9df4-261">ACTIVIDAD DE DATOS 3/17/2004 11:27:35 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-261">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="d9df4-262">Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="d9df4-262">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="d9df4-263">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-263">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-264">Operación: Assert</span><span class="sxs-lookup"><span data-stu-id="d9df4-264">Operation: Assert</span></span>  
  
 <span data-ttu-id="d9df4-265">Tipo de objeto: TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="d9df4-265">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="d9df4-266">Identificador de instancia de objeto: 375</span><span class="sxs-lookup"><span data-stu-id="d9df4-266">Object Instance Identifier: 375</span></span>  
  
 <span data-ttu-id="d9df4-267">PRUEBA DE EVALUACIÓN DE CONDICIÓN (COINCIDENCIA) 3/17/2004 11:27:35 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-267">CONDITION EVALUATION TEST (MATCH) 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="d9df4-268">Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="d9df4-268">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="d9df4-269">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-269">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-270">Expresión de prueba: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-270">Test Expression: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span></span>  
  
 <span data-ttu-id="d9df4-271">Deja el valor del operando: 1000</span><span class="sxs-lookup"><span data-stu-id="d9df4-271">Left Operand Value: 1000</span></span>  
  
 <span data-ttu-id="d9df4-272">Valor del operando de la derecha: 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-272">Right Operand Value: 0</span></span>  
  
 <span data-ttu-id="d9df4-273">Resultado de pruebas: True</span><span class="sxs-lookup"><span data-stu-id="d9df4-273">Test Result: True</span></span>  
  
 <span data-ttu-id="d9df4-274">ACTUALIZACIÓN DE AGENDA 3/17/2004 11:27:35 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-274">AGENDA UPDATE 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="d9df4-275">Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="d9df4-275">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="d9df4-276">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-276">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-277">Operación: agregar</span><span class="sxs-lookup"><span data-stu-id="d9df4-277">Operation: Add</span></span>  
  
 <span data-ttu-id="d9df4-278">Nombre de regla: TestRule1</span><span class="sxs-lookup"><span data-stu-id="d9df4-278">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="d9df4-279">Criterios de resolución de conflictos: 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-279">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="d9df4-280">ACTIVIDAD DE DATOS 3/17/2004 11:27:35 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-280">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="d9df4-281">Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="d9df4-281">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="d9df4-282">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-282">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-283">Operación: Assert</span><span class="sxs-lookup"><span data-stu-id="d9df4-283">Operation: Assert</span></span>  
  
 <span data-ttu-id="d9df4-284">Tipo de objeto: TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="d9df4-284">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="d9df4-285">Identificador de instancia de objeto: 374</span><span class="sxs-lookup"><span data-stu-id="d9df4-285">Object Instance Identifier: 374</span></span>  
  
 <span data-ttu-id="d9df4-286">PRUEBA DE EVALUACIÓN DE CONDICIÓN (COINCIDENCIA) 3/17/2004 11:27:35 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-286">CONDITION EVALUATION TEST (MATCH) 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="d9df4-287">Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="d9df4-287">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="d9df4-288">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-288">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-289">Expresión de prueba: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-289">Test Expression: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span></span>  
  
 <span data-ttu-id="d9df4-290">Deja el valor del operando: 35000</span><span class="sxs-lookup"><span data-stu-id="d9df4-290">Left Operand Value: 35000</span></span>  
  
 <span data-ttu-id="d9df4-291">Valor del operando de la derecha: 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-291">Right Operand Value: 0</span></span>  
  
 <span data-ttu-id="d9df4-292">Resultado de pruebas: True</span><span class="sxs-lookup"><span data-stu-id="d9df4-292">Test Result: True</span></span>  
  
 <span data-ttu-id="d9df4-293">ACTUALIZACIÓN DE AGENDA 3/17/2004 11:27:35 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-293">AGENDA UPDATE 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="d9df4-294">Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="d9df4-294">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="d9df4-295">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-295">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-296">Operación: agregar</span><span class="sxs-lookup"><span data-stu-id="d9df4-296">Operation: Add</span></span>  
  
 <span data-ttu-id="d9df4-297">Nombre de regla: TestRule1</span><span class="sxs-lookup"><span data-stu-id="d9df4-297">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="d9df4-298">Criterios de resolución de conflictos: 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-298">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="d9df4-299">REGLA ACTIVADA 3/17/2004 11:27:35 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-299">RULE FIRED 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="d9df4-300">Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="d9df4-300">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="d9df4-301">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-301">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-302">Nombre de regla: TestRule1</span><span class="sxs-lookup"><span data-stu-id="d9df4-302">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="d9df4-303">Criterios de resolución de conflictos: 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-303">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="d9df4-304">REGLA ACTIVADA 3/17/2004 11:27:35 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-304">RULE FIRED 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="d9df4-305">Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="d9df4-305">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="d9df4-306">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-306">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-307">Nombre de regla: TestRule1</span><span class="sxs-lookup"><span data-stu-id="d9df4-307">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="d9df4-308">Criterios de resolución de conflictos: 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-308">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="d9df4-309">REGLA ACTIVADA 3/17/2004 11:27:35 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-309">RULE FIRED 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="d9df4-310">Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="d9df4-310">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="d9df4-311">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-311">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-312">Nombre de regla: TestRule1</span><span class="sxs-lookup"><span data-stu-id="d9df4-312">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="d9df4-313">Criterios de resolución de conflictos: 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-313">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="d9df4-314">ACTIVIDAD DE DATOS 3/17/2004 11:27:35 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-314">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="d9df4-315">Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="d9df4-315">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="d9df4-316">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-316">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-317">Operación: retirar</span><span class="sxs-lookup"><span data-stu-id="d9df4-317">Operation: Retract</span></span>  
  
 <span data-ttu-id="d9df4-318">Tipo de objeto: TypedDataTable:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="d9df4-318">Object Type: TypedDataTable:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="d9df4-319">Identificador de instancia de objeto: 377</span><span class="sxs-lookup"><span data-stu-id="d9df4-319">Object Instance Identifier: 377</span></span>  
  
 <span data-ttu-id="d9df4-320">ACTIVIDAD DE DATOS 3/17/2004 11:27:35 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-320">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="d9df4-321">Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="d9df4-321">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="d9df4-322">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-322">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-323">Operación: retirar</span><span class="sxs-lookup"><span data-stu-id="d9df4-323">Operation: Retract</span></span>  
  
 <span data-ttu-id="d9df4-324">Tipo de objeto: TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="d9df4-324">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="d9df4-325">Identificador de instancia de objeto: 375</span><span class="sxs-lookup"><span data-stu-id="d9df4-325">Object Instance Identifier: 375</span></span>  
  
 <span data-ttu-id="d9df4-326">ACTIVIDAD DE DATOS 3/17/2004 11:27:35 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-326">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="d9df4-327">Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="d9df4-327">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="d9df4-328">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-328">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-329">Operación: retirar</span><span class="sxs-lookup"><span data-stu-id="d9df4-329">Operation: Retract</span></span>  
  
 <span data-ttu-id="d9df4-330">Tipo de objeto: TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="d9df4-330">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="d9df4-331">Identificador de instancia de objeto: 374</span><span class="sxs-lookup"><span data-stu-id="d9df4-331">Object Instance Identifier: 374</span></span>  
  
 <span data-ttu-id="d9df4-332">ACTIVIDAD DE DATOS 3/17/2004 11:27:35 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-332">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="d9df4-333">Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="d9df4-333">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="d9df4-334">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-334">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-335">Operación: retirar</span><span class="sxs-lookup"><span data-stu-id="d9df4-335">Operation: Retract</span></span>  
  
 <span data-ttu-id="d9df4-336">Tipo de objeto: TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="d9df4-336">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="d9df4-337">Identificador de instancia de objeto: 376</span><span class="sxs-lookup"><span data-stu-id="d9df4-337">Object Instance Identifier: 376</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9df4-338">En el ejemplo anterior se muestra que TypedDataTable contenía tres filas y todas estaban declaradas como TypedDataRow.</span><span class="sxs-lookup"><span data-stu-id="d9df4-338">The example above shows that the TypedDataTable contained three rows, and each was asserted as a TypedDataRow.</span></span>  <span data-ttu-id="d9df4-339">Todas se evaluaron como True en la condición, lo que hizo que la regla se agregara a la agenda y se activara.</span><span class="sxs-lookup"><span data-stu-id="d9df4-339">Each evaluated to True in the condition and caused the rule to be added to the agenda and fired.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="d9df4-340">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="d9df4-340">TypedXmlDocument</span></span>  
 <span data-ttu-id="d9df4-341">Regla de ejemplo "TestRule1" en la directiva "LoanProcessing":</span><span class="sxs-lookup"><span data-stu-id="d9df4-341">Example rule "TestRule1" in policy "LoanProcessing":</span></span>  
  
```  
IF Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType.TimeInMonths >= 4  
THEN <do something>  
```  
  
 <span data-ttu-id="d9df4-342">**Resultado:**</span><span class="sxs-lookup"><span data-stu-id="d9df4-342">**Output:**</span></span>  
  
 <span data-ttu-id="d9df4-343">SEGUIMIENTO de motor de reglas para conjunto de reglas: LoanProcessing 3/17/2004 9:23:05 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-343">RULE ENGINE TRACE for RULESET: LoanProcessing 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="d9df4-344">ACTIVIDAD DE DATOS 3/17/2004 9:23:05 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-344">FACT ACTIVITY 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="d9df4-345">Identificador de la instancia de motor de reglas: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="d9df4-345">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="d9df4-346">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-346">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-347">Operación: Assert</span><span class="sxs-lookup"><span data-stu-id="d9df4-347">Operation: Assert</span></span>  
  
 <span data-ttu-id="d9df4-348">Tipo de objeto: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case</span><span class="sxs-lookup"><span data-stu-id="d9df4-348">Object Type: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case</span></span>  
  
 <span data-ttu-id="d9df4-349">Identificador de instancia de objeto: 858</span><span class="sxs-lookup"><span data-stu-id="d9df4-349">Object Instance Identifier: 858</span></span>  
  
 <span data-ttu-id="d9df4-350">ACTIVIDAD DE DATOS 3/17/2004 9:23:05 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-350">FACT ACTIVITY 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="d9df4-351">Identificador de la instancia de motor de reglas: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="d9df4-351">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="d9df4-352">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-352">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-353">Operación: Assert</span><span class="sxs-lookup"><span data-stu-id="d9df4-353">Operation: Assert</span></span>  
  
 <span data-ttu-id="d9df4-354">Tipo de objeto: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType</span><span class="sxs-lookup"><span data-stu-id="d9df4-354">Object Type: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType</span></span>  
  
 <span data-ttu-id="d9df4-355">Identificador de instancia de objeto: 853</span><span class="sxs-lookup"><span data-stu-id="d9df4-355">Object Instance Identifier: 853</span></span>  
  
 <span data-ttu-id="d9df4-356">PRUEBA DE EVALUACIÓN DE CONDICIÓN (COINCIDENCIA) 3/17/2004 9:23:05 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-356">CONDITION EVALUATION TEST (MATCH) 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="d9df4-357">Identificador de la instancia de motor de reglas: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="d9df4-357">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="d9df4-358">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-358">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-359">Expresión de prueba: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType.TimeInMonths > = 4</span><span class="sxs-lookup"><span data-stu-id="d9df4-359">Test Expression: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType.TimeInMonths >= 4</span></span>  
  
 <span data-ttu-id="d9df4-360">Deja el valor del operando: 6</span><span class="sxs-lookup"><span data-stu-id="d9df4-360">Left Operand Value: 6</span></span>  
  
 <span data-ttu-id="d9df4-361">Valor del operando de la derecha: 4</span><span class="sxs-lookup"><span data-stu-id="d9df4-361">Right Operand Value: 4</span></span>  
  
 <span data-ttu-id="d9df4-362">Resultado de pruebas: True</span><span class="sxs-lookup"><span data-stu-id="d9df4-362">Test Result: True</span></span>  
  
 <span data-ttu-id="d9df4-363">ACTUALIZACIÓN DE AGENDA 3/17/2004 9:23:05 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-363">AGENDA UPDATE 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="d9df4-364">Identificador de la instancia de motor de reglas: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="d9df4-364">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="d9df4-365">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-365">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-366">Operación: agregar</span><span class="sxs-lookup"><span data-stu-id="d9df4-366">Operation: Add</span></span>  
  
 <span data-ttu-id="d9df4-367">Nombre de regla: TestRule1</span><span class="sxs-lookup"><span data-stu-id="d9df4-367">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="d9df4-368">Criterios de resolución de conflictos: 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-368">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="d9df4-369">REGLA ACTIVADA 3/17/2004 9:23:05 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-369">RULE FIRED 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="d9df4-370">Identificador de la instancia de motor de reglas: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="d9df4-370">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="d9df4-371">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-371">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-372">Nombre de regla: TestRule1</span><span class="sxs-lookup"><span data-stu-id="d9df4-372">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="d9df4-373">Criterios de resolución de conflictos: 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-373">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="d9df4-374">ACTIVIDAD DE DATOS 3/17/2004 9:23:05 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-374">FACT ACTIVITY 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="d9df4-375">Identificador de la instancia de motor de reglas: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="d9df4-375">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="d9df4-376">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-376">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-377">Operación: retirar</span><span class="sxs-lookup"><span data-stu-id="d9df4-377">Operation: Retract</span></span>  
  
 <span data-ttu-id="d9df4-378">Tipo de objeto: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case</span><span class="sxs-lookup"><span data-stu-id="d9df4-378">Object Type: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case</span></span>  
  
 <span data-ttu-id="d9df4-379">Identificador de instancia de objeto: 858</span><span class="sxs-lookup"><span data-stu-id="d9df4-379">Object Instance Identifier: 858</span></span>  
  
 <span data-ttu-id="d9df4-380">ACTIVIDAD DE DATOS 3/17/2004 9:23:05 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-380">FACT ACTIVITY 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="d9df4-381">Identificador de la instancia de motor de reglas: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="d9df4-381">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="d9df4-382">Nombre de conjunto de reglas: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="d9df4-382">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="d9df4-383">Operación: retirar</span><span class="sxs-lookup"><span data-stu-id="d9df4-383">Operation: Retract</span></span>  
  
 <span data-ttu-id="d9df4-384">Tipo de objeto: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType</span><span class="sxs-lookup"><span data-stu-id="d9df4-384">Object Type: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType</span></span>  
  
 <span data-ttu-id="d9df4-385">Identificador de instancia de objeto: 853</span><span class="sxs-lookup"><span data-stu-id="d9df4-385">Object Instance Identifier: 853</span></span>  
  
 <span data-ttu-id="d9df4-386">Este ejemplo muestra que un **TypedXmlDocument** se imponen en el motor con un tipo de documento de "Microsoft.Samples.BizTalk.LoansProcessor.Case".</span><span class="sxs-lookup"><span data-stu-id="d9df4-386">This example shows that a **TypedXmlDocument** was asserted into the engine with a document type of "Microsoft.Samples.BizTalk.LoansProcessor.Case".</span></span>  <span data-ttu-id="d9df4-387">En función del selector XPath definido en la regla, el motor creó y declaró un TypedXmlDocument secundario con el tipo "Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType" basado en el tipo de documento y la cadena de selector.</span><span class="sxs-lookup"><span data-stu-id="d9df4-387">Based on the XPath selector defined in the rule, the engine then created and asserted a child TypedXmlDocument with type  "Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType" based on the document type and selector string.</span></span>  
  
 <span data-ttu-id="d9df4-388">Dado que este TypedXmlDocument secundario fue evaluado como True en la condición, se originó una actualización de agenda y activación de reglas.</span><span class="sxs-lookup"><span data-stu-id="d9df4-388">This child TypedXmlDocument evaluated to True in the condition, causing an agenda update and rule firing.</span></span>  <span data-ttu-id="d9df4-389">El elemento primario y el secundario **TypedXmlDocument**del, a continuación, se retiraron.</span><span class="sxs-lookup"><span data-stu-id="d9df4-389">The parent and child **TypedXmlDocument**'s were then retracted.</span></span>  
  
## <a name="update-function"></a><span data-ttu-id="d9df4-390">Función Update</span><span class="sxs-lookup"><span data-stu-id="d9df4-390">Update Function</span></span>  
 <span data-ttu-id="d9df4-391">Directiva de ejemplo "Order"</span><span class="sxs-lookup"><span data-stu-id="d9df4-391">Example policy "Order"</span></span>  
  
 <span data-ttu-id="d9df4-392">**Regla "InventoryCheck"**</span><span class="sxs-lookup"><span data-stu-id="d9df4-392">**"InventoryCheck" Rule**</span></span>  
  
```  
IF Inventory.AllocateInventory == True  
THEN Order.inventoryAvailable == True  
   Update(Order)  
```  
  
 <span data-ttu-id="d9df4-393">**Regla "Ship"**</span><span class="sxs-lookup"><span data-stu-id="d9df4-393">**"Ship" Rule**</span></span>  
  
```  
IF Order.inventoryAvailable == True  
THEN Shipment.ShipOrder  
```  
  
 <span data-ttu-id="d9df4-394">**Resultado:**</span><span class="sxs-lookup"><span data-stu-id="d9df4-394">**Output:**</span></span>  
  
 <span data-ttu-id="d9df4-395">SEGUIMIENTO de motor de reglas para conjunto de reglas: ordenar 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-395">RULE ENGINE TRACE for RULESET: Order 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="d9df4-396">ACTIVIDAD DE DATOS 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-396">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="d9df4-397">Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="d9df4-397">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="d9df4-398">Nombre de conjunto de reglas: orden</span><span class="sxs-lookup"><span data-stu-id="d9df4-398">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="d9df4-399">Operación: Assert</span><span class="sxs-lookup"><span data-stu-id="d9df4-399">Operation: Assert</span></span>  
  
 <span data-ttu-id="d9df4-400">Tipo de objeto: TestClasses.Order</span><span class="sxs-lookup"><span data-stu-id="d9df4-400">Object Type: TestClasses.Order</span></span>  
  
 <span data-ttu-id="d9df4-401">Identificador de instancia de objeto: 448</span><span class="sxs-lookup"><span data-stu-id="d9df4-401">Object Instance Identifier: 448</span></span>  
  
 <span data-ttu-id="d9df4-402">PRUEBA DE EVALUACIÓN DE CONDICIÓN (COINCIDENCIA) 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-402">CONDITION EVALUATION TEST (MATCH) 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="d9df4-403">Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="d9df4-403">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="d9df4-404">Nombre de conjunto de reglas: orden</span><span class="sxs-lookup"><span data-stu-id="d9df4-404">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="d9df4-405">Expresión de prueba: TestClasses.Order.inventoryAvailable == True</span><span class="sxs-lookup"><span data-stu-id="d9df4-405">Test Expression: TestClasses.Order.inventoryAvailable == True</span></span>  
  
 <span data-ttu-id="d9df4-406">Deja el valor del operando: null</span><span class="sxs-lookup"><span data-stu-id="d9df4-406">Left Operand Value: null</span></span>  
  
 <span data-ttu-id="d9df4-407">Valor del operando de la derecha: True</span><span class="sxs-lookup"><span data-stu-id="d9df4-407">Right Operand Value: True</span></span>  
  
 <span data-ttu-id="d9df4-408">Resultado de pruebas: False</span><span class="sxs-lookup"><span data-stu-id="d9df4-408">Test Result: False</span></span>  
  
 <span data-ttu-id="d9df4-409">ACTIVIDAD DE DATOS 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-409">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="d9df4-410">Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="d9df4-410">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="d9df4-411">Nombre de conjunto de reglas: orden</span><span class="sxs-lookup"><span data-stu-id="d9df4-411">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="d9df4-412">Operación: Assert</span><span class="sxs-lookup"><span data-stu-id="d9df4-412">Operation: Assert</span></span>  
  
 <span data-ttu-id="d9df4-413">Tipo de objeto: TestClasses.Shipment</span><span class="sxs-lookup"><span data-stu-id="d9df4-413">Object Type: TestClasses.Shipment</span></span>  
  
 <span data-ttu-id="d9df4-414">Identificador de instancia de objeto: 447</span><span class="sxs-lookup"><span data-stu-id="d9df4-414">Object Instance Identifier: 447</span></span>  
  
 <span data-ttu-id="d9df4-415">ACTIVIDAD DE DATOS 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-415">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="d9df4-416">Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="d9df4-416">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="d9df4-417">Nombre de conjunto de reglas: orden</span><span class="sxs-lookup"><span data-stu-id="d9df4-417">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="d9df4-418">Operación: Assert</span><span class="sxs-lookup"><span data-stu-id="d9df4-418">Operation: Assert</span></span>  
  
 <span data-ttu-id="d9df4-419">Tipo de objeto: TestClasses.Inventory</span><span class="sxs-lookup"><span data-stu-id="d9df4-419">Object Type: TestClasses.Inventory</span></span>  
  
 <span data-ttu-id="d9df4-420">Identificador de instancia de objeto: 446</span><span class="sxs-lookup"><span data-stu-id="d9df4-420">Object Instance Identifier: 446</span></span>  
  
 <span data-ttu-id="d9df4-421">PRUEBA DE EVALUACIÓN DE CONDICIÓN (COINCIDENCIA) 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-421">CONDITION EVALUATION TEST (MATCH) 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="d9df4-422">Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="d9df4-422">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="d9df4-423">Nombre de conjunto de reglas: orden</span><span class="sxs-lookup"><span data-stu-id="d9df4-423">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="d9df4-424">Expresión de prueba: TestClasses.Inventory.AllocateInventory == True</span><span class="sxs-lookup"><span data-stu-id="d9df4-424">Test Expression: TestClasses.Inventory.AllocateInventory == True</span></span>  
  
 <span data-ttu-id="d9df4-425">Deja el valor del operando: True</span><span class="sxs-lookup"><span data-stu-id="d9df4-425">Left Operand Value: True</span></span>  
  
 <span data-ttu-id="d9df4-426">Valor del operando de la derecha: True</span><span class="sxs-lookup"><span data-stu-id="d9df4-426">Right Operand Value: True</span></span>  
  
 <span data-ttu-id="d9df4-427">Resultado de pruebas: True</span><span class="sxs-lookup"><span data-stu-id="d9df4-427">Test Result: True</span></span>  
  
 <span data-ttu-id="d9df4-428">ACTUALIZACIÓN DE AGENDA 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-428">AGENDA UPDATE 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="d9df4-429">Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="d9df4-429">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="d9df4-430">Nombre de conjunto de reglas: orden</span><span class="sxs-lookup"><span data-stu-id="d9df4-430">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="d9df4-431">Operación: agregar</span><span class="sxs-lookup"><span data-stu-id="d9df4-431">Operation: Add</span></span>  
  
 <span data-ttu-id="d9df4-432">Nombre de regla: InventoryCheck</span><span class="sxs-lookup"><span data-stu-id="d9df4-432">Rule Name: InventoryCheck</span></span>  
  
 <span data-ttu-id="d9df4-433">Criterios de resolución de conflictos: 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-433">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="d9df4-434">REGLA ACTIVADA 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-434">RULE FIRED 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="d9df4-435">Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="d9df4-435">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="d9df4-436">Nombre de conjunto de reglas: orden</span><span class="sxs-lookup"><span data-stu-id="d9df4-436">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="d9df4-437">Nombre de regla: InventoryCheck</span><span class="sxs-lookup"><span data-stu-id="d9df4-437">Rule Name: InventoryCheck</span></span>  
  
 <span data-ttu-id="d9df4-438">Criterios de resolución de conflictos: 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-438">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="d9df4-439">ACTIVIDAD DE DATOS 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-439">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="d9df4-440">Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="d9df4-440">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="d9df4-441">Nombre de conjunto de reglas: orden</span><span class="sxs-lookup"><span data-stu-id="d9df4-441">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="d9df4-442">Operación: actualización</span><span class="sxs-lookup"><span data-stu-id="d9df4-442">Operation: Update</span></span>  
  
 <span data-ttu-id="d9df4-443">Tipo de objeto: TestClasses.Order</span><span class="sxs-lookup"><span data-stu-id="d9df4-443">Object Type: TestClasses.Order</span></span>  
  
 <span data-ttu-id="d9df4-444">Identificador de instancia de objeto: 448</span><span class="sxs-lookup"><span data-stu-id="d9df4-444">Object Instance Identifier: 448</span></span>  
  
 <span data-ttu-id="d9df4-445">PRUEBA DE EVALUACIÓN DE CONDICIÓN (COINCIDENCIA) 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-445">CONDITION EVALUATION TEST (MATCH) 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="d9df4-446">Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="d9df4-446">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="d9df4-447">Nombre de conjunto de reglas: orden</span><span class="sxs-lookup"><span data-stu-id="d9df4-447">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="d9df4-448">Expresión de prueba: TestClasses.Order.inventoryAvailable == True</span><span class="sxs-lookup"><span data-stu-id="d9df4-448">Test Expression: TestClasses.Order.inventoryAvailable == True</span></span>  
  
 <span data-ttu-id="d9df4-449">Deja el valor del operando: True</span><span class="sxs-lookup"><span data-stu-id="d9df4-449">Left Operand Value: True</span></span>  
  
 <span data-ttu-id="d9df4-450">Valor del operando de la derecha: True</span><span class="sxs-lookup"><span data-stu-id="d9df4-450">Right Operand Value: True</span></span>  
  
 <span data-ttu-id="d9df4-451">Resultado de pruebas: True</span><span class="sxs-lookup"><span data-stu-id="d9df4-451">Test Result: True</span></span>  
  
 <span data-ttu-id="d9df4-452">ACTUALIZACIÓN DE AGENDA 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-452">AGENDA UPDATE 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="d9df4-453">Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="d9df4-453">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="d9df4-454">Nombre de conjunto de reglas: orden</span><span class="sxs-lookup"><span data-stu-id="d9df4-454">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="d9df4-455">Operación: agregar</span><span class="sxs-lookup"><span data-stu-id="d9df4-455">Operation: Add</span></span>  
  
 <span data-ttu-id="d9df4-456">Nombre de regla: envío</span><span class="sxs-lookup"><span data-stu-id="d9df4-456">Rule Name: Ship</span></span>  
  
 <span data-ttu-id="d9df4-457">Criterios de resolución de conflictos: 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-457">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="d9df4-458">REGLA ACTIVADA 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-458">RULE FIRED 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="d9df4-459">Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="d9df4-459">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="d9df4-460">Nombre de conjunto de reglas: orden</span><span class="sxs-lookup"><span data-stu-id="d9df4-460">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="d9df4-461">Nombre de regla: envío</span><span class="sxs-lookup"><span data-stu-id="d9df4-461">Rule Name: Ship</span></span>  
  
 <span data-ttu-id="d9df4-462">Criterios de resolución de conflictos: 0</span><span class="sxs-lookup"><span data-stu-id="d9df4-462">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="d9df4-463">ACTIVIDAD DE DATOS 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-463">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="d9df4-464">Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="d9df4-464">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="d9df4-465">Nombre de conjunto de reglas: orden</span><span class="sxs-lookup"><span data-stu-id="d9df4-465">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="d9df4-466">Operación: retirar</span><span class="sxs-lookup"><span data-stu-id="d9df4-466">Operation: Retract</span></span>  
  
 <span data-ttu-id="d9df4-467">Tipo de objeto: TestClasses.Order</span><span class="sxs-lookup"><span data-stu-id="d9df4-467">Object Type: TestClasses.Order</span></span>  
  
 <span data-ttu-id="d9df4-468">Identificador de instancia de objeto: 448</span><span class="sxs-lookup"><span data-stu-id="d9df4-468">Object Instance Identifier: 448</span></span>  
  
 <span data-ttu-id="d9df4-469">ACTIVIDAD DE DATOS 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-469">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="d9df4-470">Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="d9df4-470">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="d9df4-471">Nombre de conjunto de reglas: orden</span><span class="sxs-lookup"><span data-stu-id="d9df4-471">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="d9df4-472">Operación: retirar</span><span class="sxs-lookup"><span data-stu-id="d9df4-472">Operation: Retract</span></span>  
  
 <span data-ttu-id="d9df4-473">Tipo de objeto: TestClasses.Shipment</span><span class="sxs-lookup"><span data-stu-id="d9df4-473">Object Type: TestClasses.Shipment</span></span>  
  
 <span data-ttu-id="d9df4-474">Identificador de instancia de objeto: 447</span><span class="sxs-lookup"><span data-stu-id="d9df4-474">Object Instance Identifier: 447</span></span>  
  
 <span data-ttu-id="d9df4-475">ACTIVIDAD DE DATOS 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="d9df4-475">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="d9df4-476">Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="d9df4-476">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="d9df4-477">Nombre de conjunto de reglas: orden</span><span class="sxs-lookup"><span data-stu-id="d9df4-477">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="d9df4-478">Operación: retirar</span><span class="sxs-lookup"><span data-stu-id="d9df4-478">Operation: Retract</span></span>  
  
 <span data-ttu-id="d9df4-479">Tipo de objeto: TestClasses.Inventory</span><span class="sxs-lookup"><span data-stu-id="d9df4-479">Object Type: TestClasses.Inventory</span></span>  
  
 <span data-ttu-id="d9df4-480">Identificador de instancia de objeto: 446</span><span class="sxs-lookup"><span data-stu-id="d9df4-480">Object Instance Identifier: 446</span></span>  
  
 <span data-ttu-id="d9df4-481">En este ejemplo, la condición asociada a la regla Ship se evalúa como False la primera vez que se comprueba.</span><span class="sxs-lookup"><span data-stu-id="d9df4-481">In this example, the condition associated with the Ship rule evaluates to False the first time it is checked.</span></span>  <span data-ttu-id="d9df4-482">Sin embargo, cuando la regla InventoryCheck se activa, el campo inventoryAvailable de Order cambia y se emite un comando Actualizar en el motor para el objeto Order.</span><span class="sxs-lookup"><span data-stu-id="d9df4-482">However, when the InventoryCheck rule fires, the inventoryAvailable field on the Order is changed and an Update command is issued on the engine for the Order object.</span></span>  <span data-ttu-id="d9df4-483">Esto hace que vuelva a evaluarse la regla Ship.</span><span class="sxs-lookup"><span data-stu-id="d9df4-483">This causes the Ship rule to be reevaluated.</span></span>  <span data-ttu-id="d9df4-484">En esta ocasión la condición se evalúa como verdadera y la regla Ship se activa.</span><span class="sxs-lookup"><span data-stu-id="d9df4-484">This time the condition evaluates to true and the Ship rule fires.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9df4-485">Si las reglas están escritas incorrectamente, el encadenamiento directo con la función Update puede ocasionar un bucle infinito.</span><span class="sxs-lookup"><span data-stu-id="d9df4-485">If your rules are written incorrectly, forward chaining with the Update function may cause an infinite loop.</span></span>  <span data-ttu-id="d9df4-486">Si esto ocurriera, recibirá un mensaje de error al probar la directiva en el Compositor de reglas de negocio con el texto "El motor de reglas detectó un bucle de ejecución".</span><span class="sxs-lookup"><span data-stu-id="d9df4-486">If this occurs, you will receive an error message when testing the policy in the Business Rule Composer with the text "The rule engine detected an execution loop."</span></span>