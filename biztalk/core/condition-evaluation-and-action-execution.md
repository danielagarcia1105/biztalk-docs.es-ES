---
title: "Evaluación de condiciones y ejecución de acciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2814a97c1907b1bb29eee2a718d04d14cfe901a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="condition-evaluation-and-action-execution"></a>Evaluación de condiciones y ejecución de acciones
El marco de trabajo de reglas de negocios proporciona un motor de interferencia extremadamente eficaz que permite la vinculación de reglas a objetos .NET, documentos XML o tablas de bases de datos.  
  
 El motor de reglas de negocios utiliza un algoritmo dividido en tres fases para ejecutar la directiva. Las fases son las siguientes:  
  
-   **Coincidencia**. En la fase de coincidencia, se comparan los datos con los predicados que usan el tipo de datos (referencias de objetos almacenadas en la memoria de trabajo del motor de reglas) mediante los predicados definidos en las condiciones de reglas. Por motivos de eficacia, la coincidencia de patrones se produce en todas las reglas de la directiva, y las condiciones que son compartidas por las reglas se comparan solo una vez. Las coincidencias parciales de las condiciones se almacenan en la memoria de trabajo con el objetivo de acelerar las operaciones de coincidencia de patrones. El resultado de la fase de coincidencia de patrones se compone de las actualizaciones de la agenda del motor de reglas.  
  
-   **Resolución de conflictos**. En la fase de resolución de conflictos se analizan las reglas establecidas para la ejecución con el objeto de determinar el conjunto siguiente de acciones de reglas que se va a ejecutar en función de un esquema de resolución predeterminado. Todas las reglas candidatas que se obtengan durante la fase de coincidencia se agregan a la agenda del motor de reglas.  
  
     El esquema de resolución de conflictos predeterminado está basado en las prioridades de reglas de una directiva. La prioridad es una propiedad configurable de las reglas del Compositor de reglas de negocio. Cuanto más grande sea el número, mayor es la prioridad; de esta forma, si se activan varias reglas, las acciones de prioridad más alta se ejecutan en primer lugar.  
  
-   **Acción**. En la fase de acción se ejecutan las acciones de las reglas resueltas. Tenga en cuenta que las acciones de reglas pueden imponer nuevos datos en el motor de reglas, lo que hace que el ciclo continúe. Esto también recibe el nombre de encadenamiento directo. Es importante tener en cuenta que el algoritmo nunca se anticipa a la regla que se encuentre en ejecución en ese momento. Todas las acciones de la regla que se esté activando se ejecutarán antes de que se repita la fase de coincidencia. Sin embargo, las demás reglas de la agenda no se activarán antes de que la fase de coincidencia comience de nuevo. La fase de coincidencia puede provocar que dichas reglas se eliminen de la agenda antes de que se activen.  
  
 En el siguiente ejemplo se muestra el algoritmo en tres fases de la acción o resolución de conflictos o coincidencias.  
  
 **Regla 1: Evaluar ingreso**  
  
-   Representación declarativa:  
  
     El índice de solvencia crediticia de un solicitante debe obtenerse únicamente cuando la proporción ingresos/préstamo es inferior a 0,2.  
  
-   IF, a continuación, la representación con objetos comerciales:  
  
    ```  
    IF Application.Income / Property.Price < 0.2    
    THEN Assert new CreditRating( Application)   
    ```  
  
 **Regla 2: Evaluar solvencia**  
  
-   Representación declarativa:  
  
     Un solicitante debe considerarse aprobado solo cuando su índice de solvencia crediticia es superior a 725.  
  
-   IF, a continuación, representación con objetos comerciales:  
  
    ```  
    IF Application.SSN = CreditRating.SSN AND CreditRating.Value > 725    
    THEN SendApprovalLetter(Application)    
    ```  
  
 Los datos se resumen en la tabla siguiente.  
  
|Hecho|Campos|  
|----------|------------|  
|Application: documento XML que representa una solicitud de hipoteca|-Ingresos = 65.000 dólares<br />-SSN = XXX-XX-XXXX|  
|Property: documento XML que representa la propiedad adquirida|-Price = $225,000|  
|CreditRating: documento XML que contiene el índice de solvencia crediticia del solicitante|-Valor = 0 – 800<br />-SSN = XXX-XX-XXXX|  
  
 En un principio la agenda y la memoria de trabajo del motor de reglas están vacías. Una vez que la aplicación agrega los datos Application y Property, la agenda y la memoria de trabajo del motor de reglas se actualizan de la siguiente forma.  
  
|Memoria de trabajo|Agenda|  
|--------------------|------------|  
|: Aplicación<br />: Propiedad|Regla 1|  
  
 Regla 1 se agrega a la agenda porque su condición (Application.Income / Property.Price < 0,2) evalúan a **true** durante la fase de coincidencia. Dado que el dato CreditRating no aparece en la memoria de trabajo, no se ha evaluado la condición de la Regla 2. Al ser Regla 1 la única regla existente en la agenda, la regla se ejecuta y desaparece de la agenda. La acción sencilla que se ha definido en la Regla 1 da lugar a un dato nuevo (el documento CreditRating del solicitante) que se agrega a la memoria de trabajo. Cuando finaliza la ejecución de la Regla 1, el control vuelve a la fase de coincidencia. Puesto que el único objeto nuevo que se va a comparar es el dato CreditRating, los resultados de la fase de coincidencia son los siguientes.  
  
|Memoria de trabajo|Agenda|  
|--------------------|------------|  
|: Aplicación<br />: Propiedad<br />-CreditRating|Regla 2|  
  
 En este momento se ejecuta la Regla 2, que da como resultado la invocación de una función que envía una carta de aprobación al solicitante. Después de completarse la Regla 2, la ejecución del algoritmo de encadenamiento directo vuelve a la fase de coincidencia. Puesto que ya no existen datos nuevos que se puedan comparar y la agenda está vacía, el encadenamiento directo finaliza y se termina la ejecución de la directiva.  
  
## <a name="see-also"></a>Vea también  
 [Motor de reglas](../core/rule-engine.md)