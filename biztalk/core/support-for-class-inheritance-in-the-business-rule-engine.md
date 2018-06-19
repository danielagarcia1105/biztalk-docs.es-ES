---
title: Compatibilidad con herencia de clases en el motor de reglas de negocios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- code samples, Business Rules Engine
- Business Rules Engine, inheritance
- Business Rules Engine, code samples
- Business Rules Engine, examples
- examples, Business Rules Engine
ms.assetid: 50871f34-ccbe-4f77-8feb-5694e1b14837
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 930fc5591ce55f1a2ec988b307203a4154e85c2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278628"
---
# <a name="support-for-class-inheritance-in-the-business-rule-engine"></a><span data-ttu-id="4ee4f-102">Compatibilidad con herencia de clases en el motor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="4ee4f-102">Support for Class Inheritance in the Business Rule Engine</span></span>
<span data-ttu-id="4ee4f-103">Una de las características clave de los lenguajes de programación orientada a objetos (OOP) es la herencia.</span><span class="sxs-lookup"><span data-stu-id="4ee4f-103">One of the key features of Object Oriented Programming (OOP) languages is inheritance.</span></span> <span data-ttu-id="4ee4f-104">La herencia es la capacidad de usar toda la funcionalidad de una clase existente y ampliar esa capacidad sin escribir de nuevo la clase original.</span><span class="sxs-lookup"><span data-stu-id="4ee4f-104">Inheritance is the ability to use all of the functionality of an existing class, and extend those capabilities without rewriting the original class.</span></span>  
  
 <span data-ttu-id="4ee4f-105">El marco de trabajo de reglas de negocios admite dos tipos de herencia de clases: implementación e interfaz.</span><span class="sxs-lookup"><span data-stu-id="4ee4f-105">The Business Rules Framework supports two types of class inheritance: implementation and interface.</span></span> <span data-ttu-id="4ee4f-106">La herencia de implementación hace referencia a la capacidad de usar las propiedades y los métodos de una clase base sin codificación adicional.</span><span class="sxs-lookup"><span data-stu-id="4ee4f-106">Implementation inheritance refers to the ability to use a base class's properties and methods with no additional coding.</span></span> <span data-ttu-id="4ee4f-107">La herencia de interfaz hace referencia a la capacidad de usar sólo los nombres de las propiedades y métodos, pero la clase secundaria debe proporcionar la implementación.</span><span class="sxs-lookup"><span data-stu-id="4ee4f-107">Interface inheritance refers to the ability to use just the names of the properties and methods, but the child class must provide the implementation.</span></span>  
  
 <span data-ttu-id="4ee4f-108">Las reglas se pueden escribir en términos de una clase base común, pero los objetos afirmados en el motor pueden ser de clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="4ee4f-108">The rules can be written in terms of a common base class, but the objects asserted into the engine can be from derived classes.</span></span> <span data-ttu-id="4ee4f-109">En el ejemplo siguiente, **RegularEmployee** y **ContractEmployee** son clases derivadas de la clase base **empleado**.</span><span class="sxs-lookup"><span data-stu-id="4ee4f-109">In the following example, **RegularEmployee** and **ContractEmployee** are derived classes of the base class **Employee**.</span></span>  
  
```  
class Employee  
   {  
      public string Status()  
      {   
         // member definition  
      }  
      public string TimeInMonths()        
      {   
         // member definition  
      }  
   }  
  
class ContractEmployee : Employee  
{  
   // class definition  
}  
class RegularEmployee : Employee  
{  
   // class definition  
}  
```  
  
 <span data-ttu-id="4ee4f-110">Imagine que tiene la siguiente regla.</span><span class="sxs-lookup"><span data-stu-id="4ee4f-110">Assume you have the following rule.</span></span>  
  
## <a name="rule-1"></a><span data-ttu-id="4ee4f-111">Regla 1</span><span class="sxs-lookup"><span data-stu-id="4ee4f-111">Rule 1</span></span>  
  
```  
IF Employee.TimeInMonths < 12  
THEN Employee.Status = "New"  
```  
  
 <span data-ttu-id="4ee4f-112">Durante la ejecución, si el usuario afirma dos objetos, uno una instancia de **ContractEmployee** y el otro es una instancia de **RegularEmployee**, las instancias de objeto se evalúan con la regla descrita versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="4ee4f-112">At run time, if the user asserts two objects, one an instance of **ContractEmployee** and the other an instance of **RegularEmployee**, both the object instances are evaluated against the rule described earlier.</span></span>  
  
 <span data-ttu-id="4ee4f-113">El usuario también puede afirmar objetos de clase derivados en acciones usando un **Assert**.</span><span class="sxs-lookup"><span data-stu-id="4ee4f-113">The user can also assert derived class objects in actions by using an **Assert**.</span></span> <span data-ttu-id="4ee4f-114">Esto da lugar a que se evalúen de nuevo las reglas que contienen el objeto derivado y su tipo base en sus condiciones, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4ee4f-114">This causes the rules that contain the derived object and its base type in their conditions to be re-evaluated, as shown in the following example.</span></span>  
  
## <a name="rule-2"></a><span data-ttu-id="4ee4f-115">Regla 2</span><span class="sxs-lookup"><span data-stu-id="4ee4f-115">Rule 2</span></span>  
  
```  
IF Employee.Status = "Contract"   
THEN Employee.Bonus = false  
Assert(new ContractEmployee())  
```  
  
 <span data-ttu-id="4ee4f-116">Todas las reglas que contengan la **empleado** tipo o la **ContractEmployee** tipo en sus condiciones se evalúan de nuevo después de la aserción.</span><span class="sxs-lookup"><span data-stu-id="4ee4f-116">All rules containing the **Employee** type or the **ContractEmployee** type in their conditions get re-evaluated after the assertion.</span></span> <span data-ttu-id="4ee4f-117">El tipo de herencia de este ejemplo es implementación.</span><span class="sxs-lookup"><span data-stu-id="4ee4f-117">The type of inheritance in this example is implementation.</span></span> <span data-ttu-id="4ee4f-118">Incluso si sólo se afirma la clase derivada, la clase base se afirma también si las reglas se escriben con los métodos de la clase base en lugar de la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="4ee4f-118">Even though only the derived class is asserted, the base class also gets asserted if rules are written using methods in the base instead of the derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ee4f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ee4f-119">See Also</span></span>  
 [<span data-ttu-id="4ee4f-120">Motor de reglas</span><span class="sxs-lookup"><span data-stu-id="4ee4f-120">Rule Engine</span></span>](../core/rule-engine.md)