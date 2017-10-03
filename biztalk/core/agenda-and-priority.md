---
title: Agenda y prioridad | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4529753251c2bf7934616b91662bde836c8339e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="agenda-and-priority"></a>Agenda y prioridad
Para comprender cómo el motor de reglas de negocios evalúa las reglas y ejecuta las acciones, debe comprender los conceptos de *agenda* y *prioridad*.  
  
## <a name="agenda"></a>Agenda  
 La agenda es una programación que utiliza el motor para poner en cola las reglas que van a ejecutarse. Se encuentra en una instancia del motor y actúa sobre una única directiva, no sobre una serie de directivas. Cuando se impone un dato en la memoria de trabajo y se cumplen las condiciones de una determinada regla, la regla se coloca en la agenda y se ejecuta de acuerdo con la prioridad. Las acciones de una regla se ejecutan en orden descendente y después se ejecutan las acciones de la siguiente regla que haya en la agenda.  
  
 Las acciones que pertenecen a una regla se consideran como un bloque, de modo que se ejecutan todas las acciones antes de pasar a la regla siguiente. Todas las acciones de un bloque de reglas se ejecutarán con independencia de las demás acciones del bloque. Para obtener más información acerca de la aserción, consulte [las funciones de Control del motor](../core/engine-control-functions.md).  
  
 El siguiente ejemplo muestra cómo funciona la agenda.  
  
 **Rule1**  
  
```  
IF  
Fact1 == 1  
THEN  
Action1  
Action2  
```  
  
 **Rule2**  
  
```  
IF  
Fact1 > 0  
THEN  
Action3  
Action4  
```  
  
 Imponemos en el motor el hecho Fact1, que tiene un valor de 1. Como se cumplen las condiciones de las reglas Rule1 y Rule2, ambas reglas se mueven a la agenda para que se ejecuten las acciones correspondientes.  
  
|Memoria de trabajo|Agenda|  
|--------------------|------------|  
|Fact1 (valor = 1)|**Rule1**<br /><br /> -Action1<br />-Action2<br /><br /> **Rule2**<br /><br /> -Action3<br />-Action4|  
  
## <a name="priority"></a>Prioridad  
 La prioridad de ejecución se establece en cada regla individual, con una prioridad predeterminada de 0 para todas las reglas. El valor de prioridad puede oscilar a ambos lados del 0, donde los números más grandes significan una mayor prioridad. Las acciones se ejecutan en orden desde prioridad más alta a prioridad más baja.  
  
 En el ejemplo siguiente se muestra cómo afecta la prioridad al orden de ejecución de las reglas.  
  
 **Rule1 (prioridad = 0)**  
  
```  
IF  
Fact1 == 1  
THEN  
Discount = 10%  
```  
  
 **Rule2 (prioridad = 10)**  
  
```  
IF  
Fact1 > 0  
THEN  
Discount = 15%  
```  
  
 Las condiciones de ambas reglas se cumplen, pero la regla Rule2 se ejecuta primero porque tiene una mayor prioridad. El descuento final es de un 10 por ciento, ya que es el resultado de la acción ejecutada para la regla Rule1, como se muestra en la tabla siguiente.  
  
|Memoria de trabajo|Agenda|  
|--------------------|------------|  
|Fact1 (valor = 1)|**Rule2**<br /><br /> Descuento = 15%<br /><br /> **Rule1**<br /><br /> Descuento = 10%|  
  
## <a name="see-also"></a>Vea también  
 [Motor de reglas](../core/rule-engine.md)