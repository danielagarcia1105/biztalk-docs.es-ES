---
title: Compatibilidad con herencia de clases en el motor de reglas de negocios | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code samples, Business Rules Engine
- Business Rules Engine, inheritance
- Business Rules Engine, code samples
- Business Rules Engine, examples
- examples, Business Rules Engine
ms.assetid: 50871f34-ccbe-4f77-8feb-5694e1b14837
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 930fc5591ce55f1a2ec988b307203a4154e85c2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="support-for-class-inheritance-in-the-business-rule-engine"></a>Compatibilidad con herencia de clases en el motor de reglas de negocios
Una de las características clave de los lenguajes de programación orientada a objetos (OOP) es la herencia. La herencia es la capacidad de usar toda la funcionalidad de una clase existente y ampliar esa capacidad sin escribir de nuevo la clase original.  
  
 El marco de trabajo de reglas de negocios admite dos tipos de herencia de clases: implementación e interfaz. La herencia de implementación hace referencia a la capacidad de usar las propiedades y los métodos de una clase base sin codificación adicional. La herencia de interfaz hace referencia a la capacidad de usar sólo los nombres de las propiedades y métodos, pero la clase secundaria debe proporcionar la implementación.  
  
 Las reglas se pueden escribir en términos de una clase base común, pero los objetos afirmados en el motor pueden ser de clases derivadas. En el ejemplo siguiente, **RegularEmployee** y **ContractEmployee** son clases derivadas de la clase base **empleado**.  
  
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
  
 Imagine que tiene la siguiente regla.  
  
## <a name="rule-1"></a>Regla 1  
  
```  
IF Employee.TimeInMonths < 12  
THEN Employee.Status = "New"  
```  
  
 Durante la ejecución, si el usuario afirma dos objetos, uno una instancia de **ContractEmployee** y el otro es una instancia de **RegularEmployee**, las instancias de objeto se evalúan con la regla descrita versiones anteriores.  
  
 El usuario también puede afirmar objetos de clase derivados en acciones usando un **Assert**. Esto da lugar a que se evalúen de nuevo las reglas que contienen el objeto derivado y su tipo base en sus condiciones, como se muestra en el siguiente ejemplo.  
  
## <a name="rule-2"></a>Regla 2  
  
```  
IF Employee.Status = "Contract"   
THEN Employee.Bonus = false  
Assert(new ContractEmployee())  
```  
  
 Todas las reglas que contengan la **empleado** tipo o la **ContractEmployee** tipo en sus condiciones se evalúan de nuevo después de la aserción. El tipo de herencia de este ejemplo es implementación. Incluso si sólo se afirma la clase derivada, la clase base se afirma también si las reglas se escriben con los métodos de la clase base en lugar de la clase derivada.  
  
## <a name="see-also"></a>Vea también  
 [Motor de reglas](../core/rule-engine.md)