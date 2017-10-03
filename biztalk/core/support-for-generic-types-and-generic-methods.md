---
title: "Compatibilidad con tipos genéricos y métodos genéricos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc6b5b51-e084-4828-ad25-9209aa74dc6f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3601be46358a2f751bc44931043731d4e4b6351
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="support-for-generic-types-and-generic-methods"></a><span data-ttu-id="c5350-102">Compatibilidad para tipos y métodos genéricos</span><span class="sxs-lookup"><span data-stu-id="c5350-102">Support for Generic Types and Generic Methods</span></span>
<span data-ttu-id="c5350-103">El motor de reglas admite el uso de tipos y métodos genéricos especializados en una regla.</span><span class="sxs-lookup"><span data-stu-id="c5350-103">The rule engine supports using specialized generic types and specialized generic methods in a rule.</span></span> <span data-ttu-id="c5350-104">Sin embargo, no admite el uso de los tipos y métodos genéricos en una regla.</span><span class="sxs-lookup"><span data-stu-id="c5350-104">It does not support using generic types and generic methods themselves in a rule.</span></span> <span data-ttu-id="c5350-105">Por ejemplo, en una regla de negocios puede utilizar **lista**\<*int*>, pero no **lista**\<T > (desde el  **System.Collections.Generic** espacio de nombres en la biblioteca de clases. NET).</span><span class="sxs-lookup"><span data-stu-id="c5350-105">For example, in a business rule you can use **List**\<*int*>, but not **List**\<T> (from the **System.Collections.Generic** namespace in the .NET class library).</span></span> <span data-ttu-id="c5350-106">Actualmente, la herramienta Compositor de reglas de negocio no admite la creación de reglas mediante los tipos y métodos genéricos especializados.</span><span class="sxs-lookup"><span data-stu-id="c5350-106">Currently, the Business Rule Composer tool does not support creating rules by using specialized generic types and specialized generic methods.</span></span> <span data-ttu-id="c5350-107">Las reglas deben crearse mediante programación utilizando el modelo de objetos del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="c5350-107">You must create the rules programmatically by using the rule engine object model.</span></span> <span data-ttu-id="c5350-108">El código de ejemplo siguiente muestra cómo utilizar el **lista** clase genérica en una regla de negocios:</span><span class="sxs-lookup"><span data-stu-id="c5350-108">The following sample code demonstrates how to use the **List** generic class in a business rule:</span></span>  
  
```  
  
// Create the condition list IF 1 == 1  
Equal eq = new Equal(new Constant(1), new Constant(1));  
  
// Create the action list List<int>.Add(3)  
ActionCollection ac = new ActionCollection();  
  
//Create class binding and class member bindings  
ClassBinding lstClass = new ClassBinding(typeof(System.Collections.Generic.List<int>));  
ArgumentCollection argc = new ArgumentCollection();  
argc.Add(new Constant(3));  
ClassMemberBinding add = new ClassMemberBinding("Add", lstClass, argc);  
  
// Wrapping the .NET binding as a user function  
UserFunction uf = new UserFunction(add);  
ac.Add(uf);  
  
// Create the rule  
Rule rl = new Rule("AddToList", eq, ac);  
  
// Create the policy  
RuleSet rs = new RuleSet("GenericTest");  
rs.Rules.Add(rl);  
  
// Create the .NET List object  
List<int> lst = new List<int>();  
lst.Add(1);  
lst.Add(2);  
  
// Print the list before executing the policy  
Console.WriteLine("Contents of the lists before executing the policy");  
foreach (int i in lst)  
    Console.WriteLine(i);  
  
PolicyTester pt = new PolicyTester(rs);  
pt.Execute(lst);  
  
// Print the list after executing the policy  
Console.WriteLine("Contents of the lists before executing the policy");  
foreach (int i in lst)  
    Console.WriteLine(i);  
```